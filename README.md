<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Ahmed Ayman Elsawy — AI Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&family=DM+Mono:wght@300;400;500&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #080c14;
    --bg-card: #0e1520;
    --bg-card2: #121b2a;
    --accent: #00e5ff;
    --accent2: #7c6af7;
    --accent3: #39ff8a;
    --text: #e8eef8;
    --text-muted: #7a8fa8;
    --text-dim: #3d5068;
    --border: rgba(0,229,255,0.12);
    --border2: rgba(255,255,255,0.06);
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    font-size: 16px;
    line-height: 1.7;
    overflow-x: hidden;
  }

  ::selection { background: var(--accent); color: var(--bg); }

  /* Scrollbar */
  ::-webkit-scrollbar { width: 4px; }
  ::-webkit-scrollbar-track { background: var(--bg); }
  ::-webkit-scrollbar-thumb { background: var(--accent); border-radius: 2px; }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 1.2rem 4rem;
    background: rgba(8,12,20,0.85);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid var(--border2);
    transition: all 0.3s;
  }
  .nav-logo {
    font-family: 'DM Mono', monospace;
    font-size: 0.85rem;
    color: var(--accent);
    letter-spacing: 0.15em;
    text-transform: uppercase;
  }
  .nav-links { display: flex; gap: 2.5rem; list-style: none; }
  .nav-links a {
    font-size: 0.78rem;
    font-weight: 500;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--text-muted);
    text-decoration: none;
    transition: color 0.2s;
    position: relative;
  }
  .nav-links a::after {
    content: '';
    position: absolute; bottom: -4px; left: 0; right: 0;
    height: 1px; background: var(--accent);
    transform: scaleX(0); transition: transform 0.2s;
  }
  .nav-links a:hover { color: var(--accent); }
  .nav-links a:hover::after { transform: scaleX(1); }

  /* ── HERO ── */
  #hero {
    min-height: 100vh;
    display: flex; align-items: center;
    padding: 8rem 4rem 4rem;
    position: relative;
    overflow: hidden;
  }

  .hero-bg {
    position: absolute; inset: 0; pointer-events: none;
    background:
      radial-gradient(ellipse 60% 50% at 70% 40%, rgba(0,229,255,0.06) 0%, transparent 70%),
      radial-gradient(ellipse 40% 60% at 20% 80%, rgba(124,106,247,0.07) 0%, transparent 60%);
  }
  .hero-grid {
    position: absolute; inset: 0; pointer-events: none;
    background-image:
      linear-gradient(rgba(0,229,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,229,255,0.03) 1px, transparent 1px);
    background-size: 60px 60px;
    mask-image: radial-gradient(ellipse 80% 60% at 50% 50%, black, transparent);
  }

  .hero-content { position: relative; max-width: 1200px; width: 100%; }
  .hero-tag {
    display: inline-flex; align-items: center; gap: 0.6rem;
    font-family: 'DM Mono', monospace;
    font-size: 0.72rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--accent);
    border: 1px solid rgba(0,229,255,0.3);
    padding: 0.4rem 1rem;
    border-radius: 2rem;
    margin-bottom: 2rem;
    animation: fadeUp 0.8s ease both;
  }
  .hero-tag::before {
    content: '';
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--accent);
    animation: pulse 2s ease infinite;
  }
  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.4; transform: scale(0.7); }
  }

  .hero-name {
    font-family: 'Playfair Display', serif;
    font-size: clamp(3.5rem, 8vw, 7rem);
    font-weight: 900;
    line-height: 0.95;
    letter-spacing: -0.02em;
    margin-bottom: 0.2rem;
    animation: fadeUp 0.8s 0.1s ease both;
  }
  .hero-name span { color: var(--accent); display: block; }

  .hero-title {
    font-family: 'DM Mono', monospace;
    font-size: clamp(0.9rem, 2vw, 1.15rem);
    color: var(--text-muted);
    letter-spacing: 0.08em;
    margin-bottom: 2rem;
    animation: fadeUp 0.8s 0.2s ease both;
  }

  .hero-desc {
    max-width: 560px;
    font-size: 1.05rem;
    color: var(--text-muted);
    line-height: 1.8;
    margin-bottom: 3rem;
    animation: fadeUp 0.8s 0.3s ease both;
  }
  .hero-desc strong { color: var(--text); font-weight: 500; }

  .hero-cta {
    display: flex; gap: 1rem; flex-wrap: wrap;
    animation: fadeUp 0.8s 0.4s ease both;
  }
  .btn {
    display: inline-flex; align-items: center; gap: 0.5rem;
    padding: 0.85rem 2rem;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.85rem;
    font-weight: 500;
    letter-spacing: 0.08em;
    text-decoration: none;
    border-radius: 4px;
    transition: all 0.2s;
    cursor: pointer;
    border: none;
  }
  .btn-primary {
    background: var(--accent);
    color: var(--bg);
  }
  .btn-primary:hover { background: #33eaff; transform: translateY(-2px); box-shadow: 0 8px 24px rgba(0,229,255,0.25); }
  .btn-outline {
    background: transparent;
    color: var(--text);
    border: 1px solid var(--border2);
  }
  .btn-outline:hover { border-color: var(--accent); color: var(--accent); transform: translateY(-2px); }

  .hero-stats {
    position: absolute; right: 0; top: 50%;
    transform: translateY(-50%);
    display: flex; flex-direction: column; gap: 1.5rem;
    animation: fadeLeft 0.8s 0.5s ease both;
  }
  .stat-item {
    text-align: right;
    border-right: 2px solid var(--accent);
    padding-right: 1.5rem;
  }
  .stat-num {
    font-family: 'Playfair Display', serif;
    font-size: 2.5rem;
    font-weight: 700;
    color: var(--text);
    line-height: 1;
  }
  .stat-num span { color: var(--accent); }
  .stat-label {
    font-family: 'DM Mono', monospace;
    font-size: 0.65rem;
    color: var(--text-muted);
    letter-spacing: 0.15em;
    text-transform: uppercase;
  }

  /* ── SECTION BASE ── */
  section { padding: 7rem 4rem; max-width: 1200px; margin: 0 auto; }
  .section-label {
    font-family: 'DM Mono', monospace;
    font-size: 0.7rem;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 0.75rem;
    display: flex; align-items: center; gap: 1rem;
  }
  .section-label::before {
    content: '';
    display: inline-block;
    width: 32px; height: 1px;
    background: var(--accent);
  }
  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 4vw, 3rem);
    font-weight: 700;
    line-height: 1.1;
    letter-spacing: -0.02em;
    margin-bottom: 3.5rem;
    color: var(--text);
  }

  /* ── ABOUT / SKILLS ── */
  #about { max-width: 100%; padding: 7rem 4rem; }
  .about-inner { max-width: 1200px; margin: 0 auto; }
  .about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 5rem; align-items: start; }
  .about-text p { color: var(--text-muted); font-size: 1rem; line-height: 1.9; margin-bottom: 1.2rem; }
  .about-text p strong { color: var(--text); font-weight: 500; }

  .skills-group { margin-bottom: 2rem; }
  .skills-group-label {
    font-family: 'DM Mono', monospace;
    font-size: 0.68rem;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 0.75rem;
  }
  .skills-tags { display: flex; flex-wrap: wrap; gap: 0.5rem; }
  .tag {
    font-family: 'DM Mono', monospace;
    font-size: 0.72rem;
    padding: 0.35rem 0.85rem;
    border-radius: 2px;
    border: 1px solid var(--border2);
    color: var(--text-muted);
    background: var(--bg-card);
    transition: all 0.2s;
    cursor: default;
  }
  .tag:hover { border-color: var(--accent); color: var(--accent); background: rgba(0,229,255,0.05); }

  /* ── EXPERIENCE ── */
  #experience { background: var(--bg-card); max-width: 100%; }
  .exp-inner { max-width: 1200px; margin: 0 auto; }
  .exp-card {
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 2.5rem;
    background: var(--bg-card2);
    position: relative;
    overflow: hidden;
  }
  .exp-card::before {
    content: '';
    position: absolute; left: 0; top: 0; bottom: 0;
    width: 3px;
    background: linear-gradient(180deg, var(--accent), var(--accent2));
  }
  .exp-header { display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 1.5rem; flex-wrap: wrap; gap: 1rem; }
  .exp-org {
    font-family: 'Playfair Display', serif;
    font-size: 1.4rem;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 0.25rem;
  }
  .exp-role {
    font-family: 'DM Mono', monospace;
    font-size: 0.78rem;
    color: var(--accent);
    letter-spacing: 0.1em;
  }
  .exp-date {
    font-family: 'DM Mono', monospace;
    font-size: 0.72rem;
    color: var(--text-muted);
    letter-spacing: 0.1em;
    border: 1px solid var(--border2);
    padding: 0.3rem 0.8rem;
    border-radius: 2rem;
    white-space: nowrap;
  }
  .exp-bullets { list-style: none; }
  .exp-bullets li {
    display: flex; gap: 1rem;
    color: var(--text-muted);
    font-size: 0.95rem;
    line-height: 1.7;
    margin-bottom: 0.75rem;
  }
  .exp-bullets li::before {
    content: '→';
    color: var(--accent);
    flex-shrink: 0;
    font-family: 'DM Mono', monospace;
    margin-top: 0.05rem;
  }

  /* ── PROJECTS ── */
  .projects-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 1.5rem; }
  .project-card {
    background: var(--bg-card);
    border: 1px solid var(--border2);
    border-radius: 8px;
    padding: 2rem;
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
    display: flex; flex-direction: column;
  }
  .project-card::after {
    content: '';
    position: absolute; inset: 0;
    background: radial-gradient(ellipse 80% 60% at 50% -20%, rgba(0,229,255,0.05), transparent);
    opacity: 0; transition: opacity 0.3s;
  }
  .project-card:hover { border-color: rgba(0,229,255,0.3); transform: translateY(-4px); }
  .project-card:hover::after { opacity: 1; }
  .project-year {
    font-family: 'DM Mono', monospace;
    font-size: 0.65rem;
    letter-spacing: 0.2em;
    color: var(--text-dim);
    margin-bottom: 1rem;
  }
  .project-name {
    font-family: 'Playfair Display', serif;
    font-size: 1.25rem;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 0.35rem;
    line-height: 1.2;
  }
  .project-method {
    font-family: 'DM Mono', monospace;
    font-size: 0.68rem;
    color: var(--accent2);
    letter-spacing: 0.12em;
    margin-bottom: 1rem;
  }
  .project-desc {
    font-size: 0.9rem;
    color: var(--text-muted);
    line-height: 1.7;
    flex: 1;
    margin-bottom: 1.5rem;
  }
  .project-metric {
    display: inline-flex; align-items: center; gap: 0.5rem;
    font-family: 'DM Mono', monospace;
    font-size: 0.72rem;
    color: var(--accent3);
    background: rgba(57,255,138,0.06);
    border: 1px solid rgba(57,255,138,0.2);
    padding: 0.3rem 0.75rem;
    border-radius: 2rem;
    margin-bottom: 1rem;
  }
  .project-stack { display: flex; flex-wrap: wrap; gap: 0.4rem; }
  .stack-pill {
    font-family: 'DM Mono', monospace;
    font-size: 0.65rem;
    padding: 0.25rem 0.65rem;
    border-radius: 2px;
    background: rgba(124,106,247,0.08);
    border: 1px solid rgba(124,106,247,0.2);
    color: #a09af5;
  }

  /* ── EDUCATION & CERT ── */
  #education { background: var(--bg-card); max-width: 100%; }
  .edu-inner { max-width: 1200px; margin: 0 auto; }
  .edu-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; }
  .edu-card {
    background: var(--bg-card2);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 2rem;
  }
  .edu-inst {
    font-family: 'Playfair Display', serif;
    font-size: 1.3rem;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 0.25rem;
  }
  .edu-degree {
    font-family: 'DM Mono', monospace;
    font-size: 0.75rem;
    color: var(--accent);
    letter-spacing: 0.08em;
    margin-bottom: 0.5rem;
  }
  .edu-dates {
    font-family: 'DM Mono', monospace;
    font-size: 0.68rem;
    color: var(--text-muted);
    margin-bottom: 1rem;
  }
  .edu-courses {
    font-size: 0.85rem;
    color: var(--text-muted);
    line-height: 1.7;
  }

  .cert-card {
    background: var(--bg-card2);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 2rem;
    display: flex; align-items: flex-start; gap: 1.5rem;
  }
  .cert-icon {
    width: 48px; height: 48px;
    border-radius: 8px;
    background: rgba(0,229,255,0.08);
    border: 1px solid rgba(0,229,255,0.2);
    display: flex; align-items: center; justify-content: center;
    flex-shrink: 0;
    font-size: 1.4rem;
  }
  .cert-name {
    font-size: 0.95rem;
    font-weight: 500;
    color: var(--text);
    margin-bottom: 0.25rem;
  }
  .cert-issuer {
    font-family: 'DM Mono', monospace;
    font-size: 0.68rem;
    color: var(--accent);
    letter-spacing: 0.1em;
  }
  .cert-year {
    font-family: 'DM Mono', monospace;
    font-size: 0.65rem;
    color: var(--text-dim);
    margin-top: 0.25rem;
  }

  /* ── CONTACT ── */
  #contact { max-width: 100%; }
  .contact-inner { max-width: 1200px; margin: 0 auto; }
  .contact-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 4rem; align-items: center; }
  .contact-text .section-title { margin-bottom: 1.5rem; }
  .contact-text p { color: var(--text-muted); margin-bottom: 2rem; }
  .contact-links { display: flex; flex-direction: column; gap: 1rem; }
  .contact-link {
    display: flex; align-items: center; gap: 1rem;
    text-decoration: none;
    padding: 1.2rem 1.5rem;
    border: 1px solid var(--border2);
    border-radius: 6px;
    background: var(--bg-card);
    transition: all 0.2s;
    color: var(--text);
  }
  .contact-link:hover { border-color: var(--accent); transform: translateX(4px); }
  .contact-link-icon {
    width: 40px; height: 40px;
    border-radius: 6px;
    background: rgba(0,229,255,0.06);
    border: 1px solid rgba(0,229,255,0.15);
    display: flex; align-items: center; justify-content: center;
    font-size: 1.1rem;
    flex-shrink: 0;
  }
  .contact-link-label {
    font-family: 'DM Mono', monospace;
    font-size: 0.65rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--text-muted);
  }
  .contact-link-value {
    font-size: 0.9rem;
    color: var(--text);
  }

  .contact-form { display: flex; flex-direction: column; gap: 1rem; }
  .form-group { display: flex; flex-direction: column; gap: 0.4rem; }
  .form-label {
    font-family: 'DM Mono', monospace;
    font-size: 0.65rem;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--text-muted);
  }
  .form-input, .form-textarea {
    background: var(--bg-card);
    border: 1px solid var(--border2);
    border-radius: 4px;
    padding: 0.85rem 1rem;
    color: var(--text);
    font-family: 'DM Sans', sans-serif;
    font-size: 0.95rem;
    outline: none;
    transition: border-color 0.2s;
    resize: none;
  }
  .form-input:focus, .form-textarea:focus { border-color: var(--accent); }
  .form-textarea { height: 120px; }
  .form-submit {
    background: var(--accent);
    color: var(--bg);
    border: none;
    border-radius: 4px;
    padding: 0.9rem;
    font-family: 'DM Sans', sans-serif;
    font-size: 0.85rem;
    font-weight: 600;
    letter-spacing: 0.08em;
    cursor: pointer;
    transition: all 0.2s;
    display: flex; align-items: center; justify-content: center; gap: 0.5rem;
  }
  .form-submit:hover { background: #33eaff; transform: translateY(-2px); box-shadow: 0 8px 24px rgba(0,229,255,0.25); }

  /* ── FOOTER ── */
  footer {
    border-top: 1px solid var(--border2);
    padding: 2rem 4rem;
    display: flex; align-items: center; justify-content: space-between;
    max-width: 100%;
  }
  .footer-copy {
    font-family: 'DM Mono', monospace;
    font-size: 0.68rem;
    color: var(--text-dim);
    letter-spacing: 0.08em;
  }
  .footer-built {
    font-family: 'DM Mono', monospace;
    font-size: 0.68rem;
    color: var(--text-dim);
    letter-spacing: 0.08em;
  }
  .footer-built span { color: var(--accent); }

  /* ── DIVIDER ── */
  .divider {
    width: 100%; height: 1px;
    background: linear-gradient(90deg, transparent, var(--border2) 30%, var(--border2) 70%, transparent);
    margin: 0;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes fadeLeft {
    from { opacity: 0; transform: translateX(24px); }
    to { opacity: 1; transform: translateX(0); }
  }

  .reveal {
    opacity: 0; transform: translateY(32px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }
  .reveal.visible { opacity: 1; transform: translateY(0); }
  .reveal-delay-1 { transition-delay: 0.1s; }
  .reveal-delay-2 { transition-delay: 0.2s; }
  .reveal-delay-3 { transition-delay: 0.3s; }

  /* ── FLOATING DOTS ── */
  .dot {
    position: fixed; border-radius: 50%;
    pointer-events: none; z-index: 0;
    animation: floatDot linear infinite;
    opacity: 0.4;
  }
  @keyframes floatDot {
    0% { transform: translateY(0) rotate(0deg); opacity: 0; }
    10% { opacity: 0.4; }
    90% { opacity: 0.4; }
    100% { transform: translateY(-100vh) rotate(720deg); opacity: 0; }
  }

  /* ── CURSOR GLOW ── */
  .cursor-glow {
    position: fixed;
    width: 300px; height: 300px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(0,229,255,0.04) 0%, transparent 70%);
    pointer-events: none;
    z-index: 1;
    transform: translate(-50%, -50%);
    transition: transform 0.1s ease;
  }

  /* ── MOBILE ── */
  @media (max-width: 900px) {
    nav { padding: 1rem 1.5rem; }
    .nav-links { gap: 1.5rem; }
    #hero { padding: 7rem 1.5rem 4rem; }
    .hero-stats { display: none; }
    section { padding: 5rem 1.5rem; }
    .about-grid, .projects-grid, .edu-grid, .contact-grid { grid-template-columns: 1fr; gap: 2rem; }
    #about, #experience, #education, #contact { padding: 5rem 1.5rem; }
    footer { padding: 1.5rem; flex-direction: column; gap: 0.5rem; text-align: center; }
  }
</style>
</head>
<body>

<div class="cursor-glow" id="cursor"></div>

<!-- NAV -->
<nav>
  <div class="nav-logo">Ahmed · AE</div>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#experience">Experience</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#education">Education</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-bg"></div>
  <div class="hero-grid"></div>

  <div class="hero-content">
    <div class="hero-tag">Available for opportunities</div>
    <h1 class="hero-name">
      Ahmed
      <span>Ayman.</span>
    </h1>
    <p class="hero-title">AI Engineer &nbsp;/&nbsp; Machine Learning &nbsp;/&nbsp; Generative AI</p>
    <p class="hero-desc">
      Building <strong>intelligent systems</strong> that matter — from RAG pipelines and multi-agent architectures to computer vision and NLP solutions. Passionate about taking AI from research to <strong>production-ready</strong> impact.
    </p>
    <div class="hero-cta">
      <a href="#projects" class="btn btn-primary">View My Work →</a>
      <a href="#contact" class="btn btn-outline">Get in Touch</a>
    </div>

    <div class="hero-stats">
      <div class="stat-item">
        <div class="stat-num">4<span>+</span></div>
        <div class="stat-label">AI Projects</div>
      </div>
      <div class="stat-item">
        <div class="stat-num">93<span>%</span></div>
        <div class="stat-label">Peak Accuracy</div>
      </div>
      <div class="stat-item">
        <div class="stat-num">5<span>+</span></div>
        <div class="stat-label">Frameworks</div>
      </div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- ABOUT -->
<section id="about" style="max-width:100%; padding:7rem 4rem;">
<div class="about-inner">
  <div class="section-label">About me</div>
  <div class="about-grid">
    <div class="about-text">
      <h2 class="section-title">Engineering AI that<br>solves real problems.</h2>
      <p>
        I'm an AI Engineer based in Egypt, currently completing my <strong>Bachelor's in Artificial Intelligence</strong> at Delta University (graduating 2026). My work spans the full ML lifecycle — from raw data to deployed, production-grade systems.
      </p>
      <p>
        Through the <strong>Digital Egypt Pioneers Initiative</strong>, I've gone deep on Generative AI, RAG architectures, LoRA fine-tuning, and agentic AI systems with memory and autonomous workflows.
      </p>
      <p>
        I care about building AI that's not just accurate — but <strong>explainable, accessible, and impactful</strong> for real users.
      </p>
    </div>
    <div class="about-skills">
      <div class="skills-group">
        <div class="skills-group-label">Languages</div>
        <div class="skills-tags">
          <span class="tag">Python</span>
          <span class="tag">SQL</span>
          <span class="tag">C++</span>
          <span class="tag">Java</span>
        </div>
      </div>
      <div class="skills-group">
        <div class="skills-group-label">AI / ML Frameworks</div>
        <div class="skills-tags">
          <span class="tag">TensorFlow</span>
          <span class="tag">PyTorch</span>
          <span class="tag">Scikit-learn</span>
          <span class="tag">Keras</span>
        </div>
      </div>
      <div class="skills-group">
        <div class="skills-group-label">LLMs & NLP</div>
        <div class="skills-tags">
          <span class="tag">LangChain</span>
          <span class="tag">Hugging Face</span>
          <span class="tag">RAG Pipelines</span>
          <span class="tag">LoRA Fine-tuning</span>
          <span class="tag">Prompt Engineering</span>
          <span class="tag">Agentic AI</span>
          <span class="tag">spaCy</span>
          <span class="tag">NLTK</span>
        </div>
      </div>
      <div class="skills-group">
        <div class="skills-group-label">Computer Vision</div>
        <div class="skills-tags">
          <span class="tag">OpenCV</span>
          <span class="tag">PIL</span>
          <span class="tag">EfficientNet</span>
          <span class="tag">Transfer Learning</span>
        </div>
      </div>
      <div class="skills-group">
        <div class="skills-group-label">Tools & Platforms</div>
        <div class="skills-tags">
          <span class="tag">Docker</span>
          <span class="tag">Git / GitHub</span>
          <span class="tag">Streamlit</span>
          <span class="tag">PostgreSQL</span>
          <span class="tag">MongoDB</span>
          <span class="tag">Kaggle</span>
        </div>
      </div>
    </div>
  </div>
</div>
</section>

<div class="divider"></div>

<!-- EXPERIENCE -->
<section id="experience" style="max-width:100%; padding:7rem 4rem; background:var(--bg-card);">
<div class="exp-inner">
  <div class="section-label">Experience</div>
  <h2 class="section-title">Where I've trained<br>and contributed.</h2>

  <div class="exp-card reveal">
    <div class="exp-header">
      <div>
        <div class="exp-org">Digital Egypt Pioneers Initiative (DEPI)</div>
        <div class="exp-role">Generative & Agentic AI Trainee</div>
      </div>
      <div class="exp-date">2026</div>
    </div>
    <ul class="exp-bullets">
      <li>Completed intensive training in Generative AI, RAG systems, and Multi-Agent architectures using Transformers and advanced Prompt Engineering.</li>
      <li>Implemented LoRA fine-tuning pipelines and tool-calling AI agents with persistent memory systems and autonomous decision workflows.</li>
      <li>Built and deployed end-to-end AI solutions involving retrieval-augmented generation, agentic loops, and production-ready APIs.</li>
    </ul>
  </div>
</div>
</section>

<div class="divider"></div>

<!-- PROJECTS -->
<section id="projects" style="padding:7rem 4rem;">
  <div class="section-label">Projects</div>
  <h2 class="section-title">Things I've built.</h2>

  <div class="projects-grid">

    <div class="project-card reveal">
      <div class="project-year">2026</div>
      <div class="project-name">Intelligent University Timetable Generator</div>
      <div class="project-method">Genetic Algorithms + Reinforcement Learning</div>
      <p class="project-desc">
        AI scheduling system that auto-generates conflict-free university timetables for 180+ student groups and 40+ instructors. Eliminates room conflicts and instructor clashes with real-time constraint detection.
      </p>
      <div class="project-metric">⚡ Under 5 min vs 1–3 days manually</div>
      <div class="project-stack">
        <span class="stack-pill">Python</span>
        <span class="stack-pill">Genetic Algorithms</span>
        <span class="stack-pill">Reinforcement Learning</span>
        <span class="stack-pill">Streamlit</span>
        <span class="stack-pill">NumPy</span>
        <span class="stack-pill">Pandas</span>
      </div>
    </div>

    <div class="project-card reveal reveal-delay-1">
      <div class="project-year">2025</div>
      <div class="project-name">Smart Diagnostic System</div>
      <div class="project-method">AI-Powered Health Screening</div>
      <p class="project-desc">
        Multi-condition symptom screening system integrating ML classification models for preliminary diagnostic assessments. Correctly identifies top-2 most likely conditions in the majority of test cases.
      </p>
      <div class="project-metric">✓ 93% test accuracy</div>
      <div class="project-stack">
        <span class="stack-pill">Python</span>
        <span class="stack-pill">Machine Learning</span>
        <span class="stack-pill">Deep Learning</span>
        <span class="stack-pill">Data Processing</span>
      </div>
    </div>

    <div class="project-card reveal reveal-delay-2">
      <div class="project-year">2025</div>
      <div class="project-name">Mental Health Chatbot</div>
      <div class="project-method">NLP + Transformer Fine-tuning</div>
      <p class="project-desc">
        Context-aware chatbot using intent recognition and sentiment analysis for mental health support and resource recommendations. Fine-tuned transformers on mental health conversation datasets.
      </p>
      <div class="project-metric">↑ +15% F1-score over TF-IDF baseline</div>
      <div class="project-stack">
        <span class="stack-pill">Python</span>
        <span class="stack-pill">Hugging Face</span>
        <span class="stack-pill">NLP</span>
        <span class="stack-pill">Transformers</span>
        <span class="stack-pill">Sentiment Analysis</span>
      </div>
    </div>

    <div class="project-card reveal reveal-delay-3">
      <div class="project-year">2024</div>
      <div class="project-name">Skin Cancer Detection System</div>
      <div class="project-method">Transfer Learning + Computer Vision</div>
      <p class="project-desc">
        Deep learning model trained on the ISIC dermoscopic image dataset to classify 7 types of skin lesions. Applied transfer learning with EfficientNet-B4 and data augmentation to address class imbalance.
      </p>
      <div class="project-metric">✓ 91% accuracy · +20% sensitivity on minority classes</div>
      <div class="project-stack">
        <span class="stack-pill">PyTorch</span>
        <span class="stack-pill">TensorFlow</span>
        <span class="stack-pill">EfficientNet-B4</span>
        <span class="stack-pill">OpenCV</span>
        <span class="stack-pill">ISIC Dataset</span>
      </div>
    </div>

  </div>
</section>

<div class="divider"></div>

<!-- EDUCATION -->
<section id="education" style="max-width:100%; padding:7rem 4rem; background:var(--bg-card);">
<div class="edu-inner">
  <div class="section-label">Education & Certifications</div>
  <h2 class="section-title">Foundation &<br>continuous learning.</h2>

  <div class="edu-grid">
    <div>
      <div class="edu-card reveal">
        <div class="edu-inst">Delta University for Science & Technology</div>
        <div class="edu-degree">Bachelor of Artificial Intelligence</div>
        <div class="edu-dates">Oct 2022 — Jun 2026</div>
        <p class="edu-courses">
          <strong style="color:var(--text-muted);">Relevant coursework:</strong> Machine Learning, Deep Learning, Computer Vision, Natural Language Processing, Data Structures & Algorithms.
        </p>
      </div>
    </div>

    <div style="display:flex;flex-direction:column;gap:1rem;">
      <div class="cert-card reveal reveal-delay-1">
        <div class="cert-icon">🎓</div>
        <div>
          <div class="cert-name">Building LLM Applications with Prompt Engineering</div>
          <div class="cert-issuer">NVIDIA</div>
          <div class="cert-year">2024</div>
        </div>
      </div>

      <div class="cert-card reveal reveal-delay-2" style="background:rgba(0,229,255,0.03); border-color:rgba(0,229,255,0.1);">
        <div class="cert-icon">🤖</div>
        <div>
          <div class="cert-name">Generative & Agentic AI Program</div>
          <div class="cert-issuer">Digital Egypt Pioneers Initiative (DEPI)</div>
          <div class="cert-year">2026</div>
        </div>
      </div>

      <div style="background:var(--bg-card2); border:1px solid var(--border2); border-radius:8px; padding:1.5rem;">
        <div style="font-family:'DM Mono',monospace; font-size:0.65rem; letter-spacing:0.15em; text-transform:uppercase; color:var(--accent); margin-bottom:0.75rem;">Active Communities</div>
        <p style="font-size:0.9rem; color:var(--text-muted); line-height:1.7;">Public contributor on <strong style="color:var(--text)">GitHub</strong> and <strong style="color:var(--text)">Kaggle</strong> with repositories across ML, NLP, and computer vision — covering full ML lifecycle from data collection to deployment.</p>
      </div>
    </div>
  </div>
</div>
</section>

<div class="divider"></div>

<!-- CONTACT -->
<section id="contact" style="max-width:100%; padding:7rem 4rem;">
<div class="contact-inner">
  <div class="section-label">Contact</div>
  <div class="contact-grid">
    <div>
      <h2 class="section-title">Let's build<br>something great.</h2>
      <p style="color:var(--text-muted); margin-bottom:2rem; font-size:0.95rem; line-height:1.8;">Open to full-time roles, internships, research collaborations, and freelance AI projects. Let's connect.</p>

      <div class="contact-links">
        <a href="mailto:ahmedaymenelsawy@gmail.com" class="contact-link">
          <div class="contact-link-icon">✉️</div>
          <div>
            <div class="contact-link-label">Email</div>
            <div class="contact-link-value">ahmedaymenelsawy@gmail.com</div>
          </div>
        </a>
        <a href="tel:+201032788508" class="contact-link">
          <div class="contact-link-icon">📱</div>
          <div>
            <div class="contact-link-label">Phone</div>
            <div class="contact-link-value">+20 1032788508</div>
          </div>
        </a>
        <a href="https://linkedin.com" target="_blank" class="contact-link">
          <div class="contact-link-icon">💼</div>
          <div>
            <div class="contact-link-label">LinkedIn</div>
            <div class="contact-link-value">linkedin.com/in/ahmed-ayman</div>
          </div>
        </a>
        <a href="https://github.com" target="_blank" class="contact-link">
          <div class="contact-link-icon">⌨️</div>
          <div>
            <div class="contact-link-label">GitHub</div>
            <div class="contact-link-value">github.com/ahmed-ayman</div>
          </div>
        </a>
      </div>
    </div>

    <div>
      <div style="background:var(--bg-card); border:1px solid var(--border2); border-radius:8px; padding:2rem;">
        <div style="font-family:'DM Mono',monospace; font-size:0.7rem; letter-spacing:0.15em; text-transform:uppercase; color:var(--accent); margin-bottom:1.5rem;">Send a message</div>
        <div class="contact-form">
          <div class="form-group">
            <label class="form-label">Name</label>
            <input type="text" class="form-input" placeholder="Your name">
          </div>
          <div class="form-group">
            <label class="form-label">Email</label>
            <input type="email" class="form-input" placeholder="your@email.com">
          </div>
          <div class="form-group">
            <label class="form-label">Message</label>
            <textarea class="form-textarea" placeholder="Tell me about your project..."></textarea>
          </div>
          <button class="form-submit" onclick="handleSubmit(this)">Send Message →</button>
        </div>
      </div>
    </div>
  </div>
</div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-copy">© 2026 Ahmed Ayman Elsawy. All rights reserved.</div>
  <div class="footer-built">Built with <span>passion</span> · Cairo, Egypt</div>
</footer>

<script>
  // Cursor glow
  const cursor = document.getElementById('cursor');
  document.addEventListener('mousemove', e => {
    cursor.style.left = e.clientX + 'px';
    cursor.style.top = e.clientY + 'px';
  });

  // Scroll reveal
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver(entries => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.classList.add('visible');
        observer.unobserve(e.target);
      }
    });
  }, { threshold: 0.1, rootMargin: '0px 0px -50px 0px' });
  reveals.forEach(el => observer.observe(el));

  // Nav active highlight on scroll
  const sections = document.querySelectorAll('section[id]');
  const navLinks = document.querySelectorAll('.nav-links a');
  window.addEventListener('scroll', () => {
    let current = '';
    sections.forEach(s => {
      if (window.scrollY >= s.offsetTop - 200) current = s.getAttribute('id');
    });
    navLinks.forEach(a => {
      a.style.color = a.getAttribute('href') === '#' + current
        ? 'var(--accent)' : '';
    });
  });

  // Floating particles
  function createDot() {
    const dot = document.createElement('div');
    dot.className = 'dot';
    const size = Math.random() * 3 + 1;
    dot.style.cssText = `
      width:${size}px; height:${size}px;
      left:${Math.random() * 100}%;
      bottom:-10px;
      background:${Math.random() > 0.5 ? 'var(--accent)' : 'var(--accent2)'};
      animation-duration:${Math.random() * 15 + 10}s;
      animation-delay:${Math.random() * 5}s;
    `;
    document.body.appendChild(dot);
    setTimeout(() => dot.remove(), 25000);
  }
  setInterval(createDot, 1500);

  // Form submit
  function handleSubmit(btn) {
    btn.textContent = 'Message Sent! ✓';
    btn.style.background = 'var(--accent3)';
    setTimeout(() => {
      btn.textContent = 'Send Message →';
      btn.style.background = 'var(--accent)';
    }, 3000);
  }

  // Typing effect on hero tag
  const tag = document.querySelector('.hero-tag');
  const text = 'Available for opportunities';
  tag.innerHTML = '<span style="width:6px;height:6px;border-radius:50%;background:var(--accent);animation:pulse 2s ease infinite;flex-shrink:0;"></span><span id="typed"></span>';
  let i = 0;
  const typed = document.getElementById('typed');
  const type = () => {
    if (i < text.length) { typed.textContent += text[i++]; setTimeout(type, 60); }
  };
  setTimeout(type, 500);
</script>
</body>
</html>
