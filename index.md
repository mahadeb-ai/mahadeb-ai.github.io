---
layout: default
title: Home
last_modified_at: 2025-09-01
---

<div id="home-page-v4">

  <!-- ============= HERO / HEADER STRIP ============= -->
  <section class="v4-hero" data-aos="fade-up">
    <div class="v4-name-block">
      <h1 class="v4-name">Mahadeb Mandal</h1>
      <p class="v4-role">Research Scholar · Interdisciplinary Graduate College</p>
      <p class="v4-inst"><strong>Nanyang Technological University, Singapore</strong></p>
    </div>
  </section>

  <!-- ============= MAIN GRID ============= -->
  <section class="v4-main" data-aos="fade-in">
    <!-- Left column: photo + contact -->
    <aside class="v4-sidebar">
      <img src="/assets/images/profile.png"
           alt="Profile Photo"
           class="v4-photo" />

      <div class="v4-contact-block">
        <h2 class="v4-subheading">Contact</h2>
        <p class="v4-contact">
          📍 Lab office: SPMS-MAS-04-02, Table 9<br>
          📧 <a href="mailto:mahadeb001@e.ntu.edu.sg">mahadeb001@e.ntu.edu.sg</a>
        </p>
      </div>

      <div class="v4-meta-block">
        <h2 class="v4-subheading">Affiliation</h2>
        <p class="v4-meta">
          Interdisciplinary Graduate College<br>
          Nanyang Technological University (NTU), Singapore
        </p>
      </div>
    </aside>

    <!-- Right column: about + research interests -->
    <div class="v4-content">
      <section class="v4-section">
        <h2 class="v4-section-title">About</h2>
        <p class="v4-text">
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

      <section class="v4-section">
        <h2 class="v4-section-title">Research Interests</h2>
        <ul class="v4-interest-list">
          <li>Topological Data Analysis (TDA)</li>
          <li>Deep Learning for Scientific Material Discovery</li>
          <li>Mathematical AI</li>
        </ul>
      </section>
    </div>
  </section>

</div>

<style>
  /* ============== Global Wrapper ============== */
  #home-page-v4 {
    max-width: 1020px;
    margin: 2rem auto 3rem;
    padding: 0 1.3rem;
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

  /* ============== Hero strip ============== */
  .v4-hero {
    border-bottom: 1px solid rgba(148,163,184,0.6);
    padding-bottom: 0.9rem;
    margin-bottom: 1.4rem;
  }

  .v4-name-block {
    border-left: 4px solid #4a6bff;
    padding-left: 0.9rem;
  }

  .v4-name {
    margin: 0;
    font-size: 2.1rem;
    color: #111827;
  }

  .v4-role {
    margin: 0.35rem 0 0.1rem;
    font-size: 1rem;
    color: #374151;
  }

  .v4-inst {
    margin: 0.1rem 0 0;
    font-size: 0.98rem;
    color: #4b5563;
  }

  /* ============== Main grid ============== */
  .v4-main {
    display: grid;
    grid-template-columns: minmax(0, 260px) minmax(0, 1fr);
    gap: 2.2rem;
    margin-top: 1.2rem;
  }

  /* Sidebar */
  .v4-sidebar {
    border-right: 1px solid rgba(148,163,184,0.4);
    padding-right: 1.5rem;
    display: flex;
    flex-direction: column;
    gap: 1.6rem;
  }

  .v4-photo {
    width: 170px;
    height: 170px;
    border-radius: 50%;
    object-fit: cover;
    display: block;
    margin-bottom: 0.5rem;
    box-shadow: 0 8px 24px rgba(15,23,42,0.22);
  }

  .v4-subheading {
    margin: 0 0 0.25rem;
    font-size: 0.95rem;
    text-transform: uppercase;
    letter-spacing: 0.12em;
    color: #6b7280;
  }

  .v4-contact,
  .v4-meta {
    margin: 0;
    font-size: 0.9rem;
    color: #374151;
    line-height: 1.6;
  }

  .v4-contact-block,
  .v4-meta-block {
    padding-top: 0.2rem;
  }

  /* Right column */
  .v4-content {
    display: flex;
    flex-direction: column;
    gap: 1.8rem;
  }

  .v4-section {
    padding-bottom: 0.8rem;
    border-bottom: 1px solid rgba(226,232,240,0.9);
  }

  .v4-section:last-of-type {
    border-bottom: none;
  }

  .v4-section-title {
    margin: 0 0 0.6rem;
    font-size: 1.3rem;
    color: #111827;
  }

  .v4-text {
    margin: 0;
    font-size: 1.02rem;
    line-height: 1.8;
    color: #374151;
  }

  .v4-interest-list {
    list-style: disc;
    margin: 0.2rem 0 0;
    padding-left: 1.2rem;
    font-size: 1rem;
    color: #374151;
    line-height: 1.7;
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
  @media (max-width: 820px) {
    .v4-main {
      grid-template-columns: 1fr;
      gap: 1.4rem;
    }
    .v4-sidebar {
      border-right: none;
      border-bottom: 1px solid rgba(148,163,184,0.35);
      padding-right: 0;
      padding-bottom: 1.2rem;
      flex-direction: row;
      flex-wrap: wrap;
      gap: 1.2rem;
      align-items: flex-start;
    }
    .v4-photo {
      width: 140px;
      height: 140px;
      margin-right: 0.8rem;
    }
  }

  @media (max-width: 540px) {
    #home-page-v4 {
      padding: 0 0.9rem;
    }
    .v4-name {
      font-size: 1.7rem;
    }
    .v4-main {
      margin-top: 1rem;
    }
    .v4-sidebar {
      flex-direction: column;
      align-items: flex-start;
    }
    .v4-text {
      font-size: 0.95rem;
    }
  }
</style>
