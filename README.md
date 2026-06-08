
<style>
@import url('https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;600;800&family=JetBrains+Mono:wght@400;700&display=swap');
*{box-sizing:border-box;margin:0;padding:0}
.root{background:#040810;font-family:'Outfit',sans-serif;color:#e8edf5;border-radius:16px;overflow:hidden;position:relative}
canvas#bg{position:absolute;inset:0;width:100%;height:100%}
.over{position:relative;z-index:2}
.hero{padding:40px 36px 28px;border-bottom:1px solid rgba(99,179,255,0.1)}
.hero-top{display:flex;align-items:flex-start;justify-content:space-between;gap:24px;margin-bottom:20px}
.badge-row{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:16px}
.badge{font-family:'JetBrains Mono',monospace;font-size:10px;padding:3px 10px;border-radius:20px;letter-spacing:0.5px}
.badge-blue{background:rgba(56,139,255,0.12);color:#63b3ff;border:1px solid rgba(56,139,255,0.2)}
.badge-green{background:rgba(34,197,94,0.1);color:#4ade80;border:1px solid rgba(34,197,94,0.2)}
.badge-amber{background:rgba(251,191,36,0.1);color:#fbbf24;border:1px solid rgba(251,191,36,0.2)}
.name-block .label{font-family:'JetBrains Mono',monospace;font-size:11px;color:#3b82f6;letter-spacing:3px;margin-bottom:6px}
.name-block h1{font-size:42px;font-weight:800;line-height:1;letter-spacing:-1px;color:#fff}
.name-block h1 em{color:#3b82f6;font-style:normal}
.tagline{font-size:14px;color:#64748b;margin-top:6px;font-weight:300;letter-spacing:0.3px}
.avatar-ring{width:76px;height:76px;border-radius:50%;border:2px solid rgba(59,130,246,0.4);display:flex;align-items:center;justify-content:center;flex-shrink:0;position:relative}
.avatar-ring::before{content:'';position:absolute;inset:-5px;border-radius:50%;border:1px solid rgba(59,130,246,0.15);animation:spin 8s linear infinite}
@keyframes spin{to{transform:rotate(360deg)}}
.avatar-inner{width:60px;height:60px;border-radius:50%;background:linear-gradient(135deg,#1e3a5f,#0f2040);display:flex;align-items:center;justify-content:center;font-weight:800;font-size:20px;color:#63b3ff;font-family:'JetBrains Mono',monospace}
.type-line{font-family:'JetBrains Mono',monospace;font-size:13px;color:#94a3b8;display:flex;align-items:center;gap:6px;margin-bottom:4px}
.cursor{display:inline-block;width:2px;height:13px;background:#3b82f6;animation:blink 1s step-end infinite;vertical-align:middle}
@keyframes blink{0%,100%{opacity:1}50%{opacity:0}}
.status-dot{width:7px;height:7px;border-radius:50%;background:#4ade80;display:inline-block;margin-right:4px;animation:pulse-dot 2s ease-in-out infinite}
@keyframes pulse-dot{0%,100%{opacity:1;transform:scale(1)}50%{opacity:0.6;transform:scale(0.85)}}
.bio{font-size:14px;color:#94a3b8;line-height:1.7;max-width:520px;font-weight:300}
.bio strong{color:#cbd5e1;font-weight:400}
.stats-row{display:grid;grid-template-columns:repeat(4,1fr);gap:1px;background:rgba(99,179,255,0.08);border-top:1px solid rgba(99,179,255,0.08)}
.stat{padding:18px 20px;background:#040810;text-align:center}
.stat-n{font-family:'JetBrains Mono',monospace;font-size:22px;font-weight:700;color:#fff;line-height:1}
.stat-n span{color:#3b82f6}
.stat-l{font-size:10px;color:#475569;letter-spacing:1.5px;text-transform:uppercase;margin-top:4px}
.section{padding:24px 36px}
.section+.section{border-top:1px solid rgba(99,179,255,0.06)}
.sec-head{display:flex;align-items:center;gap:10px;margin-bottom:16px}
.sec-head-line{width:24px;height:2px;background:#3b82f6;border-radius:1px}
.sec-head-text{font-family:'JetBrains Mono',monospace;font-size:10px;color:#3b82f6;letter-spacing:2px;text-transform:uppercase}
.chips{display:flex;flex-wrap:wrap;gap:6px}
.chip{font-family:'JetBrains Mono',monospace;font-size:11px;padding:5px 12px;border-radius:4px;border:1px solid rgba(99,179,255,0.12);color:#64748b;background:rgba(99,179,255,0.03);transition:all 0.18s;cursor:default}
.chip:hover{border-color:rgba(59,130,246,0.5);color:#93c5fd;background:rgba(59,130,246,0.07);transform:translateY(-1px)}
.lang-bars{display:flex;flex-direction:column;gap:12px}
.lang-item{display:grid;grid-template-columns:100px 1fr 36px;align-items:center;gap:12px}
.lang-name{font-family:'JetBrains Mono',monospace;font-size:11px;color:#94a3b8}
.lang-track{height:3px;background:rgba(255,255,255,0.05);border-radius:2px;overflow:hidden}
.lang-bar{height:100%;border-radius:2px;background:#3b82f6;transform:scaleX(0);transform-origin:left;transition:transform 1.2s cubic-bezier(0.16,1,0.3,1)}
.lang-pct{font-family:'JetBrains Mono',monospace;font-size:10px;color:#475569;text-align:right}
.links-grid{display:flex;gap:8px;flex-wrap:wrap}
.link-btn{font-family:'JetBrains Mono',monospace;font-size:11px;padding:7px 16px;border-radius:4px;border:1px solid rgba(99,179,255,0.15);color:#64748b;text-decoration:none;display:inline-flex;align-items:center;gap:6px;transition:all 0.18s;background:transparent}
.link-btn:hover{border-color:rgba(59,130,246,0.5);color:#93c5fd;background:rgba(59,130,246,0.06)}
.link-btn i{font-size:14px}
.footer{padding:16px 36px;border-top:1px solid rgba(99,179,255,0.06);display:flex;align-items:center;justify-content:space-between}
.footer-l{font-family:'JetBrains Mono',monospace;font-size:10px;color:#1e293b}
.footer-r{font-family:'JetBrains Mono',monospace;font-size:10px;color:#1e293b}
</style>

<h2 class="sr-only">Harish M — GitHub profile card: frontend developer from Chennai, India</h2>

<div class="root">
<canvas id="bg"></canvas>
<div class="over">

<div class="hero">
  <div class="badge-row">
    <span class="badge badge-green"><span class="status-dot"></span>available for collabs</span>
    <span class="badge badge-blue">frontend dev</span>
    <span class="badge badge-amber">learning node.js</span>
  </div>
  <div class="hero-top">
    <div class="name-block">
      <div class="label">// HARISH_M.DEV</div>
      <h1>Hi, I'm <em>Harish.</em></h1>
      <div class="type-line" id="tl">Frontend Developer<span class="cursor"></span></div>
    </div>
    <div class="avatar-ring">
      <div class="avatar-inner">HM</div>
    </div>
  </div>
  <p class="bio">I build <strong>pixel-perfect, animated interfaces</strong> that live at the intersection of design craft and clean code. From Figma to production — I make the web feel alive.</p>
</div>

<div class="stats-row">
  <div class="stat"><div class="stat-n" id="s1">0<span>+</span></div><div class="stat-l">commits</div></div>
  <div class="stat"><div class="stat-n" id="s2">0<span>+</span></div><div class="stat-l">repos</div></div>
  <div class="stat"><div class="stat-n" id="s3">0</div><div class="stat-l">languages</div></div>
  <div class="stat"><div class="stat-n" id="s4">0<span>+</span></div><div class="stat-l">yrs building</div></div>
</div>

<div class="section">
  <div class="sec-head"><div class="sec-head-line"></div><div class="sec-head-text">Tech Stack</div></div>
  <div class="chips">
    <span class="chip">TypeScript</span><span class="chip">JavaScript</span><span class="chip">React</span><span class="chip">Next.js</span><span class="chip">TailwindCSS</span><span class="chip">Node.js</span><span class="chip">Python</span><span class="chip">Flutter</span><span class="chip">Dart</span><span class="chip">Java</span><span class="chip">PHP</span><span class="chip">PostgreSQL</span><span class="chip">MongoDB</span><span class="chip">Firebase</span><span class="chip">Figma</span><span class="chip">Framer</span><span class="chip">Webflow</span><span class="chip">Google Cloud</span><span class="chip">Azure</span><span class="chip">Git</span>
  </div>
</div>

<div class="section">
  <div class="sec-head"><div class="sec-head-line"></div><div class="sec-head-text">Top Languages</div></div>
  <div class="lang-bars" id="langs">
    <div class="lang-item"><span class="lang-name">TypeScript</span><div class="lang-track"><div class="lang-bar" data-w="72"></div></div><span class="lang-pct">72%</span></div>
    <div class="lang-item"><span class="lang-name">JavaScript</span><div class="lang-track"><div class="lang-bar" data-w="61"></div></div><span class="lang-pct">61%</span></div>
    <div class="lang-item"><span class="lang-name">Python</span><div class="lang-track"><div class="lang-bar" data-w="38"></div></div><span class="lang-pct">38%</span></div>
    <div class="lang-item"><span class="lang-name">Dart</span><div class="lang-track"><div class="lang-bar" data-w="21"></div></div><span class="lang-pct">21%</span></div>
    <div class="lang-item"><span class="lang-name">CSS</span><div class="lang-track"><div class="lang-bar" data-w="45"></div></div><span class="lang-pct">45%</span></div>
  </div>
</div>

<div class="section">
  <div class="sec-head"><div class="sec-head-line"></div><div class="sec-head-text">Connect</div></div>
  <div class="links-grid">
    <a class="link-btn" href="https://github.com/Harish2859"><i class="ti ti-brand-github" aria-hidden="true"></i>GitHub</a>
    <a class="link-btn" href="https://x.com/arkhamencrypted"><i class="ti ti-brand-x" aria-hidden="true"></i>X / Twitter</a>
    <a class="link-btn" href="https://harishxm.hashnode.dev"><i class="ti ti-pencil" aria-hidden="true"></i>Hashnode Blog</a>
    <a class="link-btn" href="https://gitlab.com/Harish2859"><i class="ti ti-brand-gitlab" aria-hidden="true"></i>GitLab</a>
    <a class="link-btn" href="mailto:harishm.aids2023@citchennai.net"><i class="ti ti-mail" aria-hidden="true"></i>Email</a>
  </div>
</div>

<div class="footer">
  <span class="footer-l">Chennai, India</span>
  <span class="footer-r">design with purpose · develop with precision</span>
</div>

</div>
</div>

<script>
const canvas = document.getElementById('bg');
const ctx = canvas.getContext('2d');
let W, H, pts = [];

function resize() {
  const r = canvas.parentElement;
  W = canvas.width = r.offsetWidth;
  H = canvas.height = r.offsetHeight;
}

function initPts() {
  pts = [];
  const n = Math.floor((W * H) / 18000);
  for (let i = 0; i < n; i++) {
    pts.push({ x: Math.random() * W, y: Math.random() * H, vx: (Math.random() - 0.5) * 0.3, vy: (Math.random() - 0.5) * 0.3, r: Math.random() * 1.2 + 0.3 });
  }
}

function draw() {
  ctx.clearRect(0, 0, W, H);
  const dist = 90;
  for (let i = 0; i < pts.length; i++) {
    const p = pts[i];
    p.x += p.vx; p.y += p.vy;
    if (p.x < 0 || p.x > W) p.vx *= -1;
    if (p.y < 0 || p.y > H) p.vy *= -1;
    ctx.beginPath();
    ctx.arc(p.x, p.y, p.r, 0, Math.PI * 2);
    ctx.fillStyle = 'rgba(59,130,246,0.35)';
    ctx.fill();
    for (let j = i + 1; j < pts.length; j++) {
      const q = pts[j];
      const dx = p.x - q.x, dy = p.y - q.y;
      const d = Math.sqrt(dx * dx + dy * dy);
      if (d < dist) {
        ctx.beginPath();
        ctx.moveTo(p.x, p.y);
        ctx.lineTo(q.x, q.y);
        ctx.strokeStyle = `rgba(59,130,246,${0.06 * (1 - d / dist)})`;
        ctx.lineWidth = 0.5;
        ctx.stroke();
      }
    }
  }
  requestAnimationFrame(draw);
}

resize();
initPts();
draw();
window.addEventListener('resize', () => { resize(); initPts(); });

function countTo(id, target, duration, suffix) {
  const el = document.getElementById(id);
  const base = el.querySelector('span') ? el.querySelector('span').outerHTML : '';
  let start = null;
  function step(ts) {
    if (!start) start = ts;
    const p = Math.min((ts - start) / duration, 1);
    const eased = 1 - Math.pow(1 - p, 3);
    el.innerHTML = Math.round(eased * target) + base;
    if (p < 1) requestAnimationFrame(step);
  }
  requestAnimationFrame(step);
}

setTimeout(() => {
  countTo('s1', 250, 1400, '+');
  countTo('s2', 18, 900, '+');
  countTo('s3', 10, 800, '');
  countTo('s4', 3, 700, '+');
}, 300);

setTimeout(() => {
  document.querySelectorAll('.lang-bar').forEach((bar, i) => {
    setTimeout(() => {
      bar.style.transform = `scaleX(${bar.dataset.w / 100})`;
    }, i * 120);
  });
}, 500);

const roles = ['Frontend Developer', 'UI/UX Designer', 'Creative Coder', 'Full-Stack Explorer'];
let ri = 0, ci = 0, deleting = false;
const tl = document.getElementById('tl');
function typeEffect() {
  const word = roles[ri];
  const cursor = '<span class="cursor"></span>';
  if (!deleting) {
    ci++;
    tl.innerHTML = word.slice(0, ci) + cursor;
    if (ci === word.length) { deleting = true; setTimeout(typeEffect, 2000); return; }
    setTimeout(typeEffect, 65);
  } else {
    ci--;
    tl.innerHTML = word.slice(0, ci) + cursor;
    if (ci === 0) { deleting = false; ri = (ri + 1) % roles.length; setTimeout(typeEffect, 300); return; }
    setTimeout(typeEffect, 35);
  }
}
setTimeout(typeEffect, 800);
</script>
