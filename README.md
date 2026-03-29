
<style>
  @import url('https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;700;800&display=swap');

  * { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #0d0d0f;
    --surface: #141417;
    --surface2: #1c1c21;
    --border: rgba(255,255,255,0.07);
    --accent: #6C63FF;
    --accent2: #FF6B6B;
    --accent3: #43E8C0;
    --text: #f0eff5;
    --muted: #8886a0;
    --mono: 'Space Mono', monospace;
    --sans: 'Syne', sans-serif;
  }

  body { background: var(--bg); color: var(--text); font-family: var(--sans); min-height: 100vh; padding: 0; }

  .hero {
    position: relative;
    padding: 56px 40px 48px;
    overflow: hidden;
    border-bottom: 1px solid var(--border);
  }

  .hero-bg {
    position: absolute; inset: 0; overflow: hidden; pointer-events: none;
  }

  .blob {
    position: absolute;
    border-radius: 50%;
    filter: blur(80px);
    opacity: 0.18;
    animation: drift 8s ease-in-out infinite alternate;
  }

  .blob-1 { width: 300px; height: 300px; background: var(--accent); top: -80px; left: -60px; animation-delay: 0s; }
  .blob-2 { width: 220px; height: 220px; background: var(--accent3); bottom: -60px; right: 20px; animation-delay: 3s; }
  .blob-3 { width: 180px; height: 180px; background: var(--accent2); top: 50%; left: 60%; animation-delay: 1.5s; }

  @keyframes drift {
    from { transform: translate(0,0) scale(1); }
    to { transform: translate(20px, 15px) scale(1.08); }
  }

  .grid-lines {
    position: absolute; inset: 0;
    background-image: linear-gradient(rgba(255,255,255,0.025) 1px, transparent 1px), linear-gradient(90deg, rgba(255,255,255,0.025) 1px, transparent 1px);
    background-size: 40px 40px;
  }

  .hero-inner { position: relative; z-index: 2; }

  .badge-row { display: flex; gap: 8px; flex-wrap: wrap; margin-bottom: 20px; }

  .badge {
    font-family: var(--mono);
    font-size: 10px;
    padding: 4px 10px;
    border-radius: 100px;
    border: 1px solid;
    letter-spacing: 0.08em;
  }

  .badge-purple { color: var(--accent); border-color: rgba(108,99,255,0.4); background: rgba(108,99,255,0.08); }
  .badge-green  { color: var(--accent3); border-color: rgba(67,232,192,0.4); background: rgba(67,232,192,0.08); }
  .badge-red    { color: var(--accent2); border-color: rgba(255,107,107,0.4); background: rgba(255,107,107,0.08); }

  .name {
    font-family: var(--sans);
    font-size: clamp(32px, 7vw, 52px);
    font-weight: 800;
    line-height: 1.05;
    letter-spacing: -0.02em;
    margin-bottom: 6px;
  }

  .name span { color: var(--accent); }

  .tagline {
    font-family: var(--mono);
    font-size: 13px;
    color: var(--muted);
    margin-bottom: 28px;
  }

  .tagline .cursor {
    display: inline-block;
    width: 2px;
    height: 14px;
    background: var(--accent3);
    margin-left: 4px;
    vertical-align: middle;
    animation: blink 1s step-end infinite;
  }

  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

  .social-row { display: flex; gap: 10px; flex-wrap: wrap; }

  .social-btn {
    display: flex; align-items: center; gap: 7px;
    font-family: var(--mono);
    font-size: 11px;
    padding: 8px 14px;
    border-radius: 8px;
    border: 1px solid var(--border);
    background: var(--surface2);
    color: var(--muted);
    text-decoration: none;
    transition: all 0.2s;
    cursor: pointer;
  }

  .social-btn:hover { border-color: var(--accent); color: var(--text); background: rgba(108,99,255,0.08); }

  .social-icon { width: 14px; height: 14px; fill: currentColor; }

  /* Sections */
  .section { padding: 36px 40px; border-bottom: 1px solid var(--border); }

  .section-label {
    font-family: var(--mono);
    font-size: 10px;
    letter-spacing: 0.12em;
    color: var(--accent3);
    text-transform: uppercase;
    margin-bottom: 20px;
  }

  /* Stack grid */
  .stack-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(110px, 1fr));
    gap: 8px;
  }

  .tech-pill {
    display: flex; align-items: center; gap: 8px;
    padding: 9px 12px;
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 8px;
    font-size: 12px;
    font-weight: 600;
    color: var(--muted);
    transition: all 0.2s;
    cursor: default;
  }

  .tech-pill:hover { border-color: var(--accent); color: var(--text); transform: translateY(-2px); }

  .tech-dot { width: 7px; height: 7px; border-radius: 50%; flex-shrink: 0; }

  /* Stats */
  .stats-row { display: grid; grid-template-columns: repeat(3, 1fr); gap: 12px; }

  .stat-card {
    background: var(--surface2);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px 16px;
    text-align: center;
  }

  .stat-num {
    font-family: var(--mono);
    font-size: 28px;
    font-weight: 700;
    color: var(--text);
    line-height: 1;
    margin-bottom: 4px;
  }

  .stat-label { font-size: 11px; color: var(--muted); font-family: var(--mono); }

  /* Activity bar */
  .activity-bars { display: flex; align-items: flex-end; gap: 4px; height: 60px; }

  .bar {
    flex: 1;
    border-radius: 3px 3px 0 0;
    transition: all 0.3s;
    cursor: pointer;
    opacity: 0.7;
    min-height: 6px;
  }

  .bar:hover { opacity: 1; transform: scaleY(1.05); transform-origin: bottom; }

  /* Tab switcher */
  .tabs { display: flex; gap: 0; margin-bottom: 24px; border: 1px solid var(--border); border-radius: 10px; overflow: hidden; background: var(--surface); }

  .tab {
    flex: 1; padding: 9px 0;
    font-family: var(--mono); font-size: 11px;
    color: var(--muted); background: transparent;
    border: none; cursor: pointer; transition: all 0.2s;
    letter-spacing: 0.04em;
  }

  .tab.active { background: var(--surface2); color: var(--text); }

  .tab-panel { display: none; }
  .tab-panel.active { display: block; }

  .skill-row { display: flex; align-items: center; gap: 12px; margin-bottom: 12px; }
  .skill-name { font-size: 12px; color: var(--muted); width: 90px; flex-shrink: 0; font-family: var(--mono); }
  .skill-track { flex: 1; height: 4px; background: var(--surface2); border-radius: 10px; overflow: hidden; }
  .skill-fill { height: 100%; border-radius: 10px; transition: width 0.8s ease; }
  .skill-pct { font-family: var(--mono); font-size: 10px; color: var(--muted); width: 30px; text-align: right; }

  /* Footer */
  .footer {
    padding: 24px 40px;
    font-family: var(--mono);
    font-size: 11px;
    color: var(--muted);
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 8px;
  }

  .pulse { display: inline-block; width: 7px; height: 7px; border-radius: 50%; background: var(--accent3); margin-right: 6px; animation: pulse 2s ease-in-out infinite; }
  @keyframes pulse { 0%,100%{box-shadow:0 0 0 0 rgba(67,232,192,0.5)} 50%{box-shadow:0 0 0 5px rgba(67,232,192,0)} }
</style>

<div style="background: var(--bg); min-height: 100vh;">

  <!-- Hero -->
  <div class="hero">
    <div class="hero-bg">
      <div class="grid-lines"></div>
      <div class="blob blob-1"></div>
      <div class="blob blob-2"></div>
      <div class="blob blob-3"></div>
    </div>
    <div class="hero-inner">
      <div class="badge-row">
        <span class="badge badge-purple">FULL STACK</span>
        <span class="badge badge-green">OPEN TO WORK</span>
        <span class="badge badge-red">🇲🇦 MOROCCO</span>
      </div>
      <div class="name">Mohamed<br><span>Naceri</span></div>
      <div class="tagline">
        <span id="typewriter">Développeur Web Full Stack</span><span class="cursor"></span>
      </div>
      <div class="social-row">
        <a class="social-btn" href="https://www.linkedin.com/in/mohamed-naceri-600593394/" target="_blank">
          <svg class="social-icon" viewBox="0 0 24 24"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
          LinkedIn
        </a>
        <a class="social-btn" href="https://github.com" target="_blank">
          <svg class="social-icon" viewBox="0 0 24 24"><path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0112 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z"/></svg>
          GitHub
        </a>
        <a class="social-btn" href="mailto:mohamed.naceri12@gmail.com">
          <svg class="social-icon" viewBox="0 0 24 24"><path d="M24 5.457v13.909c0 .904-.732 1.636-1.636 1.636h-3.819V11.73L12 16.64l-6.545-4.91v9.273H1.636A1.636 1.636 0 010 19.366V5.457c0-2.023 2.309-3.178 3.927-1.964L5.455 4.64 12 9.548l6.545-4.91 1.528-1.145C21.69 2.28 24 3.434 24 5.457z"/></svg>
          Email
        </a>
        <a class="social-btn" href="https://x.com/_naceri10" target="_blank">
          <svg class="social-icon" viewBox="0 0 24 24"><path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-4.714-6.231-5.401 6.231H2.744l7.73-8.835L1.254 2.25H8.08l4.259 5.631 5.905-5.631zm-1.161 17.52h1.833L7.084 4.126H5.117z"/></svg>
          X / Twitter
        </a>
      </div>
    </div>
  </div>

  <!-- Stats -->
  <div class="section">
    <div class="section-label">// overview</div>
    <div class="stats-row">
      <div class="stat-card">
        <div class="stat-num" style="color: var(--accent);">3+</div>
        <div class="stat-label">Years exp.</div>
      </div>
      <div class="stat-card">
        <div class="stat-num" style="color: var(--accent3);">20+</div>
        <div class="stat-label">Projects</div>
      </div>
      <div class="stat-card">
        <div class="stat-num" style="color: var(--accent2);">15+</div>
        <div class="stat-label">Technologies</div>
      </div>
    </div>
  </div>

  <!-- Skills tabs -->
  <div class="section">
    <div class="section-label">// compétences</div>
    <div class="tabs">
      <button class="tab active" onclick="switchTab('frontend')">Frontend</button>
      <button class="tab" onclick="switchTab('backend')">Backend</button>
      <button class="tab" onclick="switchTab('tools')">Outils</button>
    </div>

    <div id="tab-frontend" class="tab-panel active">
      <div class="skill-row"><span class="skill-name">React</span><div class="skill-track"><div class="skill-fill" style="width:90%;background:var(--accent)"></div></div><span class="skill-pct">90%</span></div>
      <div class="skill-row"><span class="skill-name">TailwindCSS</span><div class="skill-track"><div class="skill-fill" style="width:85%;background:var(--accent)"></div></div><span class="skill-pct">85%</span></div>
      <div class="skill-row"><span class="skill-name">JavaScript</span><div class="skill-track"><div class="skill-fill" style="width:88%;background:var(--accent)"></div></div><span class="skill-pct">88%</span></div>
      <div class="skill-row"><span class="skill-name">Redux</span><div class="skill-track"><div class="skill-fill" style="width:75%;background:var(--accent)"></div></div><span class="skill-pct">75%</span></div>
      <div class="skill-row"><span class="skill-name">Vite</span><div class="skill-track"><div class="skill-fill" style="width:80%;background:var(--accent)"></div></div><span class="skill-pct">80%</span></div>
    </div>
    <div id="tab-backend" class="tab-panel">
      <div class="skill-row"><span class="skill-name">Laravel</span><div class="skill-track"><div class="skill-fill" style="width:88%;background:var(--accent2)"></div></div><span class="skill-pct">88%</span></div>
      <div class="skill-row"><span class="skill-name">Node.js</span><div class="skill-track"><div class="skill-fill" style="width:78%;background:var(--accent2)"></div></div><span class="skill-pct">78%</span></div>
      <div class="skill-row"><span class="skill-name">PHP</span><div class="skill-track"><div class="skill-fill" style="width:85%;background:var(--accent2)"></div></div><span class="skill-pct">85%</span></div>
      <div class="skill-row"><span class="skill-name">MySQL</span><div class="skill-track"><div class="skill-fill" style="width:82%;background:var(--accent2)"></div></div><span class="skill-pct">82%</span></div>
      <div class="skill-row"><span class="skill-name">MongoDB</span><div class="skill-track"><div class="skill-fill" style="width:70%;background:var(--accent2)"></div></div><span class="skill-pct">70%</span></div>
    </div>
    <div id="tab-tools" class="tab-panel">
      <div class="skill-row"><span class="skill-name">Git / GitHub</span><div class="skill-track"><div class="skill-fill" style="width:90%;background:var(--accent3)"></div></div><span class="skill-pct">90%</span></div>
      <div class="skill-row"><span class="skill-name">Figma</span><div class="skill-track"><div class="skill-fill" style="width:72%;background:var(--accent3)"></div></div><span class="skill-pct">72%</span></div>
      <div class="skill-row"><span class="skill-name">Docker</span><div class="skill-track"><div class="skill-fill" style="width:60%;background:var(--accent3)"></div></div><span class="skill-pct">60%</span></div>
      <div class="skill-row"><span class="skill-name">Vercel</span><div class="skill-track"><div class="skill-fill" style="width:85%;background:var(--accent3)"></div></div><span class="skill-pct">85%</span></div>
      <div class="skill-row"><span class="skill-name">Python</span><div class="skill-track"><div class="skill-fill" style="width:65%;background:var(--accent3)"></div></div><span class="skill-pct">65%</span></div>
    </div>
  </div>

  <!-- Tech stack pills -->
  <div class="section">
    <div class="section-label">// tech stack</div>
    <div class="stack-grid">
      <div class="tech-pill"><span class="tech-dot" style="background:#61DAFB"></span>React</div>
      <div class="tech-pill"><span class="tech-dot" style="background:#FF2D20"></span>Laravel</div>
      <div class="tech-pill"><span class="tech-dot" style="background:#38B2AC"></span>Tailwind</div>
      <div class="tech-pill"><span class="tech-dot" style="background:#6DA55F"></span>Node.js</div>
      <div class="tech-pill"><span class="tech-dot" style="background:#F7DF1E"></span>JavaScript</div>
      <div class="tech-pill"><span class="tech-dot" style="background:#777BB4"></span>PHP</div>
      <div class="tech-pill"><span class="tech-dot" style="background:#4479A1"></span>MySQL</div>
      <div class="tech-pill"><span class="tech-dot" style="background:#4ea94b"></span>MongoDB</div>
      <div class="tech-pill"><span class="tech-dot" style="background:#646CFF"></span>Vite</div>
      <div class="tech-pill"><span class="tech-dot" style="background:#593d88"></span>Redux</div>
      <div class="tech-pill"><span class="tech-dot" style="background:#3670A0"></span>Python</div>
      <div class="tech-pill"><span class="tech-dot" style="background:#F24E1E"></span>Figma</div>
    </div>
  </div>

  <!-- Activity -->
  <div class="section">
    <div class="section-label">// activité mensuelle</div>
    <div class="activity-bars" id="bars"></div>
    <div style="display:flex;justify-content:space-between;margin-top:8px;font-family:var(--mono);font-size:10px;color:var(--muted);">
      <span>Jan</span><span>Fév</span><span>Mar</span><span>Avr</span><span>Mai</span><span>Jun</span><span>Jul</span><span>Aoû</span><span>Sep</span><span>Oct</span><span>Nov</span><span>Déc</span>
    </div>
  </div>

  <!-- Footer -->
  <div class="footer">
    <span><span class="pulse"></span>Disponible pour de nouveaux projets</span>
    <span style="font-family:var(--mono)">mohamed.naceri12@gmail.com</span>
  </div>

</div>

<script>
  // Tab switching
  function switchTab(name) {
    document.querySelectorAll('.tab-panel').forEach(p => p.classList.remove('active'));
    document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
    document.getElementById('tab-' + name).classList.add('active');
    event.target.classList.add('active');
  }

  // Typewriter
  const phrases = ['Développeur Web Full Stack', 'React & Laravel Specialist', 'UI/UX Enthusiast', 'Scalable App Builder'];
  let pi = 0, ci = 0, deleting = false;
  const el = document.getElementById('typewriter');
  function type() {
    const phrase = phrases[pi];
    if (!deleting) {
      el.textContent = phrase.slice(0, ++ci);
      if (ci === phrase.length) { deleting = true; setTimeout(type, 1800); return; }
    } else {
      el.textContent = phrase.slice(0, --ci);
      if (ci === 0) { deleting = false; pi = (pi + 1) % phrases.length; }
    }
    setTimeout(type, deleting ? 45 : 80);
  }
  type();

  // Activity bars
  const bars = document.getElementById('bars');
  const vals = [40, 55, 70, 45, 80, 65, 90, 75, 60, 85, 70, 55];
  const colors = ['#6C63FF','#7C74FF','#8C84FF','#43E8C0','#3DDDB6','#43E8C0','#FF6B6B','#FF7C7C','#FF8D8D','#6C63FF','#43E8C0','#7C74FF'];
  vals.forEach((v, i) => {
    const b = document.createElement('div');
    b.className = 'bar';
    b.style.height = v + '%';
    b.style.background = colors[i];
    b.title = `${['Jan','Fév','Mar','Avr','Mai','Jun','Jul','Aoû','Sep','Oct','Nov','Déc'][i]}: ${v} commits`;
    bars.appendChild(b);
  });
</script>
