<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Sabry Salah – AI Engineer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Outfit:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
* { box-sizing: border-box; margin: 0; padding: 0; }

body {
  font-family: 'Outfit', sans-serif;
  background: #080c14;
  color: #e2e8f0;
  padding: 40px 20px;
  min-height: 100vh;
  position: relative;
  overflow-x: hidden;
}

.bg-grid {
  position: fixed; inset: 0;
  background-image:
    linear-gradient(rgba(0,200,150,0.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(0,200,150,0.04) 1px, transparent 1px);
  background-size: 40px 40px;
  pointer-events: none;
  z-index: 0;
}

.bg-glow {
  position: fixed;
  border-radius: 50%;
  pointer-events: none;
  filter: blur(80px);
  z-index: 0;
}
.glow-1 { width: 500px; height: 500px; top: -120px; right: -120px; background: rgba(0,180,120,0.13); }
.glow-2 { width: 400px; height: 400px; bottom: -100px; left: -100px; background: rgba(56,100,220,0.1); }

.wrapper {
  max-width: 680px; margin: 0 auto;
  position: relative; z-index: 1;
}

/* ── Header ── */
.header { display: flex; align-items: center; gap: 22px; margin-bottom: 28px; }

.avatar {
  width: 76px; height: 76px; border-radius: 50%;
  background: linear-gradient(135deg, #00c896 0%, #3864dc 100%);
  display: flex; align-items: center; justify-content: center;
  font-family: 'Space Mono', monospace; font-size: 24px; font-weight: 700;
  color: #fff; flex-shrink: 0;
  box-shadow: 0 0 0 3px rgba(0,200,150,0.25), 0 0 24px rgba(0,200,150,0.15);
}

.header-text h1 {
  font-size: 24px; font-weight: 700; color: #f1f5f9; letter-spacing: -0.3px;
}
.header-text h1 span { color: #00c896; }
.tagline {
  font-size: 13px; color: #64748b; margin-top: 5px;
  font-family: 'Space Mono', monospace;
}

.status-dot {
  display: inline-block; width: 7px; height: 7px; border-radius: 50%;
  background: #00c896; margin-right: 7px;
  animation: pulse 2s infinite;
}
@keyframes pulse {
  0%, 100% { box-shadow: 0 0 0 0 rgba(0,200,150,0.5); }
  50% { box-shadow: 0 0 0 5px rgba(0,200,150,0); }
}

/* ── Bio ── */
.bio {
  background: rgba(255,255,255,0.03);
  border: 0.5px solid rgba(255,255,255,0.08);
  border-left: 2px solid #00c896;
  border-radius: 12px;
  padding: 16px 20px; margin-bottom: 24px;
  font-size: 14px; color: #94a3b8; line-height: 1.75;
}
.bio strong { color: #c8f5e8; font-weight: 500; }

/* ── Section Labels ── */
.section-label {
  font-family: 'Space Mono', monospace;
  font-size: 10px; letter-spacing: 2px; text-transform: uppercase;
  color: #00c896; margin-bottom: 14px;
  display: flex; align-items: center; gap: 10px;
}
.section-label::after {
  content: ''; flex: 1; height: 0.5px;
  background: rgba(0,200,150,0.2);
}

/* ── Skills Grid ── */
.skills-grid {
  display: grid; grid-template-columns: 1fr 1fr;
  gap: 10px; margin-bottom: 24px;
}

.skill-card {
  background: rgba(255,255,255,0.03);
  border: 0.5px solid rgba(255,255,255,0.07);
  border-radius: 12px; padding: 16px 18px;
  transition: border-color 0.25s, background 0.25s;
  position: relative; overflow: hidden;
}
.skill-card:hover {
  border-color: rgba(0,200,150,0.4);
  background: rgba(0,200,150,0.05);
}
.skill-card::before {
  content: ''; position: absolute; top: 0; left: 0; right: 0; height: 1px;
  background: linear-gradient(90deg, transparent, rgba(0,200,150,0.6), transparent);
  opacity: 0; transition: opacity 0.25s;
}
.skill-card:hover::before { opacity: 1; }

.skill-icon { font-size: 22px; margin-bottom: 10px; display: block; }
.skill-name { font-size: 13px; font-weight: 500; color: #e2e8f0; margin-bottom: 3px; }
.skill-desc { font-size: 11px; color: #475569; }

/* ── Pills ── */
.pills-row { display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 24px; }
.pill {
  font-family: 'Space Mono', monospace;
  font-size: 11px; padding: 5px 12px; border-radius: 20px;
  border: 0.5px solid rgba(255,255,255,0.1);
  color: #94a3b8; background: rgba(255,255,255,0.03);
  transition: all 0.2s; cursor: default;
}
.pill:hover { border-color: #00c896; color: #00c896; background: rgba(0,200,150,0.07); }
.pill.hl { border-color: rgba(0,200,150,0.4); color: #00c896; background: rgba(0,200,150,0.08); }

/* ── Interests ── */
.interests-row { display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 24px; }
.interest-tag {
  font-size: 12px; padding: 5px 13px; border-radius: 6px;
  background: rgba(56,100,220,0.12);
  border: 0.5px solid rgba(56,100,220,0.25);
  color: #7da4f7;
}

/* ── Stats Bar ── */
.stats-bar {
  display: flex;
  border: 0.5px solid rgba(255,255,255,0.07);
  border-radius: 12px; overflow: hidden;
  margin-bottom: 28px;
}
.stat {
  flex: 1; padding: 16px 12px; text-align: center;
  border-right: 0.5px solid rgba(255,255,255,0.07);
  background: rgba(255,255,255,0.02);
}
.stat:last-child { border-right: none; }
.stat-value {
  font-family: 'Space Mono', monospace;
  font-size: 18px; font-weight: 700; color: #00c896;
}
.stat-label { font-size: 10px; color: #475569; margin-top: 3px; text-transform: uppercase; letter-spacing: 0.5px; }

/* ── Footer ── */
.footer {
  text-align: center;
  font-family: 'Space Mono', monospace;
  font-size: 10px; color: #1e293b;
  padding-top: 8px; letter-spacing: 1px;
}
.footer span { color: #00c896; }
</style>
</head>
<body>
<div class="bg-grid"></div>
<div class="bg-glow glow-1"></div>
<div class="bg-glow glow-2"></div>

<div class="wrapper">

  <div class="header">
    <div class="avatar">SS</div>
    <div class="header-text">
      <h1>Hey, I'm <span>Sabry Salah</span> 👋</h1>
      <div class="tagline"><span class="status-dot"></span>AI Engineer · Building intelligent systems</div>
    </div>
  </div>

  <div class="bio">
    Passionate about <strong>Machine Learning, Computer Vision, LLMs</strong>, and AI-driven automation. I enjoy learning new technologies, building smart solutions, and turning ideas into real-world applications.
  </div>

  <div class="section-label">expertise</div>
  <div class="skills-grid">
    <div class="skill-card">
      <span class="skill-icon">🧠</span>
      <div class="skill-name">ML & Deep Learning</div>
      <div class="skill-desc">Scalable model architectures</div>
    </div>
    <div class="skill-card">
      <span class="skill-icon">👁️</span>
      <div class="skill-name">Computer Vision</div>
      <div class="skill-desc">YOLO & real-time detection</div>
    </div>
    <div class="skill-card">
      <span class="skill-icon">🤖</span>
      <div class="skill-name">LLMs & RAG</div>
      <div class="skill-desc">LangChain-powered applications</div>
    </div>
    <div class="skill-card">
      <span class="skill-icon">⚡</span>
      <div class="skill-name">Embedded & IoT</div>
      <div class="skill-desc">Intelligent edge systems</div>
    </div>
  </div>

  <div class="section-label">stack</div>
  <div class="pills-row">
    <span class="pill hl">Python</span>
    <span class="pill hl">LangChain</span>
    <span class="pill hl">YOLO</span>
    <span class="pill">PyTorch</span>
    <span class="pill">TensorFlow</span>
    <span class="pill">RAG</span>
    <span class="pill">OpenCV</span>
    <span class="pill">FastAPI</span>
    <span class="pill">Docker</span>
    <span class="pill">IoT</span>
  </div>

  <div class="section-label">interests</div>
  <div class="interests-row">
    <span class="interest-tag">Artificial Intelligence</span>
    <span class="interest-tag">Generative AI</span>
    <span class="interest-tag">Smart Automation</span>
    <span class="interest-tag">Robotics</span>
    <span class="interest-tag">AI Research</span>
    <span class="interest-tag">Intelligent Systems</span>
  </div>

  <div class="stats-bar">
    <div class="stat">
      <div class="stat-value">ML</div>
      <div class="stat-label">Core Focus</div>
    </div>
    <div class="stat">
      <div class="stat-value">CV</div>
      <div class="stat-label">Vision AI</div>
    </div>
    <div class="stat">
      <div class="stat-value">LLM</div>
      <div class="stat-label">Language AI</div>
    </div>
    <div class="stat">
      <div class="stat-value">IoT</div>
      <div class="stat-label">Edge AI</div>
    </div>
  </div>

  <div class="footer">// built with <span>intelligence</span> · sabry salah · ai engineer</div>

</div>
</body>
</html>
