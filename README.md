# arifcv
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Muhammad Arif Aminuddin</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Outfit:wght@300;400;500;600&display=swap" rel="stylesheet"/>
<style>
:root {
  --bg:    #0a0a0a;
  --bg2:   #111111;
  --bg3:   #1a1a1a;
  --white: #f5f5f0;
  --dim:   #888880;
  --acc:   #e8c547;
  --acc2:  #f0d060;
  --bord:  rgba(255,255,255,0.08);
}

*, *::before, *::after { margin:0; padding:0; box-sizing:border-box; }
html { scroll-behavior:smooth; }

body {
  background: var(--bg);
  color: var(--white);
  font-family: 'Outfit', sans-serif;
  font-weight: 300;
  overflow-x: hidden;
  cursor: none;
}

/* CURSOR */
.cursor {
  width: 10px; height: 10px;
  background: var(--acc);
  border-radius: 50%;
  position: fixed;
  top: 0; left: 0;
  pointer-events: none;
  z-index: 9999;
  transition: transform 0.15s ease;
  mix-blend-mode: difference;
}

.cursor-ring {
  width: 36px; height: 36px;
  border: 1px solid rgba(232,197,71,0.5);
  border-radius: 50%;
  position: fixed;
  top: 0; left: 0;
  pointer-events: none;
  z-index: 9998;
  transition: all 0.3s ease;
}

/* NAV */
nav {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 100;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 24px 48px;
  background: linear-gradient(180deg, rgba(10,10,10,0.95) 0%, transparent 100%);
}

.nav-logo {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 1.2rem;
  letter-spacing: 3px;
  color: var(--acc);
}

.nav-links {
  display: flex;
  gap: 36px;
  list-style: none;
}

.nav-links a {
  text-decoration: none;
  color: var(--dim);
  font-size: 0.82rem;
  letter-spacing: 1.5px;
  text-transform: uppercase;
  font-weight: 500;
  transition: color 0.3s;
  position: relative;
}

.nav-links a::after {
  content: '';
  position: absolute;
  bottom: -4px; left: 0;
  width: 0; height: 1px;
  background: var(--acc);
  transition: width 0.3s;
}

.nav-links a:hover { color: var(--white); }
.nav-links a:hover::after { width: 100%; }

/* HERO */
#home {
  min-height: 100vh;
  display: grid;
  grid-template-columns: 1fr 1fr;
  align-items: center;
  padding: 0 48px;
  position: relative;
  overflow: hidden;
}

#home::before {
  content: '';
  position: absolute;
  inset: 0;
  background:
    radial-gradient(ellipse 60% 80% at 70% 50%, rgba(232,197,71,0.04) 0%, transparent 70%),
    radial-gradient(ellipse 40% 40% at 20% 80%, rgba(232,197,71,0.03) 0%, transparent 60%);
  pointer-events: none;
}

/* Grid lines */
.grid-lines {
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(rgba(255,255,255,0.02) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255,255,255,0.02) 1px, transparent 1px);
  background-size: 60px 60px;
  pointer-events: none;
}

.hero-left { position: relative; z-index: 2; }

.hero-avail {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  font-size: 0.72rem;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: var(--acc);
  margin-bottom: 24px;
  opacity: 0;
  animation: fadeUp 0.8s ease 0.2s forwards;
}

.hero-avail::before {
  content: '';
  width: 7px; height: 7px;
  background: var(--acc);
  border-radius: 50%;
  animation: blink 2s ease infinite;
}

@keyframes blink {
  0%,100%{opacity:1;} 50%{opacity:0.3;}
}

.hero-name {
  font-family: 'Bebas Neue', sans-serif;
  font-size: clamp(3.5rem, 7vw, 6.5rem);
  line-height: 0.95;
  letter-spacing: 2px;
  margin-bottom: 20px;
  opacity: 0;
  animation: fadeUp 0.9s ease 0.3s forwards;
}

.hero-name span { color: var(--acc); }

.hero-desc {
  font-size: 0.95rem;
  line-height: 1.8;
  color: var(--dim);
  max-width: 420px;
  margin-bottom: 36px;
  opacity: 0;
  animation: fadeUp 0.9s ease 0.45s forwards;
}

.hero-btns {
  display: flex;
  gap: 14px;
  opacity: 0;
  animation: fadeUp 0.9s ease 0.6s forwards;
}

.btn-primary {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: var(--acc);
  color: var(--bg);
  font-family: 'Outfit', sans-serif;
  font-weight: 600;
  font-size: 0.82rem;
  letter-spacing: 1px;
  text-transform: uppercase;
  padding: 13px 28px;
  text-decoration: none;
  border: none;
  cursor: none;
  transition: all 0.3s;
}

.btn-primary:hover {
  background: var(--acc2);
  transform: translateY(-2px);
}

.btn-secondary {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: transparent;
  color: var(--white);
  font-family: 'Outfit', sans-serif;
  font-weight: 500;
  font-size: 0.82rem;
  letter-spacing: 1px;
  text-transform: uppercase;
  padding: 13px 28px;
  text-decoration: none;
  border: 1px solid var(--bord);
  cursor: none;
  transition: all 0.3s;
}

.btn-secondary:hover {
  border-color: var(--acc);
  color: var(--acc);
}

/* HERO RIGHT - PHOTO */
.hero-right {
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  z-index: 2;
  opacity: 0;
  animation: fadeIn 1.2s ease 0.5s forwards;
}

.photo-frame {
  position: relative;
  width: 340px;
  height: 420px;
}

.photo-border {
  position: absolute;
  inset: 0;
  border: 1px solid rgba(232,197,71,0.2);
  transform: translate(12px, 12px);
}

.photo-placeholder {
  width: 100%;
  height: 100%;
  background: var(--bg3);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  border: 1px solid var(--bord);
  position: relative;
  overflow: hidden;
}

.photo-placeholder::before {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(135deg, rgba(232,197,71,0.05) 0%, transparent 60%);
}

.photo-icon {
  font-size: 4rem;
  margin-bottom: 12px;
  opacity: 0.3;
}

.photo-hint {
  font-size: 0.75rem;
  color: var(--dim);
  letter-spacing: 1px;
  text-transform: uppercase;
  opacity: 0.6;
}

/* STATS BAR */
.stats-bar {
  position: absolute;
  bottom: 48px;
  left: 48px;
  right: 48px;
  display: flex;
  gap: 48px;
  padding-top: 32px;
  border-top: 1px solid var(--bord);
  opacity: 0;
  animation: fadeUp 0.9s ease 0.8s forwards;
  z-index: 2;
}

.stat-item {}
.stat-num {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 2rem;
  color: var(--acc);
  letter-spacing: 2px;
  line-height: 1;
}
.stat-label {
  font-size: 0.72rem;
  color: var(--dim);
  letter-spacing: 1.5px;
  text-transform: uppercase;
  margin-top: 2px;
}

/* SECTIONS */
section {
  padding: 100px 48px;
  position: relative;
}

.section-tag {
  font-size: 0.72rem;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: var(--acc);
  margin-bottom: 16px;
  display: flex;
  align-items: center;
  gap: 12px;
}
.section-tag::before { content:'//'; opacity:0.5; }

.section-title {
  font-family: 'Bebas Neue', sans-serif;
  font-size: clamp(2.5rem, 5vw, 4rem);
  letter-spacing: 2px;
  line-height: 1;
  margin-bottom: 60px;
}

/* ABOUT */
#about { background: var(--bg2); }

.about-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 80px;
  align-items: start;
}

.about-text {
  font-size: 1rem;
  line-height: 1.9;
  color: var(--dim);
}

.about-text p { margin-bottom: 20px; }

.about-details {}

.detail-group { margin-bottom: 28px; }
.detail-label {
  font-size: 0.68rem;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: var(--acc);
  margin-bottom: 6px;
}
.detail-value {
  font-size: 0.95rem;
  color: var(--white);
  font-weight: 500;
}

.lang-row {
  display: flex;
  gap: 20px;
  margin-top: 32px;
}

.lang-chip {
  padding: 8px 20px;
  border: 1px solid var(--bord);
  font-size: 0.8rem;
  color: var(--dim);
  transition: all 0.3s;
}

.lang-chip:hover {
  border-color: var(--acc);
  color: var(--acc);
}

/* SKILLS */
#skills { background: var(--bg); }

.skills-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
}

.skill-item {
  border: 1px solid var(--bord);
  padding: 24px;
  transition: all 0.3s;
  position: relative;
  overflow: hidden;
}

.skill-item::before {
  content: '';
  position: absolute;
  top: 0; left: 0;
  width: 3px; height: 0;
  background: var(--acc);
  transition: height 0.4s ease;
}

.skill-item:hover { border-color: rgba(232,197,71,0.2); }
.skill-item:hover::before { height: 100%; }

.skill-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 12px;
}

.skill-name {
  font-size: 0.9rem;
  font-weight: 500;
  color: var(--white);
}

.skill-pct {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 1.1rem;
  color: var(--acc);
  letter-spacing: 1px;
}

.bar-bg {
  height: 3px;
  background: var(--bg3);
}

.bar-fill {
  height: 100%;
  background: linear-gradient(90deg, var(--acc), var(--acc2));
  width: 0;
  transition: width 1.4s cubic-bezier(0.4,0,0.2,1);
}

/* EXPERIENCE */
#experience { background: var(--bg2); }

.exp-item {
  display: grid;
  grid-template-columns: 200px 1fr;
  gap: 48px;
  padding: 40px 0;
  border-bottom: 1px solid var(--bord);
}

.exp-item:first-of-type { border-top: 1px solid var(--bord); }

.exp-date {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 1rem;
  color: var(--acc);
  letter-spacing: 2px;
  padding-top: 4px;
}

.exp-title {
  font-size: 1.1rem;
  font-weight: 600;
  color: var(--white);
  margin-bottom: 8px;
}

.exp-bullets {
  list-style: none;
  margin-top: 16px;
}

.exp-bullets li {
  font-size: 0.88rem;
  color: var(--dim);
  padding: 5px 0 5px 20px;
  position: relative;
  line-height: 1.6;
}

.exp-bullets li::before {
  content: '—';
  position: absolute;
  left: 0;
  color: var(--acc);
  font-size: 0.7rem;
}

/* EDUCATION */
#education { background: var(--bg); }

.edu-list { display: flex; flex-direction: column; gap: 0; }

.edu-item {
  display: grid;
  grid-template-columns: 120px 1fr;
  gap: 32px;
  padding: 28px 0;
  border-bottom: 1px solid var(--bord);
  align-items: start;
  transition: all 0.3s;
}

.edu-item:hover .edu-title { color: var(--acc); }

.edu-year {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 1rem;
  color: var(--acc);
  letter-spacing: 2px;
  opacity: 0.7;
}

.edu-title {
  font-size: 1rem;
  font-weight: 600;
  color: var(--white);
  margin-bottom: 4px;
  transition: color 0.3s;
}

.edu-sub {
  font-size: 0.82rem;
  color: var(--dim);
}

/* HOBBIES */
#hobbies { background: var(--bg2); }

.hobby-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 16px;
}

.hobby-card {
  border: 1px solid var(--bord);
  padding: 28px 24px;
  display: flex;
  align-items: center;
  gap: 16px;
  transition: all 0.3s;
  cursor: none;
}

.hobby-card:hover {
  border-color: rgba(232,197,71,0.3);
  background: rgba(232,197,71,0.03);
  transform: translateY(-4px);
}

.hobby-icon { font-size: 1.8rem; }
.hobby-name { font-size: 0.9rem; font-weight: 500; color: var(--white); }

/* CONTACT */
#contact {
  background: var(--bg);
  text-align: center;
  padding: 120px 48px;
}

.contact-big {
  font-family: 'Bebas Neue', sans-serif;
  font-size: clamp(3rem, 8vw, 7rem);
  letter-spacing: 3px;
  line-height: 1;
  margin: 24px 0 16px;
  color: var(--white);
}

.contact-big span { color: var(--acc); }

.contact-sub {
  font-size: 0.9rem;
  color: var(--dim);
  margin-bottom: 48px;
}

.contact-info {
  display: flex;
  justify-content: center;
  gap: 40px;
  margin-top: 40px;
  flex-wrap: wrap;
}

.contact-item {
  display: flex;
  align-items: center;
  gap: 10px;
  font-size: 0.88rem;
  color: var(--dim);
}

.contact-item span:first-child { color: var(--acc); }

/* FOOTER */
footer {
  border-top: 1px solid var(--bord);
  padding: 24px 48px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.footer-text {
  font-size: 0.75rem;
  color: var(--dim);
  letter-spacing: 1px;
}

.footer-logo {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 1rem;
  letter-spacing: 3px;
  color: var(--acc);
}

/* ANIMATIONS */
@keyframes fadeUp {
  from { opacity:0; transform:translateY(24px); }
  to   { opacity:1; transform:translateY(0); }
}

@keyframes fadeIn {
  from { opacity:0; }
  to   { opacity:1; }
}

/* SCROLL REVEAL */
.reveal {
  opacity: 0;
  transform: translateY(30px);
  transition: all 0.8s cubic-bezier(0.4,0,0.2,1);
}

.reveal.visible {
  opacity: 1;
  transform: translateY(0);
}

/* RESPONSIVE */
@media (max-width: 768px) {
  nav { padding: 20px 24px; }
  .nav-links { display: none; }
  #home { grid-template-columns: 1fr; padding: 100px 24px 80px; text-align: center; }
  .hero-right { display: none; }
  .stats-bar { position: relative; bottom: auto; left: auto; right: auto; margin-top: 40px; flex-wrap: wrap; gap: 24px; padding: 24px 0 0; }
  section { padding: 70px 24px; }
  .about-grid { grid-template-columns: 1fr; gap: 40px; }
  .skills-grid { grid-template-columns: 1fr; }
  .exp-item { grid-template-columns: 1fr; gap: 12px; }
  .hobby-grid { grid-template-columns: 1fr 1fr; }
  footer { flex-direction: column; gap: 12px; text-align: center; }
  .hero-btns { justify-content: center; flex-wrap: wrap; }
}
</style>
</head>
<body>

<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<!-- NAV -->
<nav>
  <div class="nav-logo">ARIF.DEV</div>
  <ul class="nav-links">
    <li><a href="#home">Home</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#experience">Experience</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="home">
  <div class="grid-lines"></div>

  <div class="hero-left">
    <div class="hero-avail">Available for Work</div>
    <h1 class="hero-name">
      Muhammad<br/>
      <span>Arif</span><br/>
      Aminuddin
    </h1>
    <p class="hero-desc">
      A dedicated, dynamic, and adaptable individual based in Lahad Datu, Sabah.
      Strong communication skills with a fast-learning mindset — open to various roles
      and committed to delivering excellent results.
    </p>
    <div class="hero-btns">
      <a href="#contact" class="btn-primary">Get in Touch →</a>
      <a href="#about" class="btn-secondary">View Profile</a>
    </div>
  </div>

  <div class="hero-right">
    <div class="photo-frame">
      <div class="photo-border"></div>
      <div class="photo-placeholder">
        <div class="photo-icon">👤</div>
        <p class="photo-hint">Your Photo Here</p>
      </div>
    </div>
  </div>

  <div class="stats-bar">
    <div class="stat-item">
      <div class="stat-num">22</div>
      <div class="stat-label">Years Old</div>
    </div>
    <div class="stat-item">
      <div class="stat-num">01</div>
      <div class="stat-label">Year Experience</div>
    </div>
    <div class="stat-item">
      <div class="stat-num">07+</div>
      <div class="stat-label">Core Skills</div>
    </div>
    <div class="stat-item">
      <div class="stat-num">∞</div>
      <div class="stat-label">Work Readiness</div>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="section-tag">About Me</div>
  <h2 class="section-title reveal">WHO I AM</h2>

  <div class="about-grid">
    <div class="about-text reveal">
      <p>I am a dedicated, dynamic, and adaptable individual with strong communication
      and problem-solving skills. I have a high level of discipline and am a fast learner,
      which allows me to work effectively in a team or fast-paced environment.</p>
      <p>I am committed to providing excellent customer service and am willing to
      contribute professionally to ensure the smooth operation of any organization
      I am part of.</p>
      <p>My goal is to obtain a position where I can utilize my skills and grow
      professionally — I am open to various roles and industries and ready to give
      my absolute best.</p>
    </div>

    <div class="about-details reveal">
      <div class="detail-group">
        <div class="detail-label">Full Name</div>
        <div class="detail-value">Muhammad Arif Aminuddin bin Abdul Hamid</div>
      </div>
      <div class="detail-group">
        <div class="detail-label">Date of Birth</div>
        <div class="detail-value">21 September 2004</div>
      </div>
      <div class="detail-group">
        <div class="detail-label">Location</div>
        <div class="detail-value">Lahad Datu, Sabah, Malaysia</div>
      </div>
      <div class="detail-group">
        <div class="detail-label">Status</div>
        <div class="detail-value">Single</div>
      </div>
      <div class="detail-group">
        <div class="detail-label">Languages</div>
        <div class="lang-row">
          <div class="lang-chip">🇲🇾 Bahasa Malaysia</div>
          <div class="lang-chip">🇬🇧 English</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="section-tag">What I Can Do</div>
  <h2 class="section-title reveal">MY SKILLS</h2>

  <div class="skills-grid" id="skillsGrid">
    <div class="skill-item reveal">
      <div class="skill-header">
        <span class="skill-name">Communication & Teamwork</span>
        <span class="skill-pct">85%</span>
      </div>
      <div class="bar-bg"><div class="bar-fill" data-w="85"></div></div>
    </div>
    <div class="skill-item reveal">
      <div class="skill-header">
        <span class="skill-name">Customer Service</span>
        <span class="skill-pct">80%</span>
      </div>
      <div class="bar-bg"><div class="bar-fill" data-w="80"></div></div>
    </div>
    <div class="skill-item reveal">
      <div class="skill-header">
        <span class="skill-name">Problem Solving</span>
        <span class="skill-pct">75%</span>
      </div>
      <div class="bar-bg"><div class="bar-fill" data-w="75"></div></div>
    </div>
    <div class="skill-item reveal">
      <div class="skill-header">
        <span class="skill-name">Time Management</span>
        <span class="skill-pct">80%</span>
      </div>
      <div class="bar-bg"><div class="bar-fill" data-w="80"></div></div>
    </div>
    <div class="skill-item reveal">
      <div class="skill-header">
        <span class="skill-name">Microsoft Office</span>
        <span class="skill-pct">70%</span>
      </div>
      <div class="bar-bg"><div class="bar-fill" data-w="70"></div></div>
    </div>
    <div class="skill-item reveal">
      <div class="skill-header">
        <span class="skill-name">Attention to Detail</span>
        <span class="skill-pct">78%</span>
      </div>
      <div class="bar-bg"><div class="bar-fill" data-w="78"></div></div>
    </div>
    <div class="skill-item reveal">
      <div class="skill-header">
        <span class="skill-name">Safety Compliance</span>
        <span class="skill-pct">82%</span>
      </div>
      <div class="bar-bg"><div class="bar-fill" data-w="82"></div></div>
    </div>
    <div class="skill-item reveal">
      <div class="skill-header">
        <span class="skill-name">Fast Learner & Adaptable</span>
        <span class="skill-pct">90%</span>
      </div>
      <div class="bar-bg"><div class="bar-fill" data-w="90"></div></div>
    </div>
  </div>
</section>

<!-- EXPERIENCE -->
<section id="experience">
  <div class="section-tag">Career History</div>
  <h2 class="section-title reveal">EXPERIENCE</h2>

  <div class="exp-item reveal">
    <div class="exp-date">JAN 2022<br/>— MAY 2022</div>
    <div>
      <div class="exp-title">General Worker / Technical Assistant</div>
      <ul class="exp-bullets">
        <li>Assisted in maintenance and general tasks based on supervisor instructions</li>
        <li>Supported team members to complete tasks efficiently and on time</li>
        <li>Performed routine checks to ensure tools and work areas were in good condition</li>
        <li>Followed workplace safety procedures and company guidelines</li>
        <li>Demonstrated responsibility, discipline, and teamwork in daily tasks</li>
      </ul>
    </div>
  </div>
</section>

<!-- EDUCATION -->
<section id="education">
  <div class="section-tag">Academic Background</div>
  <h2 class="section-title reveal">EDUCATION</h2>

  <div class="edu-list">
    <div class="edu-item reveal">
      <div class="edu-year">2021–22</div>
      <div>
        <div class="edu-title">Certificate in Electrical Technology</div>
        <div class="edu-sub">College Community Tawau</div>
      </div>
    </div>
    <div class="edu-item reveal">
      <div class="edu-year">2020</div>
      <div>
        <div class="edu-title">Sijil Pelajaran Malaysia (SPM)</div>
        <div class="edu-sub">Secondary Education</div>
      </div>
    </div>
    <div class="edu-item reveal">
      <div class="edu-year">2019</div>
      <div>
        <div class="edu-title">Pentaksiran Tingkatan 3 (PT3)</div>
        <div class="edu-sub">Lower Secondary Assessment</div>
      </div>
    </div>
    <div class="edu-item reveal">
      <div class="edu-year">2016</div>
      <div>
        <div class="edu-title">UPSR</div>
        <div class="edu-sub">Primary School Assessment</div>
      </div>
    </div>
  </div>
</section>

<!-- HOBBIES -->
<section id="hobbies">
  <div class="section-tag">Personal Interests</div>
  <h2 class="section-title reveal">HOBBIES</h2>

  <div class="hobby-grid">
    <div class="hobby-card reveal"><div class="hobby-icon">🎮</div><div class="hobby-name">Gaming</div></div>
    <div class="hobby-card reveal"><div class="hobby-icon">⚽</div><div class="hobby-name">Football</div></div>
    <div class="hobby-card reveal"><div class="hobby-icon">🎬</div><div class="hobby-name">Watching Anime</div></div>
    <div class="hobby-card reveal"><div class="hobby-icon">📱</div><div class="hobby-name">Technology & Gadgets</div></div>
    <div class="hobby-card reveal"><div class="hobby-icon">🎵</div><div class="hobby-name">Listening to Music</div></div>
    <div class="hobby-card reveal"><div class="hobby-icon">📖</div><div class="hobby-name">Reading & Learning</div></div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="section-tag" style="justify-content:center;">Get In Touch</div>
  <div class="contact-big">LET'S<br/><span>CONNECT</span></div>
  <p class="contact-sub">Open to job opportunities — feel free to reach out!</p>
  <a href="mailto:arifaminuddin77@gmail.com" class="btn-primary" style="display:inline-flex;">
    Send Email →
  </a>

  <div class="contact-info">
    <div class="contact-item"><span>📞</span><span>012-862-4617</span></div>
    <div class="contact-item"><span>✉</span><span>arifaminuddin77@gmail.com</span></div>
    <div class="contact-item"><span>📍</span><span>Lahad Datu, Sabah</span></div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-text">© 2026 Muhammad Arif Aminuddin · All Rights Reserved</div>
  <div class="footer-logo">ARIF.DEV</div>
</footer>

<script>
  // Custom cursor
  const cursor = document.getElementById('cursor');
  const ring   = document.getElementById('cursorRing');
  let mx = 0, my = 0, rx = 0, ry = 0;

  document.addEventListener('mousemove', e => {
    mx = e.clientX; my = e.clientY;
    cursor.style.transform = `translate(${mx-5}px, ${my-5}px)`;
  });

  function animateRing() {
    rx += (mx - rx) * 0.12;
    ry += (my - ry) * 0.12;
    ring.style.transform = `translate(${rx-18}px, ${ry-18}px)`;
    requestAnimationFrame(animateRing);
  }
  animateRing();

  // Scroll reveal
  const reveals = document.querySelectorAll('.reveal');
  const obs = new IntersectionObserver(entries => {
    entries.forEach((e, i) => {
      if (e.isIntersecting) {
        setTimeout(() => e.target.classList.add('visible'), i * 80);
        obs.unobserve(e.target);
      }
    });
  }, { threshold: 0.15 });
  reveals.forEach(r => obs.observe(r));

  // Skill bars
  const barObs = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.querySelectorAll('.bar-fill').forEach(b => {
          setTimeout(() => { b.style.width = b.dataset.w + '%'; }, 300);
        });
        barObs.unobserve(e.target);
      }
    });
  }, { threshold: 0.3 });
  const sg = document.getElementById('skillsGrid');
  if (sg) barObs.observe(sg);
</script>
</body>
</html>
