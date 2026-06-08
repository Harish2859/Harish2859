<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Harish M - AI Professional Profile</title>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@latest/tabler-icons.min.css">
<style>
@import url('https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;600;800&family=JetBrains+Mono:wght@400;700&display=swap');

*{box-sizing:border-box;margin:0;padding:0}

body {
  background: #02040a;
  padding: 40px 20px;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}

.root{
  background:#040814;
  font-family:'Outfit',sans-serif;
  color:#e8edf5;
  border-radius:20px;
  overflow:hidden;
  position:relative;
  max-width: 650px;
  width: 100%;
  border: 1px solid rgba(99, 179, 255, 0.1);
  box-shadow: 0 20px 50px rgba(0,0,0,0.5);
}

canvas#bg{position:absolute;inset:0;width:100%;height:100%}
.over{position:relative;z-index:2;background: linear-gradient(180deg, rgba(4,8,20,0.4) 0%, rgba(4,8,20,0.8) 100%)}

.hero{padding:40px 36px 28px;border-bottom:1px solid rgba(99,179,255,0.08)}
.hero-top{display:flex;align-items:flex-start;justify-content:space-between;gap:24px;margin-bottom:20px}
.badge-row{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:16px}
.badge{font-family:'JetBrains Mono',monospace;font-size:10px;padding:4px 12px;border-radius:20px;letter-spacing:0.5px;font-weight: 700;}
.badge-blue{background:rgba(56,139,255,0.1);color:#63b3ff;border:1px solid rgba(56,139,255,0.15)}
.badge-purple{background:rgba(147,51,234,0.1);color:#c084fc;border:1px solid rgba(147,51,234,0.15)}
.badge-green{background:rgba(34,197,94,0.08);color:#4ade80;border:1px solid rgba(34,197,94,0.15)}

.name-block .label{font-family:'JetBrains Mono',monospace;font-size:11px;color:#3b82f6;letter-spacing:3px;margin-bottom:6px}
.name-block h1{font-size:42px;font-weight:800;line-height:1;letter-spacing:-1px;color:#fff}
.name-block h1 em{color:#a855f7;font-style:normal;background: linear-gradient(to right, #63b3ff, #a855f7); -webkit-background-clip: text; -webkit-text-fill-color: transparent;}
.tagline{font-size:14px;color:#64748b;margin-top:6px;font-weight:300;letter-spacing:0.3px}

.type-line{font-family:'JetBrains Mono',monospace;font-size:14px;color:#94a3b8;display:flex;align-items:center;gap:6px;margin-top:8px;min-height: 20px;}
.cursor{display:inline-block;width:2px;height:14px;background:#a855f7;animation:blink 1s step-end infinite;vertical-align:middle}
@keyframes blink{0%,100%{opacity:1}50%{opacity:0}}

.avatar-ring{width:80px;height:80px;border-radius:50%;border:2px solid rgba(168,85,247,0.3);display:flex;align-items:center;justify-content:center;flex-shrink:0;position:relative}
.avatar-ring::before{content:'';position:absolute;inset:-6px;border-radius:50%;border:1px dashed rgba(59,130,246,0.3);animation:spin 12s linear infinite}
@keyframes spin{to{transform:rotate(360deg)}}
.avatar-inner{width:64px;height:64px;border-radius:50%;background:linear-gradient(135deg,#0f172a,#1e1b4b);display:flex;align-items:center;justify-content:center;font-weight:800;font-size:22px;color:#a855f7;font-family:'JetBrains Mono',monospace;box-shadow: inset 0 0 10px rgba(168,85,247,0.2)}

.status-dot{width:7px;height:7px;border-radius:50%;background:#4ade80;display:inline-block;margin-right:6px;animation:pulse-dot 2s ease-in-out infinite}
@keyframes pulse-dot{0%,100%{opacity:1;transform:scale(1)}50%{opacity:0.5;transform:scale(0.85)}}

.bio{font-size:14px;color:#94a3b8;line-height:1.7;max-width:520px;font-weight:300}
.bio strong{color:#cbd5e1;font-weight:400}

.stats-row{display:grid;grid-template-columns:repeat(4,1fr);gap:1px;background:rgba(168,85,247,0.1);border-top:1px solid rgba(99,179,255,0.05);border-bottom:1px solid rgba(99,179,255,0.05)}
.stat{padding:18px 10px;background:#040814;text-align:center}
.stat-n{font-family:'JetBrains Mono',monospace;font-size:22px;font-weight:700;color:#fff;line-height:1}
.stat-n span{color:#a855f7}
.stat-l{font-size:9px;color:#475569;letter-spacing:1.2px;text-transform:uppercase;margin-top:6px}

.section{padding:24px 36px}
.section+.section{border-top:1px solid rgba(99,179,255,0.05)}
.sec-head{display:flex;align-items:center;gap:10px;margin-bottom:16px}
.sec-head-line{width:20px;height:2px;background:#a855f7;border-radius:1px}
.sec-head-text{font-family:'JetBrains Mono',monospace;font-size:10px;color:#93c5fd;letter-spacing:2px;text-transform:uppercase}

.chips{display:flex;flex-wrap:wrap;gap:6px}
.chip{font-family:'JetBrains Mono',monospace;font-size:11px;padding:5px 12px;border-radius:4px;border:1px solid rgba(168,85,247,0.1);color:#64748b;background:rgba(4,8,20,0.5);transition:all 0.2s}
.chip:hover{border-color:rgba(168,85,247,0.5);color:#c084fc;background:rgba(168,85,247,0.05);transform:translateY(-1px)}

.lang-bars{display:flex;flex-direction:column;gap:12px}
.lang-item{display:grid;grid-template-columns:110px 1fr 40px;align-items:center;gap:12px}
.lang-name{font-family:'JetBrains Mono',monospace;font-size:11px;color:#94a3b8}
.lang-track{height:4px;background:rgba(255,255,255,0.03);border-radius:2px;overflow:hidden}
.lang-bar{height:100%;border-radius:2px;background:linear-gradient(90deg, #3b82f6, #a855f7);transform:scaleX(0);transform-origin:left;transition:transform 1.5s cubic-bezier(0.16,1,0.3,1)}
.lang-pct{font-family:'JetBrains Mono',monospace;font-size:10px;color:#475569;text-align:right}

.links-grid{display:flex;gap:8px;flex-wrap:wrap}
.link-btn{font-family:'JetBrains Mono',monospace;font-size:11px;padding:8px 16px;border-radius:4px;border:1px solid rgba(99,179,255,0.1);color:#64748b;text-decoration:none;display:inline-flex;align-items:center;gap:8px;transition:all 0.2s;background:transparent}
.link-btn:hover{border-color:rgba(168,85,247,0.4);color:#c084fc;background:rgba(168,85,247,0.03)}

.footer{padding:16px 36px;border-top:1px solid rgba(99,179,255,0.05);display:flex;align-items:center;justify-content:space-between;background: rgba(2,4,10,0.3)}
.footer-l, .footer-r{font-family:'JetBrains Mono',monospace;font-size:10px;color:#334155}
</style>
</head>
<body>

<div class="root">
  <canvas id="bg"></canvas>
  <div class="over">

    <div class="hero">
      <div class="badge-row">
        <span class="badge badge-green"><span class="status-dot"></span>available for ML collabs</span>
        <span class="badge badge-blue">LLM & RAG Pipelines</span>
        <span class="badge badge-purple">Deep Learning</span>
      </div>
      <div class="hero-top">
        <div class="name-block">
          <div class="label">// HARISH_M.AI</div>
          <h1>Hi, I'm <em>Harish.</em></h1>
          <div class="type-line" id="tl">Data Scientist<span class="cursor"></span></div>
        </div>
        <div class="avatar-ring">
          <div class="avatar-inner">AI</div>
        </div>
      </div>
      <p class="bio">I build <strong>robust, intelligent systems</strong> leveraging state-of-the-art machine learning architectures. From training customized neural nets to deploying semantic knowledge retrieval vectors — I translate raw data into actionable scale.</p>
    </div>

    <div class="stats-row">
      <div class="stat"><div class="stat-n" id="s1">0<span>+</span></div><div class="stat-l">Inferences</div></div>
      <div class="stat"><div class="stat-n" id="s2">0<span>+</span></div><div class="stat-l">Models Tuned</div></div>
      <div class="stat"><div class="stat-n" id="s3">0</div><div class="stat-l">GPU Nodes</div></div>
      <div class="stat"><div class="stat-n" id="s4">0<span>+</span></div><div class="stat-l">Yrs Training</div></div>
    </div>

    <div class="section">
      <div class="sec-head"><div class="sec-head-line"></div><div class="sec-head-text">AI Architecture & Core Tools</div></div>
      <div class="chips">
        <span class="chip">PyTorch</span><span class="chip">TensorFlow</span><span class="chip">HuggingFace</span><span class="chip">LangChain</span><span class="chip">LlamaIndex</span><span class="chip">Python</span><span class="chip">TypeScript</span><span class="chip">FastAPI</span><span class="chip">Docker</span><span class="chip">Kubernetes</span><span class="chip">Pinecone</span><span class="chip">ChromaDB</span><span class="chip">PostgreSQL</span><span class="chip">MongoDB</span><span class="chip">MLflow</span><span class="chip">Weights & Biases</span><span class="chip">AWS Bedrock</span><span class="chip">GCP Vertex</span><span class="chip">Git</span>
      </div>
    </div>

    <div class="section">
      <div class="sec-head"><div class="sec-head-line"></div><div class="sec-head-text">Workspace Distribution</div></div>
      <div class="lang-bars" id="langs">
        <div class="lang-item"><span class="lang-name">Python (ML Core)</span><div class="lang-track"><div class="lang-bar" data-w="85"></div></div><span class="lang-pct">85%</span></div>
        <div class="lang-item"><span class="lang-name">TypeScript (API)</span><div class="lang-track"><div class="lang-bar" data-w="55"></div></div><span class="lang-pct">55%</span></div>
        <div class="lang-item"><span class="lang-name">SQL/Vector DB</span><div class="lang-track"><div class="lang-bar" data-w="68"></div></div><span class="lang-pct">68%</span></div>
        <div class="lang-item"><span class="lang-name">M LOps Pipelines</span><div class="lang-track"><div class="lang-bar" data-w="42"></div></div><span class="lang-pct">42%</span></div>
      </div>
    </div>

    <div class="section">
      <div class="sec-head"><div class="sec-head-line"></div><div class="sec-head-text">Connect Network</div></div>
      <div class="links-grid">
        <a class="link-btn" href="https://github.com/Harish2859"><i class="ti ti-brand-github"></i>GitHub Gateway</a>
        <a class="link-btn" href="https://x.com/arkhamencrypted"><i class="ti ti-brand-x"></i>X / Twitter</a>
        <a class="link-btn" href="https://harishxm.hashnode.dev"><i class="ti ti-notebook"></i>Research Blog</a>
        <a class="link-btn" href="mailto:harishm.aids2023@citchennai.net"><i class="ti ti-mail"></i>Secure Mail</a>
      </div>
    </div>

    <div class="footer">
      <span class="footer-l">Node // Chennai, India</span>
      <span class="footer-r">think with purpose · automate with precision</span>
    </div>

  </div>
</div>

<script>
// --- Deep Neural Graph Network Animation ---
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
  const n = Math.floor((W * H) / 14000); // Increased node density
  for (let i = 0; i < n; i++) {
    pts.push({ 
      x: Math.random() * W, 
      y: Math.random() * H, 
      vx: (Math.random() - 0.5) * 0.4, 
      vy: (Math.random() - 0.5) * 0.4, 
      r: Math.random() * 1.5 + 0.5,
      pulse: Math.random() * Math.PI
    });
  }
}

function draw() {
  ctx.clearRect(0, 0, W, H);
  const dist = 110;
  
  for (let i = 0; i < pts.length; i++) {
    const p = pts[i];
    p.x += p.vx; p.y += p.vy;
    p.pulse += 0.02;

    if (p.x < 0 || p.x > W) p.vx *= -1;
    if (p.y < 0 || p.y > H) p.vy *= -1;
    
    // Neural synapic blink mapping
    const alpha = 0.2 + Math.sin(p.pulse) * 0.15;
    
    ctx.beginPath();
    ctx.arc(p.x, p.y, p.r + (Math.sin(p.pulse) * 0.3), 0, Math.PI * 2);
    // Deep Cyan/Blue shifting to purple accents
    ctx.fillStyle = i % 3 === 0 ? `rgba(168,85,247,${alpha + 0.2})` : `rgba(59,130,246,${alpha})`;
    ctx.fill();
    
    for (let j = i + 1; j < pts.length; j++) {
      const q = pts[j];
      const dx = p.x - q.x, dy = p.y - q.y;
      const d = Math.sqrt(dx * dx + dy * dy);
      if (d < dist) {
        ctx.beginPath();
        ctx.moveTo(p.x, p.y);
        ctx.lineTo(q.x, q.y);
        const grad = ctx.createLinearGradient(p.x, p.y, q.x, q.y);
        grad.addColorStop(0, `rgba(59,130,246,${0.08 * (1 - d / dist)})`);
        grad.addColorStop(1, `rgba(168,85,247,${0.08 * (1 - d / dist)})`);
        ctx.strokeStyle = grad;
        ctx.lineWidth = 0.6;
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

// --- Smooth Cubic Counter Engine ---
function countTo(id, target, duration, suffix) {
  const el = document.getElementById(id);
  const base = el.querySelector('span') ? el.querySelector('span').outerHTML : '';
  let start = null;
  function step(ts) {
    if (!start) start = ts;
    const p = Math.min((ts - start) / duration, 1);
    const eased = 1 - Math.pow(1 - p, 4); // Quartic ease out
    el.innerHTML = Math.round(eased * target).toLocaleString() + base;
    if (p < 1) requestAnimationFrame(step);
  }
  requestAnimationFrame(step);
}

setTimeout(() => {
  countTo('s1', 14200, 1600, '+');
  countTo('s2', 24, 1000, '+');
  countTo('s3', 8, 900, '');
  countTo('s4', 3, 800, '+');
}, 300);

// --- Visualizing Progression Tracks ---
setTimeout(() => {
  document.querySelectorAll('.lang-bar').forEach((bar, i) => {
    setTimeout(() => {
      bar.style.transform = `scaleX(${bar.dataset.w / 100})`;
    }, i * 150);
  });
}, 500);

// --- Adaptive Dynamic Typist Engine ---
const roles = ['Data Scientist', 'AI Engineer', 'LLM Architect', 'Deep Learning Developer'];
let ri = 0, ci = 0, deleting = false;
const tl = document.getElementById('tl');

function typeEffect() {
  const word = roles[ri];
  const cursor = '<span class="cursor"></span>';
  if (!deleting) {
    ci++;
    tl.innerHTML = word.slice(0, ci) + cursor;
    if (ci === word.length) { deleting = true; setTimeout(typeEffect, 2500); return; }
    setTimeout(typeEffect, 75);
  } else {
    ci--;
    tl.innerHTML = word.slice(0, ci) + cursor;
    if (ci === 0) { deleting = false; ri = (ri + 1) % roles.length; setTimeout(typeEffect, 400); return; }
    setTimeout(typeEffect, 40);
  }
}
setTimeout(typeEffect, 800);
</script>
</body>
</html>
