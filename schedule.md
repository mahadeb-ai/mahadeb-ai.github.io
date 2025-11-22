---
title: Schedule
last_modified_at: 2025-09-01
robots: noindex
---

<div id="schedule-app">
  <!-- Auth Panel -->
  <div id="auth-panel" class="card auth-card">
    <div class="auth-header">
      <div class="auth-title-block">
        <span class="auth-badge">Private</span>
        <h3>Login</h3>
        <p id="auth-status">You must login to view your schedule.</p>
      </div>
      <div class="auth-icon">
        🔒
      </div>
    </div>

    <div id="login-form" class="auth-form">
      <div class="field">
        <label for="email">Email</label>
        <input id="email" type="email" placeholder="you@ntu.edu.sg">
      </div>

      <div class="field">
        <label for="password">Password</label>
        <input id="password" type="password" placeholder="••••••••">
      </div>

      <div class="auth-actions">
        <button id="login-btn" class="btn btn-primary">Sign In</button>
        <button id="signup-btn" class="btn btn-ghost">Create Account</button>
        <button id="logout-btn" class="btn btn-danger" style="display:none;">Sign Out</button>
      </div>
    </div>
  </div>

  <!-- Protected Area -->
  <div id="protected" class="card protected-card" style="display:none;">
    <div class="schedule-header">
      <div>
        <h3>My Upcoming Schedule</h3>
        <p class="subtitle">Synced securely from your private Firebase calendar.</p>
      </div>
      <div class="view-toggle">
        <button id="btn-list" class="btn btn-chip active">List</button>
        <button id="btn-cal"  class="btn btn-chip">Calendar</button>
        <button id="btn-ics"  class="btn btn-chip">Export .ics</button>
      </div>
    </div>

    <!-- List -->
    <div id="events" class="events-list"></div>

    <!-- Calendar -->
    <div id="calendar" class="calendar-shell" style="display:none;"></div>

    <p class="footnote">Only you can see this page. Your data stays in your Firebase project.</p>
  </div>
</div>

<!-- Firebase SDKs -->
<script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-auth-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-firestore-compat.js"></script>

<!-- FullCalendar (CDN) -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/fullcalendar@6.1.15/main.min.css">

<style>
  /* === Layout shell === */
  #schedule-app {
    max-width: 960px;
    margin: 1.5rem auto 2.5rem;
    padding: 0 1rem;
    font-family: "Times New Roman", Times, serif;
  }

  .card {
    border-radius: 18px;
    padding: 1.5rem 1.75rem;
    margin-bottom: 1.5rem;
    background: radial-gradient(circle at top left, rgba(74,107,255,0.06), transparent 55%), var(--bg, #ffffff);
    box-shadow: 0 18px 40px rgba(15,23,42,.08);
    border: 1px solid rgba(148,163,184,.3);
  }

  .auth-card {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .protected-card {
    margin-top: 0.5rem;
  }

  /* === Auth panel === */
  .auth-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    gap: 1rem;
  }

  .auth-title-block h3 {
    margin: 0.1rem 0 0.3rem;
    font-size: 1.2rem;
    color: #1f2933;
  }

  .auth-title-block p {
    margin: 0;
    font-size: 0.9rem;
    color: #64748b;
  }

  .auth-badge {
    display: inline-block;
    padding: 0.2rem 0.6rem;
    border-radius: 999px;
    background: rgba(74,107,255,0.08);
    color: #4a6bff;
    font-size: 0.72rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: .08em;
  }

  .auth-icon {
    font-size: 1.8rem;
    background: rgba(148,163,184,0.15);
    width: 42px;
    height: 42px;
    border-radius: 14px;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .auth-form {
    margin-top: 0.75rem;
    display: grid;
    gap: 0.9rem;
  }

  .field label {
    display: block;
    font-size: 0.85rem;
    margin-bottom: 0.2rem;
    color: #475569;
  }

  .field input {
    width: 100%;
    padding: 0.55rem 0.7rem;
    border-radius: 10px;
    border: 1px solid #cbd5e1;
    font-size: 0.9rem;
    background: rgba(248,250,252,0.85);
    outline: none;
    transition: border-color .18s ease, box-shadow .18s ease, background .18s ease;
  }

  .field input:focus {
    border-color: #4a6bff;
    box-shadow: 0 0 0 1px rgba(74,107,255,0.25);
    background: #ffffff;
  }

  .auth-actions {
    margin-top: 0.5rem;
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
  }

  /* === Buttons === */
  .btn {
    border-radius: 999px;
    border: none;
    cursor: pointer;
    font-size: 0.85rem;
    font-weight: 600;
    padding: 0.45rem 0.9rem;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 0.25rem;
    transition: background .18s ease, box-shadow .18s ease, transform .1s ease;
    white-space: nowrap;
  }

  .btn-primary {
    background: linear-gradient(135deg, #4a6bff, #7b8dff);
    color: #ffffff;
    box-shadow: 0 10px 25px rgba(74,107,255,.35);
  }
  .btn-primary:hover {
    background: linear-gradient(135deg, #3c58d6, #6b7cf5);
    transform: translateY(-1px);
    box-shadow: 0 14px 32px rgba(74,107,255,.45);
  }

  .btn-ghost {
    background: rgba(148,163,184,0.08);
    color: #1e293b;
  }
  .btn-ghost:hover {
    background: rgba(148,163,184,0.18);
  }

  .btn-danger {
    background: rgba(239,68,68,0.1);
    color: #b91c1c;
  }
  .btn-danger:hover {
    background: rgba(239,68,68,0.18);
  }

  .btn-chip {
    background: rgba(148,163,184,0.12);
    color: #0f172a;
    padding-inline: 0.8rem;
    font-size: 0.8rem;
  }
  .btn-chip:hover {
    background: rgba(148,163,184,0.25);
  }
  .btn-chip.active {
    background: #1e293b;
    color: #f9fafb;
  }

  /* === Protected area === */
  .schedule-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    gap: 1rem;
    margin-bottom: 1rem;
  }

  .schedule-header h3 {
    margin: 0;
    font-size: 1.2rem;
    color: #1f2937;
  }

  .subtitle {
    margin: 0.2rem 0 0;
    font-size: 0.85rem;
    color: #6b7280;
  }

  .view-toggle {
    display: flex;
    flex-wrap: wrap;
    gap: 0.4rem;
  }

  .events-list {
    margin-top: 0.5rem;
  }

  .event-card {
    border-radius: 14px;
    padding: 0.75rem 0.85rem;
    margin: 0.4rem 0;
    border: 1px solid rgba(148,163,184,0.35);
    background: rgba(248,250,252,0.85);
    display: flex;
    flex-direction: column;
    gap: 0.15rem;
  }

  .event-title {
    font-weight: 600;
    font-size: 0.95rem;
    color: #0f172a;
  }

  .event-meta {
    font-size: 0.82rem;
    color: #4b5563;
  }

  .event-notes {
    font-size: 0.8rem;
    color: #6b7280;
  }

  .calendar-shell {
    margin-top: 0.75rem;
    border-radius: 14px;
    border: 1px solid rgba(148,163,184,0.3);
    overflow: hidden;
    background: #ffffff;
  }

  .footnote {
    margin-top: 1rem;
    font-size: 0.8rem;
    color: #6b7280;
  }

  /* FullCalendar styling tweaks */
  #calendar .fc-header-toolbar {
    position: relative;
    padding: 0.25rem 0.75rem 0.5rem;
  }
  #calendar .fc-toolbar-title {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    pointer-events: none;
    font-size: 0.95rem;
    font-weight: 600;
    color: #111827;
  }
  #calendar .fc-button {
    border-radius: 999px !important;
    border: none !important;
    background: rgba(148,163,184,0.2) !important;
    color: #111827 !important;
    padding: 0.15rem 0.6rem !important;
    font-size: 0.75rem !important;
  }
  #calendar .fc-button-primary:hover {
    background: rgba(148,163,184,0.35) !important;
  }
  #calendar .fc-daygrid-day-number {
    font-size: 0.7rem;
    color: #4b5563;
  }
  #calendar .fc-event {
    border-radius: 999px;
    padding: 0 4px;
    font-size: 0.7rem;
  }

  @media (max-width: 640px) {
    #schedule-app {
      margin-top: 1rem;
    }
    .card {
      padding: 1.25rem 1.1rem;
    }
    .schedule-header {
      flex-direction: column;
      align-items: flex-start;
    }
    .view-toggle {
      width: 100%;
      justify-content: flex-start;
    }
    #calendar .fc-header-toolbar { padding-top: .7rem; }
  }
</style>

<script src="https://cdn.jsdelivr.net/npm/fullcalendar@6.1.15/index.global.min.js"></script>

<script>
/** 1) Your Firebase config (unchanged) */
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
const statusEl    = document.getElementById('auth-status');
const loginBtn    = document.getElementById('login-btn');
const signupBtn   = document.getElementById('signup-btn');
const logoutBtn   = document.getElementById('logout-btn');
const emailEl     = document.getElementById('email');
const passEl      = document.getElementById('password');
const protectedEl = document.getElementById('protected');
const eventsEl    = document.getElementById('events');
const calendarEl  = document.getElementById('calendar');
const btnList     = document.getElementById('btn-list');
const btnCal      = document.getElementById('btn-cal');
const btnIcs      = document.getElementById('btn-ics');

let CURRENT_EVENTS = [];   // unified list [{title, datetime: Date, location, notes}]
let calendar;              // FullCalendar instance

/* Auth buttons (logic unchanged) */
loginBtn.addEventListener('click', async () => {
  try {
    await auth.signInWithEmailAndPassword(emailEl.value.trim(), passEl.value);
  } catch(e) {
    alert(e.message);
  }
});

signupBtn.addEventListener('click', async () => {
  try {
    await auth.createUserWithEmailAndPassword(emailEl.value.trim(), passEl.value);
  } catch(e) {
    alert(e.message);
  }
});

logoutBtn.addEventListener('click', async () => {
  try {
    await auth.signOut();
  } catch(e) {
    alert(e.message);
  }
});

/* Auth state (logic unchanged) */
auth.onAuthStateChanged(async (user) => {
  if (user) {
    statusEl.textContent = "Signed in as " + (user.email || user.uid);
    logoutBtn.style.display = 'inline-flex';
    loginBtn.style.display  = 'none';
    signupBtn.style.display = 'none';
    protectedEl.style.display = 'block';
    await loadSchedule(user.uid);
  } else {
    statusEl.textContent = "You must login to view your schedule.";
    logoutBtn.style.display = 'none';
    loginBtn.style.display  = 'inline-flex';
    signupBtn.style.display = 'inline-flex';
    protectedEl.style.display = 'none';
    eventsEl.innerHTML = "";
    if (calendar) {
      calendar.destroy();
      calendar = null;
    }
  }
});

/* Load all docs from schedules/{uid}/items and normalize shapes (logic same) */
async function loadSchedule(uid){
  eventsEl.innerHTML = "<p>Loading…</p>";
  try {
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
        items.push({
          title: data.title || 'Untitled',
          datetime: dt,
          location: data.location || '',
          notes: data.notes || ''
        });
      } else {
        // One-field-per-doc style
        const entries = Object.entries(data);
        if (entries.length > 0){
          const [title, ts] = entries[0];
          const dt = ts?.toDate ? ts.toDate() : null;
          items.push({
            title,
            datetime: dt,
            location: '',
            notes: ''
          });
        }
      }
    });

    // Sort by time
    items.sort((a,b) => (a.datetime?.getTime() || 0) - (b.datetime?.getTime() || 0));
    CURRENT_EVENTS = items;

    renderList(items);
    renderCalendar(items);
  } catch(e) {
    eventsEl.innerHTML = "<p style='color:#ef4444'>Failed to load events: "+e.message+"</p>";
  }
}

/* List renderer (style updated only) */
function renderList(items){
  if (!items.length){
    eventsEl.innerHTML = "<p>No events yet.</p>";
    return;
  }
  let html = '';
  for (const ev of items){
    const dtStr = ev.datetime ? ev.datetime.toLocaleString() : '';
    const meta  = [dtStr, ev.location].filter(Boolean).join(' · ');
    html += `
      <div class="event-card">
        <div class="event-title">${ev.title}</div>
        ${meta ? `<div class="event-meta">${meta}</div>` : ''}
        ${ev.notes ? `<div class="event-notes">${ev.notes}</div>` : ''}
      </div>`;
  }
  eventsEl.innerHTML = html;
}

/* Calendar renderer (logic unchanged) */
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
      extendedProps: {
        location: ev.location || '',
        notes: ev.notes || ''
      }
    }));

  if (!calendar){
    calendar = new FullCalendar.Calendar(calendarEl, {
      initialView: 'dayGridMonth',
      height: 'auto',
      expandRows: true,
      headerToolbar: { left: 'prev,next today', center: 'title', right: '' },
      eventClick: function(info){
        const e  = info.event;
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

/* Toggle buttons (logic same, with active state) */
btnList.addEventListener('click', () => {
  eventsEl.style.display  = 'block';
  calendarEl.style.display = 'none';
  btnList.classList.add('active');
  btnCal.classList.remove('active');
});

btnCal.addEventListener('click', () => {
  eventsEl.style.display  = 'none';
  calendarEl.style.display = 'block';
  btnCal.classList.add('active');
  btnList.classList.remove('active');
  if (calendar) calendar.updateSize();
});

/* ICS export (unchanged) */
btnIcs.addEventListener('click', () => {
  if (!CURRENT_EVENTS.length){
    alert('No events to export.');
    return;
  }
  const lines = [
    'BEGIN:VCALENDAR',
    'VERSION:2.0',
    'PRODID:-//Mahadeb Schedule//EN',
    'CALSCALE:GREGORIAN',
    'METHOD:PUBLISH'
  ];
  CURRENT_EVENTS.forEach((ev,i) => {
    if (!ev.datetime) return;
    const dt    = new Date(ev.datetime);
    const dtEnd = new Date(dt.getTime() + 60*60*1000); // +1 hour
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
  const url  = URL.createObjectURL(blob);
  const a    = document.createElement('a');
  a.href = url;
  a.download = 'schedule.ics';
  document.body.appendChild(a);
  a.click();
  a.remove();
  URL.revokeObjectURL(url);
});
</script>
