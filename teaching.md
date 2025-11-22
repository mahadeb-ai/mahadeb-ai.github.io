---
layout: default
title: Teaching
last_modified_at: 2025-09-01
permalink: /teaching/
---

<div id="teaching-page">

  <!-- Hero / Intro card -->
  <section class="teach-card teach-hero">
    <div class="teach-hero-header">
      <div>
        <span class="teach-badge">Teaching & Mentoring</span>
        <h1>📚 Teaching</h1>
      </div>
      <div class="teach-hero-meta">
        <div class="teach-pill">
          <span class="pill-label">Roles</span>
          <span class="pill-value">TA · Mentor</span>
        </div>
        <div class="teach-pill">
          <span class="pill-label">Institutions</span>
          <span class="pill-value">NTU · IIT Bombay</span>
        </div>
      </div>
    </div>

    <p class="teach-intro">
      As part of my academic journey, I've had the privilege to contribute to various teaching and mentoring activities.
      I enjoy helping students build intuition, connect theory with practice, and become confident in tackling unfamiliar problems.
    </p>
  </section>

  <!-- Courses Assisted -->
  <section class="teach-card">
    <div class="teach-section-header">
      <h2>Courses Assisted</h2>
      <p class="teach-section-subtitle">Formal teaching roles across undergraduate and advanced courses.</p>
    </div>

    <div class="teach-grid">
      <article class="teach-course">
        <div class="teach-course-header">
          <span class="teach-course-code">MA0002</span>
          <span class="teach-tag">Teaching Assistant</span>
        </div>
        <h3 class="teach-course-title">Linear Algebra &amp; Differential Equations</h3>
        <p class="teach-course-meta">Nanyang Technological University · 2024</p>
      </article>

      <article class="teach-course">
        <div class="teach-course-header">
          <span class="teach-course-code">MA1008</span>
          <span class="teach-tag">Teaching Assistant</span>
        </div>
        <h3 class="teach-course-title">Mathematics I</h3>
        <p class="teach-course-meta">Nanyang Technological University · 2024</p>
      </article>

      <article class="teach-course">
        <div class="teach-course-header">
          <span class="teach-course-code">Workshop</span>
          <span class="teach-tag teach-tag-alt">Student Mentor</span>
        </div>
        <h3 class="teach-course-title">Advanced Mathematics Workshop</h3>
        <p class="teach-course-meta">IIT Bombay · 2023</p>
      </article>
    </div>
  </section>

  <!-- Mentoring -->
  <section class="teach-card">
    <div class="teach-section-header">
      <h2>Mentoring</h2>
      <p class="teach-section-subtitle">Guiding students beyond the classroom.</p>
    </div>

    <ul class="teach-list">
      <li>
        <span class="teach-bullet-dot"></span>
        <span>Supervised 2 undergraduate students in research projects.</span>
      </li>
      <li>
        <span class="teach-bullet-dot"></span>
        <span>Conducted weekly problem-solving sessions for junior students.</span>
      </li>
      <li>
        <span class="teach-bullet-dot"></span>
        <span>Organized study groups for complex mathematical concepts.</span>
      </li>
    </ul>
  </section>

  <!-- Teaching Philosophy -->
  <section class="teach-card teach-philosophy">
    <div class="teach-section-header">
      <h2>Teaching Philosophy</h2>
    </div>

    <div class="teach-quote">
      <div class="teach-quote-mark">“</div>
      <div class="teach-quote-body">
        <p>
          I believe in creating an inclusive learning environment where students feel comfortable asking questions
          and exploring concepts deeply. My approach combines theoretical foundations with practical applications
          to make mathematics accessible and engaging.
        </p>
      </div>
    </div>
  </section>

</div>

<style>
  #teaching-page {
    max-width: 960px;
    margin: 1.5rem auto 2.5rem;
    padding: 0 1rem;
    font-family: "Times New Roman", Times, serif;
  }

  .teach-card {
    border-radius: 18px;
    padding: 1.75rem 1.9rem;
    margin-bottom: 1.5rem;
    background:
      radial-gradient(circle at top left, rgba(74,107,255,0.06), transparent 55%),
      var(--bg, #ffffff);
    border: 1px solid rgba(148,163,184,0.35);
    box-shadow: 0 18px 40px rgba(15,23,42,.06);
  }

  .teach-hero {
    display: flex;
    flex-direction: column;
    gap: 1.1rem;
  }

  .teach-hero-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    gap: 1rem;
    flex-wrap: wrap;
  }

  .teach-badge {
    display: inline-block;
    padding: 0.22rem 0.7rem;
    border-radius: 999px;
    background: rgba(74,107,255,0.08);
    color: #4a6bff;
    font-size: 0.72rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.08em;
  }

  .teach-hero h1 {
    margin: 0.35rem 0 0;
    font-size: 1.6rem;
    color: #111827;
  }

  .teach-hero-meta {
    display: flex;
    gap: 0.5rem;
    flex-wrap: wrap;
  }

  .teach-pill {
    display: inline-flex;
    flex-direction: column;
    padding: 0.35rem 0.7rem;
    border-radius: 999px;
    background: rgba(148,163,184,0.12);
  }

  .pill-label {
    font-size: 0.68rem;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: #6b7280;
  }

  .pill-value {
    font-size: 0.82rem;
    color: #111827;
  }

  .teach-intro {
    margin: 0.3rem 0 0;
    font-size: 0.98rem;
    line-height: 1.7;
    color: #374151;
  }

  .teach-section-header h2 {
    margin: 0 0 0.15rem;
    font-size: 1.2rem;
    color: #111827;
  }

  .teach-section-subtitle {
    margin: 0;
    font-size: 0.85rem;
    color: #6b7280;
  }

  /* Courses grid */
  .teach-grid {
    margin-top: 1rem;
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 0.85rem;
  }

  .teach-course {
    border-radius: 14px;
    background: rgba(248,250,252,0.9);
    border: 1px solid rgba(148,163,184,0.4);
    padding: 0.8rem 0.85rem;
    display: flex;
    flex-direction: column;
    gap: 0.2rem;
  }

  .teach-course-header {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    gap: 0.4rem;
  }

  .teach-course-code {
    font-size: 0.8rem;
    font-weight: 700;
    color: #1d4ed8;
  }

  .teach-tag {
    font-size: 0.72rem;
    padding: 0.1rem 0.55rem;
    border-radius: 999px;
    background: rgba(37,99,235,0.08);
    color: #1d4ed8;
    font-weight: 600;
  }

  .teach-tag-alt {
    background: rgba(22,163,74,0.08);
    color: #15803d;
  }

  .teach-course-title {
    margin: 0.1rem 0;
    font-size: 0.95rem;
    color: #111827;
  }

  .teach-course-meta {
    margin: 0;
    font-size: 0.8rem;
    color: #6b7280;
  }

  /* Mentoring list */
  .teach-list {
    list-style: none;
    padding: 0;
    margin: 1rem 0 0;
    display: grid;
    gap: 0.55rem;
  }

  .teach-list li {
    display: flex;
    align-items: flex-start;
    gap: 0.5rem;
    font-size: 0.94rem;
    color: #374151;
  }

  .teach-bullet-dot {
    width: 8px;
    height: 8px;
    margin-top: 0.25rem;
    border-radius: 999px;
    background: linear-gradient(135deg, #4a6bff, #7b8dff);
    flex-shrink: 0;
  }

  /* Philosophy block */
  .teach-philosophy {
    background:
      radial-gradient(circle at top right, rgba(52,211,153,0.09), transparent 55%),
      var(--bg, #ffffff);
  }

  .teach-quote {
    margin-top: 0.8rem;
    display: flex;
    gap: 0.6rem;
    align-items: flex-start;
  }

  .teach-quote-mark {
    font-size: 2.4rem;
    line-height: 1;
    color: rgba(148,163,184,0.8);
    font-family: Georgia, "Times New Roman", serif;
  }

  .teach-quote-body p {
    margin: 0;
    font-size: 0.98rem;
    line-height: 1.8;
    color: #111827;
  }

  @media (max-width: 800px) {
    .teach-grid {
      grid-template-columns: 1fr 1fr;
    }
  }

  @media (max-width: 600px) {
    .teach-card {
      padding: 1.4rem 1.1rem;
    }
    .teach-grid {
      grid-template-columns: 1fr;
    }
    .teach-hero-header {
      flex-direction: column;
      align-items: flex-start;
    }
    .teach-hero h1 {
      font-size: 1.4rem;
    }
  }
</style>
