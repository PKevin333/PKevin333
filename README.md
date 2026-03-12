<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GitHub README – Kevin Silva</title>
<link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@300;400;500;600&family=Syne:wght@700;800&display=swap" rel="stylesheet">
<style>
* { margin:0; padding:0; box-sizing:border-box; }

body {
  background: #010409;
  font-family: 'Fira Code', monospace;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 40px 16px 60px;
  min-height: 100vh;
  color: #e6edf3;
}

/* ── GitHub chrome ── */
.gh-chrome {
  width: 100%;
  max-width: 860px;
  background: #0d1117;
  border: 1px solid #30363d;
  border-radius: 6px;
  overflow: hidden;
  box-shadow: 0 8px 48px rgba(0,0,0,.6);
}

.gh-tab-bar {
  background: #161b22;
  border-bottom: 1px solid #30363d;
  padding: 10px 20px;
  display: flex;
  gap: 6px;
  font-size: 12px;
  color: #8b949e;
}
.gh-tab { color: #e6edf3; border-bottom: 2px solid #f78166; padding: 4px 2px; margin-right: 14px; }

/* ── README area ── */
.readme {
  padding: 32px 40px 48px;
}

/* ══════════════════════════
   HEADER — Capsule Render style
══════════════════════════ */
.capsule-header {
  width: 100%;
  height: 200px;
  border-radius: 8px;
  margin-bottom: 20px;
  position: relative;
  overflow: hidden;
  background: linear-gradient(135deg, #0d1117 0%, #0a2a1a 40%, #0b1a2e 100%);
  display: flex;
  align-items: center;
  justify-content: center;
}

/* animated wave bg */
.wave-bg {
  position: absolute;
  inset: 0;
  overflow: hidden;
}
.wave {
  position: absolute;
  width: 200%;
  height: 200%;
  top: -50%;
  left: -50%;
  border-radius: 45%;
  opacity: .04;
  animation: wave-spin linear infinite;
}
.w1 { background: #3fb950; animation-duration: 12s; }
.w2 { background: #58a6ff; animation-duration: 18s; animation-direction: reverse; }
.w3 { background: #bc8cff; animation-duration: 24s; }

@keyframes wave-spin {
  from { transform: rotate(0deg); }
  to   { transform: rotate(360deg); }
}

/* particle dots */
.particles { position:absolute; inset:0; }
.p {
  position: absolute;
  width: 2px; height: 2px;
  border-radius: 50%;
  background: #3fb950;
  opacity: .5;
  animation: float-p linear infinite;
}
@keyframes float-p {
  0%   { transform: translateY(0) translateX(0); opacity:.5; }
  50%  { opacity:.15; }
  100% { transform: translateY(-60px) translateX(20px); opacity:0; }
}

.capsule-content {
  position: relative;
  z-index: 1;
  text-align: center;
}

.capsule-greeting {
  font-size: 13px;
  color: #3fb950;
  letter-spacing: 4px;
  text-transform: uppercase;
  margin-bottom: 8px;
  opacity: 0;
  animation: fade-up .6s .2s ease forwards;
}

.capsule-name {
  font-family: 'Syne', sans-serif;
  font-size: 46px;
  font-weight: 800;
  color: #e6edf3;
  letter-spacing: -1px;
  line-height: 1;
  margin-bottom: 6px;
  opacity: 0;
  animation: fade-up .6s .4s ease forwards;
}
.capsule-name span { color: #3fb950; }

.capsule-sub {
  font-size: 13px;
  color: #8b949e;
  letter-spacing: 2px;
  text-transform: uppercase;
  opacity: 0;
  animation: fade-up .6s .6s ease forwards;
}

@keyframes fade-up {
  from { opacity:0; transform:translateY(12px); }
  to   { opacity:1; transform:translateY(0); }
}

/* ── Badge row ── */
.badge-row {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin-bottom: 28px;
  align-items: center;
  justify-content: center;
}

.badge {
  display: inline-flex;
  align-items: center;
  gap: 5px;
  padding: 4px 10px;
  border-radius: 4px;
  font-size: 11px;
  font-weight: 500;
  white-space: nowrap;
  cursor: default;
  transition: opacity .2s;
  animation: badge-in .4s ease both;
}
.badge:hover { opacity: .8; }

@keyframes badge-in {
  from { opacity:0; transform:scale(.9); }
  to   { opacity:1; transform:scale(1); }
}

.badge-left  { padding: 4px 8px; border-radius: 4px 0 0 4px; color: #fff; font-size:10px; letter-spacing:.5px; }
.badge-right { padding: 4px 8px; border-radius: 0 4px 4px 0; color: #fff; font-size:10px; }
.badge-compound { display:inline-flex; align-items:center; }

/* ── Typing SVG simulation ── */
.typing-box {
  background: #161b22;
  border: 1px solid #30363d;
  border-radius: 6px;
  padding: 14px 20px;
  margin-bottom: 28px;
  overflow: hidden;
  white-space: nowrap;
}

.typing-text {
  font-size: 14px;
  color: #3fb950;
  overflow: hidden;
  white-space: nowrap;
  width: 0;
  animation: type 3s steps(60) .5s both;
  display: inline-block;
}
.typing-text::after {
  content: '|';
  animation: blink 1s step-end infinite;
  color: #3fb950;
}
@keyframes type { to { width: 100%; } }
@keyframes blink { 0%,100%{opacity:1;} 50%{opacity:0;} }

/* ── Section heading ── */
.sec-h {
  font-size: 16px;
  font-weight: 600;
  color: #e6edf3;
  margin: 28px 0 14px;
  display: flex;
  align-items: center;
  gap: 8px;
  padding-bottom: 8px;
  border-bottom: 1px solid #21262d;
}
.sec-h .ico { font-size: 18px; }

/* ── About grid ── */
.about-text {
  font-size: 13px;
  color: #8b949e;
  line-height: 1.9;
  margin-bottom: 20px;
}
.about-text strong { color: #e6edf3; }
.about-text a { color: #58a6ff; text-decoration: none; }

.about-bullets {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 7px;
  margin-bottom: 24px;
}
.about-bullets li {
  font-size: 13px;
  color: #c9d1d9;
  display: flex;
  align-items: flex-start;
  gap: 8px;
  line-height: 1.6;
}
.about-bullets li::before { content: '▸'; color: #3fb950; flex-shrink:0; }

/* ── Stats row ── */
.stats-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
  margin-bottom: 4px;
}

.stats-card {
  background: #161b22;
  border: 1px solid #30363d;
  border-radius: 6px;
  padding: 16px;
  position: relative;
  overflow: hidden;
}
.stats-card::before {
  content: '';
  position: absolute;
  top: 0; left:0; right:0;
  height: 2px;
  background: linear-gradient(90deg, #3fb950, #58a6ff);
  transform: scaleX(0);
  transform-origin: left;
  animation: bar-load 1.2s ease forwards;
  animation-delay: .3s;
}
@keyframes bar-load { to { transform: scaleX(1); } }

.stats-title {
  font-size: 10px;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: #8b949e;
  margin-bottom: 12px;
}

.stat-line {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 12px;
  color: #c9d1d9;
  margin-bottom: 6px;
}
.stat-line .val { color: #3fb950; font-weight: 600; }
.stat-line.alt .val { color: #58a6ff; }
.stat-line.alt2 .val { color: #bc8cff; }
.stat-line.alt3 .val { color: #f78166; }

/* ── WakaTime-style bars ── */
.waka-bars {
  background: #161b22;
  border: 1px solid #30363d;
  border-radius: 6px;
  padding: 18px 20px;
  margin-top: 12px;
}

.waka-title {
  font-size: 10px;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: #8b949e;
  margin-bottom: 14px;
  display: flex;
  align-items: center;
  gap: 8px;
}
.waka-title::after {
  content: '';
  flex: 1;
  height: 1px;
  background: #21262d;
}

.waka-row {
  display: grid;
  grid-template-columns: 120px 1fr 45px;
  align-items: center;
  gap: 10px;
  margin-bottom: 9px;
  font-size: 11px;
}
.waka-label { color: #c9d1d9; }
.waka-track {
  height: 7px;
  background: #21262d;
  border-radius: 3px;
  overflow: hidden;
}
.waka-fill {
  height: 100%;
  border-radius: 3px;
  transform-origin: left;
  transform: scaleX(0);
  animation: grow 1.4s cubic-bezier(.16,1,.3,1) both;
}
@keyframes grow { to { transform: scaleX(1); } }
.waka-pct { font-size: 10px; color: #8b949e; text-align: right; }

/* ── Tech stack ── */
.tech-section { }

.tech-group {
  margin-bottom: 16px;
}
.tg-title {
  font-size: 11px;
  color: #8b949e;
  letter-spacing: 2px;
  text-transform: uppercase;
  margin-bottom: 8px;
}
.tg-badges {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
}

.sk-badge {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  background: #161b22;
  border: 1px solid #30363d;
  border-radius: 4px;
  padding: 5px 12px;
  font-size: 11px;
  color: #c9d1d9;
  cursor: default;
  transition: all .2s;
}
.sk-badge:hover {
  border-color: #3fb950;
  color: #3fb950;
  background: rgba(63,185,80,.06);
}
.sk-dot { width: 8px; height: 8px; border-radius: 50%; flex-shrink:0; }

/* ── Projects ── */
.projects-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
}

.proj-card {
  background: #161b22;
  border: 1px solid #30363d;
  border-radius: 6px;
  padding: 16px;
  cursor: default;
  transition: all .2s;
  position: relative;
}
.proj-card:hover {
  border-color: rgba(63,185,80,.4);
  box-shadow: 0 0 0 1px rgba(63,185,80,.1);
}

.proj-icon { font-size: 20px; margin-bottom: 8px; }
.proj-name {
  font-size: 13px;
  color: #58a6ff;
  margin-bottom: 5px;
  font-weight: 600;
}
.proj-desc {
  font-size: 11px;
  color: #8b949e;
  line-height: 1.65;
  margin-bottom: 12px;
}
.proj-foot {
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-size: 10px;
  color: #8b949e;
}
.proj-lang { display: flex; align-items: center; gap: 5px; }
.proj-badge-tag {
  font-size: 9px;
  letter-spacing: 1px;
  text-transform: uppercase;
  background: rgba(63,185,80,.1);
  border: 1px solid rgba(63,185,80,.2);
  color: #3fb950;
  padding: 2px 7px;
  border-radius: 20px;
}

/* ── Activity / WakaTime commit heatmap ── */
.commit-section {
  background: #161b22;
  border: 1px solid #30363d;
  border-radius: 6px;
  padding: 18px 20px;
}

.commit-grid {
  display: flex;
  gap: 3px;
  flex-wrap: wrap;
  margin-top: 12px;
}
.cw { display: flex; flex-direction: column; gap: 3px; }
.cs {
  width: 10px; height: 10px;
  border-radius: 2px;
}
.c0 { background: #161b22; border: 1px solid #21262d; }
.c1 { background: #0e4429; }
.c2 { background: #006d32; }
.c3 { background: #26a641; }
.c4 { background: #39d353; }

/* ── Progress activity bars like Aaron ── */
.activity-code {
  background: #161b22;
  border: 1px solid #30363d;
  border-radius: 6px;
  padding: 18px 20px;
  font-size: 12px;
  line-height: 2;
  color: #c9d1d9;
}
.act-label { color: #8b949e; }
.act-bar-wrap {
  display: grid;
  grid-template-columns: 160px 1fr 60px;
  gap: 10px;
  align-items: center;
  margin: 4px 0;
}
.act-name { font-size: 12px; color: #c9d1d9; }
.act-blocks { letter-spacing: 1px; font-size: 12px; }
.filled { color: #3fb950; }
.empty  { color: #21262d; }
.act-pct { font-size: 11px; color: #8b949e; text-align: right; }

/* ── Links ── */
.links-row {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}
.lnk {
  display: inline-flex;
  align-items: center;
  gap: 7px;
  background: #161b22;
  border: 1px solid #30363d;
  border-radius: 6px;
  padding: 8px 16px;
  font-size: 12px;
  color: #c9d1d9;
  cursor: default;
  transition: all .2s;
}
.lnk:hover {
  background: #21262d;
  border-color: #58a6ff;
  color: #58a6ff;
}

/* ── Footer ── */
.readme-footer {
  margin-top: 36px;
  padding-top: 16px;
  border-top: 1px solid #21262d;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 11px;
  color: #484f58;
}
.footer-pulse {
  display: flex;
  align-items: center;
  gap: 6px;
}
.pulse-dot {
  width: 7px; height: 7px;
  border-radius: 50%;
  background: #3fb950;
  box-shadow: 0 0 0 0 rgba(63,185,80,.5);
  animation: pulse-ring 2s ease-in-out infinite;
}
@keyframes pulse-ring {
  0%   { box-shadow: 0 0 0 0 rgba(63,185,80,.5); }
  70%  { box-shadow: 0 0 0 7px rgba(63,185,80,0); }
  100% { box-shadow: 0 0 0 0 rgba(63,185,80,0); }
}

/* align center helper */
.center { text-align: center; }
.mt8 { margin-top: 8px; }
.mt16 { margin-top: 16px; }

/* divider */
.div { height: 1px; background: #21262d; margin: 28px 0; }
</style>
</head>
<body>

<div class="gh-chrome">
  <div class="gh-tab-bar">
    <span class="gh-tab">📄 README.md</span>
    <span style="color:#8b949e">Raw &nbsp; Blame &nbsp; History</span>
  </div>

  <div class="readme">

    <!-- ════════════ CAPSULE HEADER ════════════ -->
    <div class="capsule-header">
      <div class="wave-bg">
        <div class="wave w1"></div>
        <div class="wave w2"></div>
        <div class="wave w3"></div>
      </div>
      <div class="particles">
        <div class="p" style="left:10%;top:70%;animation-duration:4s;animation-delay:0s"></div>
        <div class="p" style="left:25%;top:80%;animation-duration:5s;animation-delay:1s"></div>
        <div class="p" style="left:40%;top:75%;animation-duration:6s;animation-delay:2s"></div>
        <div class="p" style="left:55%;top:85%;animation-duration:4.5s;animation-delay:.5s"></div>
        <div class="p" style="left:70%;top:72%;animation-duration:5.5s;animation-delay:1.5s"></div>
        <div class="p" style="left:85%;top:78%;animation-duration:4s;animation-delay:2.5s;background:#58a6ff"></div>
        <div class="p" style="left:90%;top:65%;animation-duration:6s;animation-delay:0.8s;background:#bc8cff"></div>
        <div class="p" style="left:15%;top:60%;animation-duration:5s;animation-delay:3s;background:#58a6ff"></div>
      </div>
      <div class="capsule-content">
        <div class="capsule-greeting">// olá mundo, eu sou</div>
        <div class="capsule-name">Kevin <span>Silva</span></div>
        <div class="capsule-sub">Administração · Tecnologia · IA</div>
      </div>
    </div>

    <!-- ════════════ BADGES ════════════ -->
    <div class="badge-row">
      <!-- Profile views -->
      <div class="badge-compound">
        <span class="badge-left" style="background:#555">👁 Profile Views</span>
        <span class="badge-right" style="background:#7745bf">counting...</span>
      </div>
      <!-- Location -->
      <div class="badge-compound">
        <span class="badge-left" style="background:#555">📍 location</span>
        <span class="badge-right" style="background:#0078d7">São Luís, MA</span>
      </div>
      <!-- Hiring -->
      <div class="badge-compound">
        <span class="badge-left" style="background:#555">💼 status</span>
        <span class="badge-right" style="background:#3fb950">Open to Work</span>
      </div>
      <!-- LinkedIn -->
      <div class="badge-compound">
        <span class="badge-left" style="background:#0a66c2">in</span>
        <span class="badge-right" style="background:#0a66c2">LinkedIn</span>
      </div>
      <!-- Website -->
      <div class="badge-compound">
        <span class="badge-left" style="background:#555">🌐</span>
        <span class="badge-right" style="background:#1a6b5e">ggmax.com.br</span>
      </div>
    </div>

    <!-- ════════════ TYPING LINE ════════════ -->
    <div class="typing-box">
      <span class="typing-text">Administrador apaixonado por dados, IA e tecnologia · Estagiário no setor público · UEMA 2026</span>
    </div>

    <!-- ════════════ ABOUT ════════════ -->
    <div class="sec-h"><span class="ico">📬</span> Sobre mim</div>

    <ul class="about-bullets">
      <li>🎓 Graduando em <strong>Administração</strong> na UEMA — foco em gestão, dados e inovação pública</li>
      <li>🏛️ Estagiário no <strong>setor público</strong> — acredito que dados e tecnologia transformam instituições</li>
      <li>🤖 Explorando <strong>Inteligência Artificial</strong> aplicada à gestão e análise de dados</li>
      <li>💻 Aprendendo desenvolvimento web com <strong>TypeScript, React</strong> e <strong>Node.js</strong></li>
      <li>📊 Usando <strong>Power BI, Excel avançado</strong> e <strong>SQL</strong> para transformar dados em decisões</li>
      <li>📍 Construindo coisas interessantes em São Luís — Maranhão, Brasil 🇧🇷</li>
    </ul>

    <!-- ════════════ STATS ════════════ -->
    <div class="sec-h"><span class="ico">📊</span> GitHub Stats</div>

    <div class="stats-row">
      <!-- Card 1: GitHub stats simulado -->
      <div class="stats-card">
        <div class="stats-title">github stats · PKevin333</div>
        <div class="stat-line"><span>Total Commits (2026)</span><span class="val">42+</span></div>
        <div class="stat-line alt"><span>Repositórios Públicos</span><span class="val">3</span></div>
        <div class="stat-line alt2"><span>Linguagens Usadas</span><span class="val">2</span></div>
        <div class="stat-line alt3"><span>Contribuições</span><span class="val">↗ crescendo</span></div>
      </div>

      <!-- Card 2: most used langs -->
      <div class="stats-card">
        <div class="stats-title">top languages</div>
        <div class="waka-row" style="margin-top:0">
          <span class="waka-label">TypeScript</span>
          <div class="waka-track"><div class="waka-fill" style="width:72%;background:#3178c6;animation-delay:.2s"></div></div>
          <span class="waka-pct">72%</span>
        </div>
        <div class="waka-row">
          <span class="waka-label">JavaScript</span>
          <div class="waka-track"><div class="waka-fill" style="width:21%;background:#f7df1e;animation-delay:.4s"></div></div>
          <span class="waka-pct">21%</span>
        </div>
        <div class="waka-row">
          <span class="waka-label">HTML / CSS</span>
          <div class="waka-track"><div class="waka-fill" style="width:7%;background:#e34c26;animation-delay:.6s"></div></div>
          <span class="waka-pct">7%</span>
        </div>
      </div>
    </div>

    <!-- ════════════ CONTRIBUTION HEATMAP ════════════ -->
    <div class="commit-section mt16">
      <div class="waka-title">contribution graph 2026</div>
      <div class="commit-grid" id="heatmap"></div>
    </div>

    <!-- ════════════ WHAT I DO / ACTIVITY BARS ════════════ -->
    <div class="sec-h mt16"><span class="ico">🔧</span> O que eu faço</div>

    <div class="activity-code">
      <div><span class="act-label">💼 Foco Principal  </span> Gestão Pública · Dados · Inovação</div>
      <div class="act-bar-wrap">
        <span class="act-name">Administração</span>
        <span class="act-blocks">
          <span class="filled">⬛⬛⬛⬛⬛⬛⬛⬛⬛⬛⬛⬛⬛⬛⬛</span><span class="empty">⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜</span>
        </span>
        <span class="act-pct">60.00 %</span>
      </div>
      <div class="act-bar-wrap">
        <span class="act-name">Desenvolvimento Web</span>
        <span class="act-blocks">
          <span class="filled">⬛⬛⬛⬛⬛⬛⬛⬛</span><span class="empty">⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜</span>
        </span>
        <span class="act-pct">30.00 %</span>
      </div>
      <div class="act-bar-wrap">
        <span class="act-name">Dados &amp; IA</span>
        <span class="act-blocks">
          <span class="filled">⬛⬛⬛</span><span class="empty">⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜</span>
        </span>
        <span class="act-pct">10.00 %</span>
      </div>
      <div style="margin-top:10px; color:#484f58; font-size:11px">Last Updated: March 2026 · São Luís, MA (UTC -03:00)</div>
    </div>

    <!-- ════════════ TECH STACK ════════════ -->
    <div class="sec-h"><span class="ico">✨</span> Tech Stack & Ferramentas</div>

    <div class="tech-section">
      <div class="tech-group">
        <div class="tg-title">// desenvolvimento</div>
        <div class="tg-badges">
          <span class="sk-badge"><span class="sk-dot" style="background:#3178c6"></span> TypeScript</span>
          <span class="sk-badge"><span class="sk-dot" style="background:#f7df1e"></span> JavaScript</span>
          <span class="sk-badge"><span class="sk-dot" style="background:#61dafb"></span> React</span>
          <span class="sk-badge"><span class="sk-dot" style="background:#000;border:1px solid #444"></span> Next.js</span>
          <span class="sk-badge"><span class="sk-dot" style="background:#68a063"></span> Node.js</span>
          <span class="sk-badge"><span class="sk-dot" style="background:#e34c26"></span> HTML5</span>
          <span class="sk-badge"><span class="sk-dot" style="background:#264de4"></span> CSS3</span>
        </div>
      </div>
      <div class="tech-group">
        <div class="tg-title">// dados &amp; ia</div>
        <div class="tg-badges">
          <span class="sk-badge"><span class="sk-dot" style="background:#F2C811"></span> Power BI</span>
          <span class="sk-badge"><span class="sk-dot" style="background:#217346"></span> Excel Avançado</span>
          <span class="sk-badge"><span class="sk-dot" style="background:#336791"></span> SQL</span>
          <span class="sk-badge"><span class="sk-dot" style="background:#3b82f6"></span> ChatGPT / IA</span>
          <span class="sk-badge"><span class="sk-dot" style="background:#3776AB"></span> Python (básico)</span>
        </div>
      </div>
      <div class="tech-group">
        <div class="tg-title">// gestão &amp; produtividade</div>
        <div class="tg-badges">
          <span class="sk-badge"><span class="sk-dot" style="background:#000"></span> Notion</span>
          <span class="sk-badge"><span class="sk-dot" style="background:#0052cc"></span> Trello</span>
          <span class="sk-badge"><span class="sk-dot" style="background:#f05032"></span> Git / GitHub</span>
          <span class="sk-badge"><span class="sk-dot" style="background:#a259ff"></span> Figma</span>
          <span class="sk-badge"><span class="sk-dot" style="background:#0078d4"></span> Microsoft Office</span>
        </div>
      </div>
    </div>

    <!-- ════════════ PROJECTS ════════════ -->
    <div class="sec-h"><span class="ico">🌟</span> Projetos em Destaque</div>

    <div class="projects-grid">
      <div class="proj-card">
        <div class="proj-icon">📚</div>
        <div class="proj-name">Plano-Aprovado</div>
        <div class="proj-desc">Plataforma para organização de estudos. Interface limpa para planejamento acadêmico e acompanhamento de progresso.</div>
        <div class="proj-foot">
          <div class="proj-lang"><span class="sk-dot" style="background:#3178c6;width:10px;height:10px"></span> TypeScript</div>
          <span class="proj-badge-tag">destaque</span>
        </div>
      </div>

      <div class="proj-card">
        <div class="proj-icon">🛤️</div>
        <div class="proj-name">Trilhas Project</div>
        <div class="proj-desc">Desafios práticos do Projeto Trilhas — base sólida para evolução em programação com JavaScript.</div>
        <div class="proj-foot">
          <div class="proj-lang"><span class="sk-dot" style="background:#f7df1e;width:10px;height:10px"></span> JavaScript</div>
          <span class="proj-badge-tag">formação</span>
        </div>
      </div>

      <div class="proj-card">
        <div class="proj-icon">🎓</div>
        <div class="proj-name">UEMA 2026</div>
        <div class="proj-desc">Projeto universitário desenvolvido em TypeScript para atividades acadêmicas na UEMA.</div>
        <div class="proj-foot">
          <div class="proj-lang"><span class="sk-dot" style="background:#3178c6;width:10px;height:10px"></span> TypeScript</div>
          <span class="proj-badge-tag">acadêmico</span>
        </div>
      </div>

      <div class="proj-card" style="border-style:dashed;display:flex;flex-direction:column;align-items:center;justify-content:center;min-height:120px;gap:8px">
        <div style="font-size:28px;color:#21262d">+</div>
        <div style="font-size:11px;color:#484f58;text-align:center">Mais projetos<br>em breve...</div>
      </div>
    </div>

    <div class="div"></div>

    <!-- ════════════ CONTACT ════════════ -->
    <div class="sec-h"><span class="ico">📡</span> Onde me encontrar</div>

    <div class="links-row">
      <div class="lnk">💼 LinkedIn</div>
      <div class="lnk">🌐 ggmax.com.br</div>
      <div class="lnk">📧 E-mail</div>
      <div class="lnk">🐦 Twitter / X</div>
    </div>

    <!-- ════════════ IMPORTANT CALLOUT ════════════ -->
    <div style="background:#161b22;border:1px solid #9e6a03;border-radius:6px;padding:14px 18px;margin-top:24px;font-size:12px;color:#e3b341;line-height:1.8">
      <strong>💡 Nota —</strong> Acredito que a gestão e a tecnologia não são mundos separados.<br>
      A maior transformação acontece onde as duas se encontram. É aí que quero estar.
    </div>

    <!-- ════════════ FOOTER ════════════ -->
    <div class="readme-footer">
      <span>© 2026 · Kevin Silva · PKevin333</span>
      <div class="footer-pulse">
        <div class="pulse-dot"></div>
        <span style="color:#3fb950">aberto a oportunidades</span>
      </div>
      <span>São Luís, MA 🇧🇷</span>
    </div>

  </div><!-- /readme -->
</div><!-- /gh-chrome -->

<script>
// Generate contribution heatmap
const heatmap = document.getElementById('heatmap');
const levels = [0,0,0,1,0,1,2,0,1,2,3,2,1,0,1,2,3,4,3,2,1,2,3,2,1,0,1,2,1,0,0,1,2,3,2,1,2,3,4,3,2,1,0,1,2,1,0,0,1,0];
for(let w=0; w<52; w++){
  const col = document.createElement('div');
  col.className = 'cw';
  for(let d=0; d<7; d++){
    const sq = document.createElement('div');
    const lvl = levels[(w*7+d) % levels.length];
    sq.className = `cs c${lvl}`;
    col.appendChild(sq);
  }
  heatmap.appendChild(col);
}
</script>
</body>
</html>
