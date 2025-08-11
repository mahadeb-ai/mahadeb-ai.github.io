layout: default
title: Home
last_modified_at: 2025-07-01
---

<!-- ⏱️ Clock in "navbar area" -->
<div style="position: absolute; top: 40px; right: 80px; font-size: 14px; z-index: 999;">
  🕒 Local Time: <span id="live-clock"></span>
</div>

<script>
  function updateClock() {
    const now = new Date();
    document.getElementById('live-clock').innerText = now.toLocaleTimeString();
  }
  setInterval(updateClock, 1000);
  updateClock(); // Run immediately
</script>


<!-- Main content -->
<div align="center">
  <img src="assets/images/profile.png" alt="Profile Photo" width="180" style="border-radius: 50%; box-shadow: 0 4px 10px rgba(0,0,0,0.1);" />
  
  <h1>Mahadeb Mandal</h1>

  <p><strong>Research Scholar</strong><br>
  Interdisciplinary Graduate College<br>
  <strong>Nanyang Technological University, Singapore</strong></p>
  <p>
    📍 Lab office: SPMS-MAS-04-02, Table: 9<br>
    📧 <a href="mailto:mahadeb001@e.ntu.edu.sg">mahadeb001@e.ntu.edu.sg</a>
  </p>
</div>

---

Mahadeb Mandal is currently a second-year PhD student at **Nanyang Technological University (NTU), Singapore**, working under the supervision of [**Prof. Kelin Xia**](https://personal.ntu.edu.sg/xiakelin/index.html). His academic journey is rooted in a strong passion for mathematics and artificial intelligence, with his current research focused on the intersection of **Topological Data Analysis (TDA)** and **Deep Learning**. He aims to uncover meaningful geometric and topological structures in complex data, contributing to advancements in data-driven science and intelligent systems.

### Research Interests

- Topological Data Analysis (TDA)
- Deep Learning for Scientific Material Discovery
- Mathematical AI
<!-- 💧 NTU Logo Watermark -->
<style>
  body::before {
    content: "";
    position: fixed;
    top: 0;
    left: 0;
    width: 12vw;
    height: 14vh;
    background-image: url('/assets/images/ntu_logo.png');
    background-repeat: no-repeat;
    background-position: center 95%;
    background-size: 50px;
    opacity: 0.05;
    z-index: 0;
    pointer-events: none;
    user-select: none;
  }
</style>
