---
layout: default
title: Home
last_modified_at: 2025-09-01
---

<div id="home-wrapper">

  <!-- =======================
       HERO (Vertical Layout)
  ======================== -->
  <section class="v3-hero" data-aos="zoom-in">

    <img src="/assets/images/profile.png"
         alt="Profile Photo"
         class="v3-photo" />

    <h1 class="v3-name">Mahadeb Mandal</h1>

    <p class="v3-role">Research Scholar · NTU Singapore</p>

    <p class="v3-affiliation">
      Interdisciplinary Graduate College<br>
      <strong>Nanyang Technological University</strong>
    </p>

    <div class="v3-contact">
      📍 SPMS-MAS-04-02, Table 9<br>
      📧 <a href="mailto:mahadeb001@e.ntu.edu.sg">mahadeb001@e.ntu.edu.sg</a>
    </div>

  </section>


  <!-- =======================
       ABOUT
  ======================== -->
  <section class="v3-section" data-aos="fade-up">
    <h2 class="v3-heading">About Me</h2>
    <p class="v3-text">
      Mahadeb Mandal is a second-year PhD student at 
      <strong>Nanyang Technological University (NTU), Singapore</strong>, 
      advised by 
      <a href="https://personal.ntu.edu.sg/xiakelin/index.html"><strong>Prof. Kelin Xia</strong></a>. 
      His research lies at the intersection of 
      <strong>Topological Data Analysis (TDA)</strong> 
      and <strong>Deep Learning</strong>, focused on uncovering meaningful geometric and topological 
      structures in complex datasets to enable scientific discovery and intelligent systems.
    </p>
  </section>


  <!-- =======================
       RESEARCH INTERESTS
  ======================== -->
  <section class="v3-section" data-aos="fade-up">
    <h2 class="v3-heading">Research Interests</h2>

    <div class="v3-chip-container">
      <span class="v3-chip">Topological Data Analysis (TDA)</span>
      <span class="v3-chip">Deep Learning for Materials</span>
      <span class="v3-chip">Mathematical AI</span>
    </div>
  </section>

</div>


<style>
/* -------------------------------
   GLOBAL WRAPPER
-------------------------------- */
#home-wrapper {
  max-width: 800px;
  margin: 2.2rem auto 3rem;
  padding: 0 1rem;
  font-family: "Times New Roman", Times, serif;
  position: relative;
  z-index: 1;
}

/* -------------------------------
   HERO (Vertical Glass Card)
-------------------------------- */
.v3-hero {
  text-align: center;
  padding: 2.4rem 1.5rem;
  border-radius: 22px;
  backdrop-filter: blur(18px) saturate(170%);
  background: rgba(255, 255, 255, 0.55);
  box-shadow: 0 18px 45px rgba(15, 23, 42, 0.18);
  border: 1px solid rgba(148,163,184,0.3);
  margin-bottom: 2.3rem;
  animation: fadeIn 1.2s ease-out;
}

.v3-photo {
  width: 170px;
  border-radius: 50%;
  margin-bottom: 1rem;
  border: 4px solid rgba(255,255,255,0.9);
  box-shadow: 0 10px 30px rgba(0,0,0,0.28);
}

.v3-name {
  margin: 0.5rem 0;
  font-size: 2.1rem;
  color: #0f172a;
}

.v3-role {
  font-size: 1rem;
  text-transform: uppercase;
  letter-spacing: 0.14em;
  color: #475569;
  margin-bottom: 0.5rem;
}

.v3-affiliation {
  color: #334155;
  font-size: 1.05rem;
  line-height: 1.55;
}

.v3-contact {
  margin-top: 0.8rem;
  color: #475569;
  font-size: 0.95rem;
}

.v3-contact a {
  color: #4a6bff;
  text-decoration: none;
}

/* -------------------------------
   SECTION STYLES
-------------------------------- */
.v3-section {
  margin-top: 2.3rem;
  padding: 1.6rem 1.3rem;
  border-radius: 16px;
  background: rgba(248,250,252,0.8);
  border: 1px solid rgba(148,163,184,0.35);
  box-shadow: 0 10px 28px rgba(15,23,42,0.06);
}

.v3-heading {
  margin-top: 0;
  margin-bottom: 0.9rem;
  font-size: 1.35rem;
  color: #1e293b;
  border-left: 4px solid #4a6bff;
  padding-left: 0.7rem;
}

.v3-text {
  font-size: 1.05rem;
  line-height: 1.75;
  color: #374151;
}

.v3-text a {
  color: #4a6bff;
  text-decoration: none;
}

/* -------------------------------
   INTEREST CHIPS
-------------------------------- */
.v3-chip-container {
  display: flex;
  flex-wrap: wrap;
  gap: 0.6rem;
  margin-top: 0.8rem;
}

.v3-chip {
  padding: 0.42rem 0.85rem;
  border-radius: 999px;
  background: rgba(74,107,255,0.12);
  border: 1px solid rgba(74,107,255,0.25);
  font-size: 0.9rem;
  color: #1e293b;
  transition: 0.25s ease;
}

.v3-chip:hover {
  background: #4a6bff;
  color: white;
  cursor: pointer;
}

/* -------------------------------
   WATERMARK
-------------------------------- */
body::before {
  content: "";
  position: fixed;
  top: 0;
  left: 0;
  width: 12vw;
  height: 14vh;
  background-image: url('/assets/images/ntu_logo.png');
  background-repeat: no-repeat;
  background-position: center 95%;
  background-size: 55px;
  opacity: 0.06;
  z-index: 0;
}

/* -------------------------------
   RESPONSIVE
-------------------------------- */
@media (max-width: 600px) {
  .v3-photo {
    width: 130px;
  }
  .v3-name {
    font-size: 1.65rem;
  }
  .v3-section {
    padding: 1.1rem;
  }
  .v3-text {
    font-size: 0.95rem;
  }
}
</style>
