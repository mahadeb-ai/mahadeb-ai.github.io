---
layout: default
title: Home
last_modified_at: 2025-09-01
---

<!-- =======================
     HERO SECTION
======================== -->
<section id="hero" data-aos="fade-up">
  <div class="hero-card">
    
    <img src="/assets/images/profile.png" 
         alt="Profile Photo" 
         class="hero-photo" />

    <h1 class="hero-title">Mahadeb Mandal</h1>

    <p class="hero-subtitle">
      <strong>Research Scholar</strong><br>
      Interdisciplinary Graduate College<br>
      <strong>Nanyang Technological University, Singapore</strong>
    </p>

    <p class="hero-contact">
      📍 Lab office: SPMS-MAS-04-02, Table: 9<br>
      📧 <a href="mailto:mahadeb001@e.ntu.edu.sg">mahadeb001@e.ntu.edu.sg</a>
    </p>

  </div>
</section>

<!-- Divider -->
<div class="section-divider"></div>

<!-- =======================
     ABOUT SECTION
======================== -->
<section id="about" data-aos="fade-in">
  <p class="about-text">
    Mahadeb Mandal is a second-year PhD student at 
    <strong>Nanyang Technological University (NTU), Singapore</strong>, 
    working under the supervision of 
    <a href="https://personal.ntu.edu.sg/xiakelin/index.html"><strong>Prof. Kelin Xia</strong></a>. 
    His academic journey is driven by a deep passion for mathematics and artificial intelligence.
    His current research focuses on the powerful intersection of 
    <strong>Topological Data Analysis (TDA)</strong> 
    and <strong>Deep Learning</strong>, aiming to uncover meaningful geometric and 
    topological structures in complex data to advance scientific discovery and intelligent systems.
  </p>
</section>

<!-- =======================
     RESEARCH INTERESTS
======================== -->
<section id="interests" data-aos="fade-up">
  <h2 class="section-title">Research Interests</h2>

  <ul class="interest-list">
    <li>Topological Data Analysis (TDA)</li>
    <li>Deep Learning for Scientific Material Discovery</li>
    <li>Mathematical AI</li>
  </ul>
</section>

<!-- =======================
     WATERMARK
======================== -->
<style>
  /* ===========================
     GLOBAL TYPOGRAPHY
  ============================ */
  body {
    font-family: "Times New Roman", Times, serif;
  }

  /* ===========================
     HERO SECTION STYLE
  ============================ */
  #hero {
    display: flex;
    justify-content: center;
    margin-top: 1.8rem;
  }

  .hero-card {
    background: linear-gradient(145deg, rgba(255,255,255,0.85), rgba(245,247,255,0.95));
    padding: 2.2rem 2.4rem;
    border-radius: 18px;
    text-align: center;
    max-width: 650px;
    box-shadow: 0 18px 40px rgba(15,23,42,0.08);
    border: 1px solid rgba(148,163,184,0.25);
  }

  .hero-photo {
    width: 170px;
    border-radius: 50%;
    margin-bottom: 1rem;
    box-shadow: 0 6px 20px rgba(0,0,0,0.12);
  }

  .hero-title {
    margin-top: 0.6rem;
    font-size: 2rem;
    color: #0f172a;
  }

  .hero-subtitle {
    font-size: 1.05rem;
    color: #334155;
    margin-top: 0.9rem;
    line-height: 1.55;
  }

  .hero-contact {
    margin-top: 0.7rem;
    color: #475569;
    font-size: 0.95rem;
  }

  .hero-contact a {
    color: #4a6bff;
    text-decoration: none;
  }

  /* ===========================
     SECTION DIVIDER
  ============================ */
  .section-divider {
    margin: 2.4rem auto;
    width: 90%;
    max-width: 620px;
    height: 1px;
    background: linear-gradient(to right, transparent, rgba(148,163,184,0.45), transparent);
  }

  /* ===========================
     ABOUT SECTION
  ============================ */
  #about {
    max-width: 760px;
    margin: 0 auto;
    padding: 0 1rem;
  }

  .about-text {
    font-size: 1.05rem;
    color: #334155;
    line-height: 1.7;
  }

  /* ===========================
     RESEARCH INTERESTS
  ============================ */
  #interests {
    max-width: 760px;
    margin: 2rem auto 3rem;
    padding: 0 1rem;
  }

  .section-title {
    font-size: 1.4rem;
    margin-bottom: 1rem;
    color: #1e293b;
    border-left: 4px solid #4a6bff;
    padding-left: 0.75rem;
  }

  .interest-list {
    list-style: square;
    margin-left: 1.5rem;
    color: #334155;
    font-size: 1.05rem;
    line-height: 1.7;
  }

  /* ===========================
     NTU WATERMARK
  ============================ */
  body::before {
    content: "";
    position: fixed;
    top: 0;
    left: 0;
    width: 13vw;
    height: 15vh;
    background-image: url('/assets/images/ntu_logo.png');
    background-repeat: no-repeat;
    background-position: center 95%;
    background-size: 55px;
    opacity: 0.05;
    z-index: 0;
    pointer-events: none;
    user-select: none;
  }

  /* ===========================
     MOBILE RESPONSIVE
  ============================ */
  @media (max-width: 600px) {
    .hero-card {
      padding: 1.4rem;
      border-radius: 14px;
    }
    .hero-photo {
      width: 125px;
    }
    .hero-title {
      font-size: 1.5rem;
    }
    .about-text,
    .interest-list {
      font-size: 0.92rem;
    }
  }
</style>
