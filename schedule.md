---
title: Schedule
last_modified_at: 2025-09-01
robots: noindex
---

# Schedule (Private)

<div id="schedule-app" style="max-width:960px;margin:1rem auto;">
  <!-- Auth Panel -->
  <div id="auth-panel" style="border:1px solid rgba(100,116,139,.2);border-radius:12px;padding:16px;margin-bottom:16px;">
    <h3 style="margin:.2rem 0 1rem;color:#4a6bff;">Login</h3>
    <p id="auth-status" style="color:#64748b;margin:.25rem 0 1rem;">You must login to view your schedule.</p>

    <div id="login-form">
      <label>Email<br><input id="email" type="email" style="width:100%;padding:8px;border-radius:8px;border:1px solid #cbd5e1"></label><br><br>
      <label>Password<br><input id="password" type="password" style="width:100%;padding:8px;border-radius:8px;border:1px solid #cbd5e1"></label><br><br>
      <button id="login-btn" class="btn-primary">Sign In</button>
      <button id="signup-btn" class="btn-primary" style="margin-left:8px;">Create Account</button>
      <button id="logout-btn" class="btn-primary" style="margin-left:8px;display:none;">Sign Out</button>
    </div>
  </div>

  <!-- Protected Area -->
  <div id="protected" style="display:none;">
    <div style="display:flex;gap:.5rem;align-items:center;justify-content:space-between;flex-wrap:wrap">
      <h3 style="margin:.2rem 0 1rem;color:#4a6bff;">My Upcoming Schedule</h3>
      <div>
        <button id="btn-list" class="btn-primary">List View</button>
        <button id="btn-cal"  class="btn-primary" style="margin-left:.5rem;">Calendar View</button>
        <button id="btn-ics"  class="btn-primary" style="margin-left:.5rem;">Export .ics</button>
      </div>
    </div>

    <!-- List -->
    <div id="events"></div>

    <!-- Calendar -->
    <div id="calendar" style="display:none;margin-top:1rem;"></div>

    <p style="color:#64748b;margin-top:1rem;">Only you can see this. Data is fetched from Firestore using your authenticated user ID.</p>
  </div>
</div>

<!-- Firebase SDKs -->
<script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-auth-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-firestore-compat.js"></script>

<!-- FullCalendar (CDN) -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/fullcalendar@6.1.15/main.min.css">
<script src="https://cdn.jsdelivr.net/npm/fullcalendar@6.1.15/index.global.min.js"></script>

<script>
/** 1) Your Firebase config */
const firebaseConfig = {
  apiKey: "AIzaSyCOyayGUYBREEok4rTLJIQAv-8iIvJn-VE",
  authDomain: "mahadeb-schedule.firebaseapp.com",
  projectId: "mahadeb-schedule",
  storageBucket: "mahadeb-schedule.firebasestorage.app",
  messagingSenderId: "644636693352",
  appId: "1:644636693352:web:816f7105c4158165a1fcdd",
  measurementId: "G-46S6QYBKX3"
};
/** 2) Init Firebase */
firebase.initializeApp(firebaseConfig);
const auth = firebase.auth();
const db = firebase.firestore();

/** UI handles */
const statusEl = document.getElementById('auth-status');
const loginBtn = document.getElementById('login-btn');
const signupBtn = document.getElementById('signup-btn');
const logoutBtn = document.getElementById('logout-btn');
const emailEl = document.getElementById('email');
const passEl = document.getElementById('password');
const protectedEl = document.getElementById('protected');
const eventsEl = document.getElementById('events');
const calendarEl = document.getElementById('calendar');
const btnList = document.getElementById('btn-list');
const btnCal  = document.getElementById('btn-cal');
const btnIcs  = document.getElementById('btn-ics');

let CURRENT_EVENTS = [];   // unified list [{title, datetime: Date, location, notes}]
let calendar;              // FullCalendar instance

/* Auth buttons */
loginBtn.addEventListener('click', async () => {
  try{ await auth.signInWithEmailAndPassword(emailEl.value.trim(), passEl.value); }
  catch(e){ alert(e.message); }
});
signupBtn.addEventListener('click', async () => {
  try{ await auth.createUserWithEmailAndPassword(emailEl.value.trim(), passEl.value); }
  catch(e){ alert(e.message); }
});
logoutBtn.addEventListener('click', async () => {
  try{ await auth.signOut(); }catch(e){ alert(e.message); }
});

/* Auth state */
auth.onAuthStateChanged(async (user) => {
  if(user){
    statusEl.textContent = "Signed in as " + (user.email || user.uid);
    logoutBtn.style.display = 'inline-block';
    loginBtn.style.display = 'none';
    signupBtn.style.display = 'none';
    protectedEl.style.display = 'block';
    await loadSchedule(user.uid);
  } else {
    statusEl.textContent = "You must login to view your schedule.";
    logoutBtn.style.display = 'none';
    loginBtn.style.display = 'inline-block';
    signupBtn.style.display = 'inline-block';
    protectedEl.style.display = 'none';
    eventsEl.innerHTML = "";
    if (calendar) { calendar.destroy(); calendar = null; }
  }
});

/* Load all docs from schedules/{uid}/items and normalize shapes */
async function loadSchedule(uid){
  eventsEl.innerHTML = "<p>Loading…</p>";
  try{
    const coll = db.collection('schedules').doc(uid).collection('items');
    const snap = await coll.get();

    if (snap.empty){
      CURRENT_EVENTS = [];
      eventsEl.innerHTML = "<p>No events yet.</p>";
      if (calendar) { calendar.removeAllEvents(); }
      return;
    }

    const items = [];
    snap.forEach(doc => {
      const data = doc.data() || {};
      if (data.datetime) {
        // Canonical doc
        const dt = data.datetime?.toDate ? data.datetime.toDate() : null;
        items.push({ title: data.title || 'Untitled', datetime: dt, location: data.location || '', notes: data.notes || '' });
      } else {
        // One-field-per-doc style
        const entries = Object.entries(data);
        if (entries.length > 0){
          const [title, ts] = entries[0];
          const dt = ts?.toDate ? ts.toDate() : null;
          items.push({ title, datetime: dt, location: '', notes: '' });
        }
      }
    });

    // Sort by time
    items.sort((a,b) => (a.datetime?.getTime() || 0) - (b.datetime?.getTime() || 0));
    CURRENT_EVENTS = items;

    renderList(items);
    renderCalendar(items); // build/update calendar data as well
  }catch(e){
    eventsEl.innerHTML = "<p style='color:#ef4444'>Failed to load events: "+e.message+"</p>";
  }
}

/* List renderer */
function renderList(items){
  if (!items.length){ eventsEl.innerHTML = "<p>No events yet.</p>"; return; }
  let html = '';
  for (const ev of items){
    html += `
      <div style="border:1px solid rgba(100,116,139,.2);border-radius:12px;padding:12px;margin:8px 0;">
        <strong>${ev.title}</strong><br/>
        ${ev.datetime ? ev.datetime.toLocaleString() : ''}${ev.location ? ' · ' + ev.location : ''}<br/>
        ${ev.notes ? '<span style="color:#64748b">' + ev.notes + '</span>' : ''}
      </div>`;
  }
  eventsEl.innerHTML = html;
}

/* Calendar renderer (FullCalendar) */
function toLocalISO(dt){
  if (!dt) return null;
  const p = n => String(n).padStart(2,'0');
  return `${dt.getFullYear()}-${p(dt.getMonth()+1)}-${p(dt.getDate())}T${p(dt.getHours())}:${p(dt.getMinutes())}:${p(dt.getSeconds())}`;
}
function renderCalendar(items){
  const fcEvents = items
    .filter(ev => !!ev.datetime)
    .map(ev => ({
      title: ev.title,
      start: toLocalISO(ev.datetime), // local time (no Z)
      allDay: false,
      extendedProps: { location: ev.location || '', notes: ev.notes || '' }
    }));

  if (!calendar){
    calendar = new FullCalendar.Calendar(calendarEl, {
      initialView: 'dayGridMonth',
      height: 'auto',
      expandRows: true,
      headerToolbar: { left: 'prev,next today', center: 'title', right: '' },
      eventClick: function(info){
        const e = info.event;
        const loc = e.extendedProps.location ? `\n${e.extendedProps.location}` : '';
        const notes = e.extendedProps.notes ? `\n${e.extendedProps.notes}` : '';
        alert(`${e.title}\n${e.start.toLocaleString()}${loc}${notes}`);
      }
    });
    calendar.render();
  } else {
    calendar.removeAllEvents();
  }
  calendar.addEventSource(fcEvents);
}

/* Toggle buttons */
btnList.addEventListener('click', () => {
  eventsEl.style.display = 'block';
  calendarEl.style.display = 'none';
});
btnCal.addEventListener('click', () => {
  eventsEl.style.display = 'none';
  calendarEl.style.display = 'block';
  if (calendar) calendar.updateSize();
});

/* ICS export */
btnIcs.addEventListener('click', () => {
  if (!CURRENT_EVENTS.length){ alert('No events to export.'); return; }
  const lines = [
    'BEGIN:VCALENDAR',
    'VERSION:2.0',
    'PRODID:-//Mahadeb Schedule//EN',
    'CALSCALE:GREGORIAN',
    'METHOD:PUBLISH'
  ];
  CURRENT_EVENTS.forEach((ev,i) => {
    if (!ev.datetime) return;
    const dt = new Date(ev.datetime);
    const dtEnd = new Date(dt.getTime() + 60*60*1000); // +1h
    const fmt = d => d.toISOString().replace(/[-:]/g,'').split('.')[0] + 'Z';
    lines.push('BEGIN:VEVENT');
    lines.push(`UID:${i}-${dt.getTime()}@mahadeb-schedule`);
    lines.push(`DTSTAMP:${fmt(new Date())}`);
    lines.push(`DTSTART:${fmt(dt)}`);
    lines.push(`DTEND:${fmt(dtEnd)}`);
    lines.push(`SUMMARY:${(ev.title || 'Event').replace(/\n/g,' ')}`);
    if (ev.location) lines.push(`LOCATION:${ev.location.replace(/\n/g,' ')}`);
    if (ev.notes)    lines.push(`DESCRIPTION:${ev.notes.replace(/\n/g,' ')}`);
    lines.push('END:VEVENT');
  });
  lines.push('END:VCALENDAR');

  const blob = new Blob([lines.join('\r\n')], {type:'text/calendar'});
  const url = URL.createObjectURL(blob);
  const a = document.createElement('a');
  a.href = url;
  a.download = 'schedule.ics';
  document.body.appendChild(a);
  a.click();
  a.remove();
  URL.revokeObjectURL(url);
});
</script>
