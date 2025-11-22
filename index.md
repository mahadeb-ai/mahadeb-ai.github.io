---
layout: default
title: Home
last_modified_at: 2025-09-01
---

<div id="home-v6">

  <!-- ================= HERO ================= -->
  <section class="v6-hero" data-aos="fade-up">
    <div class="v6-accent"></div>

    <div class="v6-hero-card">

      <img src="/assets/images/profile.png" 
           alt="Profile Photo"
           class="v6-photo" />

      <h1 class="v6-name">Mahadeb Mandal</h1>
      <p class="v6-role">
        Research Scholar <br>
        Interdisciplinary Graduate College <br>
        <strong>Nanyang Technological University, Singapore</strong>
      </p>

      <div class="v6-contact">
        <div>📍 SPMS-MAS-04-02, Table 9</div>
        <div>📧 <a href="mailto:mahadeb001@e.ntu.edu.sg">mahadeb001@e.ntu.edu.sg</a></div>
      </div>

    </div>
  </section>

  <!-- ================= ABOUT ================= -->
  <section class="v6-section" data-aos="fade-in">
    <h2 class="v6-title">About</h2>

    <p class="v6-text">
      Mahadeb Mandal is a second-year PhD student at 
      <strong>Nanyang Technological University (NTU), Singapore</strong>,
      working under the supervision of 
      <a href="https://personal.ntu.edu.sg/xiakelin/index.html"><strong>Prof. Kelin Xia</strong></a>.
      His research explores the intersection of 
      <strong>Topological Data Analysis (TDA)</strong>,
      <strong>Deep Learning</strong>, and 
      <strong>Mathematical AI</strong>, uncovering geometric and topological structure in 
      scientific data to enable new forms of intelligent discovery.
    </p>
  </section>

  <!-- ================= INTERESTS ================= -->
  <section class="v6-section" data-aos="fade-up">
    <h2 class="v6-title">Research Interests</h2>

    <div class="v6-chips">
      <span class="v6-chip">Topological Data Analysis (TDA)</span>
      <span class="v6-chip">Deep Learning for Materials</span>
      <span class="v6-chip">Mathematical AI</span>
    </div>
  </section>

</div>

<style>
/* ======================================================
   VERSION 6 — ULTRA MODERN GLASS + SIDE ACCENT
====================================================== */

#home-v6 {
  max-width: 900px;
  margin: 2.5rem auto 4rem;
  padding: 0 1.2rem;
  font-family: "Times New Roman", Times, serif;
  position: relative;
  z-index: 1;
}

/* -------------- Accent Bar -------------- */
.v6-accent {
  position: absolute;
  left: 0;
  top: 0;
  width: 8px;
  height: 100%;
  background: linear-gradient(to bottom, #d90429, #003f88);
  border-radius: 4px;
  opacity: 0.9;
}

/* -------------- Hero Section -------------- */
.v6-hero {
  position: relative;
  display: flex;
  justify-content: center;
  padding-left: 20px;
}

.v6-hero-card {
  background: rgba(255,255,255,0.72);
  backdrop-filter: blur(14px) saturate(150%);
  padding: 2rem 2.6rem;
  border-radius: 20px;
  max-width: 620px;
  text-align: center;
  box-shadow: 0 18px 45px rgba(0,0,0,0.12);
  border: 1px solid rgba(200,200,220,0.5);
}

.v6-photo {
  width: 170px;
  height: 170px;
  border-radius: 50%;
  object-fit: cover;
  margin-bottom: 1rem;
  box-shadow: 0 10px 25px rgba(0,0,0,0.25);
  border: 3px solid rgba(255,255,255,0.8);
}

.v6-name {
  margin-top: 0.4rem;
  font-size: 2.1rem;
  color: #0f172a;
}

.v6-role {
  font-size: 1rem;
  color: #334155;
  line-height: 1.6;
  margin: 0.6rem 0 1rem;
}

.v6-contact {
  font-size: 0.92rem;
  color: #475569;
  margin-top: 0.6rem;
}

.v6-contact a {
  color: #1d4ed8;
  text-decoration: none;
}
.v6-contact a:hover {
  text-decoration: underline;
}

/* -------------- Title -------------- */
.v6-title {
  font-size: 1.35rem;
  margin-bottom: 0.7rem;
  color: #0f172a;
  border-left: 4px solid #003f88;
  padding-left: 0.7rem;
}

/* -------------- Text Blocks -------------- */
.v6-section {
  margin-top: 2.2rem;
}

.v6-text {
  font-size: 1.05rem;
  line-height: 1.75;
  color: #374151;
}

.v6-text a {
  color: #1d4ed8;
  text-decoration: none;
}
.v6-text a:hover {
  text-decoration: underline;
}

/* -------------- Interests Chips -------------- */
.v6-chips {
  display: flex;
  flex-wrap: wrap;
  gap: 0.6rem;
  margin-top: 0.8rem;
}

.v6-chip {
  padding: 0.38rem 0.75rem;
  background: rgba(0,63,136,0.08);
  border: 1px solid rgba(0,63,136,0.3);
  color: #0f172a;
  border-radius: 999px;
  font-size: 0.9rem;
}

/* -------------- Responsive -------------- */
@media (max-width: 650px) {
  .v6-hero-card {
    padding: 1.6rem 1.3rem;
  }
  .v6-photo {
    width: 140px;
    height: 140px;
  }
  .v6-name {
    font-size: 1.7rem;
  }
  .v6-text {
    font-size: 0.97rem;
  }
}
</style>
