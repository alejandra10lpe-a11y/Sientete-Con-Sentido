
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Siéntete ConSentido — Alejandra López</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;1,400&family=Lato:wght@300;400;700&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --blush:    #f2ddd5;
    --rose:     #c97b7b;
    --rose-deep:#a85959;
    --sage:     #8a9e7e;
    --sage-light:#b8c9ad;
    --cream:    #faf6f0;
    --warm:     #e8d5c4;
    --charcoal: #3d3230;
    --muted:    #7a6a62;
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'Lato', sans-serif;
    background: var(--cream);
    color: var(--charcoal);
    overflow-x: hidden;
  }

  /* ── NAV ─────────────────────────────────────────── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 1.2rem 4rem;
    background: rgba(250,246,240,0.92);
    backdrop-filter: blur(10px);
    border-bottom: 1px solid rgba(201,123,123,0.15);
    transition: box-shadow .3s;
  }
  nav.scrolled { box-shadow: 0 4px 30px rgba(61,50,48,.08); }

  .nav-logo {
    font-family: 'Playfair Display', serif;
    font-size: 1.25rem;
    color: var(--rose-deep);
    letter-spacing: .02em;
    text-decoration: none;
  }
  .nav-logo span { color: var(--sage); }

  .nav-links { display: flex; gap: 2.5rem; list-style: none; }
  .nav-links a {
    font-size: .85rem; letter-spacing: .1em; text-transform: uppercase;
    color: var(--muted); text-decoration: none;
    position: relative; padding-bottom: 3px;
    transition: color .3s;
  }
  .nav-links a::after {
    content: ''; position: absolute; bottom: 0; left: 0;
    width: 0; height: 1.5px; background: var(--rose);
    transition: width .3s;
  }
  .nav-links a:hover { color: var(--rose); }
  .nav-links a:hover::after { width: 100%; }

  .nav-cta {
    background: var(--rose); color: #fff !important;
    padding: .5rem 1.4rem; border-radius: 50px;
    font-size: .8rem !important; letter-spacing: .12em !important;
    transition: background .3s, transform .2s !important;
  }
  .nav-cta:hover { background: var(--rose-deep) !important; transform: translateY(-1px); }
  .nav-cta::after { display: none !important; }

  /* ── HERO ────────────────────────────────────────── */
  .hero {
    min-height: 100vh;
    display: grid; grid-template-columns: 1fr 1fr;
    align-items: center;
    padding: 8rem 4rem 4rem;
    position: relative; overflow: hidden;
  }

  .hero::before {
    content: '';
    position: absolute; top: -10%; right: -5%;
    width: 55vw; height: 75vh;
    background: radial-gradient(ellipse at 60% 40%, rgba(242,221,213,.7) 0%, rgba(184,201,173,.35) 60%, transparent 80%);
    border-radius: 60% 40% 70% 30% / 50% 60% 40% 50%;
    animation: morphBlob 14s ease-in-out infinite;
    pointer-events: none;
  }
  .hero::after {
    content: '';
    position: absolute; bottom: 0; left: -5%;
    width: 40vw; height: 50vh;
    background: radial-gradient(ellipse, rgba(184,201,173,.4) 0%, transparent 70%);
    border-radius: 50% 50% 30% 70% / 60% 40% 60% 40%;
    animation: morphBlob 18s ease-in-out infinite reverse;
    pointer-events: none;
  }

  @keyframes morphBlob {
    0%, 100% { border-radius: 60% 40% 70% 30% / 50% 60% 40% 50%; }
    33%       { border-radius: 40% 60% 50% 50% / 40% 50% 60% 60%; }
    66%       { border-radius: 50% 50% 30% 70% / 60% 40% 70% 30%; }
  }

  .hero-text { position: relative; z-index: 2; }

  .hero-eyebrow {
    font-size: .75rem; letter-spacing: .25em; text-transform: uppercase;
    color: var(--sage); font-weight: 700;
    display: flex; align-items: center; gap: .75rem;
    margin-bottom: 1.5rem;
    opacity: 0; animation: fadeUp .8s .2s forwards;
  }
  .hero-eyebrow::before { content: ''; width: 2rem; height: 1px; background: var(--sage); }

  .hero-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2.8rem, 5vw, 4.5rem);
    line-height: 1.12; color: var(--charcoal);
    margin-bottom: 1.5rem;
    opacity: 0; animation: fadeUp .8s .4s forwards;
  }
  .hero-title em { color: var(--rose-deep); font-style: italic; }

  .hero-subtitle {
    font-size: 1.05rem; line-height: 1.8;
    color: var(--muted); max-width: 460px;
    margin-bottom: 2.5rem; font-weight: 300;
    opacity: 0; animation: fadeUp .8s .6s forwards;
  }

  .hero-actions {
    display: flex; gap: 1rem; flex-wrap: wrap;
    opacity: 0; animation: fadeUp .8s .8s forwards;
  }

  .btn-primary {
    background: var(--rose); color: #fff;
    padding: .85rem 2.2rem; border-radius: 50px;
    font-size: .875rem; font-weight: 700; letter-spacing: .08em;
    text-transform: uppercase; text-decoration: none;
    transition: background .3s, transform .25s, box-shadow .3s;
    box-shadow: 0 8px 25px rgba(201,123,123,.3);
  }
  .btn-primary:hover {
    background: var(--rose-deep); transform: translateY(-2px);
    box-shadow: 0 12px 35px rgba(201,123,123,.4);
  }

  .btn-secondary {
    background: transparent; color: var(--charcoal);
    padding: .85rem 2.2rem; border-radius: 50px;
    border: 1.5px solid rgba(61,50,48,.25);
    font-size: .875rem; font-weight: 700; letter-spacing: .08em;
    text-transform: uppercase; text-decoration: none;
    transition: border-color .3s, color .3s, background .3s;
  }
  .btn-secondary:hover {
    border-color: var(--sage); color: var(--sage);
    background: rgba(138,158,126,.05);
  }

  .hero-visual {
    position: relative; z-index: 2;
    display: flex; justify-content: center; align-items: center;
    opacity: 0; animation: fadeIn 1s .5s forwards;
  }

  .hero-card {
    background: white; border-radius: 2rem; padding: 2.5rem;
    max-width: 380px; width: 100%;
    box-shadow: 0 30px 80px rgba(61,50,48,.10), 0 0 0 1px rgba(201,123,123,.08);
    position: relative;
  }
  .hero-card::before {
    content: '❝';
    font-family: 'Playfair Display', serif;
    font-size: 5rem; line-height: 1; color: var(--blush);
    position: absolute; top: 1rem; left: 1.5rem; pointer-events: none;
  }

  .hero-card-text {
    font-family: 'Playfair Display', serif;
    font-size: 1.2rem; line-height: 1.65; font-style: italic;
    color: var(--charcoal); padding-top: 1.5rem; margin-bottom: 1.5rem;
  }
  .hero-card-name {
    font-size: .8rem; letter-spacing: .12em; text-transform: uppercase;
    color: var(--rose); font-weight: 700;
  }

  .hero-badge {
    position: absolute; top: -1.2rem; right: -1.2rem;
    background: var(--sage); color: white;
    border-radius: 50%; width: 90px; height: 90px;
    display: flex; flex-direction: column;
    align-items: center; justify-content: center;
    font-size: .65rem; font-weight: 700; letter-spacing: .1em;
    text-transform: uppercase; text-align: center; line-height: 1.3;
    box-shadow: 0 8px 25px rgba(138,158,126,.4);
  }
  .hero-badge strong { font-size: 1.4rem; display: block; }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(24px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  @keyframes fadeIn {
    from { opacity: 0; }
    to   { opacity: 1; }
  }

  /* ── SECTION COMMON ──────────────────────────────── */
  .section-label {
    font-size: .72rem; letter-spacing: .28em; text-transform: uppercase;
    color: var(--sage); font-weight: 700;
    display: flex; align-items: center; gap: .75rem;
    margin-bottom: 1rem;
  }
  .section-label::before { content: ''; width: 2rem; height: 1px; background: var(--sage); }

  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 3.5vw, 3rem);
    line-height: 1.2; color: var(--charcoal);
    margin-bottom: 1.2rem;
  }
  .section-title em { color: var(--rose-deep); font-style: italic; }

  .section-desc {
    font-size: 1rem; line-height: 1.85;
    color: var(--muted); max-width: 520px; font-weight: 300;
  }

  /* ═══════════════════════════════════════════════════
     SOBRE MÍ — Rediseñado
  ═══════════════════════════════════════════════════ */
  #sobre-mi {
    background: white;
    padding: 7rem 4rem;
    position: relative;
    overflow: hidden;
  }

  /* Decorative background shape */
  #sobre-mi::before {
    content: '';
    position: absolute; top: 0; right: 0;
    width: 45%; height: 100%;
    background: linear-gradient(160deg, var(--cream) 0%, var(--blush) 100%);
    clip-path: polygon(15% 0%, 100% 0%, 100% 100%, 0% 100%);
    pointer-events: none;
  }

  .sobre-inner {
    position: relative; z-index: 1;
    display: grid;
    grid-template-columns: 1fr 1.1fr;
    gap: 5rem;
    align-items: center;
    max-width: 1200px;
    margin: 0 auto;
  }

  /* ── Foto side ── */
  .sobre-foto-col {
    position: relative;
  }

  .sobre-foto-frame {
    position: relative;
    width: 100%;
    max-width: 400px;
    margin: 0 auto;
  }

  /* Decorative ring behind photo */
  .sobre-foto-frame::before {
    content: '';
    position: absolute;
    top: -20px; left: -20px;
    right: 20px; bottom: 20px;
    border: 2px solid var(--rose);
    border-radius: 2rem;
    opacity: .25;
  }

  .sobre-foto-frame::after {
    content: '';
    position: absolute;
    top: 20px; left: 20px;
    right: -20px; bottom: -20px;
    background: var(--blush);
    border-radius: 2rem;
    z-index: 0;
  }

  .sobre-foto-frame img,
  .sobre-foto-placeholder {
    position: relative; z-index: 1;
    width: 100%;
    aspect-ratio: 3/4;
    object-fit: cover;
    border-radius: 1.75rem;
    box-shadow: 0 30px 70px rgba(61,50,48,.15);
    display: block;
  }

  .sobre-foto-placeholder {
    background: linear-gradient(160deg, var(--warm) 0%, var(--blush) 60%, var(--sage-light) 100%);
    display: flex; align-items: center; justify-content: center;
    font-size: 5rem;
  }

  /* Floating pill */
  .sobre-pill {
    position: absolute;
    bottom: -1.5rem; right: -1.5rem; z-index: 3;
    background: var(--rose); color: white;
    border-radius: 1rem; padding: 1rem 1.4rem;
    font-size: .78rem; font-weight: 700; line-height: 1.5;
    box-shadow: 0 12px 35px rgba(201,123,123,.4);
    text-align: center;
  }
  .sobre-pill strong { display: block; font-size: 1.2rem; }

  /* ── Texto side ── */
  .sobre-texto-col { padding: 1rem 0; }

  .sobre-texto-col .section-desc + .section-desc { margin-top: 1rem; }

  .cedula-tag {
    display: inline-flex; align-items: center; gap: .5rem;
    background: var(--cream); border: 1px solid rgba(201,123,123,.2);
    border-radius: 50px; padding: .4rem 1rem;
    font-size: .78rem; color: var(--muted); letter-spacing: .05em;
    margin: 1.5rem 0;
  }
  .cedula-tag span { color: var(--rose); font-weight: 700; }

  .credenciales {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: .65rem; margin-bottom: 2rem;
  }
  .credencial-item {
    display: flex; align-items: flex-start; gap: .6rem;
    background: var(--cream); border-radius: .75rem;
    padding: .75rem 1rem;
    font-size: .82rem; color: var(--charcoal); line-height: 1.35;
    border: 1px solid rgba(201,123,123,.08);
    transition: border-color .3s, box-shadow .3s;
  }
  .credencial-item:hover {
    border-color: rgba(201,123,123,.2);
    box-shadow: 0 4px 16px rgba(61,50,48,.06);
  }
  .credencial-item span {
    width: 7px; height: 7px; border-radius: 50%;
    background: var(--rose); flex-shrink: 0; margin-top: .3rem;
  }

  .nota-personal {
    background: linear-gradient(135deg, var(--blush), var(--warm));
    border-radius: 1.25rem; padding: 1.5rem;
    border-left: 3px solid var(--rose);
    font-size: .9rem; color: var(--charcoal); line-height: 1.7;
    font-style: italic;
  }

  /* ═══════════════════════════════════════════════════
     SERVICIOS — Rediseñado
  ═══════════════════════════════════════════════════ */
  #servicios {
    background: var(--cream);
    padding: 7rem 4rem;
    position: relative;
  }

  #servicios::before {
    content: '';
    position: absolute; bottom: 0; left: 0; right: 0;
    height: 200px;
    background: linear-gradient(to top, white, transparent);
    pointer-events: none;
  }

  .servicios-inner {
    max-width: 1200px;
    margin: 0 auto;
  }

  .servicios-header {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 3rem;
    align-items: end;
    margin-bottom: 4rem;
    padding-bottom: 3rem;
    border-bottom: 1px solid rgba(61,50,48,.08);
  }

  .servicios-header-right {
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
  }

  .servicios-stats {
    display: flex;
    gap: 2.5rem;
  }

  .stat-item {
    text-align: center;
  }
  .stat-num {
    font-family: 'Playfair Display', serif;
    font-size: 2.4rem; font-weight: 600;
    color: var(--rose-deep); display: block;
    line-height: 1;
  }
  .stat-label {
    font-size: .75rem; letter-spacing: .1em; text-transform: uppercase;
    color: var(--muted); margin-top: .3rem; display: block;
  }

  .servicios-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
  }

  .servicio-card {
    background: white;
    border-radius: 2rem;
    overflow: hidden;
    box-shadow: 0 4px 30px rgba(61,50,48,.06);
    transition: transform .35s, box-shadow .35s;
    position: relative;
    display: flex;
    flex-direction: column;
  }
  .servicio-card:hover {
    transform: translateY(-8px);
    box-shadow: 0 25px 60px rgba(61,50,48,.13);
  }

  .servicio-top {
    padding: 2.5rem 2.5rem 0;
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    gap: 1rem;
  }

  .servicio-icon {
    width: 64px; height: 64px; border-radius: 1.25rem;
    display: flex; align-items: center; justify-content: center;
    font-size: 2rem; flex-shrink: 0;
  }
  .terapia .servicio-icon { background: var(--blush); }
  .arteterapia .servicio-icon { background: rgba(138,158,126,.15); }

  .badge-descuento {
    display: inline-flex; align-items: center; gap: .4rem;
    background: var(--blush); color: var(--rose-deep);
    font-size: .72rem; font-weight: 700; letter-spacing: .05em;
    text-transform: uppercase; padding: .35rem .9rem;
    border-radius: 50px; white-space: nowrap;
  }

  .servicio-body { padding: 1.75rem 2.5rem 2.5rem; flex: 1; display: flex; flex-direction: column; }

  .servicio-card h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.5rem; color: var(--charcoal);
    margin-bottom: .6rem;
  }
  .servicio-card > .servicio-body > p {
    font-size: .9rem; line-height: 1.75; color: var(--muted);
    margin-bottom: 1.75rem;
  }

  .servicio-divider {
    height: 1px; background: rgba(61,50,48,.07);
    margin-bottom: 1.5rem;
  }

  .servicio-precio {
    display: flex; align-items: baseline; gap: .4rem; margin-bottom: 1.25rem;
  }
  .precio-num {
    font-family: 'Playfair Display', serif;
    font-size: 2.4rem; color: var(--charcoal); font-weight: 600;
  }
  .precio-label { font-size: .82rem; color: var(--muted); }

  .servicio-includes {
    list-style: none; margin-bottom: 1.75rem; flex: 1;
  }
  .servicio-includes li {
    font-size: .875rem; color: var(--muted);
    padding: .4rem 0; display: flex; align-items: center; gap: .6rem;
    border-bottom: 1px dashed rgba(61,50,48,.06);
  }
  .servicio-includes li:last-child { border-bottom: none; }
  .servicio-includes li::before {
    content: '✓'; color: var(--sage); font-weight: 700; font-size: .85rem;
  }

  /* Accent bar at bottom of card */
  .servicio-accent {
    height: 5px;
  }
  .terapia .servicio-accent {
    background: linear-gradient(90deg, var(--rose), var(--blush));
  }
  .arteterapia .servicio-accent {
    background: linear-gradient(90deg, var(--sage), var(--sage-light));
  }

  /* ═══════════════════════════════════════════════════
     FAQ — Rediseñado
  ═══════════════════════════════════════════════════ */
  #proceso {
    background: white;
    padding: 7rem 4rem;
    position: relative;
    overflow: hidden;
  }

  #proceso::after {
    content: '';
    position: absolute; top: -100px; left: -100px;
    width: 500px; height: 500px;
    background: radial-gradient(ellipse, rgba(242,221,213,.35) 0%, transparent 70%);
    pointer-events: none;
  }

  .proceso-inner {
    max-width: 1200px;
    margin: 0 auto;
    position: relative; z-index: 1;
  }

  .proceso-header {
    text-align: center;
    margin-bottom: 4rem;
  }

  .proceso-header .section-label { justify-content: center; }
  .proceso-header .section-label::before { display: none; }
  .proceso-header .section-title { max-width: 500px; margin: 0 auto 1rem; }
  .proceso-header .section-desc { max-width: 520px; margin: 0 auto; text-align: center; }

  .proceso-layout {
    display: grid;
    grid-template-columns: 1fr 1.8fr;
    gap: 4rem;
    align-items: start;
  }

  .proceso-sidebar {
    position: sticky;
    top: 7rem;
  }

  .proceso-quote-card {
    background: linear-gradient(145deg, var(--blush), var(--warm));
    border-radius: 2rem;
    padding: 2.5rem;
    margin-bottom: 1.5rem;
    position: relative;
    overflow: hidden;
  }

  .proceso-quote-card::before {
    content: '❝';
    font-family: 'Playfair Display', serif;
    font-size: 8rem; line-height: .8;
    color: rgba(201,123,123,.15);
    position: absolute; top: -.5rem; left: 1rem;
    pointer-events: none;
  }

  .proceso-quote-card p {
    font-family: 'Playfair Display', serif;
    font-size: 1.1rem; line-height: 1.75; font-style: italic;
    color: var(--charcoal); position: relative; z-index: 1;
    margin-bottom: 1rem;
  }

  .proceso-quote-card .autor {
    font-family: 'Lato', sans-serif;
    font-size: .75rem; letter-spacing: .12em; text-transform: uppercase;
    color: var(--muted); font-style: normal;
  }

  .proceso-tip {
    background: var(--cream);
    border-radius: 1.25rem;
    padding: 1.5rem;
    border: 1px solid rgba(201,123,123,.1);
  }

  .proceso-tip-label {
    font-size: .7rem; letter-spacing: .18em; text-transform: uppercase;
    color: var(--sage); font-weight: 700; margin-bottom: .75rem;
    display: flex; align-items: center; gap: .5rem;
  }

  .proceso-tip p {
    font-size: .875rem; line-height: 1.7; color: var(--muted); font-weight: 300;
  }

  /* ── FAQ accordion ── */
  .faq-list { display: flex; flex-direction: column; gap: .75rem; }

  .faq-item {
    border: 1.5px solid rgba(61,50,48,.08);
    border-radius: 1.25rem; overflow: hidden;
    transition: border-color .3s, box-shadow .3s;
    background: var(--cream);
  }
  .faq-item:hover { border-color: rgba(201,123,123,.2); }
  .faq-item.open {
    border-color: rgba(201,123,123,.25);
    box-shadow: 0 8px 30px rgba(61,50,48,.07);
    background: white;
  }

  .faq-question {
    width: 100%; text-align: left;
    padding: 1.25rem 1.5rem;
    background: transparent; border: none; cursor: pointer;
    display: flex; justify-content: space-between; align-items: center;
    font-family: 'Lato', sans-serif;
    font-size: .95rem; font-weight: 700;
    color: var(--charcoal); gap: 1rem;
  }

  .faq-icon {
    width: 30px; height: 30px; border-radius: 50%;
    background: var(--blush);
    display: flex; align-items: center; justify-content: center;
    font-size: 1.1rem; color: var(--rose); flex-shrink: 0;
    transition: transform .3s, background .3s;
  }
  .faq-item.open .faq-icon { transform: rotate(45deg); background: var(--rose); color: white; }

  .faq-answer {
    max-height: 0; overflow: hidden;
    transition: max-height .4s ease, padding .3s;
    padding: 0 1.5rem;
  }
  .faq-item.open .faq-answer { max-height: 300px; padding-bottom: 1.5rem; }
  .faq-answer p {
    font-size: .9rem; line-height: 1.85; color: var(--muted); font-weight: 300;
    border-top: 1px solid rgba(61,50,48,.07);
    padding-top: 1rem;
  }

  /* ── CTA / CONTACTO ──────────────────────────────── */
  #contacto {
    background: linear-gradient(135deg, var(--charcoal) 0%, #2a201e 100%);
    text-align: center; position: relative; overflow: hidden;
    padding: 6rem 4rem;
  }
  #contacto::before {
    content: '';
    position: absolute; top: -30%; left: -10%;
    width: 60%; height: 80%;
    background: radial-gradient(ellipse, rgba(201,123,123,.15) 0%, transparent 70%);
    pointer-events: none;
  }
  #contacto::after {
    content: '';
    position: absolute; bottom: -20%; right: -5%;
    width: 40%; height: 60%;
    background: radial-gradient(ellipse, rgba(138,158,126,.12) 0%, transparent 70%);
    pointer-events: none;
  }

  .contacto-content { position: relative; z-index: 1; max-width: 640px; margin: 0 auto; }

  #contacto .section-label { justify-content: center; color: var(--sage-light); }
  #contacto .section-label::before { background: var(--sage-light); }
  #contacto .section-title { color: white; }
  #contacto .section-title em { color: var(--blush); }

  #contacto p {
    color: rgba(255,255,255,.65);
    font-size: 1rem; line-height: 1.8; font-weight: 300;
    margin-bottom: 2.5rem;
    max-width: 500px; margin-left: auto; margin-right: auto;
  }

  .contacto-btns { display: flex; gap: 1rem; justify-content: center; flex-wrap: wrap; }

  .btn-light {
    background: white; color: var(--charcoal);
    padding: .9rem 2.5rem; border-radius: 50px;
    font-size: .875rem; font-weight: 700; letter-spacing: .08em;
    text-transform: uppercase; text-decoration: none;
    transition: transform .25s, box-shadow .3s;
    box-shadow: 0 8px 30px rgba(0,0,0,.2);
  }
  .btn-light:hover { transform: translateY(-2px); box-shadow: 0 14px 40px rgba(0,0,0,.3); }

  .contacto-extras {
    margin-top: 3rem;
    display: flex; justify-content: center; gap: 2.5rem; flex-wrap: wrap;
  }
  .contacto-extra-item {
    display: flex; align-items: center; gap: .6rem;
    font-size: .82rem; color: rgba(255,255,255,.5);
  }
  .contacto-extra-item span { color: var(--sage-light); font-size: 1rem; }

  /* ── FOOTER ──────────────────────────────────────── */
  footer {
    background: #1e1614;
    padding: 2.5rem 4rem;
    display: flex; align-items: center; justify-content: space-between;
    flex-wrap: wrap; gap: 1rem;
  }
  .footer-logo {
    font-family: 'Playfair Display', serif;
    font-size: 1.1rem; color: rgba(255,255,255,.5); text-decoration: none;
  }
  .footer-logo strong { color: var(--rose); }
  footer p { font-size: .8rem; color: rgba(255,255,255,.3); }

  /* ── RESPONSIVE ──────────────────────────────────── */
  @media (max-width: 1024px) {
    .servicios-header { grid-template-columns: 1fr; gap: 2rem; }
    .servicios-stats { justify-content: flex-start; }
    .proceso-layout { grid-template-columns: 1fr; gap: 2.5rem; }
    .proceso-sidebar { position: static; }
  }

  @media (max-width: 900px) {
    nav { padding: 1rem 2rem; }
    .nav-links { gap: 1.5rem; }

    .hero { grid-template-columns: 1fr; padding: 7rem 2rem 4rem; gap: 3rem; }
    .hero-visual { order: -1; }
    .hero-card { max-width: 360px; }

    #sobre-mi { padding: 4rem 2rem; }
    #sobre-mi::before { display: none; }
    .sobre-inner { grid-template-columns: 1fr; gap: 3rem; }
    .sobre-foto-frame { max-width: 300px; }

    #servicios { padding: 4rem 2rem; }
    .servicios-grid { grid-template-columns: 1fr; }

    #proceso { padding: 4rem 2rem; }

    footer { padding: 2rem; flex-direction: column; align-items: flex-start; }
  }

  @media (max-width: 600px) {
    .nav-links { display: none; }
    .credenciales { grid-template-columns: 1fr; }
    .servicios-stats { gap: 1.5rem; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav id="navbar">
  <a href="#" class="nav-logo">Siéntete <span>Con</span>Sentido</a>
  <ul class="nav-links">
    <li><a href="#sobre-mi">Sobre mí</a></li>
    <li><a href="#servicios">Servicios</a></li>
    <li><a href="#proceso">Preguntas</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero" id="inicio">
  <div class="hero-text">
    <div class="hero-eyebrow">Terapia Gestalt · Tanatología</div>
    <h1 class="hero-title">
      Un espacio para<br>
      <em>sentirte</em>, escucharte y caminar<br><em>con sentido</em>
    </h1>
    <p class="hero-subtitle">
      Encuentra el equilibrio entre cuidarte con amor y vivir con conciencia. 
    </p>
    <div class="hero-actions">
      <a href="https://forms.gle/X3PMQz4dAkMQHNr78" class="btn-primary">Quiero Agendar</a>
      <a href="#servicios" class="btn-secondary">Ver servicios</a>
    </div>
  </div>

  <div class="hero-visual">
    <div class="hero-card">
      <div class="hero-badge">
        <strong>50%</strong>
        1ª y 2ª<br>sesión
      </div>
      <p class="hero-card-text">
        "Ser amable contigo te ayuda a alcanzar tus metas sin perderte en el camino."
      </p>
    </div>
  </div>
</section>

<!-- ═══ SOBRE MÍ ═══ -->
<section id="sobre-mi">
  <div class="sobre-inner">

    <!-- Columna foto -->
    <div class="sobre-foto-col">
      <div class="sobre-foto-frame">
        <img src="data:image/jpeg;base64,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" alt="Ana Alejandra López" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
        <div class="sobre-foto-placeholder" style="display:none;">🌿</div>
        <div class="sobre-pill">
          <strong>Gestalt</strong>
          Humanista
        </div>
      </div>
    </div>

    <!-- Columna texto -->
    <div class="sobre-texto-col">
      <div class="section-label">Sobre mí</div>
      <h2 class="section-title">Hola, soy <em>Ana Alejandra López</em></h2>

      <p class="section-desc">
        Psicoterapeuta tanatóloga Gestalt. Mi trabajo se centra en acompañarte
        para apoyar tu propio entendimiento desde una mirada compasiva, utilizando técnicas de mindflness y arte.
      </p>
      <p class="section-desc" style="margin-top:1rem;">
        Me emociona acompañarte en tu proceso con claridad, amabilidad y respeto 
        profundo por quien eres.
      </p>

      <div class="cedula-tag">
        🪪 Cédula profesional: <span>13339631</span>
      </div>

      <div class="credenciales">
        <div class="credencial-item"><span></span>Licenciatura en Psicología</div>
        <div class="credencial-item"><span></span>Maestría en Psicoterapia Gestalt</div>
        <div class="credencial-item"><span></span>Diplomado en Tanatología</div>
        <div class="credencial-item"><span></span>Diplomado en Trastornos Depresivos</div>
        <div class="credencial-item"><span></span>Diplomado en Ansiedad y Suicidio</div>
      </div>

      <div class="nota-personal">
        En mi vida personal, el arte y la meditación me mantienen conectada y en equilibrio. Creo profundamente en vivir lo que comparto.
      </div>
    </div>

  </div>
</section>

<!-- ═══ SERVICIOS ═══ -->
<section id="servicios">
  <div class="servicios-inner">

    <div class="servicios-header">
      <div>
        <div class="section-label">Servicios</div>
        <h2 class="section-title">¿Qué forma de <em>acompañamiento</em> necesitas hoy?</h2>
        <p class="section-desc">Cada persona es única. Elige el camino que resuene contigo.</p>
      </div>
      <div class="servicios-header-right">
        <div class="servicios-stats">
          <div class="stat-item">
            <span class="stat-num">50%</span>
            <span class="stat-label">1ª y 2ª sesión</span>
          </div>
          <div class="stat-item">
            <span class="stat-num">2</span>
            <span class="stat-label">Modalidades</span>
          </div>
        </div>
      </div>
    </div>

    <div class="servicios-grid">

      <!-- Terapia Individual -->
      <div class="servicio-card terapia">
        <div class="servicio-top">
          <div class="servicio-icon">🌿</div>
        </div>
        <div class="servicio-body">
          <h3>Terapia Psicológica</h3>
          <p>Un espacio seguro para explorar lo que te mueve, 
          escucharte con mayor profundidad y caminar hacia tu bienestar.</p>
          </div>
          <ul class="servicio-includes">
            <li>Sesión individual de 50 minutos</li>
            <li>Presencial o en línea para adultos</li>
            <li>Enfoque Gestalt humanista</li>
          </ul>
          <a href="https://forms.gle/U5htUKLZUE494FbQ7" class="btn-primary">Agendar sesión</a>
        </div>
        <div class="servicio-accent"></div>

<!-- ═══ PREGUNTAS FRECUENTES ═══ -->
<section id="proceso">
  <div class="proceso-inner">

    <div class="proceso-header">
      <div class="section-label">Preguntas frecuentes</div>
      <h2 class="section-title">Todo lo que <em>necesitas saber</em></h2>
      <p class="section-desc">Aquí resuelvo las dudas más comunes antes de tu primera sesión.</p>
    </div>

    <div class="proceso-layout">

      <!-- Sidebar -->
      <div class="proceso-sidebar">
        <div class="proceso-quote-card">
          <p>"No tienes que contar todo en la primera sesión. Vas a tu ritmo. Este es tu espacio."</p>
        </div>
        <div class="proceso-tip">
          <div class="proceso-tip-label">🌿 Recuerda</div>
          <p>Si aún tienes dudas después de leer, escríbeme directamente. Con gusto conversamos antes de que decidas agendar.</p>
        </div>
      </div>

      <!-- FAQ list -->
      <div class="faq-list">

        <div class="faq-item open">
          <button class="faq-question" onclick="toggleFaq(this)">
            ¿Qué pasa en la primera sesión?
            <span class="faq-icon">+</span>
          </button>
          <div class="faq-answer">
            <p>La primera sesión es un espacio para conocernos. Quisiera entender mejor quién eres, qué te trae a consulta y qué necesitas.</p>
          </div>
        </div>

        <div class="faq-item">
          <button class="faq-question" onclick="toggleFaq(this)">
            ¿Qué es importante para empezar tu proceso?
            <span class="faq-icon">+</span>
          </button>
          <div class="faq-answer">
            <p>Lo más importante es la honestidad: contigo mismo y con tu terapeuta. El consultorio es un espacio completamente seguro, sin juicios. Si no entiendes algo, pregunta siempre; es tu proceso y mereces claridad en cada momento.</p>
          </div>
        </div>

        <div class="faq-item">
          <button class="faq-question" onclick="toggleFaq(this)">
            ¿Cómo son las sesiones de arte terapia?
            <span class="faq-icon">+</span>
          </button>
          <div class="faq-answer">
            <p>Son talleres grupales íntimos de 6 personas. A través de actividades artísticas y creativas podrás expresar tus emociones, conectar contigo mismo/a y relajarte. Puedes compartir con el grupo si lo deseas, pero no es necesario. Te permitirá conocerte mejor y olvidarte por un momento de tus actividades cotidianas.</p>
          </div>
        </div>

        <div class="faq-item">
          <button class="faq-question" onclick="toggleFaq(this)">
            ¿Qué es la Terapia Gestalt? ¿Cómo sé si es para mí?
            <span class="faq-icon">+</span>
          </button>
          <div class="faq-answer">
            <p>La terapia Gestalt es para quien quiera escucharse, entenderse mejor y mejorar su relación consigo misma y con los demás. Si quieres tratarte con compasión, tomar decisiones más alineadas, o atravesar momentos de crisis, duelo o cambio.</p>
          </div>
        </div>

      </div>
    </div>
  </div>
</section>

<!-- psico.mx badge -->
<div id="box" align="center" style="padding: 1.5rem 0; background: var(--cream); display:flex; justify-content:center; align-items:center; gap:1.5rem; flex-wrap:wrap;">
  <a rel="nofollow" href="https://www.psico.mx/psicologos/ana-alejandra-lopez-perez?utm_source=481846&utm_medium=widget&utm_campaign=widget-company_stamp" target="_blank">
    <img src="https://www.psico.mx/stamp.xpng?com=481846&v=10" alt="Ana Alejandra López Pérez" border="0" />
  </a>
  <a href="https://psicologosmexico.mx/#790" title="psicologos-en-ciudad-de-mexico-cdmx" rel="nofollow">
    <img src="https://psicologosmexico.mx/certified/psiguide-expert-s.png" alt="psicologos-en-ciudad-de-mexico-cdmx" border="0">
  </a>
</div>

<!-- CONTACTO -->
<section id="contacto">
  <div class="contacto-content">
    <div class="section-label">Contacto</div>
    <h2 class="section-title">¿Lista/o para <em>comenzar</em>?</h2>
    <p>
      Escríbeme, cuéntame un poco sobre ti y lo que buscas. 
      Con gusto te acompaño a encontrar el espacio que necesitas.
    </p>
    <div class="contacto-btns">
      <p style="color:rgba(255,255,255,.75); font-size:.95rem; font-weight:300; margin-bottom:1.25rem;">
        Envíame un mensaje por correo o google chat:
      </p>
      <a href="mailto:psic.alejandralp16@gmail.com" style="display:inline-flex; align-items:center; gap:.85rem; background:rgba(255,255,255,.08); border:1.5px solid rgba(255,255,255,.2); border-radius:1rem; padding:1rem 1.75rem; text-decoration:none; transition: background .3s, border-color .3s;" onmouseover="this.style.background='rgba(255,255,255,.14)'; this.style.borderColor='rgba(255,255,255,.4)'" onmouseout="this.style.background='rgba(255,255,255,.08)'; this.style.borderColor='rgba(255,255,255,.2)'">
        <span style="width:44px; height:44px; border-radius:.75rem; background:var(--rose); display:flex; align-items:center; justify-content:center; flex-shrink:0; font-size:1.3rem;">✉️</span>
        <span style="text-align:left;">
          <span style="display:block; font-size:.7rem; letter-spacing:.15em; text-transform:uppercase; color:rgba(255,255,255,.5); margin-bottom:.2rem;">Correo electrónico</span>
          <span style="display:block; color:var(--blush); font-weight:700; font-size:1rem; letter-spacing:.01em;">psic.alejandralp16@gmail.com</span>
        </span>
      </a>
    </div>
    <div class="contacto-extras">
      <div class="contacto-extra-item"><span>🌿</span> Respuesta en menos de 24h</div>
      <div class="contacto-extra-item"><span>💻</span> Sesiones presenciales y en línea</div>
      <div class="contacto-extra-item"><span>🔒</span> Espacio seguro y confidencial</div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <a href="#inicio" class="footer-logo">Siéntete <strong>ConSentido</strong></a>
  <p>© 2025 Ana Alejandra López — Psicoterapia Gestalt &amp; Arte Terapia</p>
</footer>

<script>
  window.addEventListener('scroll', () => {
    document.getElementById('navbar').classList.toggle('scrolled', window.scrollY > 20);
  });

  function toggleFaq(btn) {
    const item = btn.closest('.faq-item');
    const isOpen = item.classList.contains('open');
    document.querySelectorAll('.faq-item.open').forEach(el => el.classList.remove('open'));
    if (!isOpen) item.classList.add('open');
  }
</script>

