<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ABnirob | Md. Abul Bashar Nirob</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;600;700&family=Syne:wght@400;600;700;800&display=swap');

  :root {
    --bg: #050810;
    --surface: #0b1120;
    --border: #1a2744;
    --accent1: #00d4ff;
    --accent2: #7c3aed;
    --accent3: #06ffa5;
    --accent4: #ff6b35;
    --text: #e2eaf7;
    --muted: #5a7299;
    --glow1: rgba(0,212,255,0.15);
    --glow2: rgba(124,58,237,0.15);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'JetBrains Mono', monospace;
    overflow-x: hidden;
    min-height: 100vh;
  }

  /* ── GRID BG ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,212,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,212,255,0.03) 1px, transparent 1px);
    background-size: 50px 50px;
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 900px;
    margin: 0 auto;
    padding: 60px 24px 100px;
    position: relative;
    z-index: 1;
  }

  /* ── HERO ── */
  .hero {
    text-align: center;
    margin-bottom: 72px;
    animation: fadeUp 0.8s ease both;
  }

  .avatar-ring {
    display: inline-block;
    position: relative;
    margin-bottom: 28px;
  }

  .avatar-ring::before {
    content: '';
    position: absolute;
    inset: -4px;
    border-radius: 50%;
    background: conic-gradient(var(--accent1), var(--accent2), var(--accent3), var(--accent1));
    animation: spin 4s linear infinite;
    z-index: -1;
  }

  .avatar-ring::after {
    content: '';
    position: absolute;
    inset: -12px;
    border-radius: 50%;
    background: conic-gradient(var(--accent2), transparent, var(--accent1), transparent, var(--accent2));
    animation: spin 8s linear infinite reverse;
    z-index: -2;
    opacity: 0.4;
  }

  .avatar {
    width: 110px;
    height: 110px;
    border-radius: 50%;
    background: var(--surface);
    border: 3px solid var(--bg);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 3rem;
    position: relative;
    overflow: hidden;
  }

  .avatar img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 50%;
  }

  .hero-greeting {
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.78rem;
    color: var(--accent3);
    letter-spacing: 0.3em;
    text-transform: uppercase;
    margin-bottom: 10px;
  }

  .hero-greeting::before { content: '> '; color: var(--muted); }

  .hero-name {
    font-family: 'Syne', sans-serif;
    font-size: clamp(2.2rem, 6vw, 3.6rem);
    font-weight: 800;
    line-height: 1.1;
    background: linear-gradient(135deg, var(--accent1) 0%, #a78bfa 50%, var(--accent3) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 8px;
    letter-spacing: -0.02em;
  }

  .hero-handle {
    font-size: 0.9rem;
    color: var(--muted);
    margin-bottom: 20px;
  }
  .hero-handle span { color: var(--accent1); }

  .hero-bio {
    font-size: 0.92rem;
    line-height: 1.7;
    color: #8facc7;
    max-width: 560px;
    margin: 0 auto 28px;
  }

  /* ── TYPING TAGLINE ── */
  .tagline {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 10px 18px;
    font-size: 0.82rem;
    color: var(--accent3);
    margin-bottom: 32px;
  }

  .tagline .cursor {
    width: 8px; height: 16px;
    background: var(--accent3);
    display: inline-block;
    animation: blink 1s step-end infinite;
  }

  .typed-text { min-width: 280px; text-align: left; }

  /* ── BADGES ── */
  .badge-row {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    justify-content: center;
    margin-bottom: 12px;
  }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 5px 14px;
    border-radius: 100px;
    font-size: 0.72rem;
    font-weight: 600;
    letter-spacing: 0.05em;
    border: 1px solid;
    transition: all 0.2s;
    text-decoration: none;
    cursor: default;
  }

  .badge:hover { transform: translateY(-2px); filter: brightness(1.2); }

  .badge-cyan { color: var(--accent1); border-color: rgba(0,212,255,0.3); background: rgba(0,212,255,0.05); }
  .badge-purple { color: #a78bfa; border-color: rgba(167,139,250,0.3); background: rgba(167,139,250,0.05); }
  .badge-green { color: var(--accent3); border-color: rgba(6,255,165,0.3); background: rgba(6,255,165,0.05); }
  .badge-orange { color: var(--accent4); border-color: rgba(255,107,53,0.3); background: rgba(255,107,53,0.05); }

  /* ── SECTION ── */
  .section {
    margin-bottom: 56px;
    animation: fadeUp 0.8s ease both;
  }

  .section-label {
    font-size: 0.7rem;
    letter-spacing: 0.3em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .section-label::before { content: '//'; color: var(--accent2); font-size: 0.85rem; }
  .section-label::after { content: ''; flex: 1; height: 1px; background: var(--border); }

  /* ── PIPELINE ── */
  .pipeline {
    display: flex;
    align-items: center;
    gap: 0;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 28px 32px;
    overflow-x: auto;
    position: relative;
  }

  .pipeline::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent1), var(--accent2), var(--accent3));
    border-radius: 12px 12px 0 0;
  }

  .pipe-step {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    flex: 1;
    min-width: 80px;
    position: relative;
  }

  .pipe-icon {
    width: 48px; height: 48px;
    border-radius: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.3rem;
    border: 1px solid var(--border);
    background: var(--bg);
    transition: all 0.3s;
    animation: pulseGlow 3s ease-in-out infinite;
  }

  .pipe-step:hover .pipe-icon {
    transform: scale(1.1);
    border-color: var(--accent1);
    box-shadow: 0 0 20px var(--glow1);
  }

  .pipe-step:nth-child(1) .pipe-icon { animation-delay: 0s; }
  .pipe-step:nth-child(3) .pipe-icon { animation-delay: 0.5s; }
  .pipe-step:nth-child(5) .pipe-icon { animation-delay: 1s; }
  .pipe-step:nth-child(7) .pipe-icon { animation-delay: 1.5s; }
  .pipe-step:nth-child(9) .pipe-icon { animation-delay: 2s; }

  .pipe-label {
    font-size: 0.62rem;
    color: var(--muted);
    text-align: center;
    letter-spacing: 0.05em;
    text-transform: uppercase;
  }

  .pipe-arrow {
    color: var(--border);
    font-size: 1.2rem;
    flex-shrink: 0;
    animation: flowArrow 1.5s ease-in-out infinite;
    margin: 0 4px;
    padding-bottom: 20px;
  }

  .pipe-arrow:nth-child(2) { animation-delay: 0.2s; }
  .pipe-arrow:nth-child(4) { animation-delay: 0.4s; }
  .pipe-arrow:nth-child(6) { animation-delay: 0.6s; }
  .pipe-arrow:nth-child(8) { animation-delay: 0.8s; }

  /* ── SKILLS GRID ── */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 14px;
  }

  .skill-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 18px;
    transition: all 0.25s;
    position: relative;
    overflow: hidden;
  }

  .skill-card::before {
    content: '';
    position: absolute;
    inset: 0;
    opacity: 0;
    transition: opacity 0.3s;
    pointer-events: none;
  }

  .skill-card:hover { border-color: var(--accent1); transform: translateY(-3px); box-shadow: 0 8px 32px var(--glow1); }
  .skill-card:hover::before { opacity: 1; background: radial-gradient(circle at 50% 0, var(--glow1), transparent 70%); }

  .skill-cat {
    font-size: 0.62rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    margin-bottom: 10px;
  }

  .skill-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .skill-tag {
    font-size: 0.68rem;
    padding: 3px 9px;
    background: var(--bg);
    border: 1px solid var(--border);
    border-radius: 4px;
    color: #8facc7;
  }

  /* ── PROJECTS ── */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 16px;
  }

  .project-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 22px;
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
    text-decoration: none;
    color: inherit;
    display: block;
    cursor: pointer;
  }

  .project-card::after {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent1), var(--accent2));
    transform: scaleX(0);
    transition: transform 0.3s;
    transform-origin: left;
  }

  .project-card:hover { border-color: rgba(0,212,255,0.3); transform: translateY(-4px); box-shadow: 0 16px 48px rgba(0,0,0,0.4); }
  .project-card:hover::after { transform: scaleX(1); }

  .project-emoji { font-size: 1.8rem; margin-bottom: 12px; }
  .project-name { font-family: 'Syne', sans-serif; font-size: 1rem; font-weight: 700; margin-bottom: 8px; color: var(--text); }
  .project-desc { font-size: 0.75rem; line-height: 1.6; color: var(--muted); margin-bottom: 14px; }
  .project-lang { font-size: 0.65rem; color: var(--accent3); letter-spacing: 0.1em; }

  /* ── STATS ── */
  .stats-row {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 14px;
  }

  .stat-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 22px 16px;
    text-align: center;
    transition: all 0.25s;
  }

  .stat-card:hover { border-color: var(--accent2); box-shadow: 0 0 20px var(--glow2); }

  .stat-num {
    font-family: 'Syne', sans-serif;
    font-size: 2rem;
    font-weight: 800;
    background: linear-gradient(135deg, var(--accent1), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    display: block;
    line-height: 1;
    margin-bottom: 6px;
  }

  .stat-label { font-size: 0.65rem; color: var(--muted); letter-spacing: 0.1em; text-transform: uppercase; }

  /* ── CONNECT ── */
  .connect-row {
    display: flex;
    gap: 12px;
    flex-wrap: wrap;
  }

  .connect-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 10px 20px;
    border-radius: 8px;
    font-size: 0.78rem;
    font-family: 'JetBrains Mono', monospace;
    font-weight: 600;
    text-decoration: none;
    border: 1px solid;
    transition: all 0.2s;
    cursor: pointer;
  }

  .connect-btn:hover { transform: translateY(-2px); filter: brightness(1.15); }

  .btn-github { color: var(--text); border-color: var(--border); background: var(--surface); }
  .btn-github:hover { border-color: var(--text); }
  .btn-linkedin { color: #60a5fa; border-color: rgba(96,165,250,0.3); background: rgba(96,165,250,0.05); }
  .btn-linkedin:hover { border-color: #60a5fa; box-shadow: 0 0 16px rgba(96,165,250,0.2); }
  .btn-fb { color: #818cf8; border-color: rgba(129,140,248,0.3); background: rgba(129,140,248,0.05); }
  .btn-fb:hover { border-color: #818cf8; box-shadow: 0 0 16px rgba(129,140,248,0.2); }

  /* ── FOOTER ── */
  .footer {
    text-align: center;
    margin-top: 72px;
    padding-top: 32px;
    border-top: 1px solid var(--border);
    font-size: 0.72rem;
    color: var(--muted);
    line-height: 2;
  }

  .footer span { color: var(--accent1); }

  /* ── DATA FLOW VISUAL ── */
  .data-flow {
    position: relative;
    height: 5px;
    background: var(--border);
    border-radius: 10px;
    margin: 8px 0 0;
    overflow: hidden;
  }

  .data-flow::after {
    content: '';
    position: absolute;
    top: 0; left: -40%;
    width: 40%; height: 100%;
    background: linear-gradient(90deg, transparent, var(--accent1), var(--accent3), transparent);
    animation: flow 2s linear infinite;
  }

  /* ── LOCATION TAG ── */
  .location-tag {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-size: 0.75rem;
    color: var(--muted);
    margin-bottom: 32px;
  }

  .location-dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--accent3);
    animation: blink 2s ease-in-out infinite;
  }

  /* ── NSU TAG ── */
  .nsu-tag {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(124,58,237,0.1);
    border: 1px solid rgba(124,58,237,0.3);
    border-radius: 6px;
    padding: 6px 14px;
    font-size: 0.72rem;
    color: #a78bfa;
    margin-bottom: 24px;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to { opacity: 1; transform: translateY(0); }
  }

  @keyframes spin {
    to { transform: rotate(360deg); }
  }

  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0; }
  }

  @keyframes pulseGlow {
    0%, 100% { box-shadow: 0 0 0 rgba(0,212,255,0); }
    50% { box-shadow: 0 0 16px rgba(0,212,255,0.2); }
  }

  @keyframes flowArrow {
    0%, 100% { color: var(--border); }
    50% { color: var(--accent1); }
  }

  @keyframes flow {
    to { left: 140%; }
  }

  .section:nth-child(2) { animation-delay: 0.1s; }
  .section:nth-child(3) { animation-delay: 0.2s; }
  .section:nth-child(4) { animation-delay: 0.3s; }
  .section:nth-child(5) { animation-delay: 0.4s; }
  .section:nth-child(6) { animation-delay: 0.5s; }

  /* ── SCROLL FADE IN ── */
  .fade-in {
    opacity: 0;
    transform: translateY(20px);
    transition: opacity 0.6s ease, transform 0.6s ease;
  }
  .fade-in.visible {
    opacity: 1;
    transform: none;
  }

  /* ── CURRENTLY LEARNING BAR ── */
  .learning-bar {
    display: flex;
    align-items: center;
    gap: 16px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-left: 3px solid var(--accent3);
    border-radius: 0 8px 8px 0;
    padding: 14px 20px;
    margin-bottom: 14px;
    font-size: 0.78rem;
  }

  .learning-label { color: var(--accent3); font-weight: 600; flex-shrink: 0; font-size: 0.68rem; letter-spacing: 0.1em; text-transform: uppercase; }
  .learning-text { color: #8facc7; }

  /* ── COMPANY ── */
  .company-tag {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-size: 0.75rem;
    color: var(--accent4);
    background: rgba(255,107,53,0.08);
    border: 1px solid rgba(255,107,53,0.2);
    border-radius: 5px;
    padding: 4px 12px;
    margin-bottom: 20px;
  }
</style>
</head>
<body>

<div class="container">

  <!-- HERO -->
  <div class="hero">
    <div class="avatar-ring">
      <div class="avatar">
        <img src="https://avatars.githubusercontent.com/u/88394238?v=4" alt="ABnirob" onerror="this.style.display='none';this.parentNode.innerHTML='👨‍💻'">
      </div>
    </div>

    <div class="hero-greeting">Hello, World!</div>
    <h1 class="hero-name">Md. Abul Bashar Nirob</h1>
    <div class="hero-handle"><span>@ABnirob</span> · Data Enthusiast & CSE Student</div>

    <div class="nsu-tag">
      🎓 BSc in Computer Science & Engineering · North South University, Dhaka
    </div>

    <div class="company-tag">
      🏢 TrillionData · Bashundhara RA, Dhaka, Bangladesh
    </div>

    <div class="tagline">
      <span style="color:var(--muted)">$</span>
      <span class="typed-text" id="typed"></span>
      <span class="cursor"></span>
    </div>

    <div class="location-tag">
      <span class="location-dot"></span>
      Dhaka, Bangladesh &nbsp;·&nbsp; UTC+6
    </div>

    <div class="badge-row">
      <span class="badge badge-cyan">🐍 Python</span>
      <span class="badge badge-purple">📊 Data Analysis</span>
      <span class="badge badge-green">⚡ Excel Dashboards</span>
      <span class="badge badge-orange">🌐 React · TypeScript</span>
      <span class="badge badge-cyan">🗄️ Supabase</span>
      <span class="badge badge-purple">📈 Business Intelligence</span>
    </div>
  </div>

  <!-- DATA PIPELINE -->
  <div class="section fade-in">
    <div class="section-label">data pipeline</div>
    <div class="pipeline">
      <div class="pipe-step">
        <div class="pipe-icon">🗃️</div>
        <div class="pipe-label">Raw Data</div>
      </div>
      <div class="pipe-arrow">→</div>
      <div class="pipe-step">
        <div class="pipe-icon">🧹</div>
        <div class="pipe-label">Clean</div>
      </div>
      <div class="pipe-arrow">→</div>
      <div class="pipe-step">
        <div class="pipe-icon">🔄</div>
        <div class="pipe-label">Transform</div>
      </div>
      <div class="pipe-arrow">→</div>
      <div class="pipe-step">
        <div class="pipe-icon">📊</div>
        <div class="pipe-label">Analyze</div>
      </div>
      <div class="pipe-arrow">→</div>
      <div class="pipe-step">
        <div class="pipe-icon">🚀</div>
        <div class="pipe-label">Insights</div>
      </div>
    </div>
    <div class="data-flow" style="margin-top:2px;border-radius:0 0 10px 10px;height:3px;"></div>
  </div>

  <!-- STATS -->
  <div class="section fade-in">
    <div class="section-label">by the numbers</div>
    <div class="stats-row">
      <div class="stat-card">
        <span class="stat-num">10</span>
        <div class="stat-label">Repositories</div>
      </div>
      <div class="stat-card">
        <span class="stat-num">2+</span>
        <div class="stat-label">Data Projects</div>
      </div>
      <div class="stat-card">
        <span class="stat-num">∞</span>
        <div class="stat-label">Lines to Write</div>
      </div>
    </div>
  </div>

  <!-- SKILLS -->
  <div class="section fade-in">
    <div class="section-label">tech stack</div>

    <div class="learning-bar">
      <span class="learning-label">🔥 Learning</span>
      <span class="learning-text">Data Engineering · Pipeline Architecture · Advanced SQL · Cloud Data Warehousing</span>
    </div>

    <div class="skills-grid">
      <div class="skill-card">
        <div class="skill-cat" style="color:var(--accent3)">📊 Data & Analytics</div>
        <div class="skill-tags">
          <span class="skill-tag">Python</span>
          <span class="skill-tag">Excel</span>
          <span class="skill-tag">Pivot Tables</span>
          <span class="skill-tag">Matplotlib</span>
          <span class="skill-tag">Pandas</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-cat" style="color:var(--accent1)">🌐 Web Development</div>
        <div class="skill-tags">
          <span class="skill-tag">React 18</span>
          <span class="skill-tag">TypeScript</span>
          <span class="skill-tag">Vite</span>
          <span class="skill-tag">Tailwind CSS</span>
          <span class="skill-tag">HTML/CSS</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-cat" style="color:var(--accent2)">🗄️ Backend & DB</div>
        <div class="skill-tags">
          <span class="skill-tag">Supabase</span>
          <span class="skill-tag">Laravel</span>
          <span class="skill-tag">React Query</span>
          <span class="skill-tag">React Router</span>
        </div>
      </div>
      <div class="skill-card">
        <div class="skill-cat" style="color:var(--accent4)">🛠️ Tools</div>
        <div class="skill-tags">
          <span class="skill-tag">Git</span>
          <span class="skill-tag">GitHub</span>
          <span class="skill-tag">VS Code</span>
          <span class="skill-tag">Zod</span>
          <span class="skill-tag">shadcn/ui</span>
        </div>
      </div>
    </div>
  </div>

  <!-- PROJECTS -->
  <div class="section fade-in">
    <div class="section-label">featured projects</div>
    <div class="projects-grid">
      <div class="project-card" onclick="window.open('https://github.com/ABnirob/Car-Sales-Profit-Analysis-Dashboard-SwiftAuto-Traders-','_blank')">
        <div class="project-emoji">🚗</div>
        <div class="project-name">SwiftAuto Sales Dashboard</div>
        <div class="project-desc">Analyzes historical car sales & profit data for a multi-dealer automotive company. Built interactive Excel dashboards revealing dealer efficiency and profitability trends.</div>
        <div class="project-lang">Python · Excel · HTML · Data Viz</div>
      </div>
      <div class="project-card" onclick="window.open('https://github.com/ABnirob/seismarch_frontend','_blank')">
        <div class="project-emoji">🏗️</div>
        <div class="project-name">SeismArch Frontend</div>
        <div class="project-desc">Luxury construction company website with a black & gold design aesthetic. Full admin CRUD capabilities powered by Supabase, React 18, and TypeScript.</div>
        <div class="project-lang">React · TypeScript · Supabase · Tailwind</div>
      </div>
      <div class="project-card" onclick="window.open('https://github.com/ABnirob/TourOn','_blank')">
        <div class="project-emoji">✈️</div>
        <div class="project-name">TourOn</div>
        <div class="project-desc">A tour and travel agency management system — handling bookings, destinations, and client data with a clean user interface.</div>
        <div class="project-lang">HTML · Web Development</div>
      </div>
    </div>
  </div>

  <!-- CONNECT -->
  <div class="section fade-in">
    <div class="section-label">let's connect</div>
    <div class="connect-row">
      <a class="connect-btn btn-github" href="https://github.com/ABnirob" target="_blank">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0024 12c0-6.63-5.37-12-12-12z"/></svg>
        GitHub
      </a>
      <a class="connect-btn btn-linkedin" href="https://linkedin.com/in/md-abul-bashar-nirob" target="_blank">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
        LinkedIn
      </a>
      <a class="connect-btn btn-fb" href="https://www.facebook.com/ab.nirob.7" target="_blank">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/></svg>
        Facebook
      </a>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer fade-in">
    <div>⚡ Transforming raw data into actionable insights · One pipeline at a time</div>
    <div style="margin-top:8px">Built with <span>❤️</span> in Dhaka · <span>@ABnirob</span> · North South University</div>
    <div style="margin-top:12px; font-size:0.6rem; letter-spacing:0.2em; text-transform:uppercase; color:#2a3e5e">
      data · code · learn · build · repeat
    </div>
  </div>

</div>

<script>
  // Typing animation
  const phrases = [
    'turning data into decisions',
    'building data pipelines',
    'CSE @ North South University',
    'analyzing & visualizing data',
    'learning every single day',
  ];
  let pi = 0, ci = 0, deleting = false;
  const el = document.getElementById('typed');

  function type() {
    const current = phrases[pi];
    if (!deleting) {
      el.textContent = current.slice(0, ++ci);
      if (ci === current.length) {
        deleting = true;
        setTimeout(type, 1800);
        return;
      }
    } else {
      el.textContent = current.slice(0, --ci);
      if (ci === 0) {
        deleting = false;
        pi = (pi + 1) % phrases.length;
      }
    }
    setTimeout(type, deleting ? 40 : 70);
  }
  type();

  // Scroll fade-in
  const obs = new IntersectionObserver((entries) => {
    entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('visible'); });
  }, { threshold: 0.1 });

  document.querySelectorAll('.fade-in').forEach(el => obs.observe(el));
</script>
</body>
</html>
