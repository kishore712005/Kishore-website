<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>C. Kishore – AI & Data Science</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Space+Grotesk:wght@400;600;700&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg:        #0D1117;
      --surface:   #161B22;
      --card:      #1C2330;
      --accent:    #2F81F7;
      --accent2:   #58A6FF;
      --green:     #3FB950;
      --text:      #E6EDF3;
      --muted:     #8B949E;
      --border:    #30363D;
      --tag-bg:    #1F2D3D;
      --font-head: 'Space Grotesk', sans-serif;
      --font-body: 'Inter', sans-serif;
    }

    html { scroll-behavior: smooth; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: var(--font-body);
      font-size: 15px;
      line-height: 1.6;
      min-height: 100vh;
    }

    /* ── NAV ── */
    nav {
      position: fixed; top: 0; left: 0; right: 0;
      background: rgba(13,17,23,0.85);
      backdrop-filter: blur(12px);
      border-bottom: 1px solid var(--border);
      z-index: 100;
      display: flex; justify-content: space-between; align-items: center;
      padding: 0 5%;
      height: 56px;
    }
    .nav-logo {
      font-family: var(--font-head);
      font-weight: 700;
      font-size: 18px;
      color: var(--accent2);
      letter-spacing: -0.5px;
    }
    .nav-links { display: flex; gap: 28px; }
    .nav-links a {
      color: var(--muted);
      text-decoration: none;
      font-size: 13px;
      font-weight: 500;
      letter-spacing: 0.3px;
      transition: color 0.2s;
    }
    .nav-links a:hover { color: var(--text); }

    /* ── HERO ── */
    .hero {
      min-height: 100vh;
      display: flex; flex-direction: column;
      justify-content: center; align-items: center;
      text-align: center;
      padding: 80px 5% 60px;
      position: relative;
      overflow: hidden;
    }
    .hero::before {
      content: '';
      position: absolute;
      top: -200px; left: 50%; transform: translateX(-50%);
      width: 700px; height: 700px;
      background: radial-gradient(circle, rgba(47,129,247,0.12) 0%, transparent 70%);
      pointer-events: none;
    }
    .hero-badge {
      display: inline-flex; align-items: center; gap: 8px;
      background: var(--tag-bg);
      border: 1px solid var(--border);
      border-radius: 100px;
      padding: 5px 16px;
      font-size: 12px;
      color: var(--green);
      font-weight: 500;
      margin-bottom: 28px;
      letter-spacing: 0.5px;
    }
    .hero-badge::before {
      content: '';
      width: 7px; height: 7px;
      border-radius: 50%;
      background: var(--green);
      animation: pulse 2s infinite;
    }
    @keyframes pulse {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.4; }
    }
    .hero h1 {
      font-family: var(--font-head);
      font-size: clamp(40px, 8vw, 72px);
      font-weight: 700;
      letter-spacing: -2px;
      line-height: 1.05;
      margin-bottom: 16px;
    }
    .hero h1 span { color: var(--accent2); }
    .hero-sub {
      font-size: clamp(15px, 2vw, 18px);
      color: var(--muted);
      max-width: 480px;
      margin: 0 auto 36px;
      font-weight: 400;
    }
    .contact-row {
      display: flex; flex-wrap: wrap;
      justify-content: center; gap: 12px;
      margin-bottom: 40px;
    }
    .contact-chip {
      display: inline-flex; align-items: center; gap: 7px;
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 8px 16px;
      font-size: 13px;
      color: var(--text);
      text-decoration: none;
      transition: border-color 0.2s, background 0.2s;
    }
    .contact-chip:hover {
      border-color: var(--accent);
      background: var(--tag-bg);
    }
    .contact-chip svg { width: 15px; height: 15px; flex-shrink: 0; }
    .hero-cta {
      display: inline-flex; align-items: center; gap: 8px;
      background: var(--accent);
      color: #fff;
      font-weight: 600;
      font-size: 14px;
      padding: 11px 28px;
      border-radius: 8px;
      text-decoration: none;
      transition: background 0.2s, transform 0.15s;
    }
    .hero-cta:hover { background: var(--accent2); transform: translateY(-1px); }

    /* ── MAIN LAYOUT ── */
    main {
      max-width: 900px;
      margin: 0 auto;
      padding: 0 5% 80px;
    }

    /* ── SECTION ── */
    section { margin-bottom: 64px; }
    .section-label {
      display: flex; align-items: center; gap: 12px;
      margin-bottom: 28px;
    }
    .section-label span {
      font-family: var(--font-head);
      font-size: 11px;
      font-weight: 600;
      letter-spacing: 2px;
      color: var(--accent);
      text-transform: uppercase;
    }
    .section-label::after {
      content: '';
      flex: 1;
      height: 1px;
      background: var(--border);
    }

    /* ── ABOUT ── */
    .about-text {
      font-size: 16px;
      color: var(--muted);
      line-height: 1.8;
      max-width: 680px;
      border-left: 3px solid var(--accent);
      padding-left: 20px;
    }

    /* ── EDUCATION ── */
    .timeline { display: flex; flex-direction: column; gap: 16px; }
    .timeline-item {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 20px 24px;
      display: flex; justify-content: space-between; align-items: flex-start;
      gap: 16px;
      transition: border-color 0.2s;
    }
    .timeline-item:hover { border-color: var(--accent); }
    .timeline-item .degree {
      font-family: var(--font-head);
      font-weight: 600;
      font-size: 15px;
      color: var(--text);
      margin-bottom: 4px;
    }
    .timeline-item .school {
      font-size: 13px;
      color: var(--muted);
    }
    .timeline-item .year {
      font-size: 12px;
      font-weight: 600;
      color: var(--accent2);
      white-space: nowrap;
      background: var(--tag-bg);
      border: 1px solid var(--border);
      border-radius: 6px;
      padding: 4px 10px;
    }

    /* ── CERTIFICATES ── */
    .cert-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(260px, 1fr)); gap: 16px; }
    .cert-card {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 20px;
      transition: border-color 0.2s, transform 0.15s;
    }
    .cert-card:hover { border-color: var(--green); transform: translateY(-2px); }
    .cert-issuer {
      font-size: 11px;
      font-weight: 600;
      letter-spacing: 1.5px;
      color: var(--green);
      text-transform: uppercase;
      margin-bottom: 8px;
    }
    .cert-name {
      font-family: var(--font-head);
      font-size: 15px;
      font-weight: 600;
      color: var(--text);
      margin-bottom: 6px;
    }
    .cert-year {
      font-size: 12px;
      color: var(--muted);
    }

    /* ── SKILLS ── */
    .skills-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(220px, 1fr)); gap: 16px; }
    .skill-group {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 20px;
    }
    .skill-group-title {
      font-size: 11px;
      font-weight: 600;
      letter-spacing: 1.5px;
      color: var(--accent);
      text-transform: uppercase;
      margin-bottom: 12px;
    }
    .skill-tags { display: flex; flex-wrap: wrap; gap: 8px; }
    .skill-tag {
      background: var(--tag-bg);
      border: 1px solid var(--border);
      border-radius: 6px;
      padding: 4px 10px;
      font-size: 12px;
      font-weight: 500;
      color: var(--text);
    }

    /* ── PROJECTS ── */
    .project-card {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 12px;
      padding: 24px;
      transition: border-color 0.2s;
    }
    .project-card:hover { border-color: var(--accent2); }
    .project-top {
      display: flex; justify-content: space-between; align-items: flex-start;
      margin-bottom: 10px;
    }
    .project-title {
      font-family: var(--font-head);
      font-size: 17px;
      font-weight: 600;
      color: var(--text);
    }
    .project-link {
      display: inline-flex; align-items: center; gap: 5px;
      color: var(--accent2);
      font-size: 12px;
      font-weight: 500;
      text-decoration: none;
      transition: color 0.2s;
    }
    .project-link:hover { color: var(--text); }
    .project-desc {
      font-size: 14px;
      color: var(--muted);
      line-height: 1.7;
    }

    /* ── PERSONAL ── */
    .personal-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); gap: 12px; }
    .personal-item {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 14px 18px;
    }
    .personal-item .p-label {
      font-size: 11px;
      color: var(--muted);
      text-transform: uppercase;
      letter-spacing: 1px;
      margin-bottom: 4px;
    }
    .personal-item .p-value {
      font-size: 14px;
      font-weight: 500;
      color: var(--text);
    }

    /* ── DECLARATION ── */
    .declaration {
      background: var(--card);
      border: 1px solid var(--border);
      border-left: 3px solid var(--accent);
      border-radius: 0 12px 12px 0;
      padding: 20px 24px;
      font-size: 14px;
      color: var(--muted);
      line-height: 1.7;
    }
    .declaration strong { color: var(--text); display: block; margin-top: 16px; font-size: 15px; }

    /* ── FOOTER ── */
    footer {
      text-align: center;
      border-top: 1px solid var(--border);
      padding: 28px 5%;
      font-size: 12px;
      color: var(--muted);
    }
    footer a { color: var(--accent2); text-decoration: none; }

    /* ── RESPONSIVE ── */
    @media (max-width: 600px) {
      .nav-links { display: none; }
      .timeline-item { flex-direction: column; }
      .project-top { flex-direction: column; gap: 8px; }
    }

    /* ── PRINT ── */
    @media print {
      nav, .hero-cta { display: none; }
      body { background: #fff; color: #000; }
      .card, .timeline-item, .cert-card, .skill-group, .project-card, .personal-item { border: 1px solid #ccc; }
    }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">kishore.dev</div>
  <div class="nav-links">
    <a href="#about">About</a>
    <a href="#education">Education</a>
    <a href="#certifications">Certifications</a>
    <a href="#skills">Skills</a>
    <a href="#projects">Projects</a>
    <a href="#contact">Contact</a>
  </div>
</nav>

<!-- HERO -->
<header class="hero">
  <div class="hero-badge">Open to Internships &amp; Opportunities</div>
  <h1>C. <span>Kishore</span></h1>
  <p class="hero-sub">B.Tech in Artificial Intelligence &amp; Data Science · JCT Institutions, Coimbatore</p>

  <div class="contact-row" id="contact">
    <a class="contact-chip" href="tel:8637414217">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.92v3a2 2 0 01-2.18 2 19.79 19.79 0 01-8.63-3.07A19.5 19.5 0 013.07 9.81 19.79 19.79 0 01.22 1.18 2 2 0 012.18 0h3a2 2 0 012 1.72c.127.96.361 1.903.7 2.81a2 2 0 01-.45 2.11L6.91 7.91a16 16 0 006.29 6.29l1.28-1.28a2 2 0 012.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0122 16.92z"/></svg>
      8637414217
    </a>
    <a class="contact-chip" href="mailto:kishore712005@gmail.com">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
      kishore712005@gmail.com
    </a>
    <a class="contact-chip" href="https://github.com/kishore712005" target="_blank" rel="noopener">
      <svg viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"/></svg>
      github.com/kishore712005
    </a>
    <a class="contact-chip" href="#">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0118 0z"/><circle cx="12" cy="10" r="3"/></svg>
      Coimbatore – 642109
    </a>
  </div>

  <a class="hero-cta" href="https://github.com/kishore712005/Kishore-website" target="_blank" rel="noopener">
    <svg width="15" height="15" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"/></svg>
    View on GitHub
  </a>
</header>

<!-- MAIN -->
<main>

  <!-- ABOUT -->
  <section id="about">
    <div class="section-label"><span>About</span></div>
    <p class="about-text">
      I'm a B.Tech student specialising in Artificial Intelligence &amp; Data Science at JCT Institutions, Coimbatore. I enjoy building software-oriented solutions and exploring system-level work. Currently expanding my skills through NPTEL certifications and hands-on projects in Python and data science.
    </p>
  </section>

  <!-- EDUCATION -->
  <section id="education">
    <div class="section-label"><span>Education</span></div>
    <div class="timeline">
      <div class="timeline-item">
        <div>
          <div class="degree">B.Tech – Artificial Intelligence &amp; Data Science</div>
          <div class="school">JCT Institutions, Coimbatore</div>
        </div>
        <div class="year">2023 – Present</div>
      </div>
      <div class="timeline-item">
        <div>
          <div class="degree">Higher Secondary (12th)</div>
          <div class="school">TMT. Rukmaniyammal Hr. Sec. School</div>
        </div>
        <div class="year">2023 · 69%</div>
      </div>
    </div>
  </section>

  <!-- CERTIFICATIONS -->
  <section id="certifications">
    <div class="section-label"><span>Certifications</span></div>
    <div class="cert-grid">
      <div class="cert-card">
        <div class="cert-issuer">NPTEL</div>
        <div class="cert-name">Python for Data Science</div>
        <div class="cert-year">2025 – 26 · 3rd Year B.Tech</div>
      </div>
      <div class="cert-card">
        <div class="cert-issuer">DCA</div>
        <div class="cert-name">Programming in C &amp; C++</div>
        <div class="cert-year">Diploma in Computer Applications</div>
      </div>
    </div>
  </section>

  <!-- SKILLS -->
  <section id="skills">
    <div class="section-label"><span>Skills</span></div>
    <div class="skills-grid">
      <div class="skill-group">
        <div class="skill-group-title">Languages</div>
        <div class="skill-tags">
          <span class="skill-tag">Python</span>
          <span class="skill-tag">C</span>
          <span class="skill-tag">C++</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Tools &amp; Software</div>
        <div class="skill-tags">
          <span class="skill-tag">MS Office</span>
          <span class="skill-tag">MS DOS</span>
          <span class="skill-tag">Microsoft Word</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Interests</div>
        <div class="skill-tags">
          <span class="skill-tag">Data Science</span>
          <span class="skill-tag">System Programming</span>
          <span class="skill-tag">Software Dev</span>
        </div>
      </div>
      <div class="skill-group">
        <div class="skill-group-title">Soft Skills</div>
        <div class="skill-tags">
          <span class="skill-tag">Optimistic</span>
          <span class="skill-tag">Adaptability</span>
          <span class="skill-tag">Communication</span>
        </div>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section id="projects">
    <div class="section-label"><span>Projects</span></div>
    <div class="project-card">
      <div class="project-top">
        <div class="project-title">Personal Portfolio Website</div>
        <a class="project-link" href="https://github.com/kishore712005/Kishore-website" target="_blank" rel="noopener">
          <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M18 13v6a2 2 0 01-2 2H5a2 2 0 01-2-2V8a2 2 0 012-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>
          View on GitHub
        </a>
      </div>
      <p class="project-desc">A personal website hosted on GitHub showcasing my profile, skills, and background. Built with HTML/CSS as part of learning frontend web development.</p>
    </div>
  </section>

  <!-- PERSONAL -->
  <section id="personal">
    <div class="section-label"><span>Personal Details</span></div>
    <div class="personal-grid">
      <div class="personal-item">
        <div class="p-label">Full Name</div>
        <div class="p-value">C. Kishore</div>
      </div>
      <div class="personal-item">
        <div class="p-label">Date of Birth</div>
        <div class="p-value">07 December 2005</div>
      </div>
      <div class="personal-item">
        <div class="p-label">Nationality</div>
        <div class="p-value">Indian</div>
      </div>
      <div class="personal-item">
        <div class="p-label">Languages</div>
        <div class="p-value">English, Tamil</div>
      </div>
      <div class="personal-item">
        <div class="p-label">Location</div>
        <div class="p-value">Coimbatore – 642109</div>
      </div>
      <div class="personal-item">
        <div class="p-label">Hobbies</div>
        <div class="p-value">Learning New Things, Travelling</div>
      </div>
    </div>
  </section>

  <!-- DECLARATION -->
  <section>
    <div class="section-label"><span>Declaration</span></div>
    <div class="declaration">
      I hereby declare that the information and facts stated above are true, correct, and complete to the best of my knowledge and belief.
      <strong>C. Kishore &nbsp;·&nbsp; Coimbatore</strong>
    </div>
  </section>

</main>

<!-- FOOTER -->
<footer>
  <p>Designed &amp; built by <a href="https://github.com/kishore712005" target="_blank">C. Kishore</a> · Hosted on GitHub Pages</p>
</footer>

</body>
</html>

