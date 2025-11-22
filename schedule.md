---
layout: default
title: Schedule
last_modified_at: 2025-09-01
permalink: /schedule/
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

    <p style="color:#64748b;margin-top:1rem;">Only you can see this.</p>
  </div>
</div>

<!-- Firebase SDKs -->
<script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-auth-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-firestore-compat.js"></script>

<!-- FullCalendar (CDN) -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/fullcalendar@6.1.15/main.min.css">
<script src="https://cdn.jsdelivr.net/npm/fullcalendar@6.1.15/index.global.min.js"></script>

<style>
  .btn-primary {
    background: #4a6bff;
    color: white;
    border: none;
    padding: 8px 16px;
    border-radius: 8px;
    cursor: pointer;
    transition: background 0.2s;
  }
  .btn-primary:hover {
    background: #3b55d6;
  }
  
  /* Center the month title over the whole grid */
  #calendar .fc-header-toolbar { position: relative; }
  #calendar .fc-toolbar-title {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    pointer-events: none;
  }

  @media (max-width: 640px) {
    #calendar .fc-header-toolbar { padding-top: .5rem; }
  }
</style>

<script>
// ... (keep the existing Firebase and schedule JavaScript code) ...
// The existing JavaScript code for the schedule functionality remains the same
</script>
