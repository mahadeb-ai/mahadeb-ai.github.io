---
layout: default
title: Home
last_modified_at: 2025-09-01
---

<div id="home-v7">

  <!-- ================= HERO BANNER ================= -->
  <section class="v7-hero" data-aos="fade-down">
    <div class="v7-hero-inner">
      <div class="v7-hero-text">
        <p class="v7-label">Research Scholar · NTU Singapore</p>
        <h1 class="v7-name">Mahadeb Mandal</h1>
        <p class="v7-role">
          Interdisciplinary Graduate College<br>
          <strong>Nanyang Technological University, Singapore</strong>
        </p>

        <div class="v7-contact">
          <div>📍 SPMS-MAS-04-02, Table 9</div>
          <div>📧 <a href="mailto:mahadeb001@e.ntu.edu.sg">mahadeb001@e.ntu.edu.sg</a></div>
        </div>
      </div>

      <div class="v7-hero-photo-wrap">
        <img src="/assets/images/profile.png"
             alt="Profile Photo"
             class="v7-photo" />
      </div>
    </div>
  </section>

  <!-- ================= ABOUT ================= -->
  <section class="v7-section" data-aos="fade-in">
    <h2 class="v7-heading">About</h2>
    <p class="v7-text">
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

  <!-- ================= RESEARCH INTERESTS ================= -->
  <section class="v7-section" data-aos="fade-up">
    <h2 class="v7-heading">Research Interests</h2>
    <ul class="v7-pill-list">
      <li>Topological Data Analysis (TDA)</li>
      <li>Deep Learning for Scientific Material Discovery</li>
      <li>Mathematical AI</li>
    </ul>
  </section>

</div>

<style>
  /* ================= GLOBAL SHELL ================= */
  #home-v7 {
    max-width: 1040px;
    margin: 2.4rem auto 3.5rem;
    padding: 0 1.4rem;
    font-family: "Times New Roman", Times, serif;
    position: relative;
    z-index: 1;
  }

  a {
    color: #1d4ed8;
    text-decoration: none;
  }
  a:hover {
    text-decoration: underline;
  }

  /* ================= HERO BANNER ================= */
  .v7-hero {
    border-radius: 18px;
    overflow: hidden;
    background: linear-gradient(120deg, #0f172a, #1e293b 60%, #0b1120);
    color: #e5e7eb;
    box-shadow: 0 22px 50px rgba(15,23,42,0.45);
    margin-bottom: 2.4rem;
  }

  .v7-hero-inner {
    display: grid;
    grid-template-columns: minmax(0, 2.1fr) minmax(0, 1.4fr);
    gap: 1.8rem;
    padding: 2.1rem 2.3rem;
    align-items: center;
  }

  .v7-hero-text {
    position: relative;
  }

  .v7-hero-text::before {
    content: "";
    position: absolute;
    top: 0.3rem;
    left: -1.1rem;
    width: 4px;
    height: 2.8rem;
    background: linear-gradient(to bottom, #f97316, #e11d48);
    border-radius: 999px;
  }

  .v7-label {
    margin: 0;
    font-size: 0.78rem;
    text-transform: uppercase;
    letter-spacing: 0.16em;
    color: #9ca3af;
  }

  .v7-name {
    margin: 0.35rem 0 0.1rem;
    font-size: 2.1rem;
    color: #f9fafb;
  }

  .v7-role {
    margin: 0.3rem 0 0.9rem;
    font-size: 1rem;
    color: #d1d5db;
    line-height: 1.6;
  }

  .v7-contact {
    font-size: 0.92rem;
    color: #e5e7eb;
    line-height: 1.5;
  }

  .v7-contact a {
    color: #bfdbfe;
  }

  .v7-hero-photo-wrap {
    display: flex;
    justify-content: flex-end;
  }

  .v7-photo {
    width: 180px;
    height: 180px;
    border-radius: 50%;
    object-fit: cover;
    box-shadow: 0 16px 40px rgba(0,0,0,0.6);
    border: 3px solid rgba(248,250,252,0.9);
  }

  /* ================= SECTIONS ================= */
  .v7-section {
    margin-top: 2rem;
  }

  .v7-heading {
    margin: 0 0 0.7rem;
    font-size: 1.3rem;
    color: #111827;
    border-left: 3px solid #4b5563;
    padding-left: 0.7rem;
  }

  .v7-text {
    margin: 0;
    font-size: 1.02rem;
    line-height: 1.8;
    color: #374151;
  }

  .v7-pill-list {
    list-style: none;
    padding: 0;
    margin: 0.4rem 0 0;
    display: flex;
    flex-wrap: wrap;
    gap: 0.6rem;
  }

  .v7-pill-list li {
    padding: 0.35rem 0.8rem;
    border-radius: 999px;
    border: 1px solid rgba(148,163,184,0.7);
    background: #f9fafb;
    font-size: 0.9rem;
    color: #111827;
  }

  /* ================= NTU WATERMARK (SUBTLE) ================= */
  body::before {
    content: "";
    position: fixed;
    top: 0.6rem;
    left: 0.8rem;
    width: 80px;
    height: 80px;
    background-image: url('/assets/images/ntu_logo.png');
    background-repeat: no-repeat;
    background-position: center;
    background-size: 60px;
    opacity: 0.05;
    z-index: 0;
    pointer-events: none;
    user-select: none;
  }

  /* ================= RESPONSIVE ================= */
  @media (max-width: 840px) {
    .v7-hero-inner {
      grid-template-columns: minmax(0, 1.6fr) minmax(0, 1.2fr);
      padding: 1.8rem 1.7rem;
    }
    .v7-name {
      font-size: 1.8rem;
    }
    .v7-photo {
      width: 150px;
      height: 150px;
    }
  }

  @media (max-width: 640px) {
    .v7-hero-inner {
      grid-template-columns: 1fr;
      padding: 1.6rem 1.4rem 1.5rem;
      gap: 1.4rem;
    }
    .v7-hero-photo-wrap {
      justify-content: flex-start;
    }
    .v7-photo {
      width: 130px;
      height: 130px;
    }
  }

  @media (max-width: 520px) {
    #home-v7 {
      padding: 0 1rem;
    }
    .v7-text {
      font-size: 0.95rem;
    }
    .v7-pill-list li {
      font-size: 0.86rem;
    }
  }
</style>
