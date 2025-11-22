---
layout: default
title: CV
last_modified_at: 2025-09-01
permalink: /cv/
---

<div id="cv-page">

  <!-- Hero Section -->
  <section class="cv-card cv-hero">
    <div class="cv-hero-header">
      <div>
        <span class="cv-badge">Curriculum Vitae</span>
        <h1>Academic CV</h1>
      </div>

      <div class="cv-hero-meta">
        <div class="cv-pill">
          <span class="cv-pill-label">Status</span>
          <span class="cv-pill-value">PhD Scholar</span>
        </div>
        <div class="cv-pill">
          <span class="cv-pill-label">Field</span>
          <span class="cv-pill-value">AI + Mathematics</span>
        </div>
      </div>
    </div>

    <p class="cv-intro">
      A concise overview of my academic background, research journey, and key achievements
      across mathematics, artificial intelligence, and scientific computing.
    </p>
  </section>

  <!-- Academic Positions -->
  <section class="cv-card">
    <div class="cv-section-header">
      <h2>Academic Positions</h2>
    </div>

    <div class="cv-timeline">

      <div class="cv-timeline-item">
        <div class="cv-timeline-date">Jan 2025 – May 2025</div>
        <div class="cv-timeline-body">
          <h3>Non-Graduating PhD Exchange Fellow</h3>
          <p class="cv-timeline-venue">National University of Singapore (NUS), Singapore</p>
        </div>
      </div>

      <div class="cv-timeline-item">
        <div class="cv-timeline-date">Aug 2024 – Present</div>
        <div class="cv-timeline-body">
          <h3>PhD Scholar</h3>
          <p class="cv-timeline-venue">Interdisciplinary Graduate College, Nanyang Technological University (NTU), Singapore</p>
        </div>
      </div>

    </div>
  </section>

  <!-- Education -->
  <section class="cv-card">
    <div class="cv-section-header">
      <h2>Education</h2>
    </div>

    <div class="cv-timeline">

      <div class="cv-timeline-item">
        <div class="cv-timeline-date">Aug 2024 – Present</div>
        <div class="cv-timeline-body">
          <h3>Ph.D. in Artificial Intelligence</h3>
          <p class="cv-timeline-venue">Nanyang Technological University (NTU), Singapore</p>
          <p class="cv-note">Supervisor: Assoc Prof. Kelin Xia</p>
        </div>
      </div>

      <div class="cv-timeline-item">
        <div class="cv-timeline-date">Jul 2022 – May 2024</div>
        <div class="cv-timeline-body">
          <h3>M.Sc. in Mathematics</h3>
          <p class="cv-timeline-venue">Indian Institute of Technology Bombay, India</p>
          <p class="cv-note">Advisor: Dr. Kummari Mallesham</p>
        </div>
      </div>

      <div class="cv-timeline-item">
        <div class="cv-timeline-date">Jun 2019 – Jun 2022</div>
        <div class="cv-timeline-body">
          <h3>B.Sc. in Mathematics</h3>
          <p class="cv-timeline-venue">Midnapore College (Autonomous), Vidyasagar University, India</p>
        </div>
      </div>

    </div>
  </section>

  <!-- Awards -->
  <section class="cv-card">
    <div class="cv-section-header">
      <h2>Awards</h2>
    </div>

    <ul class="cv-list">
      <li><span class="cv-dot"></span> <strong>2024–2028</strong>: NTU Research Scholarship</li>
      <li><span class="cv-dot"></span> <strong>2022–2024</strong>: IIT Bombay Merit Cum Means Scholarship <em>(Top 25% Students)</em></li>
      <li><span class="cv-dot"></span> <strong>2019–2024</strong>: NSP Scholarship</li>
      <li><span class="cv-dot"></span> <strong>2019–2022</strong>: Swami Vivekananda Merit Cum Means Scholarship</li>
    </ul>
  </section>

  <!-- Achievements -->
  <section class="cv-card">
    <div class="cv-section-header">
      <h2>Achievements</h2>
      <p class="cv-section-subtitle">National-level examinations qualified in India.</p>
    </div>

    <div class="cv-grid">

      <article class="cv-ach-item">
        <div class="cv-ach-header">
          <h3>GATE – Data Science &amp; AI</h3>
          <span class="cv-ach-year">2024</span>
        </div>
        <p class="cv-item-note">Conducted by IISc Bangalore</p>
      </article>

      <article class="cv-ach-item">
        <div class="cv-ach-header">
          <h3>GATE – Mathematics</h3>
          <span class="cv-ach-year">2023</span>
        </div>
        <p class="cv-item-note">All India Rank: 154 · Conducted by IIT Kanpur</p>
      </article>

      <article class="cv-ach-item">
        <div class="cv-ach-header">
          <h3>IIT JAM – Mathematics</h3>
          <span class="cv-ach-year">2022</span>
        </div>
        <p class="cv-item-note">All India Rank: 111 · Conducted by IIT Roorkee</p>
      </article>

      <article class="cv-ach-item">
        <div class="cv-ach-header">
          <h3>Madhava Mathematics Competition</h3>
          <span class="cv-ach-year">2022</span>
        </div>
        <p class="cv-item-note">Top 50 Students · Conducted by HBCSE, TIFR &amp; S.P. College, Pune</p>
      </article>

    </div>

    <p class="cv-footnote">
      A detailed résumé is available upon request (for valid academic or professional reasons).
    </p>
  </section>

</div>

<style>
  #cv-page {
    max-width: 960px;
    margin: 1.5rem auto 2.5rem;
    padding: 0 1rem;
    font-family: "Times New Roman", Times, serif;
  }

  /* Card container */
  .cv-card {
    border-radius: 18px;
    padding: 1.75rem 1.9rem;
    margin-bottom: 1.5rem;
    background:
      radial-gradient(circle at top left, rgba(74,107,255,0.06), transparent 55%),
      var(--bg, #ffffff);
    border: 1px solid rgba(148,163,184,0.35);
    box-shadow: 0 18px 40px rgba(15,23,42,.06);
  }

  .cv-hero {
    display: flex;
    flex-direction: column;
    gap: 1.1rem;
  }

  .cv-hero-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    gap: 1rem;
    flex-wrap: wrap;
  }

  .cv-badge {
    display: inline-block;
    padding: 0.22rem 0.7rem;
    border-radius: 999px;
    background: rgba(74,107,255,0.08);
    color: #4a6bff;
    font-size: 0.72rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: .08em;
  }

  .cv-hero h1 {
    margin: 0.35rem 0 0;
    font-size: 1.6rem;
    color: #111827;
  }

  .cv-hero-meta {
    display: flex;
    gap: 0.5rem;
    flex-wrap: wrap;
  }

  .cv-pill {
    display: inline-flex;
    flex-direction: column;
    padding: 0.35rem 0.7rem;
    border-radius: 999px;
    background: rgba(148,163,184,0.12);
  }

  .cv-pill-label {
    font-size: 0.68rem;
    text-transform: uppercase;
    letter-spacing: .08em;
    color: #6b7280;
  }

  .cv-pill-value {
    font-size: 0.82rem;
    color: #111827;
  }

  .cv-intro {
    margin: 0.3rem 0 0;
    font-size: 0.98rem;
    line-height: 1.7;
    color: #374151;
  }

  .cv-section-header h2 {
    margin: 0 0 0.15rem;
    font-size: 1.2rem;
    color: #111827;
  }

  .cv-section-subtitle {
    margin: 0;
    font-size: 0.85rem;
    color: #6b7280;
  }

  /* Timeline layout */
  .cv-timeline {
    margin-top: 1rem;
    position: relative;
    padding-left: 1.2rem;
  }

  .cv-timeline::before {
    content: "";
    position: absolute;
    left: 0.4rem;
    top: 0.2rem;
    bottom: 0.4rem;
    width: 2px;
    background: linear-gradient(to bottom, rgba(148,163,184,0.8), rgba(148,163,184,0.2));
  }

  .cv-timeline-item {
    position: relative;
    padding-left: 1.2rem;
    margin-bottom: 1rem;
  }

  .cv-timeline-item::before {
    content: "";
    position: absolute;
    left: -0.05rem;
    top: 0.3rem;
    width: 9px;
    height: 9px;
    border-radius: 999px;
    background: #4a6bff;
    box-shadow: 0 0 0 3px rgba(74,107,255,0.18);
  }

  .cv-timeline-date {
    font-size: 0.78rem;
    color: #6b7280;
  }

  .cv-timeline-body h3 {
    margin: 0.1rem 0;
    font-size: 0.98rem;
    color: #111827;
  }

  .cv-timeline-venue {
    margin: 0;
    font-size: 0.84rem;
    color: #4b5563;
  }

  .cv-note {
    margin: 0.2rem 0 0;
    font-size: 0.8rem;
    color: #6b7280;
  }

  /* Awards */
  .cv-list {
    list-style: none;
    padding: 0;
    margin: 1rem 0 0;
    display: grid;
    gap: 0.55rem;
  }

  .cv-list li {
    display: flex;
    gap: 0.5rem;
    font-size: 0.94rem;
    color: #374151;
  }

  .cv-dot {
    width: 8px;
    height: 8px;
    border-radius: 999px;
    background: linear-gradient(135deg, #4a6bff, #7b8dff);
    margin-top: 0.25rem;
    flex-shrink: 0;
  }

  /* Achievements grid */
  .cv-grid {
    margin-top: 1rem;
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 1rem;
  }

  .cv-ach-item {
    padding: 1.1rem 1.2rem;
    border-radius: 14px;
    background: rgba(248,250,252,0.9);
    border: 1px solid rgba(148,163,184,0.35);
    position: relative;
  }

  .cv-ach-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    margin-bottom: 0.35rem;
  }

  .cv-ach-item h3 {
    margin: 0;
    font-size: 0.97rem;
    font-weight: 600;
    color: #111827;
  }

  .cv-ach-year {
    font-size: 0.82rem;
    font-weight: 600;
    color: #475569;
    padding: 0.15rem 0.55rem;
    border-radius: 999px;
    background: rgba(148,163,184,0.15);
  }

  .cv-item-note {
    font-size: 0.86rem;
    color: #4b5563;
    margin: 0;
  }

  .cv-footnote {
    margin-top: 1.1rem;
    font-size: 0.85rem;
    color: #6b7280;
    font-style: italic;
  }

  /* Responsive */
  @media (max-width: 800px) {
    .cv-grid {
      grid-template-columns: 1fr;
    }
  }

  @media (max-width: 600px) {
    .cv-card {
      padding: 1.4rem 1.1rem;
    }

    .cv-hero-header {
      flex-direction: column;
      align-items: flex-start;
    }

    .cv-hero h1 {
      font-size: 1.4rem;
    }
  }
</style>
