---
layout: default
title: Home
last_modified_at: 2025-07-01
---

<!-- Live clock -->
<div class="clock" aria-live="polite">
  🕒 Local Time: <span id="live-clock"></span>
</div>

<script>
  function updateClock() {
    const now = new Date();
    document.getElementById('live-clock').textContent = now.toLocaleTimeString();
  }
  updateClock();
  setInterval(updateClock, 1000);
</script>

<!-- Page content -->
<section class="container">
  <header class="hero">
    <img
      class="avatar"
      src="assets/images/profile.png"
      alt="Profile photo of Mahadeb Mandal"
    />

    <h1 class="title">Mahadeb Mandal</h1>

    <p class="subtitle">
      <strong>Research Scholar</strong><br>
      Interdisciplinary Graduate College<br>
      <strong>Nanyang Technological University, Singapore</strong>
    </p>

    <p class="contact">
      📍 Lab office: SPMS-MAS-04-02, Table: 9<br>
      📧 <a href="mailto:mahadeb001@e.ntu.edu.sg">mahadeb001@e.ntu.edu.sg</a>
    </p>
  </header>

  <hr class="sep">

  <article class="content">
    <p>
      Mahadeb Mandal is currently a second-year PhD student at
      <strong>Nanyang Technological University (NTU), Singapore</strong>, working under
      the supervision of <a href="https://personal.ntu.edu.sg/xiakelin/index.html"><strong>Prof. Kelin Xia</strong></a>.
      His academic journey is rooted in a strong passion for mathematics and artificial intelligence, with his current
      research focused on the intersection of <strong>Topological Data Analysis (TDA)</strong> and
      <strong>Deep Learning</strong>. He aims to uncover meaningful geometric and topological structures in complex data,
      contributing to advancements in data-driven science and intelligent systems.
    </p>

    <h3>Research Interests</h3>
    <ul>
      <li>Topological Data Analysis (TDA)</li>
      <li>Deep Learning for Scientific Material Discovery</li>
      <li>Mathematical AI</li>
    </ul>
  </article>
</section>

<!-- Styles -->
<style>
  /* Ensure your default layout has this in <head>:
     <meta name="viewport" content="width=device-width, initial-scale=1"> */

  :root{
    --space-1: 0.5rem;
    --space-2: 1rem;
    --space-3: 1.5rem;
    --space-4: 2rem;
    --maxw: 60rem; /* ~960px */
  }

  /* Subtle NTU watermark */
  body::before {
    content: "";
    position: fixed;
    inset: 0 auto auto 0;
    width: clamp(80px, 20vw, 140px);
    height: clamp(80px, 20vw, 140px);
    background: url('/assets/images/ntu_logo.png') no-repeat center/contain;
    opacity: 0.05;
    z-index: 0;
    pointer-events: none;
    user-select: none;
  }

  /* Live clock: fixed on desktop, inline on mobile */
  .clock {
    position: fixed;
    top: 12px;
    right: 16px;
    font-size: 0.95rem;
    z-index: 10;
    background: rgba(255,255,255,0.7);
    backdrop-filter: blur(6px);
    padding: 0.35rem 0.6rem;
    border-radius: 999px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.06);
  }

  .container{
    position: relative;
    z-index: 1; /* above watermark */
    max-width: var(--maxw);
    margin: 0 auto;
    padding: var(--space-3) var(--space-2) var(--space-4);
  }

  .hero{
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    gap: var(--space-2);
    margin-top: clamp(1rem, 4vw, 2rem);
  }

  .avatar{
    width: clamp(96px, 22vw, 180px);
    aspect-ratio: 1/1;
    border-radius: 50%;
    object-fit: cover;
    box-shadow: 0 4px 14px rgba(0,0,0,0.12);
  }

  .title{
    font-size: clamp(1.6rem, 4vw, 2.4rem);
    line-height: 1.15;
    margin: 0.2rem 0 0;
  }

  .subtitle, .contact{
    margin: 0;
    font-size: clamp(0.98rem, 2.2vw, 1.05rem);
  }

  .sep{
    margin: var(--space-3) auto;
    width: min(96%, 40rem);
    border: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, #e6e6e6, transparent);
  }

  .content{
    font-size: clamp(1rem, 2.2vw, 1.06rem);
    line-height: 1.7;
  }

  .content h3{
    margin-top: var(--space-3);
    margin-bottom: var(--space-1);
    font-size: clamp(1.1rem, 2.5vw, 1.25rem);
  }

  .content ul{
    padding-left: 1.2rem;
  }

  /* Mobile tweaks */
  @media (max-width: 640px){
    .clock{
      position: static;
      display: inline-block;
      margin: var(--space-1) auto 0;
      text-align: center;
    }
    .container{
      padding-top: var(--space-2);
    }
    body::before{
      opacity: 0.04;
    }
  }

  /* Large screens */
  @media (min-width: 1200px){
    .container{
      padding-top: var(--space-4);
    }
  }
</style>
