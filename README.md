# Nanthees-Ramesh-_portfolio
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Nanthees Ramesh | Data Analyst · Data Scientist · Security Engineer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=JetBrains+Mono:wght@300;400;600&family=Bebas+Neue&display=swap" rel="stylesheet">
<style>
:root {
  --bg: #04060e;
  --surface: #080d1a;
  --surface2: #0c1424;
  --teal: #00e5cc;
  --amber: #ffb830;
  --blue: #1e6fff;
  --red: #ff3e5e;
  --text: #e8edf5;
  --muted: #4a5a7a;
  --border: rgba(0,229,204,0.1);
}

*, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

html { scroll-behavior: smooth; }

body {
  background: var(--bg);
  color: var(--text);
  font-family: 'Syne', sans-serif;
  overflow-x: hidden;
  cursor: none;
}

/* Custom cursor */
.cursor {
  position: fixed;
  width: 10px; height: 10px;
  background: var(--teal);
  border-radius: 50%;
  pointer-events: none;
  z-index: 9999;
  transition: transform 0.1s;
  box-shadow: 0 0 15px var(--teal);
}
.cursor-ring {
  position: fixed;
  width: 36px; height: 36px;
  border: 1px solid rgba(0,229,204,0.4);
  border-radius: 50%;
  pointer-events: none;
  z-index: 9998;
  transition: all 0.15s ease;
}

/* Noise overlay */
body::before {
  content: '';
  position: fixed;
  inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
  pointer-events: none;
  z-index: 9990;
  opacity: 0.6;
}

/* NAV */
nav {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 1000;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 20px 60px;
  background: rgba(4,6,14,0.8);
  backdrop-filter: blur(20px);
  border-bottom: 1px solid var(--border);
}

.nav-logo {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 22px;
  letter-spacing: 3px;
  color: var(--teal);
}

.nav-links {
  display: flex;
  gap: 40px;
  list-style: none;
}

.nav-links a {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: var(--muted);
  text-decoration: none;
  letter-spacing: 2px;
  text-transform: uppercase;
  transition: color 0.3s;
  position: relative;
}
.nav-links a::after {
  content: '';
  position: absolute;
  bottom: -4px; left: 0; right: 0;
  height: 1px;
  background: var(--teal);
  transform: scaleX(0);
  transition: transform 0.3s;
}
.nav-links a:hover { color: var(--teal); }
.nav-links a:hover::after { transform: scaleX(1); }

/* HERO */
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  position: relative;
  overflow: hidden;
  padding: 120px 60px 60px;
}

.hero-bg {
  position: absolute;
  inset: 0;
  overflow: hidden;
}

/* Animated grid */
.hero-grid {
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(rgba(0,229,204,0.03) 1px, transparent 1px),
    linear-gradient(90deg, rgba(0,229,204,0.03) 1px, transparent 1px);
  background-size: 60px 60px;
  animation: gridPan 30s linear infinite;
}
@keyframes gridPan {
  from { transform: translate(0,0); }
  to { transform: translate(60px,60px); }
}

.hero-orb-1 {
  position: absolute;
  width: 700px; height: 700px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(0,229,204,0.12) 0%, transparent 65%);
  top: -200px; right: -100px;
  animation: breathe 8s ease-in-out infinite;
}
.hero-orb-2 {
  position: absolute;
  width: 500px; height: 500px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(30,111,255,0.1) 0%, transparent 65%);
  bottom: -150px; left: 200px;
  animation: breathe 12s ease-in-out infinite reverse;
}
@keyframes breathe {
  0%,100% { transform: scale(1); opacity: 0.8; }
  50% { transform: scale(1.15); opacity: 1; }
}

/* Floating particles */
.particles {
  position: absolute;
  inset: 0;
  pointer-events: none;
}
.particle {
  position: absolute;
  width: 2px; height: 2px;
  background: var(--teal);
  border-radius: 50%;
  animation: floatUp var(--dur, 8s) ease-in-out infinite;
  opacity: 0;
}
@keyframes floatUp {
  0% { transform: translateY(100vh) translateX(0); opacity: 0; }
  10% { opacity: 0.6; }
  90% { opacity: 0.2; }
  100% { transform: translateY(-100px) translateX(var(--drift, 50px)); opacity: 0; }
}

.hero-content {
  position: relative;
  z-index: 10;
  max-width: 900px;
}

.hero-badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: var(--teal);
  letter-spacing: 3px;
  border: 1px solid rgba(0,229,204,0.25);
  padding: 8px 16px;
  margin-bottom: 32px;
  clip-path: polygon(10px 0%, 100% 0%, calc(100% - 10px) 100%, 0% 100%);
  background: rgba(0,229,204,0.05);
}
.hero-badge .blink {
  width: 6px; height: 6px;
  background: var(--teal);
  border-radius: 50%;
  animation: blinkAnim 1.5s step-end infinite;
  box-shadow: 0 0 8px var(--teal);
}
@keyframes blinkAnim { 0%,100%{opacity:1} 50%{opacity:0} }

.hero-name {
  font-family: 'Bebas Neue', sans-serif;
  font-size: clamp(72px, 9vw, 140px);
  line-height: 0.9;
  letter-spacing: 2px;
  color: var(--text);
  margin-bottom: 24px;
}
.hero-name .highlight {
  color: var(--teal);
  position: relative;
  display: inline-block;
}
.hero-name .highlight::after {
  content: '';
  position: absolute;
  bottom: 4px; left: 0; right: 0;
  height: 4px;
  background: linear-gradient(90deg, var(--teal), transparent);
}

.hero-roles {
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
  margin-bottom: 32px;
}

.role-chip {
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  padding: 8px 20px;
  letter-spacing: 2px;
  text-transform: uppercase;
  border: 1px solid;
  position: relative;
  overflow: hidden;
  transition: all 0.3s;
}
.role-chip.teal { border-color: var(--teal); color: var(--teal); }
.role-chip.amber { border-color: var(--amber); color: var(--amber); }
.role-chip.blue { border-color: var(--blue); color: #6699ff; }
.role-chip::before {
  content: '';
  position: absolute;
  inset: 0;
  background: currentColor;
  opacity: 0;
  transition: opacity 0.3s;
}
.role-chip:hover::before { opacity: 0.1; }

.hero-tagline {
  font-size: 16px;
  color: var(--muted);
  line-height: 1.7;
  max-width: 560px;
  margin-bottom: 48px;
  font-weight: 400;
}

.hero-cta {
  display: flex;
  gap: 16px;
  align-items: center;
  flex-wrap: wrap;
}

.btn-primary {
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  letter-spacing: 2px;
  padding: 14px 32px;
  background: var(--teal);
  color: var(--bg);
  text-decoration: none;
  font-weight: 600;
  text-transform: uppercase;
  clip-path: polygon(8px 0%, 100% 0%, calc(100% - 8px) 100%, 0% 100%);
  transition: all 0.3s;
}
.btn-primary:hover { background: #00ffdd; transform: translateY(-2px); box-shadow: 0 10px 30px rgba(0,229,204,0.3); }

.btn-ghost {
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  letter-spacing: 2px;
  padding: 13px 32px;
  border: 1px solid var(--muted);
  color: var(--muted);
  text-decoration: none;
  text-transform: uppercase;
  transition: all 0.3s;
  clip-path: polygon(8px 0%, 100% 0%, calc(100% - 8px) 100%, 0% 100%);
}
.btn-ghost:hover { border-color: var(--teal); color: var(--teal); }

/* Terminal block */
.terminal {
  position: absolute;
  right: 60px;
  top: 50%;
  transform: translateY(-50%);
  width: 380px;
  background: rgba(8,13,26,0.9);
  border: 1px solid rgba(0,229,204,0.2);
  border-radius: 2px;
  overflow: hidden;
  box-shadow: 0 30px 80px rgba(0,0,0,0.5), 0 0 40px rgba(0,229,204,0.05);
}
.terminal-header {
  background: rgba(0,229,204,0.08);
  padding: 10px 16px;
  display: flex;
  align-items: center;
  gap: 8px;
  border-bottom: 1px solid rgba(0,229,204,0.1);
}
.t-dot { width: 10px; height: 10px; border-radius: 50%; }
.terminal-body {
  padding: 20px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  line-height: 2;
}
.t-line { display: flex; align-items: center; gap: 8px; }
.t-prompt { color: var(--teal); }
.t-cmd { color: var(--text); }
.t-out { color: var(--muted); padding-left: 16px; }
.t-val { color: var(--amber); }
.t-comment { color: #2a4060; }
.t-cursor-blink {
  display: inline-block;
  width: 8px; height: 14px;
  background: var(--teal);
  animation: blinkAnim 1s step-end infinite;
  vertical-align: middle;
  margin-left: 2px;
}

/* Section base */
section {
  padding: 120px 60px;
  position: relative;
}

.section-label {
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  letter-spacing: 4px;
  text-transform: uppercase;
  color: var(--teal);
  margin-bottom: 16px;
  opacity: 0;
  transform: translateY(20px);
  transition: all 0.6s;
}
.section-title {
  font-family: 'Bebas Neue', sans-serif;
  font-size: clamp(48px, 6vw, 90px);
  line-height: 0.95;
  margin-bottom: 60px;
  opacity: 0;
  transform: translateY(20px);
  transition: all 0.6s 0.1s;
}
.in-view .section-label,
.in-view .section-title { opacity: 1; transform: translateY(0); }

/* ABOUT */
.about {
  background: var(--surface);
}
.about-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 80px;
  align-items: center;
}
.about-text p {
  font-size: 16px;
  line-height: 1.9;
  color: rgba(232,237,245,0.75);
  margin-bottom: 20px;
}
.about-text strong { color: var(--teal); font-weight: 600; }

.stats-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2px;
}
.stat-card {
  background: var(--bg);
  padding: 32px 28px;
  border: 1px solid var(--border);
  position: relative;
  overflow: hidden;
  transition: border-color 0.3s;
}
.stat-card:hover { border-color: rgba(0,229,204,0.3); }
.stat-card::before {
  content: '';
  position: absolute;
  bottom: 0; left: 0; right: 0;
  height: 2px;
  background: linear-gradient(90deg, var(--teal), transparent);
  opacity: 0;
  transition: opacity 0.3s;
}
.stat-card:hover::before { opacity: 1; }
.stat-number {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 52px;
  color: var(--teal);
  line-height: 1;
  margin-bottom: 4px;
}
.stat-label {
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  color: var(--muted);
  letter-spacing: 2px;
  text-transform: uppercase;
}

/* DATA ANALYTICS */
.analytics {
  background: var(--bg);
  position: relative;
  overflow: hidden;
}

.section-header-line {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  margin-bottom: 60px;
}

.skill-showcase {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2px;
  margin-bottom: 60px;
}

.skill-card {
  background: var(--surface);
  padding: 36px 32px;
  border: 1px solid var(--border);
  position: relative;
  overflow: hidden;
  transition: all 0.4s;
  opacity: 0;
  transform: translateY(30px);
}
.skill-card.in-view { opacity: 1; transform: translateY(0); }
.skill-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 3px;
  background: linear-gradient(90deg, var(--teal), var(--blue));
  transform: scaleX(0);
  transform-origin: left;
  transition: transform 0.4s;
}
.skill-card:hover { border-color: rgba(0,229,204,0.25); background: var(--surface2); }
.skill-card:hover::before { transform: scaleX(1); }

.skill-icon {
  font-size: 36px;
  margin-bottom: 20px;
  display: block;
}
.skill-card h3 {
  font-family: 'Syne', sans-serif;
  font-size: 20px;
  font-weight: 700;
  margin-bottom: 10px;
  color: var(--text);
}
.skill-card p {
  font-size: 13px;
  color: var(--muted);
  line-height: 1.7;
}

/* Skill bars section */
.skill-bars {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 30px 80px;
}
.bar-item {}
.bar-header {
  display: flex;
  justify-content: space-between;
  margin-bottom: 8px;
}
.bar-name {
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  letter-spacing: 1px;
  color: var(--text);
}
.bar-pct {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: var(--teal);
}
.bar-track {
  height: 4px;
  background: rgba(255,255,255,0.05);
  border-radius: 2px;
  overflow: hidden;
}
.bar-fill {
  height: 100%;
  border-radius: 2px;
  width: 0%;
  transition: width 1.5s cubic-bezier(0.16,1,0.3,1);
}
.bar-fill.teal { background: linear-gradient(90deg, #0066cc, var(--teal)); }
.bar-fill.amber { background: linear-gradient(90deg, #cc7700, var(--amber)); }

/* DATA SCIENCE */
.datascience {
  background: var(--surface);
  overflow: hidden;
}

.ds-grid {
  display: grid;
  grid-template-columns: 1fr 1.2fr;
  gap: 80px;
  align-items: start;
}

.ds-categories {
  display: flex;
  flex-direction: column;
  gap: 2px;
}

.ds-cat {
  padding: 24px 28px;
  background: var(--bg);
  border: 1px solid var(--border);
  cursor: pointer;
  transition: all 0.3s;
  position: relative;
  overflow: hidden;
}
.ds-cat.active, .ds-cat:hover {
  border-color: var(--teal);
  background: rgba(0,229,204,0.04);
}
.ds-cat.active::before {
  content: '';
  position: absolute;
  left: 0; top: 0; bottom: 0;
  width: 3px;
  background: var(--teal);
}

.ds-cat-title {
  font-family: 'Syne', sans-serif;
  font-size: 16px;
  font-weight: 700;
  color: var(--text);
  margin-bottom: 4px;
}
.ds-cat-sub {
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  color: var(--muted);
  letter-spacing: 1px;
}

.ds-detail {
  padding: 40px;
  background: var(--bg);
  border: 1px solid var(--border);
  min-height: 400px;
}
.ds-detail-title {
  font-family: 'Bebas Neue', sans-serif;
  font-size: 40px;
  color: var(--teal);
  margin-bottom: 20px;
  letter-spacing: 2px;
}
.ds-detail-text {
  font-size: 14px;
  color: rgba(232,237,245,0.7);
  line-height: 1.9;
  margin-bottom: 24px;
}
.tech-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}
.tech-tag {
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  padding: 5px 12px;
  border: 1px solid rgba(255,184,48,0.3);
  color: var(--amber);
  letter-spacing: 1px;
}

/* PROJECTS */
.projects {
  background: var(--bg);
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2px;
}

.project-card {
  background: var(--surface);
  border: 1px solid var(--border);
  overflow: hidden;
  position: relative;
  transition: all 0.4s;
  opacity: 0;
  transform: translateY(40px);
}
.project-card.in-view { opacity: 1; transform: translateY(0); }
.project-card:hover { border-color: rgba(0,229,204,0.3); transform: translateY(-4px); }

.project-card-top {
  height: 160px;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}
.project-card-body { padding: 28px; }
.project-cat {
  font-family: 'JetBrains Mono', monospace;
  font-size: 9px;
  letter-spacing: 3px;
  margin-bottom: 8px;
  text-transform: uppercase;
}
.project-card h3 {
  font-size: 18px;
  font-weight: 700;
  margin-bottom: 10px;
}
.project-card p {
  font-size: 12px;
  color: var(--muted);
  line-height: 1.7;
  margin-bottom: 20px;
}
.project-link {
  font-family: 'JetBrains Mono', monospace;
  font-size: 10px;
  letter-spacing: 2px;
  color: var(--teal);
  text-decoration: none;
  text-transform: uppercase;
  display: flex;
  align-items: center;
  gap: 6px;
}
.project-link::after {
  content: '→';
  transition: transform 0.3s;
}
.project-card:hover .project-link::after { transform: translateX(4px); }

/* SECURITY */
.security {
  background: linear-gradient(180deg, var(--surface) 0%, #060410 100%);
  position: relative;
  overflow: hidden;
}
.security::before {
  content: '';
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(rgba(255,62,94,0.03) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255,62,94,0.03) 1px, transparent 1px);
  background-size: 50px 50px;
}

.security .section-title { color: var(--red); }
.security .section-label { color: var(--red); }

.security-grid {
  display: grid;
  grid-template-columns: 1.2fr 1fr;
  gap: 60px;
  align-items: start;
}

.threat-display {
  background: #080010;
  border: 1px solid rgba(255,62,94,0.2);
  padding: 30px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  line-height: 2.2;
}
.threat-header {
  color: var(--red);
  font-size: 9px;
  letter-spacing: 3px;
  border-bottom: 1px solid rgba(255,62,94,0.15);
  padding-bottom: 12px;
  margin-bottom: 16px;
}
.threat-row {
  display: flex;
  justify-content: space-between;
  padding: 4px 0;
  border-bottom: 1px solid rgba(255,62,94,0.04);
}
.threat-key { color: #6a4a7a; }
.threat-val { color: rgba(255,62,94,0.8); }
.threat-val.green { color: #00e5a0; }
.threat-val.amber { color: var(--amber); }

.sec-skills {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.sec-skill-item {
  display: flex;
  align-items: center;
  gap: 16px;
  padding: 18px 20px;
  background: rgba(255,62,94,0.04);
  border: 1px solid rgba(255,62,94,0.1);
  transition: all 0.3s;
}
.sec-skill-item:hover {
  border-color: rgba(255,62,94,0.3);
  background: rgba(255,62,94,0.08);
}
.sec-icon { font-size: 22px; flex-shrink: 0; }
.sec-info h4 { font-size: 14px; font-weight: 700; margin-bottom: 3px; }
.sec-info p { font-size: 11px; color: var(--muted); font-family: 'JetBrains Mono', monospace; }

/* CONTACT */
.contact {
  background: var(--bg);
  text-align: center;
  padding: 120px 60px;
}

.contact-inner {
  max-width: 700px;
  margin: 0 auto;
}
.contact-title {
  font-family: 'Bebas Neue', sans-serif;
  font-size: clamp(56px, 8vw, 120px);
  line-height: 0.9;
  margin-bottom: 32px;
  color: var(--text);
}
.contact-title span { color: var(--teal); }
.contact-desc {
  font-size: 16px;
  color: var(--muted);
  margin-bottom: 48px;
  line-height: 1.7;
}

.contact-links {
  display: flex;
  justify-content: center;
  gap: 16px;
  flex-wrap: wrap;
  margin-bottom: 60px;
}

.contact-link {
  display: flex;
  align-items: center;
  gap: 10px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 12px;
  color: var(--text);
  text-decoration: none;
  padding: 14px 24px;
  border: 1px solid var(--border);
  letter-spacing: 1px;
  transition: all 0.3s;
  clip-path: polygon(8px 0%, 100% 0%, calc(100% - 8px) 100%, 0% 100%);
}
.contact-link:hover { border-color: var(--teal); color: var(--teal); transform: translateY(-2px); }
.contact-link.primary { background: var(--teal); color: var(--bg); border-color: var(--teal); font-weight: 600; }
.contact-link.primary:hover { background: #00ffdd; }

/* Footer */
footer {
  background: var(--surface);
  border-top: 1px solid var(--border);
  padding: 24px 60px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
footer .logo { font-family: 'Bebas Neue', sans-serif; font-size: 18px; color: var(--muted); letter-spacing: 3px; }
footer .copy { font-family: 'JetBrains Mono', monospace; font-size: 10px; color: var(--muted); letter-spacing: 1px; }

/* Scroll reveal */
.reveal {
  opacity: 0;
  transform: translateY(30px);
  transition: opacity 0.7s ease, transform 0.7s ease;
}
.reveal.visible {
  opacity: 1;
  transform: translateY(0);
}

/* Responsive tweaks */
@media (max-width: 900px) {
  nav { padding: 16px 24px; }
  section { padding: 80px 24px; }
  .hero { padding: 120px 24px 60px; }
  .terminal { display: none; }
  .about-grid,
  .ds-grid,
  .security-grid { grid-template-columns: 1fr; gap: 40px; }
  .skill-showcase,
  .projects-grid { grid-template-columns: 1fr; }
  .skill-bars { grid-template-columns: 1fr; }
  footer { flex-direction: column; gap: 8px; text-align: center; }
  .nav-links { display: none; }
}
</style>
</head>
<body>

<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<!-- NAV -->
<nav>
  <div class="nav-logo">NR</div>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#analytics">Analytics</a></li>
    <li><a href="#datascience">Data Science</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#security">Security</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="https://www.linkedin.com/in/nanthees-rameshbabu-604a7b262" target="_blank">LinkedIn ↗</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-bg">
    <div class="hero-grid"></div>
    <div class="hero-orb-1"></div>
    <div class="hero-orb-2"></div>
    <div class="particles" id="particles"></div>
  </div>

  <div class="hero-content">
    <div class="hero-badge">
      <div class="blink"></div>
      Available for Opportunities
    </div>

    <h1 class="hero-name">
      NANTHEES<br>
      <span class="highlight">RAMESH</span>
    </h1>

    <div class="hero-roles">
      <div class="role-chip teal">Data Analyst</div>
      <div class="role-chip amber">Data Scientist</div>
      <div class="role-chip blue">Security Engineer</div>
    </div>

    <p class="hero-tagline">
      Transforming raw data into powerful insights — and securing the systems that hold them.
      I operate at the intersection of <strong style="color:var(--teal)">analytics</strong>, 
      <strong style="color:var(--amber)">machine learning</strong>, and 
      <strong style="color:#6699ff">cybersecurity</strong>.
    </p>

    <div class="hero-cta">
      <a href="#projects" class="btn-primary">View My Work</a>
      <a href="#contact" class="btn-ghost">Get In Touch</a>
    </div>
  </div>

  <!-- Floating terminal -->
  <div class="terminal">
    <div class="terminal-header">
      <div class="t-dot" style="background:#ff3e5e"></div>
      <div class="t-dot" style="background:#ffb830"></div>
      <div class="t-dot" style="background:#00e5cc"></div>
      <span style="font-family:'JetBrains Mono',monospace;font-size:10px;color:var(--muted);margin-left:8px">profile.py</span>
    </div>
    <div class="terminal-body">
      <div class="t-line"><span class="t-comment"># nanthees_ramesh.py</span></div>
      <div class="t-line" style="margin-top:8px"><span class="t-prompt">»</span><span class="t-cmd"> profile = {</span></div>
      <div class="t-line"><span class="t-out">&nbsp;&nbsp;"name":</span> <span class="t-val">"Nanthees Ramesh"</span><span class="t-cmd">,</span></div>
      <div class="t-line"><span class="t-out">&nbsp;&nbsp;"role":</span> <span class="t-val">["Analyst","DS","SecEng"]</span><span class="t-cmd">,</span></div>
      <div class="t-line"><span class="t-out">&nbsp;&nbsp;"skills": {</span></div>
      <div class="t-line"><span class="t-out">&nbsp;&nbsp;&nbsp;&nbsp;"sql":</span> <span class="t-val">True</span><span class="t-cmd">,</span></div>
      <div class="t-line"><span class="t-out">&nbsp;&nbsp;&nbsp;&nbsp;"python":</span> <span class="t-val">["pandas","numpy"]</span><span class="t-cmd">,</span></div>
      <div class="t-line"><span class="t-out">&nbsp;&nbsp;&nbsp;&nbsp;"bi":</span> <span class="t-val">"Power BI"</span><span class="t-cmd">,</span></div>
      <div class="t-line"><span class="t-out">&nbsp;&nbsp;&nbsp;&nbsp;"security":</span> <span class="t-val">True</span></div>
      <div class="t-line"><span class="t-out">&nbsp;&nbsp;}</span></div>
      <div class="t-line"><span class="t-cmd">}</span></div>
      <div class="t-line" style="margin-top:8px"><span class="t-prompt">»</span><span class="t-cmd"> status = </span><span class="t-val">"READY"</span></div>
      <div class="t-line"><span class="t-prompt">»</span><span class="t-cmd"> <span class="t-cursor-blink"></span></span></div>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section class="about" id="about">
  <div class="section-label reveal">// 01 — About</div>
  <div class="about-grid">
    <div class="about-text reveal">
      <div class="section-title">WHO I<br>AM</div>
      <p>I'm <strong>Nanthees Ramesh</strong>, a multi-disciplinary tech professional with a passion for turning complex data into clear decisions — and making sure those systems stay bulletproof.</p>
      <p>My work spans <strong>data analytics</strong> (SQL, Excel, Power BI), <strong>data science</strong> (Python, Pandas, NumPy), and <strong>cybersecurity engineering</strong> — a rare combination that lets me build, analyze, and protect.</p>
      <p>I thrive at the edge where data intelligence meets system security.</p>
    </div>
    <div class="stats-grid reveal" style="transition-delay:0.2s">
      <div class="stat-card">
        <div class="stat-number">3+</div>
        <div class="stat-label">Domains Mastered</div>
      </div>
      <div class="stat-card">
        <div class="stat-number">5+</div>
        <div class="stat-label">Core Tools</div>
      </div>
      <div class="stat-card">
        <div class="stat-number">∞</div>
        <div class="stat-label">Curiosity Level</div>
      </div>
      <div class="stat-card">
        <div class="stat-number">01</div>
        <div class="stat-label">Focus: Impact</div>
      </div>
    </div>
  </div>
</section>

<!-- DATA ANALYTICS -->
<section class="analytics" id="analytics">
  <div class="section-label reveal">// 02 — Data Analytics</div>
  <div class="section-title reveal">DATA<br>ANALYTICS</div>

  <div class="skill-showcase">
    <div class="skill-card reveal" style="transition-delay:0s">
      <span class="skill-icon">🗃️</span>
      <h3>SQL & Databases</h3>
      <p>Advanced querying, complex JOINs, window functions, CTEs, and performance optimization for large-scale datasets.</p>
    </div>
    <div class="skill-card reveal" style="transition-delay:0.1s">
      <span class="skill-icon">📊</span>
      <h3>Power BI</h3>
      <p>Interactive dashboards, DAX formulas, data modeling, and storytelling that drives executive decisions.</p>
    </div>
    <div class="skill-card reveal" style="transition-delay:0.2s">
      <span class="skill-icon">📋</span>
      <h3>Excel & Spreadsheets</h3>
      <p>Pivot tables, VLOOKUP, macros, financial modelling, and automated reporting workflows.</p>
    </div>
  </div>

  <div style="margin-top: 60px;">
    <div class="section-label reveal" style="margin-bottom:32px">// Technical Proficiency</div>
    <div class="skill-bars" id="skillBars">
      <div class="bar-item reveal">
        <div class="bar-header"><span class="bar-name">SQL / Database Querying</span><span class="bar-pct">92%</span></div>
        <div class="bar-track"><div class="bar-fill teal" data-w="92"></div></div>
      </div>
      <div class="bar-item reveal" style="transition-delay:0.1s">
        <div class="bar-header"><span class="bar-name">Microsoft Excel</span><span class="bar-pct">90%</span></div>
        <div class="bar-track"><div class="bar-fill teal" data-w="90"></div></div>
      </div>
      <div class="bar-item reveal" style="transition-delay:0.2s">
        <div class="bar-header"><span class="bar-name">Power BI & Visualization</span><span class="bar-pct">85%</span></div>
        <div class="bar-track"><div class="bar-fill amber" data-w="85"></div></div>
      </div>
      <div class="bar-item reveal" style="transition-delay:0.3s">
        <div class="bar-header"><span class="bar-name">Python — Pandas / NumPy</span><span class="bar-pct">88%</span></div>
        <div class="bar-track"><div class="bar-fill amber" data-w="88"></div></div>
      </div>
      <div class="bar-item reveal" style="transition-delay:0.4s">
        <div class="bar-header"><span class="bar-name">Data Storytelling & Reporting</span><span class="bar-pct">87%</span></div>
        <div class="bar-track"><div class="bar-fill teal" data-w="87"></div></div>
      </div>
      <div class="bar-item reveal" style="transition-delay:0.5s">
        <div class="bar-header"><span class="bar-name">Statistical Analysis</span><span class="bar-pct">80%</span></div>
        <div class="bar-track"><div class="bar-fill amber" data-w="80"></div></div>
      </div>
    </div>
  </div>
</section>

<!-- DATA SCIENCE -->
<section class="datascience" id="datascience">
  <div class="section-label reveal">// 03 — Data Science</div>
  <div class="section-title reveal">DATA<br>SCIENCE</div>

  <div class="ds-grid">
    <div class="ds-categories reveal">
      <div class="ds-cat active" onclick="showDs(this,'eda')">
        <div class="ds-cat-title">Exploratory Data Analysis</div>
        <div class="ds-cat-sub">pandas · matplotlib · seaborn</div>
      </div>
      <div class="ds-cat" onclick="showDs(this,'ml')">
        <div class="ds-cat-title">Machine Learning</div>
        <div class="ds-cat-sub">scikit-learn · models · pipelines</div>
      </div>
      <div class="ds-cat" onclick="showDs(this,'wrangling')">
        <div class="ds-cat-title">Data Wrangling & Cleaning</div>
        <div class="ds-cat-sub">numpy · pandas · ETL workflows</div>
      </div>
      <div class="ds-cat" onclick="showDs(this,'stats')">
        <div class="ds-cat-title">Statistical Modelling</div>
        <div class="ds-cat-sub">hypothesis testing · regression</div>
      </div>
    </div>

    <div class="ds-detail reveal" style="transition-delay:0.2s" id="dsDetail">
      <div class="ds-detail-title" id="dsTitle">EXPLORATORY DATA ANALYSIS</div>
      <p class="ds-detail-text" id="dsText">
        Deep-dive into datasets using Python's Pandas and visualization libraries. 
        I uncover hidden patterns, correlations, outliers, and distributions — 
        building a clear understanding before any modelling begins.
        Every insight starts with asking the right question of the data.
      </p>
      <div class="tech-tags" id="dsTags">
        <span class="tech-tag">PANDAS</span>
        <span class="tech-tag">MATPLOTLIB</span>
        <span class="tech-tag">SEABORN</span>
        <span class="tech-tag">NUMPY</span>
        <span class="tech-tag">JUPYTER</span>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section class="projects" id="projects">
  <div class="section-label reveal">// 04 — Projects</div>
  <div class="section-title reveal">FEATURED<br>WORK</div>

  <div class="projects-grid">
    <div class="project-card reveal" style="transition-delay:0s">
      <div class="project-card-top" style="background:linear-gradient(135deg,#050d20,#0a1a35);">
        <svg width="80" height="60" viewBox="0 0 80 60">
          <rect x="5" y="40" width="10" height="15" fill="rgba(0,229,204,0.7)" rx="1"/>
          <rect x="20" y="28" width="10" height="27" fill="rgba(0,229,204,0.5)" rx="1"/>
          <rect x="35" y="18" width="10" height="37" fill="rgba(0,229,204,0.8)" rx="1"/>
          <rect x="50" y="32" width="10" height="23" fill="rgba(0,229,204,0.4)" rx="1"/>
          <rect x="65" y="10" width="10" height="45" fill="rgba(0,229,204,0.9)" rx="1"/>
          <polyline points="10,40 25,28 40,18 55,32 70,10" stroke="rgba(0,229,204,0.4)" stroke-width="1" fill="none" stroke-dasharray="3,3"/>
        </svg>
      </div>
      <div class="project-card-body">
        <div class="project-cat" style="color:var(--teal)">Data Analytics</div>
        <h3>Sales Performance Dashboard</h3>
        <p>Interactive Power BI dashboard tracking KPIs, regional performance, and revenue trends with drill-through capabilities.</p>
        <a href="#" class="project-link">View Project</a>
      </div>
    </div>

    <div class="project-card reveal" style="transition-delay:0.1s">
      <div class="project-card-top" style="background:linear-gradient(135deg,#130c00,#261800);">
        <svg width="100" height="60" viewBox="0 0 100 60">
          <circle cx="30" cy="30" r="18" fill="none" stroke="rgba(255,184,48,0.5)" stroke-width="1.5"/>
          <circle cx="30" cy="30" r="10" fill="rgba(255,184,48,0.2)"/>
          <circle cx="30" cy="30" r="3" fill="rgba(255,184,48,0.9)"/>
          <line x1="48" y1="30" x2="70" y2="30" stroke="rgba(255,184,48,0.3)" stroke-width="1"/>
          <text x="72" y="34" fill="rgba(255,184,48,0.6)" font-size="9" font-family="monospace">0.92</text>
          <circle cx="30" cy="10" r="2" fill="rgba(255,184,48,0.4)"/>
          <circle cx="50" cy="20" r="2" fill="rgba(255,184,48,0.4)"/>
          <circle cx="15" cy="45" r="2" fill="rgba(255,184,48,0.4)"/>
          <circle cx="40" cy="48" r="2" fill="rgba(255,184,48,0.4)"/>
        </svg>
      </div>
      <div class="project-card-body">
        <div class="project-cat" style="color:var(--amber)">Data Science</div>
        <h3>Predictive Analytics Model</h3>
        <p>ML model built with scikit-learn and Python to forecast business outcomes with 92% accuracy using historical data.</p>
        <a href="#" class="project-link">View Project</a>
      </div>
    </div>

    <div class="project-card reveal" style="transition-delay:0.2s">
      <div class="project-card-top" style="background:linear-gradient(135deg,#0e0008,#1a0010);">
        <svg width="90" height="60" viewBox="0 0 90 60">
          <rect x="15" y="10" width="60" height="40" rx="4" fill="none" stroke="rgba(255,62,94,0.4)" stroke-width="1.5"/>
          <rect x="25" y="18" width="40" height="4" rx="2" fill="rgba(255,62,94,0.3)"/>
          <rect x="25" y="26" width="28" height="3" rx="1.5" fill="rgba(255,62,94,0.15)"/>
          <rect x="25" y="33" width="34" height="3" rx="1.5" fill="rgba(255,62,94,0.15)"/>
          <circle cx="68" cy="15" r="8" fill="#0e0008" stroke="rgba(255,62,94,0.5)" stroke-width="1.5"/>
          <text x="64" y="19" fill="rgba(255,62,94,0.9)" font-size="10">🔒</text>
        </svg>
      </div>
      <div class="project-card-body">
        <div class="project-cat" style="color:var(--red)">Security</div>
        <h3>Network Threat Monitor</h3>
        <p>Real-time security monitoring system that detects anomalies and potential intrusions using log analysis and alerting.</p>
        <a href="#" class="project-link">View Project</a>
      </div>
    </div>
  </div>
</section>

<!-- SECURITY -->
<section class="security" id="security">
  <div class="section-label reveal">// 05 — Cybersecurity</div>
  <div class="section-title reveal">SECURITY<br>ENGINEERING</div>

  <div class="security-grid">
    <div class="reveal">
      <div class="threat-display">
        <div class="threat-header">SYSTEM SECURITY AUDIT LOG — LIVE FEED</div>
        <div class="threat-row"><span class="threat-key">Network_Scan</span><span class="threat-val green">✔ CLEAR</span></div>
        <div class="threat-row"><span class="threat-key">Intrusion_Detection</span><span class="threat-val green">✔ ACTIVE</span></div>
        <div class="threat-row"><span class="threat-key">Vulnerability_Assessment</span><span class="threat-val green">✔ PASS</span></div>
        <div class="threat-row"><span class="threat-key">Encryption_Status</span><span class="threat-val green">AES-256</span></div>
        <div class="threat-row"><span class="threat-key">Firewall</span><span class="threat-val green">✔ ENABLED</span></div>
        <div class="threat-row"><span class="threat-key">Threat_Level</span><span class="threat-val amber">MONITOR</span></div>
        <div class="threat-row"><span class="threat-key">Last_Scan</span><span class="threat-val">00:00:02 ago</span></div>
        <div class="threat-row" style="margin-top:12px;border-top:1px solid rgba(255,62,94,0.1);padding-top:12px">
          <span class="threat-key">System_Status</span><span class="threat-val green">SECURED BY NR</span>
        </div>
      </div>
    </div>

    <div class="sec-skills reveal" style="transition-delay:0.2s">
      <div class="sec-skill-item">
        <div class="sec-icon">🛡️</div>
        <div class="sec-info">
          <h4>Network Security</h4>
          <p>Monitoring · Firewalls · IDS/IPS</p>
        </div>
      </div>
      <div class="sec-skill-item">
        <div class="sec-icon">🔍</div>
        <div class="sec-info">
          <h4>Vulnerability Analysis</h4>
          <p>Pen Testing · CVE Review · Risk Assessment</p>
        </div>
      </div>
      <div class="sec-skill-item">
        <div class="sec-icon">🔐</div>
        <div class="sec-info">
          <h4>Encryption & Auth</h4>
          <p>PKI · SSL/TLS · Access Control</p>
        </div>
      </div>
      <div class="sec-skill-item">
        <div class="sec-icon">📈</div>
        <div class="sec-info">
          <h4>Security Analytics</h4>
          <p>SIEM · Log Analysis · Threat Intelligence</p>
        </div>
      </div>
      <div class="sec-skill-item">
        <div class="sec-icon">🧩</div>
        <div class="sec-info">
          <h4>Incident Response</h4>
          <p>Detection · Containment · Recovery</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section class="contact" id="contact">
  <div class="contact-inner">
    <div class="section-label reveal" style="justify-content:center;display:flex">// 06 — Contact</div>
    <h2 class="contact-title reveal">LET'S<br><span>CONNECT</span></h2>
    <p class="contact-desc reveal">
      Whether you're looking for a data analyst, data scientist, or security engineer — or all three — I'd love to hear from you.
    </p>

    <div class="contact-links reveal">
      <a href="mailto:nnantheesr@gmail.com" class="contact-link primary">
        ✉ nnantheesr@gmail.com
      </a>
      <a href="tel:9345006032" class="contact-link">
        📱 9345006032
      </a>
      <a href="https://www.linkedin.com/in/nanthees-rameshbabu-604a7b262" target="_blank" class="contact-link">
        in LinkedIn Profile
      </a>
    </div>
  </div>
</section>

<footer>
  <div class="logo">NANTHEES RAMESH</div>
  <div class="copy">© 2025 · Data Analyst · Data Scientist · Security Engineer</div>
</footer>

<script>
// Cursor
const cursor = document.getElementById('cursor');
const ring = document.getElementById('cursorRing');
let mx = 0, my = 0, rx = 0, ry = 0;
document.addEventListener('mousemove', e => {
  mx = e.clientX; my = e.clientY;
  cursor.style.left = mx - 5 + 'px';
  cursor.style.top = my - 5 + 'px';
});
function animRing() {
  rx += (mx - rx - 18) * 0.12;
  ry += (my - ry - 18) * 0.12;
  ring.style.left = rx + 'px';
  ring.style.top = ry + 'px';
  requestAnimationFrame(animRing);
}
animRing();

// Particles
const container = document.getElementById('particles');
for (let i = 0; i < 30; i++) {
  const p = document.createElement('div');
  p.className = 'particle';
  p.style.left = Math.random() * 100 + '%';
  p.style.setProperty('--dur', (6 + Math.random() * 10) + 's');
  p.style.setProperty('--drift', (Math.random() * 100 - 50) + 'px');
  p.style.animationDelay = (Math.random() * 10) + 's';
  p.style.width = p.style.height = (Math.random() > 0.7 ? 3 : 2) + 'px';
  container.appendChild(p);
}

// Scroll reveal
const observer = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      e.target.classList.add('visible');
      // Animate skill bars
      if (e.target.closest('#skillBars') || e.target.querySelector('.bar-fill')) {
        const fills = e.target.querySelectorAll ? e.target.querySelectorAll('.bar-fill') : [];
        fills.forEach(f => { f.style.width = f.dataset.w + '%'; });
      }
      // If bar-item itself
      if (e.target.classList.contains('bar-item')) {
        const fill = e.target.querySelector('.bar-fill');
        if (fill) fill.style.width = fill.dataset.w + '%';
      }
    }
  });
}, { threshold: 0.15 });

document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

// Also animate bars on section reveal
const barObserver = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      e.target.querySelectorAll('.bar-fill').forEach(f => {
        setTimeout(() => { f.style.width = f.dataset.w + '%'; }, 300);
      });
    }
  });
}, { threshold: 0.3 });
const skillBarsSection = document.querySelector('#skillBars');
if (skillBarsSection) barObserver.observe(skillBarsSection.parentElement);

// DS tab switching
const dsData = {
  eda: {
    title: 'EXPLORATORY DATA ANALYSIS',
    text: 'Deep-dive into datasets using Python\'s Pandas and visualization libraries. I uncover hidden patterns, correlations, outliers, and distributions — building a clear understanding before any modelling begins. Every insight starts with asking the right question of the data.',
    tags: ['PANDAS','MATPLOTLIB','SEABORN','NUMPY','JUPYTER']
  },
  ml: {
    title: 'MACHINE LEARNING',
    text: 'Building predictive models using supervised and unsupervised learning techniques. From feature engineering to model evaluation and deployment — I bridge the gap between raw data and intelligent automated decision-making.',
    tags: ['SCIKIT-LEARN','REGRESSION','CLASSIFICATION','CLUSTERING','MODEL TUNING']
  },
  wrangling: {
    title: 'DATA WRANGLING & ETL',
    text: 'Raw, messy data is inevitable. I design robust cleaning and transformation pipelines using Pandas and NumPy — handling missing values, outliers, encoding, merging, and reshaping datasets at scale for reliable downstream analysis.',
    tags: ['PANDAS','NUMPY','ETL PIPELINES','DATA CLEANING','FEATURE ENGINEERING']
  },
  stats: {
    title: 'STATISTICAL MODELLING',
    text: 'Applying rigorous statistical methods to validate hypotheses and quantify uncertainty. From A/B testing to regression analysis, I bring mathematical precision to business decision-making through evidence-based reasoning.',
    tags: ['HYPOTHESIS TESTING','REGRESSION','ANOVA','CORRELATION','DISTRIBUTIONS']
  }
};

function showDs(el, key) {
  document.querySelectorAll('.ds-cat').forEach(c => c.classList.remove('active'));
  el.classList.add('active');
  const d = dsData[key];
  const detail = document.getElementById('dsDetail');
  detail.style.opacity = '0';
  detail.style.transform = 'translateY(10px)';
  setTimeout(() => {
    document.getElementById('dsTitle').textContent = d.title;
    document.getElementById('dsText').textContent = d.text;
    const tagsEl = document.getElementById('dsTags');
    tagsEl.innerHTML = d.tags.map(t => `<span class="tech-tag">${t}</span>`).join('');
    detail.style.transition = 'all 0.4s ease';
    detail.style.opacity = '1';
    detail.style.transform = 'translateY(0)';
  }, 150);
}

// Threat feed animation
const vals = document.querySelectorAll('.threat-val.green');
setInterval(() => {
  vals.forEach(v => {
    if (Math.random() > 0.7) {
      v.style.opacity = '0.4';
      setTimeout(() => { v.style.opacity = '1'; v.style.transition = 'opacity 0.3s'; }, 200);
    }
  });
}, 2000);

// Nav active state
window.addEventListener('scroll', () => {
  const sections = document.querySelectorAll('section[id]');
  const links = document.querySelectorAll('.nav-links a');
  let current = '';
  sections.forEach(s => {
    if (window.scrollY >= s.offsetTop - 100) current = s.id;
  });
  links.forEach(l => {
    l.style.color = l.getAttribute('href') === '#' + current ? 'var(--teal)' : '';
  });
});
</script>
</body>
</html>
