---
title: Schedule
last_modified_at: 2025-09-01
robots: noindex
---

# Schedule (Private)

<div id="schedule-app" style="max-width:760px;margin:1rem auto;">
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
    <h3 style="margin:.2rem 0 1rem;color:#4a6bff;">My Upcoming Schedule</h3>
    <div id="events"></div>
    <p style="color:#64748b;margin-top:1rem;">Only you can see this. Data is fetched from Firestore using your authenticated user ID.</p>
  </div>
</div>

<!-- Firebase SDKs -->
<script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-auth-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-firestore-compat.js"></script>

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

loginBtn.addEventListener('click', async () => {
  try { await auth.signInWithEmailAndPassword(emailEl.value.trim(), passEl.value); }
  catch(e){ alert(e.message); }
});
signupBtn.addEventListener('click', async () => {
  try { await auth.createUserWithEmailAndPassword(emailEl.value.trim(), passEl.value); }
  catch(e){ alert(e.message); }
});
logoutBtn.addEventListener('click', async () => {
  try { await auth.signOut(); }
  catch(e){ alert(e.message); }
});

/** Auth state observer */
auth.onAuthStateChanged(async (user) => {
  if(user){
    statusEl.textContent = "Signed in as " + (user.email || user.uid);
    document.getElementById('logout-btn').style.display = 'inline-block';
    document.getElementById('login-btn').style.display = 'none';
    document.getElementById('signup-btn').style.display = 'none';
    protectedEl.style.display = 'block';
    await loadSchedule(user.uid);
  } else {
    statusEl.textContent = "You must login to view your schedule.";
    document.getElementById('logout-btn').style.display = 'none';
    document.getElementById('login-btn').style.display = 'inline-block';
    document.getElementById('signup-btn').style.display = 'inline-block';
    protectedEl.style.display = 'none';
    eventsEl.innerHTML = "";
  }
});

/** Load schedules from Firestore: schedules/{uid}/items */
async function loadSchedule(uid){
  eventsEl.innerHTML = "<p>Loading…</p>";
  try{
    // Read the subcollection (no orderBy so this works with either shape)
    const coll = db.collection('schedules').doc(uid).collection('items');
    const snap = await coll.get();

    if (snap.empty){
      eventsEl.innerHTML = "<p>No events yet.</p>";
      return;
    }

    // Build a unified list of events from both possible shapes
    const events = [];
    snap.forEach(doc => {
      const data = doc.data() || {};

      // Shape A (canonical): fields title, datetime (Timestamp), optional location/notes
      if (data.datetime) {
        const dt = data.datetime?.toDate ? data.datetime.toDate() : null;
        events.push({
          title: data.title || 'Untitled',
          datetime: dt,
          location: data.location || '',
          notes: data.notes || ''
        });
      } else {
        // Shape B (your current): one field where key = title, value = Timestamp
        const entries = Object.entries(data);
        if (entries.length > 0){
          const [title, ts] = entries[0];
          const dt = ts?.toDate ? ts.toDate() : null;
          events.push({ title, datetime: dt, location: '', notes: '' });
        }
      }
    });

    // Sort by time ascending
    events.sort((a,b) => (a.datetime?.getTime() || 0) - (b.datetime?.getTime() || 0));

    // Render
    let html = '';
    for (const ev of events){
      html += `
        <div style="border:1px solid rgba(100,116,139,.2);border-radius:12px;padding:12px;margin:8px 0;">
          <strong>${ev.title}</strong><br/>
          ${ev.datetime ? ev.datetime.toLocaleString() : ''}${ev.location ? ' · ' + ev.location : ''}<br/>
          ${ev.notes ? '<span style="color:#64748b">' + ev.notes + '</span>' : ''}
        </div>`;
    }
    eventsEl.innerHTML = html || "<p>No events yet.</p>";
  }catch(e){
    eventsEl.innerHTML = "<p style='color:#ef4444'>Failed to load events: "+e.message+"</p>";
  }
}
</script>
