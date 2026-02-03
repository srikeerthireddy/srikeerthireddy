<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Y Sri Keerthi — Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Rajdhani:wght@300;400;500;600;700&family=Share+Tech+Mono&display=swap" rel="stylesheet"/>
<style>
/* ─── RESET & ROOT ─── */
*, *::before, *::after { margin:0; padding:0; box-sizing:border-box; }

:root {
  --clr-bg:        #060a14;
  --clr-surface:   rgba(14,20,38,0.72);
  --clr-border:    rgba(99,102,241,0.25);
  --clr-accent1:   #6366f1;   /* indigo */
  --clr-accent2:   #06b6d4;   /* cyan  */
  --clr-accent3:   #a855f7;   /* purple */
  --clr-accent4:   #f59e0b;   /* amber  */
  --clr-text:      #e2e8f0;
  --clr-text-dim:  #7d8aa0;
  --font-display: 'Orbitron', sans-serif;
  --font-body:    'Rajdhani', sans-serif;
  --font-mono:    'Share Tech Mono', monospace;
  --glass:        backdrop-filter: blur(18px) saturate(1.4);
  --shadow-glow:  0 0 40px rgba(99,102,241,0.18), 0 8px 32px rgba(0,0,0,0.4);
}

html { scroll-behavior: smooth; }

body {
  background: var(--clr-bg);
  color: var(--clr-text);
  font-family: var(--font-body);
  min-height: 100vh;
  overflow-x: hidden;
  line-height: 1.6;
}

/* ─── ANIMATED BG LAYER ─── */
.bg-layer {
  position: fixed; inset: 0; z-index: 0;
  background:
    radial-gradient(ellipse 80% 50% at 20% 20%, rgba(99,102,241,0.12) 0%, transparent 70%),
    radial-gradient(ellipse 60% 40% at 80% 70%, rgba(6,182,212,0.10) 0%, transparent 70%),
    radial-gradient(ellipse 50% 50% at 50% 90%, rgba(168,85,247,0.08) 0%, transparent 70%);
  animation: bgShift 18s ease-in-out infinite alternate;
}
@keyframes bgShift {
  0%   { transform: scale(1) rotate(0deg); }
  100% { transform: scale(1.12) rotate(3deg); }
}

/* ─── GRID OVERLAY ─── */
.grid-overlay {
  position: fixed; inset: 0; z-index: 0; pointer-events: none;
  background-image:
    linear-gradient(rgba(99,102,241,0.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(99,102,241,0.04) 1px, transparent 1px);
  background-size: 60px 60px;
  mask-image: radial-gradient(ellipse 70% 70% at center, black 30%, transparent 100%);
  -webkit-mask-image: radial-gradient(ellipse 70% 70% at center, black 30%, transparent 100%);
}

/* ─── CANVAS (PARTICLES) ─── */
canvas#particles { position:fixed; inset:0; z-index:1; pointer-events:none; }

/* ─── MAIN CONTENT ─── */
.content { position:relative; z-index:2; max-width:960px; margin:0 auto; padding:40px 24px 80px; }

/* ─── HERO ─── */
.hero {
  text-align:center;
  padding: 80px 0 60px;
  position: relative;
}

/* avatar ring */
.avatar-wrap {
  width:140px; height:140px; margin:0 auto 28px;
  position:relative;
  perspective: 600px;
}
.avatar-ring {
  width:100%; height:100%;
  border-radius:50%;
  background: conic-gradient(from 200deg, var(--clr-accent1), var(--clr-accent2), var(--clr-accent3), var(--clr-accent1));
  padding: 4px;
  animation: spin 4s linear infinite;
}
@keyframes spin { to { transform: rotate(360deg); } }
.avatar-inner {
  width:100%; height:100%;
  border-radius:50%;
  background: var(--clr-bg);
  display:flex; align-items:center; justify-content:center;
  font-size: 52px;
}

.hero h1 {
  font-family: var(--font-display);
  font-size: clamp(1.8rem, 5vw, 2.8rem);
  font-weight: 900;
  letter-spacing: 3px;
  text-transform: uppercase;
  background: linear-gradient(135deg, var(--clr-accent1), var(--clr-accent2), var(--clr-accent3));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  filter: drop-shadow(0 0 24px rgba(99,102,241,0.4));
  margin-bottom: 10px;
}

.hero .subtitle {
  font-family: var(--font-mono);
  font-size: 0.95rem;
  color: var(--clr-accent2);
  letter-spacing: 2px;
  margin-bottom: 28px;
  opacity: 0.85;
}

/* social pills */
.social-row { display:flex; flex-wrap:wrap; gap:10px; justify-content:center; }
.social-pill {
  display:inline-flex; align-items:center; gap:7px;
  background: var(--clr-surface);
  border: 1px solid var(--clr-border);
  border-radius: 30px;
  padding: 8px 18px;
  color: var(--clr-text);
  text-decoration: none;
  font-family: var(--font-mono);
  font-size: 0.82rem;
  letter-spacing: 0.5px;
  transition: all .3s cubic-bezier(.4,0,.2,1);
  var(--glass);
  backdrop-filter: blur(12px);
}
.social-pill:hover {
  border-color: var(--clr-accent1);
  box-shadow: 0 0 20px rgba(99,102,241,0.3), inset 0 1px 0 rgba(255,255,255,0.08);
  transform: translateY(-3px) scale(1.03);
  color: #fff;
}
.social-pill .icon { font-size:1rem; }

/* ─── SECTION TITLES ─── */
.section-title {
  font-family: var(--font-display);
  font-size: clamp(1.1rem, 2.5vw, 1.35rem);
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 4px;
  color: var(--clr-text);
  margin-bottom: 28px;
  text-align: center;
  position: relative;
}
.section-title::after {
  content:'';
  display:block;
  width: 60px; height: 3px;
  margin: 10px auto 0;
  background: linear-gradient(90deg, var(--clr-accent1), var(--clr-accent2));
  border-radius: 2px;
  box-shadow: 0 0 12px var(--clr-accent1);
}
.section-title .icon { margin-right:10px; }

/* ─── GLASS CARD ─── */
.glass-card {
  background: var(--clr-surface);
  border: 1px solid var(--clr-border);
  border-radius: 20px;
  padding: 32px;
  backdrop-filter: blur(18px) saturate(1.3);
  -webkit-backdrop-filter: blur(18px) saturate(1.3);
  box-shadow: var(--shadow-glow);
  margin-bottom: 36px;
  position: relative;
  overflow: hidden;
  transition: transform .4s cubic-bezier(.4,0,.2,1), box-shadow .4s;
  transform-style: preserve-3d;
}
.glass-card::before {
  content:'';
  position:absolute;
  inset:0;
  background: linear-gradient(135deg, rgba(99,102,241,0.06) 0%, transparent 50%, rgba(6,182,212,0.04) 100%);
  pointer-events:none;
}
.glass-card:hover {
  transform: translateY(-6px) rotateX(1deg);
  box-shadow: 0 0 60px rgba(99,102,241,0.22), 0 16px 48px rgba(0,0,0,0.5);
  border-color: rgba(99,102,241,0.45);
}

/* ─── ABOUT SECTION ─── */
.about-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 18px;
  margin-top: 8px;
}
.about-item {
  display:flex; align-items:center; gap:12px;
  background: rgba(99,102,241,0.06);
  border: 1px solid rgba(99,102,241,0.12);
  border-radius: 14px;
  padding: 16px 18px;
  transition: background .3s, border-color .3s, transform .3s;
}
.about-item:hover {
  background: rgba(99,102,241,0.12);
  border-color: rgba(99,102,241,0.3);
  transform: translateX(4px);
}
.about-item .ai-icon { font-size:1.5rem; flex-shrink:0; }
.about-item p { font-size:0.92rem; color: var(--clr-text); font-weight:500; }
@media(max-width:600px){ .about-grid { grid-template-columns:1fr; } }

/* ─── TECH STACK ─── */
.tech-category { margin-bottom: 26px; }
.tech-category-title {
  font-family: var(--font-mono);
  font-size: 0.78rem;
  letter-spacing:3px;
  text-transform:uppercase;
  color: var(--clr-accent2);
  margin-bottom:12px;
  padding-left: 4px;
}
.tech-row { display:flex; flex-wrap:wrap; gap:10px; }

/* 3D tech badge */
.tech-badge {
  display:inline-flex; align-items:center; gap:9px;
  background: rgba(14,20,38,0.85);
  border: 1px solid rgba(99,102,241,0.2);
  border-radius: 12px;
  padding: 10px 16px;
  font-family: var(--font-body);
  font-size: 0.88rem;
  font-weight: 600;
  color: var(--clr-text);
  position: relative;
  transition: all .35s cubic-bezier(.4,0,.2,1);
  transform-style: preserve-3d;
  box-shadow: 0 4px 12px rgba(0,0,0,0.3), inset 0 1px 0 rgba(255,255,255,0.06);
}
.tech-badge:hover {
  transform: translateY(-4px) rotateX(5deg) rotateZ(-1deg);
  border-color: var(--clr-accent1);
  box-shadow: 0 8px 28px rgba(99,102,241,0.3), inset 0 1px 0 rgba(255,255,255,0.1);
}
.tech-badge .tb-dot {
  width:10px; height:10px; border-radius:50%;
  box-shadow: 0 0 8px currentColor;
  flex-shrink:0;
}

/* concept tags */
.concept-tag {
  display:inline-block;
  background: linear-gradient(135deg, rgba(99,102,241,0.12), rgba(168,85,247,0.1));
  border: 1px solid rgba(168,85,247,0.22);
  border-radius: 20px;
  padding: 6px 16px;
  font-family: var(--font-mono);
  font-size: 0.76rem;
  color: var(--clr-accent3);
  letter-spacing:1px;
  transition: all .3s;
}
.concept-tag:hover {
  background: rgba(168,85,247,0.2);
  border-color: var(--clr-accent3);
  box-shadow: 0 0 14px rgba(168,85,247,0.25);
  transform: scale(1.05);
}

/* ─── EXPERIENCE CARD ─── */
.exp-header {
  display:flex; align-items:flex-start; justify-content:space-between; flex-wrap:wrap; gap:10px;
  margin-bottom: 18px;
}
.exp-company { font-family: var(--font-display); font-size:1.05rem; font-weight:700; letter-spacing:1px; color:#fff; }
.exp-role { font-family: var(--font-mono); font-size:0.82rem; color: var(--clr-accent2); margin-top:3px; }
.exp-date {
  font-family: var(--font-mono);
  font-size: 0.76rem;
  color: var(--clr-text-dim);
  background: rgba(6,182,212,0.1);
  border: 1px solid rgba(6,182,212,0.2);
  border-radius: 20px;
  padding: 4px 14px;
  white-space: nowrap;
}
.exp-bullets { list-style:none; margin-bottom:20px; }
.exp-bullets li {
  padding: 7px 0 7px 24px;
  position:relative;
  font-size:0.9rem;
  color: var(--clr-text);
}
.exp-bullets li::before {
  content:'';
  position:absolute; left:0; top:14px;
  width:8px; height:8px; border-radius:50%;
  background: linear-gradient(135deg, var(--clr-accent1), var(--clr-accent2));
  box-shadow: 0 0 8px var(--clr-accent1);
}

/* ─── PROJECT CARD ─── */
.project-card {
  border-radius:18px;
  padding: 28px;
  background: linear-gradient(135deg, rgba(6,182,212,0.06), rgba(99,102,241,0.06));
  border: 1px solid rgba(6,182,212,0.18);
  margin-bottom: 20px;
  transition: all .35s;
  position:relative; overflow:hidden;
}
.project-card::before {
  content:'';
  position:absolute; top:-40px; right:-40px;
  width:140px; height:140px;
  border-radius:50%;
  background: radial-gradient(circle, rgba(6,182,212,0.12), transparent 70%);
  pointer-events:none;
}
.project-card:hover {
  border-color: rgba(6,182,212,0.4);
  box-shadow: 0 0 40px rgba(6,182,212,0.15);
  transform: translateY(-4px);
}
.project-name {
  font-family: var(--font-display);
  font-size: 1rem;
  font-weight:700;
  letter-spacing:1px;
  color:#fff;
  margin-bottom:4px;
}
.project-desc { font-size:0.88rem; color: var(--clr-text-dim); margin-bottom:16px; }
.project-features { list-style:none; margin-bottom:18px; }
.project-features li {
  font-size:0.87rem; color: var(--clr-text);
  padding: 4px 0 4px 20px;
  position:relative;
}
.project-features li::before {
  content:'›'; position:absolute; left:2px; color: var(--clr-accent2); font-weight:700; font-size:1.1rem;
}
.project-links { display:flex; gap:14px; flex-wrap:wrap; }
.project-link {
  font-family: var(--font-mono);
  font-size:0.77rem;
  color: var(--clr-accent2);
  text-decoration:none;
  border:1px solid rgba(6,182,212,0.25);
  border-radius:8px;
  padding:5px 14px;
  transition: all .3s;
}
.project-link:hover { background: rgba(6,182,212,0.12); border-color: var(--clr-accent2); }

/* ─── EDUCATION ─── */
.edu-row {
  display:grid; grid-template-columns:1fr 1fr; gap:16px;
}
.edu-item {
  background: rgba(168,85,247,0.06);
  border: 1px solid rgba(168,85,247,0.15);
  border-radius:14px;
  padding:18px 20px;
  transition: all .3s;
}
.edu-item:hover { border-color: rgba(168,85,247,0.35); background: rgba(168,85,247,0.1); transform: translateY(-3px); }
.edu-label { font-family: var(--font-mono); font-size:0.72rem; color: var(--clr-accent3); letter-spacing:2px; text-transform:uppercase; margin-bottom:4px; }
.edu-value { font-size:0.92rem; font-weight:600; color:#fff; }
@media(max-width:550px){ .edu-row { grid-template-columns:1fr; } }

/* ─── ACHIEVEMENTS ─── */
.ach-list { list-style:none; }
.ach-item {
  display:flex; align-items:center; gap:14px;
  padding: 14px 18px;
  border-radius: 12px;
  border: 1px solid transparent;
  background: rgba(245,158,11,0.04);
  margin-bottom: 10px;
  transition: all .3s;
  position:relative; overflow:hidden;
}
.ach-item::before {
  content:'';
  position:absolute; left:0; top:0; bottom:0;
  width:3px;
  background: linear-gradient(180deg, var(--clr-accent4), var(--clr-accent3));
}
.ach-item:hover {
  background: rgba(245,158,11,0.09);
  border-color: rgba(245,158,11,0.2);
  transform: translateX(6px);
}
.ach-medal { font-size:1.3rem; flex-shrink:0; }
.ach-text { font-size:0.9rem; font-weight:500; color: var(--clr-text); }

/* ─── FOOTER ─── */
.footer {
  text-align:center;
  padding-top:20px;
  font-family: var(--font-mono);
  font-size:0.78rem;
  color: var(--clr-text-dim);
  letter-spacing:1px;
}
.footer .cta {
  display:inline-block;
  margin-bottom:16px;
  background: linear-gradient(135deg, var(--clr-accent1), var(--clr-accent3));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  font-family: var(--font-display);
  font-size:1rem;
  font-weight:700;
  letter-spacing:2px;
  text-transform:uppercase;
}

/* ─── SCROLLBAR ─── */
::-webkit-scrollbar { width:6px; }
::-webkit-scrollbar-track { background: var(--clr-bg); }
::-webkit-scrollbar-thumb { background: var(--clr-accent1); border-radius:3px; }

/* ─── STAGGERED ENTRANCE ─── */
.reveal {
  opacity:0; transform: translateY(30px);
  transition: opacity .7s cubic-bezier(.4,0,.2,1), transform .7s cubic-bezier(.4,0,.2,1);
}
.reveal.visible { opacity:1; transform: translateY(0); }
</style>
</head>
<body>

<!-- BG LAYERS -->
<div class="bg-layer"></div>
<div class="grid-overlay"></div>
<canvas id="particles"></canvas>

<!-- MAIN -->
<div class="content">

  <!-- ═══ HERO ═══ -->
  <section class="hero reveal">
    <div class="avatar-wrap">
      <div class="avatar-ring">
        <div class="avatar-inner">🚀</div>
      </div>
    </div>
    <h1>Y Sri Keerthi</h1>
    <p class="subtitle">⟨ Full-Stack Engineer · Backend-Focused · CS @ Kalvium ⟩</p>
    <div class="social-row">
      <a href="https://www.linkedin.com/in/sri-keerthi-y/" class="social-pill" target="_blank"><span class="icon">💼</span> LinkedIn</a>
      <a href="https://portfolio-srikeerthi.vercel.app/" class="social-pill" target="_blank"><span class="icon">🌐</span> Portfolio</a>
      <a href="https://leetcode.com/u/srikeerthireddy/" class="social-pill" target="_blank"><span class="icon">⚡</span> LeetCode</a>
      <a href="mailto:srikeerthireddy24@gmail.com" class="social-pill"><span class="icon">✉️</span> Email</a>
    </div>
  </section>

  <!-- ═══ ABOUT ═══ -->
  <section class="reveal">
    <h2 class="section-title"><span class="icon">🎯</span> About Me</h2>
    <div class="glass-card">
      <div class="about-grid">
        <div class="about-item"><span class="ai-icon">🚀</span><p>Backend-focused <strong>Full-Stack Engineer</strong></p></div>
        <div class="about-item"><span class="ai-icon">🌐</span><p>Passionate about <strong>scalable systems</strong> & cloud-native architectures</p></div>
        <div class="about-item"><span class="ai-icon">🗄️</span><p>Strong in <strong>system design</strong>, databases & performance optimization</p></div>
        <div class="about-item"><span class="ai-icon">🎓</span><p>CS Undergraduate @ <strong>Kalvium (Apollo University)</strong></p></div>
        <div class="about-item"><span class="ai-icon">✔️</span><p>Design & develop <strong>RESTful APIs</strong></p></div>
        <div class="about-item"><span class="ai-icon">⚙️</span><p>Deploy & maintain <strong>production-grade applications</strong></p></div>
        <div class="about-item"><span class="ai-icon">📦</span><p>Work with <strong>databases, caching</strong> & async job queues</p></div>
        <div class="about-item"><span class="ai-icon">🔥</span><p>Always building. Always <strong>learning</strong>. Always shipping.</p></div>
      </div>
    </div>
  </section>

  <!-- ═══ TECH STACK ═══ -->
  <section class="reveal">
    <h2 class="section-title"><span class="icon">🛠️</span> Tech Stack</h2>
    <div class="glass-card">

      <div class="tech-category">
        <div class="tech-category-title">// Programming Languages</div>
        <div class="tech-row">
          <div class="tech-badge"><span class="tb-dot" style="color:#00599C;background:#00599C;"></span> C++</div>
          <div class="tech-badge"><span class="tb-dot" style="color:#ED8B00;background:#ED8B00;"></span> Java</div>
          <div class="tech-badge"><span class="tb-dot" style="color:#3572A5;background:#3572A5;"></span> Python</div>
          <div class="tech-badge"><span class="tb-dot" style="color:#F7DF1E;background:#F7DF1E;"></span> JavaScript</div>
        </div>
      </div>

      <div class="tech-category">
        <div class="tech-category-title">// Frontend</div>
        <div class="tech-row">
          <div class="tech-badge"><span class="tb-dot" style="color:#61DAFB;background:#61DAFB;"></span> React.js</div>
          <div class="tech-badge"><span class="tb-dot" style="color:#ffffff;background:#ffffff;"></span> Next.js</div>
          <div class="tech-badge"><span class="tb-dot" style="color:#06B6D4;background:#06B6D4;"></span> Tailwind CSS</div>
        </div>
      </div>

      <div class="tech-category">
        <div class="tech-category-title">// Backend</div>
        <div class="tech-row">
          <div class="tech-badge"><span class="tb-dot" style="color:#339933;background:#339933;"></span> Node.js</div>
          <div class="tech-badge"><span class="tb-dot" style="color:#aaaaaa;background:#aaaaaa;"></span> Express.js</div>
          <div class="tech-badge"><span class="tb-dot" style="color:#00ADD8;background:#00ADD8;"></span> Go (Golang)</div>
        </div>
      </div>

      <div class="tech-category">
        <div class="tech-category-title">// Databases & Caching</div>
        <div class="tech-row">
          <div class="tech-badge"><span class="tb-dot" style="color:#47A248;background:#47A248;"></span> MongoDB</div>
          <div class="tech-badge"><span class="tb-dot" style="color:#336791;background:#336791;"></span> PostgreSQL</div>
          <div class="tech-badge"><span class="tb-dot" style="color:#D00000;background:#D00000;"></span> Redis</div>
        </div>
      </div>

      <div class="tech-category">
        <div class="tech-category-title">// DevOps & Tools</div>
        <div class="tech-row">
          <div class="tech-badge"><span class="tb-dot" style="color:#F05032;background:#F05032;"></span> Git</div>
          <div class="tech-badge"><span class="tb-dot" style="color:#ffffff;background:#ffffff;"></span> GitHub</div>
          <div class="tech-badge"><span class="tb-dot" style="color:#2496ED;background:#2496ED;"></span> Docker</div>
          <div class="tech-badge"><span class="tb-dot" style="color:#aaaaaa;background:#aaaaaa;"></span> GitHub Actions</div>
          <div class="tech-badge"><span class="tb-dot" style="color:#FF6365;background:#FF6365;"></span> Postman</div>
          <div class="tech-badge"><span class="tb-dot" style="color:#ffffff;background:#ffffff;"></span> Vercel</div>
        </div>
      </div>

      <div class="tech-category">
        <div class="tech-category-title">// Concepts & Libraries</div>
        <div class="tech-row">
          <span class="concept-tag">OOP</span>
          <span class="concept-tag">DSA</span>
          <span class="concept-tag">API Testing</span>
          <span class="concept-tag">JWT Auth</span>
          <span class="concept-tag">BullMQ</span>
          <span class="concept-tag">Node-Cron</span>
          <span class="concept-tag">Ably</span>
        </div>
      </div>

    </div>
  </section>

  <!-- ═══ EXPERIENCE ═══ -->
  <section class="reveal">
    <h2 class="section-title"><span class="icon">💼</span> Experience</h2>
    <div class="glass-card">
      <div class="exp-header">
        <div>
          <div class="exp-company">🏈 ShotGun Fantasy</div>
          <div class="exp-role">Backend Developer Intern</div>
        </div>
        <div class="exp-date">Jul 2025 – Jan 2026</div>
      </div>
      <ul class="exp-bullets">
        <li>Built and optimized backend services for an <strong>NFL Fantasy Sports Platform</strong></li>
        <li>Improved <strong>API response time & system stability</strong> for high-traffic draft workflows</li>
        <li>Contributed to the <strong>Draft Room module</strong> used during live fantasy drafts</li>
      </ul>
      <div class="tech-row">
        <div class="tech-badge"><span class="tb-dot" style="color:#339933;background:#339933;"></span> Node.js</div>
        <div class="tech-badge"><span class="tb-dot" style="color:#00ADD8;background:#00ADD8;"></span> Golang</div>
        <div class="tech-badge"><span class="tb-dot" style="color:#aaaaaa;background:#aaaaaa;"></span> Express.js</div>
        <div class="tech-badge"><span class="tb-dot" style="color:#336791;background:#336791;"></span> PostgreSQL</div>
        <div class="tech-badge"><span class="tb-dot" style="color:#D00000;background:#D00000;"></span> Redis</div>
        <div class="tech-badge"><span class="tb-dot" style="color:#2496ED;background:#2496ED;"></span> Docker</div>
      </div>
    </div>
  </section>

  <!-- ═══ PROJECTS ═══ -->
  <section class="reveal">
    <h2 class="section-title"><span class="icon">🚀</span> Projects</h2>
    <div class="glass-card">
      <div class="project-card">
        <div class="project-name">🌿 Calm Corner</div>
        <div class="project-desc">Mental Health & Mindfulness Platform</div>
        <ul class="project-features">
          <li>Built a responsive platform for <strong>emotion tracking & mindfulness</strong></li>
          <li>Implemented <strong>secure JWT authentication</strong> and scalable backend APIs</li>
          <li>Automated <strong>CI/CD pipelines</strong> for production deployment via GitHub Actions</li>
        </ul>
        <div class="tech-row" style="margin-bottom:18px;">
          <div class="tech-badge"><span class="tb-dot" style="color:#61DAFB;background:#61DAFB;"></span> React.js</div>
          <div class="tech-badge"><span class="tb-dot" style="color:#ED8538;background:#ED8538;"></span> Chakra UI</div>
          <div class="tech-badge"><span class="tb-dot" style="color:#aaaaaa;background:#aaaaaa;"></span> Express.js</div>
          <div class="tech-badge"><span class="tb-dot" style="color:#47A248;background:#47A248;"></span> MongoDB</div>
          <div class="tech-badge"><span class="tb-dot" style="color:#ffffff;background:#ffffff;"></span> JWT</div>
          <div class="tech-badge"><span class="tb-dot" style="color:#aaaaaa;background:#aaaaaa;"></span> GitHub Actions</div>
        </div>
        <div class="project-links">
          <span class="project-link">🔗 GitHub — Coming Soon</span>
          <span class="project-link">🌐 Live Demo — Coming Soon</span>
        </div>
      </div>
    </div>
  </section>

  <!-- ═══ EDUCATION ═══ -->
  <section class="reveal">
    <h2 class="section-title"><span class="icon">🎓</span> Education</h2>
    <div class="glass-card">
      <div class="edu-row">
        <div class="edu-item"><div class="edu-label">Degree</div><div class="edu-value">B.Tech in Software Engineering</div></div>
        <div class="edu-item"><div class="edu-label">University</div><div class="edu-value">Apollo University, Chittoor</div></div>
        <div class="edu-item"><div class="edu-label">Program</div><div class="edu-value">Kalvium UG Program</div></div>
        <div class="edu-item"><div class="edu-label">Duration</div><div class="edu-value">2023 – 2027</div></div>
      </div>
    </div>
  </section>

  <!-- ═══ ACHIEVEMENTS ═══ -->
  <section class="reveal">
    <h2 class="section-title"><span class="icon">🏆</span> Achievements</h2>
    <div class="glass-card">
      <ul class="ach-list">
        <li class="ach-item"><span class="ach-medal">🏅</span><span class="ach-text">Backend Engineering Intern @ <strong>ShotGun Fantasy</strong></span></li>
        <li class="ach-item"><span class="ach-medal">🏅</span><span class="ach-text">Full-Stack Programming <strong>Certification</strong></span></li>
        <li class="ach-item"><span class="ach-medal">🏅</span><span class="ach-text">SQL Database & <strong>Optimization</strong></span></li>
        <li class="ach-item"><span class="ach-medal">🏅</span><span class="ach-text">Google <strong>Cloud Computing</strong></span></li>
        <li class="ach-item"><span class="ach-medal">🏅</span><span class="ach-text">Deployed <strong>4+ Production-Grade Applications</strong></span></li>
      </ul>
    </div>
  </section>

  <!-- ═══ FOOTER ═══ -->
  <footer class="footer reveal">
    <div class="cta">⭐ Always open to learning, building & collaborating</div><br/>
    <span>Crafted with depth · Powered by curiosity</span>
  </footer>

</div><!-- /content -->

<!-- ═══ SCRIPTS ═══ -->
<script>
// ─── PARTICLE SYSTEM ───
(function(){
  const c = document.getElementById('particles');
  const ctx = c.getContext('2d');
  let W, H, pts = [], mouse = {x:-999,y:-999};

  function resize(){ W=c.width=innerWidth; H=c.height=innerHeight; }
  resize(); window.addEventListener('resize', resize);

  class P {
    constructor(){
      this.reset();
    }
    reset(){
      this.x = Math.random()*W;
      this.y = Math.random()*H;
      this.r = Math.random()*1.8+0.4;
      this.vx = (Math.random()-.5)*.6;
      this.vy = (Math.random()-.5)*.6;
      this.a = Math.random()*.5+.15;
      this.hue = 220+Math.random()*40; // indigo-cyan range
    }
    update(){
      this.x+=this.vx; this.y+=this.vy;
      if(this.x<0||this.x>W) this.vx*=-1;
      if(this.y<0||this.y>H) this.vy*=-1;
      // subtle mouse repel
      let dx=this.x-mouse.x, dy=this.y-mouse.y, d=Math.sqrt(dx*dx+dy*dy);
      if(d<120){ let f=80/d; this.vx+=dx/d*f*0.02; this.vy+=dy/d*f*0.02; }
    }
    draw(){
      ctx.beginPath();
      ctx.arc(this.x, this.y, this.r, 0, Math.PI*2);
      ctx.fillStyle=`hsla(${this.hue},70%,65%,${this.a})`;
      ctx.fill();
    }
  }

  for(let i=0;i<70;i++) pts.push(new P());

  function lines(){
    for(let i=0;i<pts.length;i++){
      for(let j=i+1;j<pts.length;j++){
        let dx=pts[i].x-pts[j].x, dy=pts[i].y-pts[j].y;
        let d=Math.sqrt(dx*dx+dy*dy);
        if(d<130){
          ctx.beginPath();
          ctx.moveTo(pts[i].x, pts[i].y);
          ctx.lineTo(pts[j].x, pts[j].y);
          let a=1-d/130;
          ctx.strokeStyle=`hsla(230,65%,65%,${a*0.12})`;
          ctx.lineWidth=1;
          ctx.stroke();
        }
      }
    }
  }

  function loop(){
    ctx.clearRect(0,0,W,H);
    pts.forEach(p=>{p.update();p.draw();});
    lines();
    requestAnimationFrame(loop);
  }
  loop();

  document.addEventListener('mousemove',e=>{mouse.x=e.clientX;mouse.y=e.clientY;});
})();

// ─── SCROLL REVEAL ───
(function(){
  const els = document.querySelectorAll('.reveal');
  const obs = new IntersectionObserver(entries=>{
    entries.forEach(e=>{
      if(e.isIntersecting){ e.target.classList.add('visible'); }
    });
  },{ threshold:0.15 });
  els.forEach(el=>obs.observe(el));
})();

// ─── 3D TILT on glass-card (mouse tracking) ───
(function(){
  document.querySelectorAll('.glass-card').forEach(card=>{
    card.addEventListener('mousemove', e=>{
      let rect=card.getBoundingClientRect();
      let x=e.clientX-rect.left, y=e.clientY-rect.top;
      let cx=rect.width/2, cy=rect.height/2;
      let rx=((y-cy)/cy)*-4;  // max ±4 deg
      let ry=((x-cx)/cx)*4;
      card.style.transform=`translateY(-6px) rotateX(${rx}deg) rotateY(${ry}deg)`;
    });
    card.addEventListener('mouseleave', ()=>{
      card.style.transform='translateY(0) rotateX(0deg) rotateY(0deg)';
      card.style.transition='transform .5s cubic-bezier(.4,0,.2,1)';
      setTimeout(()=>card.style.transition='',500);
    });
    card.addEventListener('mouseenter', ()=>{ card.style.transition=''; });
  });
})();
</script>
</body>
</html>
