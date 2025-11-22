---
layout: default
title: Schedule
last_modified_at: 2025-11-22
permalink: /schedule/
robots: noindex
---

<div id="schedule-app" style="max-width:960px;margin:2rem auto;padding:1rem;">
  <div id="auth-panel" style="background:var(--bg);border:1px solid rgba(100,116,139,.2);border-radius:16px;padding:2rem;box-shadow:var(--shadow);" data-aos="fade-right">
    <h3 style="color:var(--brand-600);margin-bottom:1rem;">Private Schedule Login</h3>
    <p id="auth-status" style="color:var(--txt-500);margin-bottom:1.5rem;">Sign in to view your personal schedule.</p>
    <div id="login-form">
      <input id="email" type="email" placeholder="Email" required style="width:100%;padding:12px;margin-bottom:1rem;border-radius:8px;border:1px solid #cbd5e1;">
      <input id="password" type="password" placeholder="Password" required style="width:100%;padding:12px;margin-bottom:1rem;border-radius:8px;border:1px solid #cbd5e1;">
      <button id="login-btn" class="btn-primary">Sign In</button>
      <button id="signup-btn" class="btn-primary" style="margin-left:12px;background:#10b981;">Create Account</button>
      <button id="logout-btn" class="btn-primary" style="display:none;margin-top:1rem;background:#ef4444;">Sign Out</button>
    </div>
  </div>

  <div id="protected" style="display:none;margin-top:2rem;" data-aos="fade-left">
    <div style="display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:1rem;margin-bottom:1rem;">
      <h3 style="color:var(--brand-600);">My Upcoming Schedule</h3>
      <div>
        <button id="btn-list" class="btn-primary active">List</button>
        <button id="btn-cal" class="btn-primary" style="margin-left:8px;">Calendar</button>
        <button id="btn-ics" class="btn-primary" style="margin-left:8px;">Export .ics</button>
      </div>
    </div>
    <div id="events"></div>
    <div id="calendar" style="display:none;background:var(--bg);padding:1rem;border-radius:12px;box-shadow:var(--shadow);"></div>
    <p style="color:var(--txt-500);margin-top:2rem;font-size:.9rem;">Only you can access this page.</p>
  </div>
</div>

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/fullcalendar@6.1.15/main.min.css">
<script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-auth-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-firestore-compat.js"></script>
<script src="https://cdn.jsdelivr.net/npm/fullcalendar@6.1.15/index.global.min.js"></script>

<style>
  .btn-primary{background:var(--brand-600);color:white;border:none;padding:10px 18px;border-radius:8px;cursor:pointer;font-weight:600;transition:.2s}
  .btn-primary:hover{background:var(--brand-700)}
  .btn-primary.active{background:#1e293b;color:white}
  .fc { --fc-border-color: #e2e8f0; --fc-daygrid-event-dot-width: 8px; }
</style>

<script>
// === REPLACE WITH YOUR OWN Firebase Config ===
const firebaseConfig = {
  apiKey: "AIzaSyCOyayGUYBREEok4rTLJIQAv-8iIvJn-VE",
  authDomain: "mahadeb-schedule.firebaseapp.com",
  databaseURL: "https://mahadeb-schedule-default-rtdb.asia-southeast1.firebasedatabase.app",
  projectId: "mahadeb-schedule",
  storageBucket: "mahadeb-schedule.firebasestorage.app",
  messagingSenderId: "644636693352",
  appId: "1:644636693352:web:816f7105c4158165a1fcdd",
  measurementId: "G-46S6QYBKX3"
};

firebase.initializeApp(firebaseConfig);
const db = firebase.firestore();
const auth = firebase.auth();

let calendar;
document.addEventListener('DOMContentLoaded', function() {
  const protected = document.getElementById('protected');
  const authPanel = document.getElementById('auth-panel');
  const eventsDiv = document.getElementById('events');
  const calendarDiv = document.getElementById('calendar');

  auth.onAuthStateChanged(user => {
    if (user && user.email === "mahadeb001@e.ntu.edu.sg") {
      authPanel.style.display = 'none';
      protected.style.display = 'block';
      document.getElementById('logout-btn').style.display = 'inline-block';
      loadEvents();
    } else {
      authPanel.style.display = 'block';
      protected.style.display = 'none';
      document.getElementById('logout-btn').style.display = 'none';
    }
  });

  document.getElementById('login-btn').onclick = () => {
    const email = document.getElementById('email').value;
    const pass = document.getElementById('password').value;
    auth.signInWithEmailAndPassword(email, pass).catch(e => alert(e.message));
  };

  document.getElementById('signup-btn').onclick = () => {
    const email = document.getElementById('email').value;
    const pass = document.getElementById('password').value;
    auth.createUserWithEmailAndPassword(email, pass).catch(e => alert(e.message));
  };

  document.getElementById('logout-btn').onclick = () => auth.signOut();

  document.getElementById('btn-list').onclick = () => { eventsDiv.style.display = 'block'; calendarDiv.style.display = 'none'; this.classList.add('active'); document.getElementById('btn-cal').classList.remove('active'); }
  document.getElementById('btn-cal').onclick = () => { eventsDiv.style.display = 'none'; calendarDiv.style.display = 'block'; this.classList.add('active'); document.getElementById('btn-list').classList.remove('active'); initCalendar(); }

  function loadEvents() {
    db.collection('events').orderBy('start', 'asc').get().then(snapshot => {
      const events = [];
      snapshot.forEach(doc => events.push({id: doc.id, ...doc.data()}));
      renderList(events);
      window.allEvents = events;
    });
  }

  function renderList(events) {
    eventsDiv.innerHTML = events.length === 0 ? '<p>No upcoming events.</p>' : '';
    events.forEach(ev => {
      const div = document.createElement('div');
      div.style = 'padding:1rem;margin:1rem 0;background:var(--bg-soft);border-radius:12px;border-left:5px solid var(--brand-600);';
      div.innerHTML = `<strong>${ev.title}</strong><br><small>${new Date(ev.start).toLocaleString()} – ${ev.end ? new Date(ev.end).toLocaleString() : ''}</small><p>${ev.description || ''}</p>`;
      eventsDiv.appendChild(div);
    });
  }

  function initCalendar() {
    if (calendar) return;
    calendar = new FullCalendar.Calendar(calendarDiv, {
      initialView: 'dayGridMonth',
      events: window.allEvents.map(e => ({
        title: e.title,
        start: e.start,
        end: e.end,
        description: e.description
      })),
      headerToolbar: { left: 'prev,next today', center: 'title', right: 'dayGridMonth,timeGridWeek' }
    });
    calendar.render();
  }
});
</script>
