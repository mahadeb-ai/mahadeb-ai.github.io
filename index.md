---
layout: default
title: Home
---

<div align="center">
  <img src="assets/images/profile.png" alt="Profile Photo" width="180" style="border-radius: 50%; box-shadow: 0 4px 10px rgba(0,0,0,0.1);" />
  
  <h1>Mahadeb Mandal</h1>

  <p><strong>Research Scholar</strong><br>
  Interdisciplinary Graduate College<br>
  <strong>Nanyang Technological University, Singapore</strong></p>
</div>

---

Mahadeb Mandal is currently a second-year PhD student at **Nanyang Technological University (NTU), Singapore**, working under the supervision of [**Prof. Kelin Xia**](https://personal.ntu.edu.sg/xiakelin/index.html). His academic journey is rooted in a strong passion for mathematics and artificial intelligence, with his current research focused on the intersection of **Topological Data Analysis (TDA)** and **Deep Learning**. He aims to uncover meaningful geometric and topological structures in complex data, contributing to advancements in data-driven science and intelligent systems.


<section class="contact-section">
  <h2 class="section-title">Get In Touch</h2>
  <div class="contact-container">
    <div class="contact-card">
      <div class="contact-details">
        <h3>Email</h3>
        <a href="mailto:wbmm2017@gmail.com" class="contact-link">wbmm2017@gmail.com</a>
        <a href="mailto:mahadeb001@e.ntu.edu.sg" class="contact-link">mahadeb001@e.ntu.edu.sg</a>
      </div>
    </div>
    
    <div class="contact-card">
      <div class="contact-details">
        <h3>Office</h3>
        <p>SPMS-MAS-04-02, Table: 9,</p>
        <p>Division of Mathematical Sciences,</p>
        <p>21 Nanyang Link, Singapore 637371</p>
      </div>
    </div>
    
    <div class="contact-card">
      <div class="contact-details">
        <h3>Phone</h3>
        <p>+65 94XX XX12</p>
      </div>
    </div>
  </div>
</section>

<p>🕒 Local Time: <span id="live-clock"></span></p>

<script>
  function updateClock() {
    const now = new Date();
    document.getElementById('live-clock').innerText = now.toLocaleTimeString();
  }
  setInterval(updateClock, 1000);
  updateClock(); // Run immediately
</script>



<!-- Visitor Counter -->
<p>👀 Total Visitors: <span id="visitor-count">Loading...</span></p>

<script>
  // Using CountAPI (free, no backend needed)
  fetch('https://api.countapi.xyz/hit/mahadeb-ai.github.io/visits')
    .then(res => res.json())
    .then(data => {
      document.getElementById('visitor-count').innerText = data.value;
    });
</script>


![Visitors](https://visitor-badge.glitch.me/badge?page_id=mahadeb-ai.github.io)

**Last Updated**: ![Last Updated](https://img.shields.io/badge/dynamic/json?url=https://api.github.com/repos/mahadeb-ai/mahadeb-ai.github.io&label=Last%20Updated&query=$.pushed_at&color=blue)

![Visitor Count](https://hitwebcounter.com/counter/counter.php?page=1234567&style=0006&nbdigits=5&type=page&initCount=0)

