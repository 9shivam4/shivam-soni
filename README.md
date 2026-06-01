<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Shivam Soni</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,400;0,500;1,400;1,500&family=DM+Mono:wght@300;400&family=Outfit:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
  --bg: #f9f7f4;
  --ink: #1c1c1a;
  --ink2: #4a4a45;
  --ink3: #8a8a82;
  --accent: #2a5c45;
  --accent-light: #e8f2ed;
  --warm: #c4622d;
  --border: rgba(28,28,26,0.1);
  --serif: 'Lora', Georgia, serif;
  --sans: 'Outfit', system-ui, sans-serif;
  --mono: 'DM Mono', monospace;
}

html { scroll-behavior: smooth; }

body {
  font-family: var(--sans);
  background: var(--bg);
  color: var(--ink);
  font-size: 16px;
  line-height: 1.7;
  -webkit-font-smoothing: antialiased;
}

/* ── NOISE TEXTURE ── */
body::before {
  content: '';
  position: fixed;
  inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.025'/%3E%3C/svg%3E");
  pointer-events: none;
  z-index: 1000;
  opacity: 0.4;
}

/* ── NAV ── */
nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 100;
  padding: 0 3rem;
  height: 58px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  background: rgba(249,247,244,0.85);
  backdrop-filter: blur(14px);
  border-bottom: 0.5px solid var(--border);
}

.nav-name {
  font-family: var(--serif);
  font-size: 17px;
  font-weight: 500;
  color: var(--ink);
  text-decoration: none;
  letter-spacing: -0.2px;
}

.nav-links {
  display: flex;
  align-items: center;
  gap: 2rem;
}

.nav-links a {
  font-size: 13px;
  font-weight: 400;
  color: var(--ink3);
  text-decoration: none;
  letter-spacing: 0.02em;
  transition: color 0.2s;
}

.nav-links a:hover { color: var(--ink); }

.nav-links a.active { color: var(--ink); font-weight: 500; }

/* ── LAYOUT ── */
main {
  max-width: 680px;
  margin: 0 auto;
  padding: 120px 2rem 80px;
}

/* ── HOME PAGE ── */
.hero {
  padding-bottom: 5rem;
  border-bottom: 0.5px solid var(--border);
  margin-bottom: 5rem;
}

.hero-label {
  font-family: var(--mono);
  font-size: 11px;
  letter-spacing: 0.12em;
  color: var(--accent);
  text-transform: uppercase;
  margin-bottom: 1.5rem;
  display: flex;
  align-items: center;
  gap: 10px;
}

.hero-label::before {
  content: '';
  width: 24px;
  height: 1px;
  background: var(--accent);
}

.hero h1 {
  font-family: var(--serif);
  font-size: clamp(2rem, 5vw, 2.8rem);
  font-weight: 400;
  line-height: 1.25;
  letter-spacing: -0.5px;
  color: var(--ink);
  margin-bottom: 1.75rem;
}

.hero h1 em {
  font-style: italic;
  color: var(--accent);
}

.hero-body {
  font-size: 17px;
  color: var(--ink2);
  line-height: 1.8;
  max-width: 580px;
  margin-bottom: 2rem;
}

.hero-body p + p {
  margin-top: 1rem;
}

.hero-links {
  display: flex;
  gap: 1.5rem;
  flex-wrap: wrap;
  align-items: center;
  margin-top: 2rem;
}

.hero-link {
  font-size: 13px;
  color: var(--ink3);
  text-decoration: none;
  display: flex;
  align-items: center;
  gap: 6px;
  transition: color 0.2s;
  font-family: var(--mono);
}

.hero-link:hover { color: var(--ink); }

.hero-link svg { width: 14px; height: 14px; }

/* ── PAGES (sections) ── */
.page { display: none; }
.page.active { display: block; }

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(10px); }
  to   { opacity: 1; transform: translateY(0); }
}

.page.active { animation: fadeIn 0.35s ease forwards; }

/* ── PAGE HEADER ── */
.page-eyebrow {
  font-family: var(--mono);
  font-size: 11px;
  letter-spacing: 0.12em;
  color: var(--accent);
  text-transform: uppercase;
  margin-bottom: 0.6rem;
}

.page-title {
  font-family: var(--serif);
  font-size: clamp(1.8rem, 4vw, 2.4rem);
  font-weight: 400;
  letter-spacing: -0.5px;
  color: var(--ink);
  margin-bottom: 2.5rem;
  padding-bottom: 1.5rem;
  border-bottom: 0.5px solid var(--border);
  line-height: 1.2;
}

/* ── PROSE ── */
.prose p {
  font-size: 16px;
  color: var(--ink2);
  line-height: 1.85;
  margin-bottom: 1.25rem;
}

.prose p strong {
  color: var(--ink);
  font-weight: 600;
}

.prose p a {
  color: var(--accent);
  text-decoration: underline;
  text-underline-offset: 3px;
}

/* ── EXPERIENCE ENTRIES ── */
.exp-list { display: flex; flex-direction: column; gap: 0; }

.exp-item {
  padding: 2rem 0;
  border-bottom: 0.5px solid var(--border);
  display: grid;
  grid-template-columns: 160px 1fr;
  gap: 2rem;
  align-items: start;
}

.exp-meta {
  padding-top: 3px;
}

.exp-date {
  font-family: var(--mono);
  font-size: 11px;
  color: var(--ink3);
  letter-spacing: 0.06em;
  margin-bottom: 4px;
}

.exp-co {
  font-size: 12px;
  color: var(--accent);
  font-weight: 500;
}

.exp-role {
  font-size: 16px;
  font-weight: 600;
  color: var(--ink);
  margin-bottom: 0.5rem;
  letter-spacing: -0.1px;
}

.exp-desc {
  font-size: 14.5px;
  color: var(--ink2);
  line-height: 1.75;
}

.exp-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 5px;
  margin-top: 0.75rem;
}

.tag {
  font-family: var(--mono);
  font-size: 10px;
  padding: 2px 8px;
  border-radius: 3px;
  background: var(--accent-light);
  color: var(--accent);
  letter-spacing: 0.04em;
}

/* ── CASE STUDIES ── */
.cs-list { display: flex; flex-direction: column; gap: 0; }

.cs-item {
  padding: 2.5rem 0;
  border-bottom: 0.5px solid var(--border);
  cursor: pointer;
}

.cs-item:last-child { border-bottom: none; }

.cs-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  margin-bottom: 0.75rem;
}

.cs-num {
  font-family: var(--mono);
  font-size: 11px;
  color: var(--ink3);
  letter-spacing: 0.06em;
}

.cs-arrow {
  font-size: 18px;
  color: var(--ink3);
  transition: transform 0.2s, color 0.2s;
}

.cs-item:hover .cs-arrow {
  transform: translate(3px, -3px);
  color: var(--ink);
}

.cs-title {
  font-family: var(--serif);
  font-size: 1.25rem;
  font-weight: 400;
  color: var(--ink);
  margin-bottom: 0.5rem;
  line-height: 1.35;
}

.cs-type {
  font-family: var(--mono);
  font-size: 11px;
  color: var(--accent);
  letter-spacing: 0.08em;
  text-transform: uppercase;
  margin-bottom: 0.75rem;
}

.cs-summary {
  font-size: 14.5px;
  color: var(--ink3);
  line-height: 1.7;
  max-width: 520px;
}

.cs-metrics {
  display: flex;
  gap: 2rem;
  margin-top: 1.25rem;
  flex-wrap: wrap;
}

.cs-metric .val {
  font-family: var(--serif);
  font-size: 1.4rem;
  font-style: italic;
  color: var(--ink);
  display: block;
  line-height: 1;
}

.cs-metric .lbl {
  font-size: 11px;
  color: var(--ink3);
  font-family: var(--mono);
  letter-spacing: 0.04em;
  margin-top: 3px;
}

/* ── CASE STUDY DETAIL ── */
.cs-detail { display: none; }
.cs-detail.open { display: block; animation: fadeIn 0.3s ease; }

.cs-detail-inner {
  background: white;
  border: 0.5px solid var(--border);
  border-radius: 12px;
  padding: 2.5rem;
  margin-top: 1.5rem;
}

.cs-section {
  margin-bottom: 2rem;
}

.cs-section-label {
  font-family: var(--mono);
  font-size: 10px;
  letter-spacing: 0.14em;
  text-transform: uppercase;
  color: var(--ink3);
  margin-bottom: 0.6rem;
}

.cs-section p {
  font-size: 14px;
  color: var(--ink2);
  line-height: 1.8;
}

.cs-decisions {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.cs-decision {
  padding: 1rem 1.25rem;
  border-left: 2px solid var(--accent);
  background: var(--accent-light);
  border-radius: 0 6px 6px 0;
}

.cs-decision-title {
  font-size: 13px;
  font-weight: 600;
  color: var(--ink);
  margin-bottom: 4px;
}

.cs-decision-desc {
  font-size: 13px;
  color: var(--ink2);
  line-height: 1.65;
}

.outcome-row {
  display: flex;
  align-items: baseline;
  gap: 0.75rem;
  padding: 0.5rem 0;
  border-bottom: 0.5px solid var(--border);
  font-size: 14px;
}

.outcome-row:last-child { border-bottom: none; }

.outcome-val {
  font-family: var(--serif);
  font-style: italic;
  font-size: 1.1rem;
  color: var(--accent);
  min-width: 60px;
}

.outcome-lbl { color: var(--ink2); }

.cs-close-btn {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  font-family: var(--mono);
  font-size: 12px;
  color: var(--ink3);
  cursor: pointer;
  margin-top: 1.5rem;
  background: none;
  border: none;
  padding: 0;
  transition: color 0.2s;
}

.cs-close-btn:hover { color: var(--ink); }

/* ── SKILLS ── */
.skills-grid {
  display: flex;
  flex-direction: column;
  gap: 0;
}

.skill-row {
  display: grid;
  grid-template-columns: 180px 1fr;
  gap: 2rem;
  padding: 1.5rem 0;
  border-bottom: 0.5px solid var(--border);
  align-items: start;
}

.skill-cat {
  font-family: var(--mono);
  font-size: 11px;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--ink3);
  padding-top: 3px;
}

.skill-items {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
}

.skill-pill {
  font-size: 13px;
  color: var(--ink2);
  padding: 3px 10px;
  border: 0.5px solid var(--border);
  border-radius: 4px;
  background: white;
  transition: border-color 0.15s;
}

.skill-pill:hover {
  border-color: var(--accent);
  color: var(--accent);
}

/* ── FRAMEWORKS TABLE ── */
.fw-table {
  width: 100%;
  border-collapse: collapse;
  font-size: 14px;
  margin-top: 1rem;
}

.fw-table th {
  text-align: left;
  font-family: var(--mono);
  font-size: 10px;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--ink3);
  padding: 0.5rem 0;
  border-bottom: 0.5px solid var(--border);
}

.fw-table td {
  padding: 0.75rem 0;
  border-bottom: 0.5px solid var(--border);
  color: var(--ink2);
  vertical-align: top;
}

.fw-table td:first-child {
  font-weight: 600;
  color: var(--ink);
  width: 160px;
  font-size: 13px;
}

.fw-table td:last-child {
  font-size: 13px;
  line-height: 1.6;
}

/* ── CONTACT ── */
.contact-section {
  margin-bottom: 3rem;
}

.contact-intro {
  font-family: var(--serif);
  font-size: 1.3rem;
  font-weight: 400;
  font-style: italic;
  color: var(--ink2);
  line-height: 1.5;
  margin-bottom: 2.5rem;
}

.contact-list {
  display: flex;
  flex-direction: column;
  gap: 0;
}

.contact-item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1.25rem 0;
  border-bottom: 0.5px solid var(--border);
}

.contact-label {
  font-family: var(--mono);
  font-size: 11px;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--ink3);
}

.contact-val {
  font-size: 15px;
  color: var(--ink);
  text-decoration: none;
  transition: color 0.2s;
}

.contact-val:hover { color: var(--accent); }

.avail-badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  font-family: var(--mono);
  font-size: 11px;
  color: var(--accent);
  letter-spacing: 0.06em;
  padding: 8px 14px;
  border: 1px solid var(--accent);
  border-radius: 999px;
  margin-top: 2.5rem;
}

.avail-dot {
  width: 7px;
  height: 7px;
  border-radius: 50%;
  background: var(--accent);
  animation: blink 2s ease infinite;
}

@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.3; }
}

/* ── FOOTER ── */
footer {
  max-width: 680px;
  margin: 0 auto;
  padding: 0 2rem 3rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-family: var(--mono);
  font-size: 11px;
  color: var(--ink3);
  border-top: 0.5px solid var(--border);
  padding-top: 2rem;
}

/* ── DIVIDER LINE ── */
.divider {
  height: 0.5px;
  background: var(--border);
  margin: 3rem 0;
}

/* ── RESPONSIVE ── */
@media (max-width: 640px) {
  nav { padding: 0 1.25rem; }
  main { padding: 100px 1.25rem 60px; }
  .exp-item { grid-template-columns: 1fr; gap: 0.25rem; }
  .skill-row { grid-template-columns: 1fr; gap: 0.5rem; }
  .nav-links { gap: 1.2rem; }
}
</style>
</head>
<body>

<nav>
  <a href="#" class="nav-name" onclick="showPage('home')">Shivam Soni</a>
  <div class="nav-links">
    <a href="#" onclick="showPage('about')" id="nav-about">About</a>
    <a href="#" onclick="showPage('work')" id="nav-work">Work</a>
    <a href="#" onclick="showPage('skills')" id="nav-skills">Skills</a>
    <a href="https://www.linkedin.com/in/shivamsoni29/" target="_blank">LinkedIn ↗</a>
    <a href="#" onclick="showPage('contact')" id="nav-contact">Contact</a>
  </div>
</nav>

<main>

  <!-- ══ HOME ══ -->
  <div id="page-home" class="page active">
    <div class="hero">
      <div class="hero-label">Product Manager · Jaipur, India</div>
      <h1>My name is Shivam.<br>I build <em>AI-powered products</em><br>that convert and scale.</h1>
      <div class="hero-body">
        <p>I'm a Product Manager with experience building AI-powered ERP/LMS, D2C e-commerce, and device management platforms. My work has driven ₹200Cr+ in business impact — from a 0→1 D2C storefront that cut cart abandonment by 24%, to an AI hybrid grading system that reduced manual effort by 70%.</p>
        <p>I spent two years at Mafatlal Industries in Mumbai owning four platforms end-to-end — from discovery and PRDs to sprint execution and post-launch analytics. I'm currently consulting independently, helping early-stage teams build with intent.</p>
      </div>
      <div class="hero-links">
        <a href="mailto:9shivam4@gmail.com" class="hero-link">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M3 8l9 6 9-6M3 8v10a1 1 0 001 1h16a1 1 0 001-1V8M3 8a1 1 0 011-1h16a1 1 0 011 1"/></svg>
          9shivam4@gmail.com
        </a>
        <a href="https://www.linkedin.com/in/shivamsoni29/" target="_blank" class="hero-link">
          <svg viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg>
          LinkedIn
        </a>
        <a href="tel:+919462696994" class="hero-link">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"/></svg>
          +91 94626 96994
        </a>
      </div>
    </div>

    <!-- Featured work on home -->
    <div>
      <div style="font-family:var(--mono);font-size:11px;letter-spacing:.1em;text-transform:uppercase;color:var(--ink3);margin-bottom:1.5rem">Selected work</div>
      <div class="cs-list">
        <div class="cs-item" onclick="showPage('work')">
          <div class="cs-header">
            <span class="cs-num">01</span>
            <span class="cs-arrow">↗</span>
          </div>
          <div class="cs-type">D2C · E-Commerce · 0→1</div>
          <div class="cs-title">School Essentials Storefront — Built from Zero</div>
          <div class="cs-summary">Owned the full product roadmap for Mafatlal's first B2C storefront — from discovery and PLP/PDP architecture to GTM. Opened a new revenue stream.</div>
          <div class="cs-metrics">
            <div class="cs-metric"><span class="val">−24%</span><span class="lbl">cart abandonment</span></div>
            <div class="cs-metric"><span class="val">+32%</span><span class="lbl">parent engagement</span></div>
            <div class="cs-metric"><span class="val">+19%</span><span class="lbl">browse-to-buy</span></div>
          </div>
        </div>
        <div class="cs-item" onclick="showPage('work')">
          <div class="cs-header">
            <span class="cs-num">02</span>
            <span class="cs-arrow">↗</span>
          </div>
          <div class="cs-type">AI · EdTech · ERP/LMS</div>
          <div class="cs-title">AI-Powered Education ERP & LMS</div>
          <div class="cs-summary">Led a unified platform with hybrid AI grading (AI + peer + teacher) and an AI chatbot. Consolidated five fragmented admin workflows into one product.</div>
          <div class="cs-metrics">
            <div class="cs-metric"><span class="val">+40%</span><span class="lbl">user engagement</span></div>
            <div class="cs-metric"><span class="val">−70%</span><span class="lbl">manual grading effort</span></div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- ══ ABOUT ══ -->
  <div id="page-about" class="page">
    <div class="page-eyebrow">About</div>
    <h2 class="page-title">Product Manager building AI-powered platforms that close the loop between behaviour, logic, and revenue.</h2>

    <div class="prose">
      <p>I'm a Product Manager based in Jaipur, India, with a background that spans Computer Science (B.Tech) and Marketing & Operations (MBA from IMT Nagpur). That combination gives me technical vocabulary to work closely with engineering and commercial instincts to tie every feature to a business outcome.</p>

      <p>My two years at <strong>Mafatlal Industries</strong> in Mumbai were defined by building from scratch — no playbooks, no existing infrastructure. I built the D2C storefront, the AI-powered ERP/LMS, and the Device Management System as 0→1 products, each with its own discovery process, technical constraints, and stakeholder landscape.</p>

      <p>Before that, I interned at <strong>Amul GCMMF</strong>, where I worked on consumer research and GTM strategy — giving me an early intuition for how upstream channel decisions affect downstream adoption. Earlier still, I ran digital campaigns at Bizz Boost Media, which taught me how paid and organic channels interact and reinforce each other.</p>

      <p>I'm now consulting independently, helping early-stage founders define product KPIs, build MVP roadmaps, and reduce feature rework before they scale.</p>

      <p>A principle I keep coming back to: <em>discoverability, product experience, and conversion are one connected system — not three separate workstreams.</em> I build accordingly.</p>
    </div>

    <div class="divider"></div>

    <div style="font-family:var(--mono);font-size:11px;letter-spacing:.1em;text-transform:uppercase;color:var(--ink3);margin-bottom:1.5rem">Education</div>
    <div class="exp-list">
      <div class="exp-item">
        <div class="exp-meta">
          <div class="exp-date">2021 — 2023</div>
          <div class="exp-co">IMT Nagpur</div>
        </div>
        <div>
          <div class="exp-role">MBA — Marketing & Operations</div>
          <div class="exp-desc">Institute of Management Technology, Nagpur</div>
        </div>
      </div>
      <div class="exp-item">
        <div class="exp-meta">
          <div class="exp-date">2014 — 2019</div>
          <div class="exp-co">UEM Jaipur</div>
        </div>
        <div>
          <div class="exp-role">B.Tech — Computer Science</div>
          <div class="exp-desc">University of Engineering & Management, Jaipur</div>
        </div>
      </div>
    </div>

    <div class="divider"></div>
    <div style="font-family:var(--mono);font-size:11px;letter-spacing:.1em;text-transform:uppercase;color:var(--ink3);margin-bottom:1.5rem">Certifications</div>
    <div class="exp-list">
      <div class="exp-item">
        <div class="exp-meta"><div class="exp-co">IBM</div></div>
        <div><div class="exp-role">Product Manager</div><div class="exp-desc" style="font-family:var(--mono);font-size:12px;color:var(--ink3)">GXPOUNSKLWBV</div></div>
      </div>
      <div class="exp-item">
        <div class="exp-meta"><div class="exp-co">Google</div></div>
        <div><div class="exp-role">Project Management</div><div class="exp-desc" style="font-family:var(--mono);font-size:12px;color:var(--ink3)">DJK5V37QJQHF</div></div>
      </div>
      <div class="exp-item">
        <div class="exp-meta"><div class="exp-co">Google</div></div>
        <div><div class="exp-role">Data Analytics</div><div class="exp-desc" style="font-family:var(--mono);font-size:12px;color:var(--ink3)">TUYPNY3YOPF</div></div>
      </div>
    </div>
  </div>

  <!-- ══ WORK ══ -->
  <div id="page-work" class="page">
    <div class="page-eyebrow">Case Studies</div>
    <h2 class="page-title">Three platforms. Four years. One consistent thread — build with data, ship with intent.</h2>

    <div class="cs-list">

      <!-- CS 1 -->
      <div class="cs-item" onclick="toggleCS('cs1')">
        <div class="cs-header">
          <span class="cs-num">01 / 2023–2025</span>
          <span class="cs-arrow" id="arr-cs1">↓</span>
        </div>
        <div class="cs-type">D2C · E-Commerce · 0→1 Build</div>
        <div class="cs-title">School Essentials Storefront — Mafatlal Industries</div>
        <div class="cs-summary">Built Mafatlal's first B2C storefront from zero. Owned discovery, PLP/PDP architecture, cross-sell logic, checkout edge cases, A/B tests, and GTM. Opened a new revenue stream targeting parents buying school essentials.</div>
        <div class="cs-metrics">
          <div class="cs-metric"><span class="val">−24%</span><span class="lbl">cart abandonment</span></div>
          <div class="cs-metric"><span class="val">+32%</span><span class="lbl">parent engagement</span></div>
          <div class="cs-metric"><span class="val">+19%</span><span class="lbl">browse-to-buy</span></div>
          <div class="cs-metric"><span class="val">+18%</span><span class="lbl">repeat purchase</span></div>
        </div>
      </div>

      <div class="cs-detail" id="cs1">
        <div class="cs-detail-inner">
          <div class="cs-section">
            <div class="cs-section-label">Problem</div>
            <p>Mafatlal's institutional B2B model left an untapped adjacent market — parents buying school essentials from unorganised retail. No storefront, no B2C revenue history, no product infrastructure existed.</p>
          </div>
          <div class="cs-section">
            <div class="cs-section-label">Key Decisions</div>
            <div class="cs-decisions">
              <div class="cs-decision">
                <div class="cs-decision-title">Prioritised PLP filter architecture before marketing spend</div>
                <div class="cs-decision-desc">A poorly structured catalogue means every product goes live misconfigured. I pushed to solve taxonomy first — post-launch fix tickets dropped significantly.</div>
              </div>
              <div class="cs-decision">
                <div class="cs-decision-title">Seasonal promotions tied to school calendars, not retail events</div>
                <div class="cs-decision-desc">Parents' intent peaks at academic milestones — not Diwali. Structured all promotional logic around term starts and new academic year windows.</div>
              </div>
              <div class="cs-decision">
                <div class="cs-decision-title">Instrumented Mixpanel from Day 1, not as an afterthought</div>
                <div class="cs-decision-desc">You can't optimise a funnel you can't measure. Full GMV/AOV/cart abandonment tracking from week one enabled ranked feature recommendations from day 8.</div>
              </div>
            </div>
          </div>
          <div class="cs-section">
            <div class="cs-section-label">Outcomes</div>
            <div>
              <div class="outcome-row"><span class="outcome-val">+32%</span><span class="outcome-lbl">Parent engagement</span></div>
              <div class="outcome-row"><span class="outcome-val">−24%</span><span class="outcome-lbl">Cart abandonment</span></div>
              <div class="outcome-row"><span class="outcome-val">+19%</span><span class="outcome-lbl">Browse-to-buy conversion</span></div>
              <div class="outcome-row"><span class="outcome-val">+18%</span><span class="outcome-lbl">Repeat purchase rate</span></div>
              <div class="outcome-row"><span class="outcome-val">New</span><span class="outcome-lbl">B2C revenue stream opened from zero</span></div>
            </div>
          </div>
          <div class="cs-section">
            <div class="cs-section-label">Frameworks</div>
            <p style="font-size:13px;color:var(--ink3)">AARRR · RICE prioritisation · JTBD discovery · A/B testing · Funnel analytics (Mixpanel)</p>
          </div>
          <button class="cs-close-btn" onclick="toggleCS('cs1')">↑ collapse</button>
        </div>
      </div>

      <!-- CS 2 -->
      <div class="cs-item" onclick="toggleCS('cs2')">
        <div class="cs-header">
          <span class="cs-num">02 / 2023–2025</span>
          <span class="cs-arrow" id="arr-cs2">↓</span>
        </div>
        <div class="cs-type">AI · EdTech · ERP/LMS</div>
        <div class="cs-title">AI-Powered Education ERP & LMS — Mafatlal Industries</div>
        <div class="cs-summary">Led a unified Education ERP and LMS with an AI chatbot and hybrid grading system. Brought attendance, fees, assignments, grading, and communication under one platform — eliminating five disconnected tools.</div>
        <div class="cs-metrics">
          <div class="cs-metric"><span class="val">+40%</span><span class="lbl">user engagement</span></div>
          <div class="cs-metric"><span class="val">−70%</span><span class="lbl">manual grading effort</span></div>
          <div class="cs-metric"><span class="val">₹200Cr+</span><span class="lbl">revenue impact</span></div>
        </div>
      </div>

      <div class="cs-detail" id="cs2">
        <div class="cs-detail-inner">
          <div class="cs-section">
            <div class="cs-section-label">Problem</div>
            <p>Institutional clients ran attendance, fees, assignments, grading, and parent communication across disconnected tools. Teachers spent hours on manual grading. There was no intelligent layer and no single student progress view.</p>
          </div>
          <div class="cs-section">
            <div class="cs-section-label">Key Decisions</div>
            <div class="cs-decisions">
              <div class="cs-decision">
                <div class="cs-decision-title">Hybrid grading over full AI automation</div>
                <div class="cs-decision-desc">Teachers didn't want to lose authority — they wanted to reduce volume. Three-layer model: AI auto-grades → peer review validates → teacher moderates exceptions. Cut effort 70%, preserved trust.</div>
              </div>
              <div class="cs-decision">
                <div class="cs-decision-title">Scoped chatbot to admin queries, not academic decisions</div>
                <div class="cs-decision-desc">Academic advice carries accountability — it stays with teachers. The chatbot handled fees, schedules, results, and FAQs. High-volume, low-judgment tasks freed teachers for what matters.</div>
              </div>
            </div>
          </div>
          <div class="cs-section">
            <div class="cs-section-label">Outcomes</div>
            <div>
              <div class="outcome-row"><span class="outcome-val">+40%</span><span class="outcome-lbl">User engagement</span></div>
              <div class="outcome-row"><span class="outcome-val">−70%</span><span class="outcome-lbl">Manual grading effort</span></div>
              <div class="outcome-row"><span class="outcome-val">+25%</span><span class="outcome-lbl">Market share growth</span></div>
              <div class="outcome-row"><span class="outcome-val">5</span><span class="outcome-lbl">Institutional clients validated via UAT</span></div>
            </div>
          </div>
          <div class="cs-section">
            <div class="cs-section-label">Frameworks</div>
            <p style="font-size:13px;color:var(--ink3)">JTBD interviews · Kano model · OKR-aligned roadmap · UAT cycles</p>
          </div>
          <button class="cs-close-btn" onclick="toggleCS('cs2')">↑ collapse</button>
        </div>
      </div>

      <!-- CS 3 -->
      <div class="cs-item" onclick="toggleCS('cs3')">
        <div class="cs-header">
          <span class="cs-num">03 / 2023–2025</span>
          <span class="cs-arrow" id="arr-cs3">↓</span>
        </div>
        <div class="cs-type">IoT · Device Management · Compliance</div>
        <div class="cs-title">Centralized Device Management System — Mafatlal Industries</div>
        <div class="cs-summary">Designed a device management platform with real-time asset tracking, geo-fencing, and remote intervention. Wrote epics and user stories for enrolment, policy enforcement, remote wipe, and compliance reporting.</div>
        <div class="cs-metrics">
          <div class="cs-metric"><span class="val">5</span><span class="lbl">clients UAT validated</span></div>
          <div class="cs-metric"><span class="val">+20%</span><span class="lbl">sprint predictability</span></div>
        </div>
      </div>

      <div class="cs-detail" id="cs3">
        <div class="cs-detail-inner">
          <div class="cs-section">
            <div class="cs-section-label">Problem</div>
            <p>No centralised visibility over device fleets. Devices went missing with no audit trail, policies were inconsistently enforced, and compliance reporting was entirely manual — spreadsheets and physical checks.</p>
          </div>
          <div class="cs-section">
            <div class="cs-section-label">Key Decisions</div>
            <div class="cs-decisions">
              <div class="cs-decision">
                <div class="cs-decision-title">Geo-fencing as a first-class feature, not a setting</div>
                <div class="cs-decision-desc">Off-campus device use was the #1 misuse pattern. Making geo-fencing prominent — not buried in settings — drove admin adoption and surfaced compliance issues immediately.</div>
              </div>
              <div class="cs-decision">
                <div class="cs-decision-title">Remote wipe with mandatory two-step confirmation</div>
                <div class="cs-decision-desc">A misclick on remote wipe is irreversible. Added intentional friction — two separate confirmations required — protecting against accidental data loss while keeping the feature accessible.</div>
              </div>
            </div>
          </div>
          <div class="cs-section">
            <div class="cs-section-label">Outcomes</div>
            <div>
              <div class="outcome-row"><span class="outcome-val">5</span><span class="outcome-lbl">Institutional clients validated via UAT</span></div>
              <div class="outcome-row"><span class="outcome-val">+20%</span><span class="outcome-lbl">Sprint predictability</span></div>
              <div class="outcome-row"><span class="outcome-val">Live</span><span class="outcome-lbl">Real-time asset tracking & geo-fencing</span></div>
              <div class="outcome-row"><span class="outcome-val">Zero</span><span class="outcome-lbl">Accidental wipe incidents post-launch</span></div>
            </div>
          </div>
          <div class="cs-section">
            <div class="cs-section-label">Frameworks</div>
            <p style="font-size:13px;color:var(--ink3)">MoSCoW · User story mapping · UAT-driven validation · Sprint retrospectives</p>
          </div>
          <button class="cs-close-btn" onclick="toggleCS('cs3')">↑ collapse</button>
        </div>
      </div>

    </div>
  </div>

  <!-- ══ SKILLS ══ -->
  <div id="page-skills" class="page">
    <div class="page-eyebrow">Skills</div>
    <h2 class="page-title">Built across 2+ years of hands-on platform ownership.</h2>

    <div class="skills-grid">
      <div class="skill-row">
        <div class="skill-cat">Product</div>
        <div class="skill-items">
          <span class="skill-pill">Product Strategy</span>
          <span class="skill-pill">Roadmapping</span>
          <span class="skill-pill">PRDs</span>
          <span class="skill-pill">User Stories</span>
          <span class="skill-pill">Agile / Scrum</span>
          <span class="skill-pill">Sprint Planning</span>
          <span class="skill-pill">Backlog Grooming</span>
          <span class="skill-pill">GTM Strategy</span>
          <span class="skill-pill">UAT</span>
          <span class="skill-pill">Stakeholder Mgmt</span>
        </div>
      </div>
      <div class="skill-row">
        <div class="skill-cat">E-commerce</div>
        <div class="skill-items">
          <span class="skill-pill">Shopify</span>
          <span class="skill-pill">CRO</span>
          <span class="skill-pill">PLP / PDP Optimisation</span>
          <span class="skill-pill">Funnel Optimisation</span>
          <span class="skill-pill">Cross-sell Logic</span>
          <span class="skill-pill">Merchandising</span>
          <span class="skill-pill">D2C</span>
          <span class="skill-pill">SEO / AEO</span>
        </div>
      </div>
      <div class="skill-row">
        <div class="skill-cat">Analytics</div>
        <div class="skill-items">
          <span class="skill-pill">Mixpanel</span>
          <span class="skill-pill">GA4</span>
          <span class="skill-pill">A/B Testing</span>
          <span class="skill-pill">AARRR</span>
          <span class="skill-pill">GMV / AOV / CLTV</span>
          <span class="skill-pill">NPS</span>
          <span class="skill-pill">Feature Adoption</span>
          <span class="skill-pill">KPI Tracking</span>
        </div>
      </div>
      <div class="skill-row">
        <div class="skill-cat">AI & Platforms</div>
        <div class="skill-items">
          <span class="skill-pill">AI Product Design</span>
          <span class="skill-pill">LLM Chatbot Spec</span>
          <span class="skill-pill">Hybrid Grading</span>
          <span class="skill-pill">ERP / LMS</span>
          <span class="skill-pill">Device Management</span>
          <span class="skill-pill">Workflow Automation</span>
        </div>
      </div>
      <div class="skill-row">
        <div class="skill-cat">Tools</div>
        <div class="skill-items">
          <span class="skill-pill">Jira</span>
          <span class="skill-pill">Confluence</span>
          <span class="skill-pill">Figma</span>
          <span class="skill-pill">Google Analytics</span>
          <span class="skill-pill">Notion</span>
        </div>
      </div>
    </div>

    <div class="divider"></div>
    <div style="font-family:var(--mono);font-size:11px;letter-spacing:.1em;text-transform:uppercase;color:var(--ink3);margin-bottom:1.25rem">PM Frameworks I apply regularly</div>
    <table class="fw-table">
      <thead>
        <tr>
          <th>Framework</th>
          <th>How I apply it</th>
        </tr>
      </thead>
      <tbody>
        <tr><td>RICE</td><td>Feature prioritisation across sprint backlogs — reach, impact, confidence, effort</td></tr>
        <tr><td>JTBD</td><td>Structuring discovery interviews — "When I'm doing X, I want to Y, so I can Z"</td></tr>
        <tr><td>Kano Model</td><td>Distinguishing hygiene features from delighters in early roadmap scoping</td></tr>
        <tr><td>MoSCoW</td><td>Scope negotiation with stakeholders during UAT and GTM planning</td></tr>
        <tr><td>AARRR</td><td>End-to-end funnel tracking on both e-commerce and LMS platforms</td></tr>
        <tr><td>OKRs</td><td>Tying roadmap items explicitly to institution/business-level goals</td></tr>
        <tr><td>Design Thinking</td><td>Problem framing and user research before writing a single user story</td></tr>
      </tbody>
    </table>
  </div>

  <!-- ══ CONTACT ══ -->
  <div id="page-contact" class="page">
    <div class="page-eyebrow">Contact</div>
    <h2 class="page-title">Open to Senior PM roles and select consulting engagements.</h2>

    <p class="contact-intro">"Let's build something worth shipping."</p>

    <div class="contact-list">
      <div class="contact-item">
        <span class="contact-label">Email</span>
        <a href="mailto:9shivam4@gmail.com" class="contact-val">9shivam4@gmail.com</a>
      </div>
      <div class="contact-item">
        <span class="contact-label">Phone</span>
        <a href="tel:+919462696994" class="contact-val">+91 94626 96994</a>
      </div>
      <div class="contact-item">
        <span class="contact-label">LinkedIn</span>
        <a href="https://www.linkedin.com/in/shivamsoni29/" target="_blank" class="contact-val">linkedin.com/in/shivamsoni29 ↗</a>
      </div>
      <div class="contact-item">
        <span class="contact-label">Location</span>
        <span class="contact-val">Jaipur, India · Open to remote & relocation</span>
      </div>
      <div class="contact-item">
        <span class="contact-label">Looking for</span>
        <span class="contact-val">Senior PM · D2C / E-commerce · AI Products · EdTech SaaS</span>
      </div>
    </div>
    <div class="avail-badge">
      <div class="avail-dot"></div>
      AVAILABLE NOW · ACTIVELY INTERVIEWING
    </div>
  </div>

</main>

<footer>
  <span>Shivam Soni · Product Manager</span>
  <span>Jaipur, India · 2025</span>
</footer>

<script>
  function showPage(id) {
    document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
    document.querySelectorAll('.nav-links a').forEach(a => a.classList.remove('active'));
    document.getElementById('page-' + id).classList.add('active');
    const navEl = document.getElementById('nav-' + id);
    if (navEl) navEl.classList.add('active');
    window.scrollTo({ top: 0, behavior: 'smooth' });
    return false;
  }

  function toggleCS(id) {
    const detail = document.getElementById(id);
    const arrow = document.getElementById('arr-' + id);
    const isOpen = detail.classList.contains('open');
    // Close all
    document.querySelectorAll('.cs-detail').forEach(d => d.classList.remove('open'));
    document.querySelectorAll('[id^="arr-"]').forEach(a => a.textContent = '↓');
    if (!isOpen) {
      detail.classList.add('open');
      arrow.textContent = '↑';
      detail.scrollIntoView({ behavior: 'smooth', block: 'nearest' });
    }
  }

  document.querySelectorAll('nav a, .hero-link, button').forEach(el => {
    el.addEventListener('click', e => e.preventDefault ? null : null);
  });
</script>

</body>
</html>
