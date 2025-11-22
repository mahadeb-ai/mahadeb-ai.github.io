---
layout: default
title: Home
last_modified_at: 2025-09-01
---

<div id="home-page-v5">

  <div class="v5-paper">

    <!-- ============= HEADER STRIP ============= -->
    <header class="v5-header" data-aos="fade-down">
      <div>
        <h1 class="v5-name">Mahadeb Mandal</h1>
        <p class="v5-role">Research Scholar · Interdisciplinary Graduate College</p>
        <p class="v5-inst"><strong>Nanyang Technological University, Singapore</strong></p>
      </div>
      <div class="v5-contact">
        <div>📍 SPMS-MAS-04-02, Table 9</div>
        <div>📧 <a href="mailto:mahadeb001@e.ntu.edu.sg">mahadeb001@e.ntu.edu.sg</a></div>
      </div>
    </header>

    <hr class="v5-rule" />

    <!-- ============= PROFILE ROW ============= -->
    <section class="v5-profile-row" data-aos="fade-up">
      <img src="/assets/images/profile.png"
           alt="Profile Photo"
           class="v5-photo" />
      <div class="v5-profile-text">
        <p class="v5-tagline">
          PhD student working at the interface of <strong>Topological Data Analysis</strong>,
          <strong>Deep Learning</strong>, and <strong>Mathematical AI</strong>.
        </p>
      </div>
    </section>

    <!-- ============= ABOUT ============= -->
    <section class="v5-section" data-aos="fade-in">
      <h2 class="v5-heading">About</h2>
      <p class="v5-body-text">
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
    <section class="v5-section" data-aos="fade-up">
      <h2 class="v5-heading">Research Interests</h2>
      <ul class="v5-list">
        <li>Topological Data Analysis (TDA)</li>
        <li>Deep Learning for Scientific Material Discovery</li>
        <li>Mathematical AI</li>
      </ul>
    </section>

  </div>

</div>

<style>
  /* ========= Page background & shell ========= */
  #home-page-v5 {
    font-family: "Times New Roman", Times, serif;
    min-height: 60vh;
    padding: 2rem 0;
    position: relative;
    z-index: 1;
    background: radial-gradient(circle at top, #f3f4f6 0, #e5e7eb 28%, #f9fafb 100%);
  }

  .v5-paper {
    max-width: 900px;
    margin: 0 auto;
    padding: 2.2rem 2.3rem;
    background: #ffffff;
    border-radius: 8px;
    box-shadow: 0 18px 40px rgba(15,23,42,0.12);
    border: 1px solid rgba(209,213,219,0.8);
  }

  /* ========= Header strip ========= */
  .v5-header {
    display: flex;
    justify-content: space-between;
    gap: 1.5rem;
    align-items: flex-start;
  }

  .v5-name {
    margin: 0;
    font-size: 2.0rem;
    color: #111827;
  }

  .v5-role {
    margin: 0.35rem 0 0.1rem;
    font-size: 0.98rem;
    color: #374151;
  }

  .v5-inst {
    margin: 0.1rem 0 0;
    font-size: 0.96rem;
    color: #4b5563;
  }

  .v5-contact {
    font-size: 0.9rem;
    color: #4b5563;
    text-align: right;
    line-height: 1.5;
  }

  .v5-contact a {
    color: #1d4ed8;
    text-decoration: none;
  }

  .v5-contact a:hover {
    text-decoration: underline;
  }

  .v5-rule {
    margin: 1.4rem 0 1.7rem;
    border: none;
    border-top: 1px solid rgba(209,213,219,0.9);
  }

  /* ========= Profile row ========= */
  .v5-profile-row {
    display: grid;
    grid-template-columns: auto minmax(0, 1fr);
    gap: 1.4rem;
    align-items: center;
    margin-bottom: 1.8rem;
  }

  .v5-photo {
    width: 150px;
    height: 150px;
    border-radius: 50%;
    object-fit: cover;
    box-shadow: 0 10px 28px rgba(15,23,42,0.28);
  }

  .v5-profile-text {
    font-size: 0.98rem;
    color: #374151;
  }

  .v5-tagline {
    margin: 0;
    font-style: italic;
    line-height: 1.7;
  }

  /* ========= Sections ========= */
  .v5-section {
    margin-top: 1.8rem;
  }

  .v5-heading {
    margin: 0 0 0.6rem;
    font-size: 1.3rem;
    color: #111827;
  }

  .v5-body-text {
    margin: 0;
    font-size: 1.02rem;
    line-height: 1.8;
    color: #374151;
  }

  .v5-body-text a {
    color: #1d4ed8;
    text-decoration: none;
  }

  .v5-body-text a:hover {
    text-decoration: underline;
  }

  .v5-list {
    margin: 0.2rem 0 0;
    padding-left: 1.2rem;
    font-size: 1.0rem;
    color: #374151;
    line-height: 1.7;
  }

  /* ========= NTU watermark (subtle) ========= */
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
    opacity: 0.04;
    z-index: 0;
    pointer-events: none;
    user-select: none;
  }

  /* ========= Responsive ========= */
  @media (max-width: 820px) {
    .v5-paper {
      padding: 1.7rem 1.6rem;
    }
    .v5-header {
      flex-direction: column;
      align-items: flex-start;
    }
    .v5-contact {
      text-align: left;
    }
    .v5-profile-row {
      grid-template-columns: 1fr;
      text-align: left;
    }
    .v5-photo {
      width: 130px;
      height: 130px;
    }
  }

  @media (max-width: 540px) {
    .v5-paper {
      padding: 1.5rem 1.2rem;
    }
    .v5-name {
      font-size: 1.7rem;
    }
    .v5-body-text,
    .v5-list {
      font-size: 0.95rem;
    }
  }
</style>
