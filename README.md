# gourav-digital-portfolio
Personal portfolio and resume website showcasing my skills, projects, and experience as a Full-Stack Web Developer.
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Gourav Yadav — Personal Portfolio · BCA Fresher</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin/>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet"/>
<style>
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
* { font-family: 'Inter', system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif; }

html, body {
  margin: 0; padding: 0;
  background: #E4E4E4;
  color: #111111;
  overflow-x: hidden;
  scroll-behavior: smooth;
}

/* ===== SPLASH ===== */
.splash {
  position: fixed; inset: 0;
  width: 100vw; height: 100vh;
  z-index: 9999;
  pointer-events: none;
  overflow: hidden;
  animation: splashHide 0.3s ease forwards;
  animation-delay: 1.35s;
}
.splash-row { display: flex; width: 100%; height: 50%; }
.splash-box { width: 20%; height: 100%; background: #75C5DE; }
.splash-row-top .splash-box { animation: splashTop 1s cubic-bezier(0.96,-0.02,0.38,1.01) forwards; }
.splash-row-bottom .splash-box { animation: splashBottom 1s cubic-bezier(0.96,-0.02,0.38,1.01) forwards; }
.splash-box:nth-child(1) { animation-delay: 0s; }
.splash-box:nth-child(2) { animation-delay: 0.05s; }
.splash-box:nth-child(3) { animation-delay: 0.1s; }
.splash-box:nth-child(4) { animation-delay: 0.15s; }
.splash-box:nth-child(5) { animation-delay: 0.2s; }

@keyframes splashTop { from { transform: translateY(0%); } to { transform: translateY(-100%); } }
@keyframes splashBottom { from { transform: translateY(0%); } to { transform: translateY(100%); } }
@keyframes splashHide { to { opacity: 0; visibility: hidden; } }

/* ===== HERO IMAGE ENTRANCE ===== */
@keyframes heroImageIn {
  from { opacity: 0; transform: scale(1.5) rotate(3deg); }
  to { opacity: 1; transform: scale(1) rotate(0deg); }
}
.hero-image-animate {
  animation: heroImageIn 1.2s cubic-bezier(0.25,0.46,0.45,0.94) forwards;
  animation-delay: 1s;
  opacity: 0;
}

/* ===== WORD REVEAL ===== */
@keyframes wordReveal {
  from { opacity: 0; transform: translateY(10px); filter: blur(10px); }
  to { opacity: 1; transform: translateY(0); filter: blur(0); }
}
.word-reveal {
  opacity: 0;
  display: inline-block;
  margin-right: 0.3em;
  animation: wordReveal 0.4s ease forwards;
}

/* ===== CTA ENTRANCE ===== */
@keyframes slideUpScale {
  from { opacity: 0; transform: translateY(60px) scale(0.4); }
  to { opacity: 1; transform: translateY(0) scale(1); }
}
.cta-animate {
  opacity: 0;
  animation: slideUpScale 0.8s cubic-bezier(0.25,0.46,0.45,0.94) forwards;
  animation-delay: 1s;
}

/* ===== CTA BUTTON ===== */
.cta-btn {
  position: relative; overflow: hidden; display: inline-flex; align-items: center;
  border: none; background: none; cursor: pointer; border-radius: 9999px;
  padding: 8px; gap: 12px; text-decoration: none;
}
.cta-btn-bg {
  position: absolute; top: 5px; bottom: 5px; left: 8px;
  width: calc(100% - 8px - 8px - 48px - 12px);
  border-radius: 9999px; background: white; z-index: 0;
  transition: width 0.4s cubic-bezier(0.25,0.46,0.45,0.94);
}
@media (min-width: 768px) { .cta-btn-bg { width: calc(100% - 8px - 8px - 54px - 12px); } }
.cta-btn:hover .cta-btn-bg { width: calc(100% - 16px); }
.cta-btn-text { position: relative; z-index: 1; color: #111111; font-weight: 500; font-size: 16px; padding: 12px 32px; white-space: nowrap; }
@media (min-width: 768px) { .cta-btn-text { font-size: 18px; padding: 16px 40px; } }
.cta-btn-circle {
  position: relative; z-index: 1; display: flex; align-items: center; justify-content: center;
  width: 48px; height: 48px; border-radius: 50%; background: #75C5DE; flex-shrink: 0;
  transition: transform 0.4s cubic-bezier(0.25,0.46,0.45,0.94);
}
@media (min-width: 768px) { .cta-btn-circle { width: 54px; height: 54px; } }
.cta-btn:hover .cta-btn-circle { transform: translateX(-7px); }

/* ===== MENU CTA (smaller) ===== */
.menu-cta-btn {
  position: relative; overflow: hidden; display: inline-flex; align-items: center;
  border: none; background: none; cursor: pointer; border-radius: 9999px;
  padding: 6px; gap: 8px; text-decoration: none;
}
.menu-cta-bg {
  position: absolute; top: 5px; bottom: 5px; left: 8px;
  width: calc(100% - 8px - 8px - 38px - 8px);
  border-radius: 9999px; background: white; z-index: 0;
  transition: width 0.4s cubic-bezier(0.25,0.46,0.45,0.94);
}
.menu-cta-btn:hover .menu-cta-bg { width: calc(100% - 12px); }
.menu-cta-text { position: relative; z-index: 1; color: #111111; font-weight: 500; font-size: 14px; padding: 8px 40px; white-space: nowrap; }
.menu-cta-circle {
  position: relative; z-index: 1; display: flex; align-items: center; justify-content: center;
  width: 38px; height: 38px; border-radius: 50%; background: #75C5DE; flex-shrink: 0;
  transition: transform 0.3s ease;
}
.menu-cta-btn:hover .menu-cta-circle { transform: translateX(-4px); }

/* ===== CREATOR TEXT ===== */
@keyframes creatorSlideUp { from { transform: translateY(330px); } to { transform: translateY(0); } }
.creator-text-animate {
  transform: translateY(330px);
  animation: creatorSlideUp 1s cubic-bezier(0.16,1,0.3,1) forwards;
  animation-delay: 1.5s;
}

/* ===== NAVIGATION ===== */
.logo-wrapper {
  position: fixed; top: 30px; left: 0; width: 50%; z-index: 100;
  display: flex; justify-content: flex-start; align-items: center; mix-blend-mode: difference;
}
@media (min-width: 768px) { .logo-wrapper { top: 40px; } }
.logo-wrapper .inner { padding-left: 20px; display: flex; align-items: center; gap: 12px; }
@media (min-width: 768px) { .logo-wrapper .inner { padding-left: 40px; } }
.logo-wrapper a {
  display: flex; align-items: center; gap: 10px;
  text-decoration: none; color: #F4F1E8; font-weight: 600; font-size: 16px; letter-spacing: -0.02em;
}
.logo-wrapper img { width: 32px; height: 32px; }

.burger-wrapper {
  position: fixed; top: 16px; right: 0; width: 50%; z-index: 100;
  display: flex; justify-content: flex-end; align-items: center;
}
@media (min-width: 768px) { .burger-wrapper { top: 27px; } }
.burger-wrapper .inner { padding-right: 20px; }
@media (min-width: 768px) { .burger-wrapper .inner { padding-right: 40px; } }

.burger-btn {
  width: 59px; height: 59px; border-radius: 50%; border: 1px solid rgba(17,17,17,0.08); cursor: pointer;
  display: flex; flex-direction: column; gap: 4px; align-items: center; justify-content: center;
  background: #F4F1E8; transition: background 0.4s ease, transform 0.3s ease;
  box-shadow: 0 8px 24px rgba(0,0,0,0.08);
}
.burger-btn:hover { background: #0B0B0B; transform: scale(1.04); }
.burger-btn .bar {
  display: block; width: 24px; height: 2px; background: #111111;
  transition: all 0.3s ease;
}
.burger-btn:hover .bar { background: #F4F1E8; }
.burger-btn.open { background: #0B0B0B; }
.burger-btn.open .bar { background: #F4F1E8; }
.burger-btn.open .bar:first-child { transform: rotate(45deg) translate(2px, 2px); }
.burger-btn.open .bar:last-child { transform: rotate(-45deg) translate(2px, -2px); }

/* ===== MENU PANEL ===== */
.menu-panel {
  position: fixed; z-index: 99;
  left: 8px; right: 8px;
  border-radius: 20px;
  background: rgba(17,17,17,0.96);
  backdrop-filter: blur(26px); -webkit-backdrop-filter: blur(26px);
  padding: 90px 32px 32px 32px;
  display: flex; flex-direction: column; justify-content: space-between;
  transition: top 0.5s cubic-bezier(0.25,0.46,0.45,0.94), opacity 0.4s ease;
  top: -650px; opacity: 0; pointer-events: none;
  box-shadow: 0 24px 60px rgba(0,0,0,0.28);
}
@media (min-width: 768px) {
  .menu-panel { left: auto; right: 7px; width: 420px; padding: 60px; }
}
.menu-panel.open { top: 8px; opacity: 1; pointer-events: auto; }
@media (min-width: 768px) { .menu-panel.open { top: 7px; } }

.menu-panel nav { display: flex; flex-direction: column; gap: 8px; }
.menu-panel nav a {
  color: #F4F1E8; font-size: 36px; font-weight: 500; text-decoration: none;
  line-height: 130%; transition: opacity 0.3s ease, transform 0.3s ease;
}
@media (min-width: 768px) { .menu-panel nav a { font-size: 42px; } }
.menu-panel nav a:hover { opacity: 0.7; transform: translateX(6px); }

.menu-contact { display: flex; flex-direction: column; gap: 14px; margin-top: 32px; }
.menu-email { color: #9A9590; font-size: 17px; text-decoration: none; transition: color 0.3s ease; word-break: break-all; }
@media (min-width: 768px) { .menu-email { font-size: 19px; } }
.menu-email:hover { color: #F4F1E8; }
.menu-socials { display: flex; flex-wrap: wrap; gap: 20px; }
.menu-socials a, .menu-socials span {
  color: #9A9590; font-size: 14px; text-decoration: underline;
  text-underline-offset: 3px; transition: color 0.3s ease;
}
.menu-socials a:hover { color: #F4F1E8; }

/* ===== HERO ===== */
.hero {
  position: relative; width: 100%; overflow: hidden;
  background: #E4E4E4; min-height: 100vh;
}
@media (min-width: 768px) { .hero { height: 100vh; min-height: 800px; } }

.hero-big-text {
  position: absolute; bottom: -25px; left: 0; right: 0; z-index: 2;
  pointer-events: none; width: 100%; text-align: center;
}
@media (min-width: 768px) { .hero-big-text { bottom: -40px; } }
.hero-big-text h2 {
  font-weight: 500; color: #F4F1E8; line-height: 80%;
  letter-spacing: -0.04em; white-space: nowrap;
  font-size: clamp(140px, 25vw, 520px);
}

.hero-base-img {
  position: absolute; top: 30vh; left: 0; right: 0; bottom: 0;
  background-size: cover; background-repeat: no-repeat;
  background-position: 60% center; z-index: 5;
}
@media (min-width: 768px) { .hero-base-img { top: 0; background-position: center; } }

.hero-reveal-img {
  position: absolute; top: 30vh; left: 0; right: 0; bottom: 0;
  background-size: cover; background-repeat: no-repeat;
  background-position: 60% center; z-index: 7; pointer-events: none;
}
@media (min-width: 768px) { .hero-reveal-img { top: 0; background-position: center; } }

.hero-content {
  position: relative; z-index: 8;
  display: flex; flex-direction: column; justify-content: flex-start; align-items: flex-start;
  width: 100%; max-width: 1600px; margin: 0 auto;
  padding: 110px 20px 24px 20px; pointer-events: none;
}
@media (min-width: 768px) {
  .hero-content {
    position: absolute; inset: 0;
    justify-content: space-between;
    padding: 150px 40px 100px 40px;
  }
}
.hero-content-inner {
  display: flex; flex-direction: column; align-items: flex-start;
  gap: 24px; width: 100%; pointer-events: auto;
}

.hero-badge {
  display: inline-flex; align-items: center; gap: 8px;
  padding: 8px 16px; border-radius: 9999px;
  background: rgba(244, 241, 232, 0.85);
  backdrop-filter: blur(8px);
  color: #111111; font-size: 13px; font-weight: 600;
  letter-spacing: 0.04em; text-transform: uppercase;
  border: 1px solid rgba(17,17,17,0.08);
}
.hero-badge-dot {
  width: 8px; height: 8px; border-radius: 50%; background: #75C5DE;
  box-shadow: 0 0 0 4px rgba(117, 197, 222, 0.25);
}

.hero-headline {
  font-size: 22px; font-weight: 500; line-height: 125%;
  letter-spacing: -0.02em; color: #111111; max-width: 470px;
}
@media (min-width: 768px) { .hero-headline { font-size: 28px; } }

/* ===== CANVAS (hidden) ===== */
#reveal-canvas { display: none; position: absolute; inset: 0; pointer-events: none; }

/* ===== PORTFOLIO SECTIONS (#about, #projects, #contact) ===== */
.portfolio-body {
  position: relative;
  z-index: 10;
  background: #E4E4E4;
  color: #111111;
}

section {
  padding: 96px 20px;
  border-top: 1px solid rgba(17, 17, 17, 0.09);
}
@media (min-width: 768px) {
  section { padding: 120px 40px; }
}

.wrap {
  max-width: 1240px;
  margin: 0 auto;
  width: 100%;
}

.section-head {
  margin-bottom: 48px;
  max-width: 680px;
}

.kicker {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  font-size: 13px;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: #111111;
  background: #F4F1E8;
  padding: 7px 16px;
  border-radius: 9999px;
  margin-bottom: 18px;
  border: 1px solid rgba(17, 17, 17, 0.08);
}
.kicker::before {
  content: "";
  display: inline-block;
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: #75C5DE;
}

.section-title {
  font-size: clamp(36px, 5vw, 56px);
  font-weight: 600;
  letter-spacing: -0.03em;
  line-height: 1.08;
  color: #111111;
  margin-bottom: 16px;
}

.section-intro {
  font-size: 18px;
  line-height: 1.6;
  color: #4A4A4A;
  font-weight: 400;
}

/* ===== CARDS ===== */
.card {
  background: #F4F1E8;
  border-radius: 24px;
  padding: 32px;
  border: 1px solid rgba(17, 17, 17, 0.07);
  box-shadow: 0 12px 32px rgba(17, 17, 17, 0.04);
  transition: transform 0.35s cubic-bezier(0.25, 0.46, 0.45, 0.94), box-shadow 0.35s ease;
}
@media (min-width: 768px) {
  .card { padding: 44px; }
}
.card:hover {
  transform: translateY(-4px);
  box-shadow: 0 20px 44px rgba(17, 17, 17, 0.08);
}

.card h3 {
  font-size: 24px;
  font-weight: 600;
  letter-spacing: -0.02em;
  color: #111111;
  margin-bottom: 14px;
}

.card p {
  font-size: 16px;
  line-height: 1.7;
  color: #3A3A3A;
}

/* ===== TAGS ===== */
.taglist {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  margin-top: 26px;
}

.tag {
  display: inline-flex;
  align-items: center;
  padding: 9px 18px;
  border-radius: 9999px;
  font-size: 14px;
  font-weight: 500;
  background: #FFFFFF;
  color: #111111;
  border: 1px solid rgba(17, 17, 17, 0.1);
  transition: background 0.25s ease, border-color 0.25s ease;
}
.tag:hover {
  background: #75C5DE;
  border-color: #75C5DE;
}

.note {
  font-size: 14px;
  line-height: 1.6;
  color: #4A4A4A;
  background: rgba(244, 241, 232, 0.65);
  border-left: 4px solid #75C5DE;
  padding: 14px 18px;
  border-radius: 0 14px 14px 0;
}

/* ===== ABOUT GRID ===== */
.about-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 24px;
}
@media (min-width: 768px) {
  .about-grid { grid-template-columns: 1.25fr 0.75fr; }
}
.info-list {
  display: flex;
  flex-direction: column;
  gap: 16px;
  margin-top: 8px;
}
.info-row {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-bottom: 14px;
  border-bottom: 1px solid rgba(17, 17, 17, 0.08);
  font-size: 15px;
}
.info-row:last-child { border-bottom: none; padding-bottom: 0; }
.info-row span { color: #5A5A5A; }
.info-row strong { color: #111111; font-weight: 600; text-align: right; }

/* ===== CONTACT PANEL ===== */
.contact-panel {
  display: grid;
  grid-template-columns: 1fr;
  gap: 24px;
}
@media (min-width: 768px) {
  .contact-panel { grid-template-columns: 1fr 1fr; }
}

.contact-item {
  display: flex;
  flex-direction: column;
  gap: 4px;
  padding: 16px 0;
  border-bottom: 1px solid rgba(17, 17, 17, 0.08);
}
.contact-item:first-of-type { padding-top: 6px; }
.contact-item:last-of-type { border-bottom: none; padding-bottom: 0; }

.contact-item small {
  font-size: 12px;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.06em;
  color: #6E6A63;
}

.contact-item a,
.contact-item strong {
  font-size: 18px;
  font-weight: 500;
  color: #111111;
  text-decoration: none;
  transition: color 0.25s ease;
  word-break: break-word;
}
.contact-item a:hover {
  color: #2B89A8;
  text-decoration: underline;
  text-underline-offset: 4px;
}

/* ===== ACTION BUTTONS ===== */
.actions {
  display: flex;
  flex-wrap: wrap;
  gap: 14px;
}

.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 14px 28px;
  border-radius: 9999px;
  font-size: 15px;
  font-weight: 500;
  text-decoration: none;
  transition: all 0.3s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  cursor: pointer;
}

.btn.primary {
  background: #111111;
  color: #F4F1E8;
  border: 1px solid #111111;
}
.btn.primary:hover {
  background: #75C5DE;
  color: #111111;
  border-color: #75C5DE;
  transform: translateY(-2px);
}

.btn.secondary {
  background: #FFFFFF;
  color: #111111;
  border: 1px solid rgba(17, 17, 17, 0.16);
}
.btn.secondary:hover {
  background: #111111;
  color: #F4F1E8;
  border-color: #111111;
  transform: translateY(-2px);
}

/* ===== FOOTER ===== */
footer {
  background: #111111;
  color: #F4F1E8;
  padding: 40px 20px;
  border-top: 1px solid rgba(255, 255, 255, 0.08);
}
@media (min-width: 768px) {
  footer { padding: 48px 40px; }
}
footer .wrap {
  display: flex;
  flex-direction: column;
  gap: 12px;
  justify-content: space-between;
  align-items: flex-start;
  font-size: 15px;
  color: #9A9590;
}
@media (min-width: 640px) {
  footer .wrap {
    flex-direction: row;
    align-items: center;
  }
}
footer .wrap span:first-child {
  color: #F4F1E8;
  font-weight: 500;
}

/* ===== REDUCED MOTION ===== */
@media (prefers-reduced-motion: reduce) {
  .splash { animation: splashHide 0.01s linear forwards; }
  .splash-box { animation: none !important; }
  .hero-image-animate, .word-reveal, .cta-animate, .creator-text-animate {
    animation: none !important; opacity: 1 !important;
    transform: none !important; filter: none !important; visibility: visible !important;
  }
}
</style>
</head>
<body>

<!-- SPLASH -->
<div class="splash" id="splash">
  <div class="splash-row splash-row-top">
    <div class="splash-box"></div><div class="splash-box"></div><div class="splash-box"></div><div class="splash-box"></div><div class="splash-box"></div>
  </div>
  <div class="splash-row splash-row-bottom">
    <div class="splash-box"></div><div class="splash-box"></div><div class="splash-box"></div><div class="splash-box"></div><div class="splash-box"></div>
  </div>
</div>

<!-- LOGO -->
<div class="logo-wrapper">
  <div class="inner">
    <a href="#top" aria-label="Gourav Yadav Home">
      <img src="https://framerusercontent.com/images/VMcS7YYTM5PXfXvlHc9u3hSCMM.svg" alt="Logo"/>
      <span>Gourav Yadav</span>
    </a>
  </div>
</div>

<!-- BURGER -->
<div class="burger-wrapper">
  <div class="inner">
    <button class="burger-btn" id="burger-btn" aria-label="Open menu">
      <span class="bar"></span>
      <span class="bar"></span>
    </button>
  </div>
</div>

<!-- MENU PANEL -->
<div class="menu-panel" id="menu-panel">
  <nav>
    <a href="#about">About</a>
    <a href="#projects">Projects</a>
    <a href="#contact">Contact</a>
  </nav>
  <div class="menu-contact">
    <a href="mailto:gouravy330@gmail.com" class="menu-email">gouravy330@gmail.com</a>
    <div class="menu-socials">
      <a href="tel:+917015209365">+91 70152 09365</a>
      <span>Bhiwadi, Rajasthan</span>
    </div>
  </div>
  <div style="margin-top:32px;">
    <a href="#contact" class="menu-cta-btn" id="menu-talk-btn">
      <span class="menu-cta-bg"></span>
      <span class="menu-cta-text">Let's talk</span>
      <span class="menu-cta-circle">
        <svg width="14" height="14" viewBox="0 0 18 18" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M5 13L13 5M13 5H6M13 5V12" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
      </span>
    </a>
  </div>
</div>

<main id="top">
  <!-- HERO -->
  <section class="hero" id="hero-section" style="padding:0; border:none;">
    <!-- Big text behind image -->
    <div class="hero-big-text creator-text-animate">
      <h2>Gourav</h2>
    </div>

    <!-- Base image -->
    <div class="hero-base-img hero-image-animate"
         style="background-image:url('https://soft-zoom-63098134.figma.site/_assets/v11/5c9f982199fde1d9b85a20e5396f0fa7bacaf9a3.png?w=2560');">
    </div>

    <!-- Reveal layer -->
    <canvas id="reveal-canvas"></canvas>
    <div class="hero-reveal-img" id="reveal-img"
         style="background-image:url('https://soft-zoom-63098134.figma.site/_assets/v11/6be2165e31648955b4e071f4cf2a50bc572b9bfd.png?w=1536');">
    </div>

    <!-- Content -->
    <div class="hero-content">
      <div class="hero-content-inner">
        <div class="hero-badge cta-animate">
          <span class="hero-badge-dot"></span>
          <span>Gourav Yadav · BCA Fresher</span>
        </div>
        <h1 class="hero-headline" id="headline"></h1>
        <a href="#projects" class="cta-btn cta-animate">
          <span class="cta-btn-bg"></span>
          <span class="cta-btn-text">Explore my portfolio</span>
          <span class="cta-btn-circle">
            <svg width="18" height="18" viewBox="0 0 18 18" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M5 13L13 5M13 5H6M13 5V12" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </span>
        </a>
      </div>
    </div>
  </section>

  <!-- PORTFOLIO CONTENT -->
  <div class="portfolio-body">
    <!-- ABOUT SECTION -->
    <section id="about">
      <div class="wrap">
        <div class="section-head">
          <div class="kicker">Introduction</div>
          <h2 class="section-title">About Me</h2>
          <p class="section-intro">BCA fresher focused on building practical technical skills, clean digital experiences, and continuous professional growth.</p>
        </div>
        <div class="about-grid">
          <div class="card">
            <h3>Hello, I’m Gourav Yadav</h3>
            <p>
              I am a Bachelor of Computer Applications (BCA) graduate based in Bhiwadi, Alwar, Rajasthan. As a motivated fresher, I am eager to begin my professional journey in software, web technologies, and IT operations where I can apply my academic foundation and learn from experienced teams.
            </p>
            <div class="taglist">
              <span class="tag">BCA Graduate</span>
              <span class="tag">Quick Learner</span>
              <span class="tag">Problem Solving</span>
              <span class="tag">Team Collaboration</span>
            </div>
          </div>
          <div class="card">
            <h3>Quick Profile</h3>
            <div class="info-list">
              <div class="info-row"><span>Name</span><strong>Gourav Yadav</strong></div>
              <div class="info-row"><span>Qualification</span><strong>BCA Fresher</strong></div>
              <div class="info-row"><span>Location</span><strong>Bhiwadi, Rajasthan</strong></div>
              <div class="info-row"><span>Availability</span><strong>Immediate / Open to Work</strong></div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- PROJECTS SECTION (Exact content provided) -->
    <section id="projects">
      <div class="wrap">
        <div class="section-head">
          <div class="kicker">Work showcase</div>
          <h2 class="section-title">Projects</h2>
          <p class="section-intro">This section is ready for college projects, practical assignments, or personal work.</p>
        </div>
        <div class="card">
          <h3>Project showcase coming soon</h3>
          <p>
            I’m preparing this section to feature projects, including each project’s goal, tools used,
            my contribution, and outcome. No projects have been listed yet because project details
            were not included in my resume.
          </p>
          <div class="taglist"><span class="tag">Project title</span><span class="tag">Tools / technologies</span><span class="tag">What I built</span></div>
        </div>
        <p class="note" style="margin-top:18px">Tip: Add verified skills such as programming languages, web technologies, databases, or software tools only if you have actually studied or used them.</p>
      </div>
    </section>

    <!-- CONTACT SECTION (Exact content provided) -->
    <section id="contact">
      <div class="wrap">
        <div class="section-head">
          <div class="kicker">Get in touch</div>
          <h2 class="section-title">Let’s connect</h2>
          <p class="section-intro">I’m open to suitable entry-level opportunities and professional learning.</p>
        </div>
        <div class="contact-panel">
          <div class="card">
            <h3>Contact details</h3>
            <div class="contact-item"><small>Phone</small><a href="tel:+917015209365">+91 70152 09365</a></div>
            <div class="contact-item"><small>Email</small><a href="mailto:gouravy330@gmail.com">gouravy330@gmail.com</a></div>
            <div class="contact-item"><small>Location</small><strong>Bhiwadi, Alwar, Rajasthan, India</strong></div>
          </div>
          <div class="card">
            <h3>Professional note</h3>
            <p>
              As a fresher, I’m looking forward to an opportunity where I can learn from experienced
              colleagues, build hands-on skills, and make a positive contribution.
            </p>
            <div class="actions" style="margin-top:20px">
              <a class="btn primary" href="mailto:gouravy330@gmail.com?subject=Opportunity%20for%20Gourav%20Yadav">Email Me</a>
              <a class="btn secondary" href="tel:+917015209365">Call Me</a>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</main>

<!-- FOOTER (Exact content provided) -->
<footer>
  <div class="wrap">
    <span>© <span id="year"></span> Gourav Yadav</span>
    <span>Personal portfolio · BCA fresher</span>
  </div>
</footer>

<script>
document.getElementById("year").textContent = new Date().getFullYear();

(function() {
  // Word reveal in Hero
  const headline = document.getElementById('headline');
  const text = "I’m Gourav Yadav, a BCA fresher ready to learn, build hands-on skills, and make a positive impact.";
  const words = text.split(' ');
  words.forEach(function(word, i) {
    const span = document.createElement('span');
    span.className = 'word-reveal';
    span.textContent = word;
    span.style.animationDelay = (1 + i * 0.045) + 's';
    headline.appendChild(span);
  });

  // Burger menu toggle
  const burgerBtn = document.getElementById('burger-btn');
  const menuPanel = document.getElementById('menu-panel');
  const menuTalkBtn = document.getElementById('menu-talk-btn');
  let menuOpen = false;

  function closeMenu() {
    menuOpen = false;
    burgerBtn.classList.remove('open');
    menuPanel.classList.remove('open');
    burgerBtn.setAttribute('aria-label', 'Open menu');
  }

  burgerBtn.addEventListener('click', function() {
    menuOpen = !menuOpen;
    if (menuOpen) {
      burgerBtn.classList.add('open');
      menuPanel.classList.add('open');
      burgerBtn.setAttribute('aria-label', 'Close menu');
    } else {
      closeMenu();
    }
  });

  // Close menu on nav link or CTA click
  menuPanel.querySelectorAll('nav a').forEach(function(a) {
    a.addEventListener('click', closeMenu);
  });
  if (menuTalkBtn) {
    menuTalkBtn.addEventListener('click', closeMenu);
  }

  // Spotlight reveal on Hero
  const SPOTLIGHT_R = 260;
  const heroSection = document.getElementById('hero-section');
  const canvas = document.getElementById('reveal-canvas');
  const imgLayer = document.getElementById('reveal-img');
  const ctx = canvas.getContext('2d');

  function resizeCanvas() {
    canvas.width = heroSection.clientWidth || window.innerWidth;
    canvas.height = heroSection.clientHeight || window.innerHeight;
  }
  resizeCanvas();
  window.addEventListener('resize', resizeCanvas);

  const mouse = { x: -999, y: -999 };
  const smooth = { x: -999, y: -999 };

  window.addEventListener('mousemove', function(e) {
    const rect = heroSection.getBoundingClientRect();
    mouse.x = e.clientX - rect.left;
    mouse.y = e.clientY - rect.top;
  });

  window.addEventListener('touchmove', function(e) {
    if (e.touches && e.touches[0]) {
      const rect = heroSection.getBoundingClientRect();
      mouse.x = e.touches[0].clientX - rect.left;
      mouse.y = e.touches[0].clientY - rect.top;
    }
  }, { passive: true });

  function loop() {
    smooth.x += (mouse.x - smooth.x) * 0.12;
    smooth.y += (mouse.y - smooth.y) * 0.12;

    ctx.clearRect(0, 0, canvas.width, canvas.height);

    var grad = ctx.createRadialGradient(smooth.x, smooth.y, 0, smooth.x, smooth.y, SPOTLIGHT_R);
    grad.addColorStop(0, 'rgba(255,255,255,1)');
    grad.addColorStop(0.4, 'rgba(255,255,255,1)');
    grad.addColorStop(0.6, 'rgba(255,255,255,0.75)');
    grad.addColorStop(0.75, 'rgba(255,255,255,0.4)');
    grad.addColorStop(0.88, 'rgba(255,255,255,0.12)');
    grad.addColorStop(1, 'rgba(255,255,255,0)');

    ctx.beginPath();
    ctx.arc(smooth.x, smooth.y, SPOTLIGHT_R, 0, Math.PI * 2);
    ctx.fillStyle = grad;
    ctx.fill();

    var dataUrl = canvas.toDataURL();
    imgLayer.style.webkitMaskImage = 'url(' + dataUrl + ')';
    imgLayer.style.maskImage = 'url(' + dataUrl + ')';
    imgLayer.style.webkitMaskSize = '100% 100%';
    imgLayer.style.maskSize = '100% 100%';

    requestAnimationFrame(loop);
  }
  requestAnimationFrame(loop);
})();
</script>
</body>
</html>
