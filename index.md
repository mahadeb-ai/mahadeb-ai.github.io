---
layout: default
title: Home
last_modified_at: 2025-09-01
---

<div id="home-page">

  <!-- ============= HERO ============= -->
  <section class="home-hero" data-aos="fade-up">
    <div class="home-hero-photo-wrap">
      <img src="/assets/images/profile.png"
           alt="Profile Photo"
           class="home-hero-photo" />
    </div>

    <div class="home-hero-text">
      <p class="home-label">Research Scholar · NTU Singapore</p>
      <h1 class="home-name">Mahadeb Mandal</h1>

      <p class="home-affiliation">
        Interdisciplinary Graduate College<br>
        <strong>Nanyang Technological University, Singapore</strong>
      </p>

      <div class="home-contact">
        <div>📍 Lab office: SPMS-MAS-04-02, Table: 9</div>
        <div>📧 <a href="mailto:mahadeb001@e.ntu.edu.sg">mahadeb001@e.ntu.edu.sg</a></div>
      </div>
    </div>
  </section>

  <!-- ============= ABOUT ============= -->
  <section class="home-section" data-aos="fade-in">
    <h2 class="home-section-title">About</h2>
    <p class="home-about">
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

  <!-- ============= RESEARCH INTERESTS ============= -->
  <section class="home-section" data-aos="fade-up">
    <h2 class="home-section-title">Research Interests</h2>
    <ul class="home-interest-list">
      <li>Topological Data Analysis (TDA)</li>
      <li>Deep Learning for Scientific Material Discovery</li>
      <li>Mathematical AI</li>
    </ul>
  </section>

</div>

<style>
  /* ============== Global ============== */
  #home-page {
    max-width: 980px;
    margin: 1.8rem auto 3rem;
    padding: 0 1.2rem;
    font-family: "Times New Roman", Times, serif;
    position: relative;
    z-index: 1;
  }

  /* ============== Hero ============== */
  .home-hero {
    display: grid;
    grid-template-columns: minmax(0, 260px) minmax(0, 1fr);
    gap: 1.8rem;
    align-items: center;
    padding: 1.8rem 2rem;
    border-radius: 20px;
    background:
      radial-gradient(circle at top left, rgba(74,107,255,0.08), transparent 55%),
      linear-gradient(135deg, #ffffff, #f8fafc);
    border: 1px solid rgba(148,163,184,0.35);
    box-shadow: 0 18px 40px rgba(15,23,42,.06);
  }

  .home-hero-photo-wrap {
    display: flex;
    justify-content: center;
  }

  .home-hero-photo {
    width: 180px;
    height: 180px;
    border-radius: 50%;
    object-fit: cover;
    box-shadow: 0 10px 25px rgba(15,23,42,0.22);
    border: 3px solid rgba(255,255,255,0.9);
  }

  .home-hero-text {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
  }

  .home-label {
    margin: 0;
    font-size: 0.78rem;
    text-transform: uppercase;
    letter-spacing: 0.14em;
    color: #6b7280;
  }

  .home-name {
    margin: 0.2rem 0 0.1rem;
    font-size: 2rem;
    color: #0f172a;
  }

  .home-affiliation {
    margin: 0.1rem 0 0.6rem;
    font-size: 1rem;
    color: #334155;
    line-height: 1.6;
  }

  .home-contact {
    font-size: 0.92rem;
    color: #475569;
    line-height: 1.5;
  }

  .home-contact a {
    color: #4a6bff;
    text-decoration: none;
  }

  .home-contact a:hover {
    text-decoration: underline;
  }

  /* ============== Sections ============== */
  .home-section {
    margin-top: 2.2rem;
  }

  .home-section-title {
    font-size: 1.25rem;
    color: #111827;
    margin: 0 0 0.8rem;
    padding-left: 0.75rem;
    border-left: 3px solid #4a6bff;
  }

  .home-about {
    margin: 0;
    font-size: 1.02rem;
    line-height: 1.8;
    color: #374151;
  }

  .home-about a {
    color: #4a6bff;
    text-decoration: none;
  }

  .home-about a:hover {
    text-decoration: underline;
  }

  .home-interest-list {
    list-style: none;
    padding: 0;
    margin: 0.2rem 0 0;
    display: flex;
    flex-wrap: wrap;
    gap: 0.6rem;
  }

  .home-interest-list li {
    padding: 0.35rem 0.7rem;
    border-radius: 999px;
    border: 1px solid rgba(148,163,184,0.6);
    background: rgba(248,250,252,0.9);
    font-size: 0.9rem;
    color: #111827;
  }

  /* ============== NTU Watermark ============== */
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

  /* ============== Responsive ============== */
  @media (max-width: 780px) {
    .home-hero {
      grid-template-columns: 1fr;
      padding: 1.5rem 1.4rem;
    }
    .home-hero-photo {
      width: 145px;
      height: 145px;
    }
    .home-name {
      font-size: 1.7rem;
    }
  }

  @media (max-width: 520px) {
    #home-page {
      padding: 0 0.8rem;
    }
    .home-hero {
      padding: 1.3rem 1.1rem;
      border-radius: 16px;
    }
    .home-about {
      font-size: 0.94rem;
    }
    .home-interest-list li {
      font-size: 0.86rem;
    }
  }
</style>
