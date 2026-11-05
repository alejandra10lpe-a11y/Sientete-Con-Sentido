<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Siéntete ConSentido — Alejandra López</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;1,400&family=Lato:wght@300;400;700&display=swap" rel="stylesheet">
<style>
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
--blush: #e8e0f5;
--rose: #9b89c4;
--rose-deep:#6e5a9e;
--sage: #b5a8d4;
--sage-light:#d4cce8;
--cream: #faf8fc;
--warm: #ede8f5;
--charcoal: #2e2a38;
--muted: #6b6280;
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
33% { border-radius: 40% 60% 50% 50% / 40% 50% 60% 60%; }
66% { border-radius: 50% 50% 30% 70% / 60% 40% 70% 30%; }
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
to { opacity: 1; transform: translateY(0); }
}
@keyframes fadeIn {
from { opacity: 0; }
to { opacity: 1; }
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
grid-template-columns: repeat(3, 1fr);
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

/* ── FORMULARIO DE CONTACTO ── */
.contacto-form {
margin-top: 3rem;
background: rgba(255,255,255,.06);
border: 1.5px solid rgba(255,255,255,.15);
border-radius: 1.75rem;
padding: 2.25rem;
text-align: left;
}
.contacto-form h3 {
font-family: 'Playfair Display', serif;
font-size: 1.4rem; color: white;
margin-bottom: .4rem; text-align: center;
}
#contacto .contacto-form .form-intro {
font-size: .9rem; color: rgba(255,255,255,.6);
text-align: center; margin: 0 auto 1.75rem; max-width: 420px;
}
.form-group { margin-bottom: 1.25rem; }
.form-group label {
display: block;
font-size: .72rem; letter-spacing: .15em; text-transform: uppercase;
color: rgba(255,255,255,.6); font-weight: 700;
margin-bottom: .5rem;
}
.form-group input,
.form-group textarea {
width: 100%;
background: rgba(255,255,255,.08);
border: 1.5px solid rgba(255,255,255,.2);
border-radius: .85rem;
padding: .9rem 1.1rem;
font-family: 'Lato', sans-serif;
font-size: .95rem; color: white;
transition: border-color .3s, background .3s;
}
.form-group textarea { min-height: 130px; resize: vertical; }
.form-group input::placeholder,
.form-group textarea::placeholder { color: rgba(255,255,255,.35); }
.form-group input:focus,
.form-group textarea:focus {
outline: none;
border-color: var(--sage-light);
background: rgba(255,255,255,.12);
}
.form-submit {
display: block; width: 100%;
background: var(--rose); color: #fff;
border: none; cursor: pointer;
padding: 1rem 2rem; border-radius: 50px;
font-family: 'Lato', sans-serif;
font-size: .875rem; font-weight: 700; letter-spacing: .08em;
text-transform: uppercase;
transition: background .3s, transform .25s;
box-shadow: 0 8px 25px rgba(0,0,0,.25);
}
.form-submit:hover { background: var(--rose-deep); transform: translateY(-2px); }

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
@media (max-width: 1100px) {
.servicios-grid { grid-template-columns: 1fr 1fr; }
}

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

#contacto { padding: 4rem 2rem; }

footer { padding: 2rem; flex-direction: column; align-items: flex-start; }
}

@media (max-width: 600px) {
.nav-links { display: none; }
.credenciales { grid-template-columns: 1fr; }
.servicios-stats { gap: 1.5rem; }
.servicio-top { padding: 2rem 1.5rem 0; }
.servicio-body { padding: 1.5rem 1.5rem 2rem; }
.contacto-form { padding: 1.5rem; }
}
</style>
</head>
<body>

<!-- NAV -->
<nav id="navbar">
<a href="#" class="nav-logo">Siéntete <span>Con</span>Sentido</a>
<ul class="nav-links">
<li><a href="#servicios">Servicios</a></li>
<li><a href="#proceso">Preguntas</a></li>
<li><a href="#sobre-mi">Sobre mí</a></li>
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
Encuentra un espacio donde puedas mirarte sin juicio y construir a tu ritmo una relación sana contigo y con tu entorno.
</p>
<div class="hero-actions">
<a href="https://forms.gle/QQ6nXRoQfx6FLf3w5" class="btn-primary">Quiero Agendar</a>
<a href="#servicios" class="btn-secondary">Ver servicios</a>
</div>
</div>

<div class="hero-visual">
<div class="hero-card">
<p class="hero-card-text">
"La congruencia entre el pensamiento, la emoción y la acción lleva a la autenticidad del ser."
</p>
</div>
</div>
</section>

<!-- ═══ SERVICIOS ═══ -->
<section id="servicios">
<div class="servicios-inner">

<div class="servicios-header">
<div>
<div class="section-label">Servicios</div>
<h2 class="section-title">¿Sientes que esta es la forma de <em>acompañamiento</em> que necesitas hoy?</h2>

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
<div class="badge-descuento">⭐ 1ª y 2ª sesión 
  con 50% de descuento</div>
</div>
<div class="servicio-body">
<h3>Terapia Psicológica</h3>
<p>Un espacio seguro para escucharte y explorar a profundidad tus experiencias buscando tu bienestar mental y emocional.</p>
<div class="servicio-divider"></div>
<ul class="servicio-includes">
<li>Sesión individual de 50 minutos</li>
<li>Presencial o en línea</li>
<li>Enfoque Gestalt Humanista para adultos</li>
</ul>
<a href="https://forms.gle/U5htUKLZUE494FbQ7" class="btn-primary">Agendar sesión</a>
</div>
<div class="servicio-accent"></div>
</div>

<!-- Mini-talleres -->
<div class="servicio-card terapia">
<div class="servicio-top">
<div class="servicio-icon">🌸</div>
<div class="badge-descuento">💻 Online</div>
</div>
<div class="servicio-body">
<h3>Mini-talleres</h3>
<p>Un pequeño espacio solo para ti, para pausar, respirar y reconectar contigo a lo largo del mes.</p>
<div class="servicio-divider"></div>
<ul class="servicio-includes">
<li>30 min solo para ti, 2 veces al mes (1er y 3er miércoles de cada mes)</li>
<li>Contenido educativo y expresivo, no sustituye la terapia individual</li>
<li>Sesiones grupales</li>
<li>Modalidad Online (Google Meet) de 7:00 pm a 7:30 pm</li>
</ul>
<a href="#contacto" class="btn-primary">Más información</a>
</div>
<div class="servicio-accent"></div>
</div>

<!-- Talleres expresivos con arte -->
<div class="servicio-card arteterapia">
<div class="servicio-top">
<div class="servicio-icon">🎨</div>
<div class="badge-descuento">📍 Presencial CDMX</div>
</div>
<div class="servicio-body">
<h3>Talleres expresivos con arte</h3>
<p>¿Es difícil para ti expresar o comunicar tus emociones? Este taller te puede ayudar a sacarlas por medio del arte.</p>
<div class="servicio-divider"></div>
<ul class="servicio-includes">
<li>Duración: 90 min</li>
<li>Modalidad presencial en la CDMX</li>
<li>Pregunta por fechas y horarios</li>
</ul>
<a href="#contacto" class="btn-primary" style="background:var(--sage);">Más información</a>
</div>
<div class="servicio-accent"></div>
</div>

</div>
</div>
</section>

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
<p>"Siéntete cómoda/o y en libertad al tomar decisiones."</p>
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
¿Cuál es el costo de las sesiones terapeúticas?
<span class="faq-icon">+</span>
</button>
<div class="faq-answer">
<p>El costo por sesión es de $500 (pesos mexicanos). Sin embargo, la primera y segunda sesión tienen un 50% de descuento debido a que se realizará una entrevista inicial y se aclararán cuestiones del tratamiento y la metodología. Si consideras que el costo no entra dentro de tu presupuesto, te puedo dar otras opciones que se ajusten a ti.</p>
</div>
</div>

<div class="faq-item open">
<button class="faq-question" onclick="toggleFaq(this)">
¿Qué pasa en la primera sesión?
<span class="faq-icon">+</span>
</button>
<div class="faq-answer">
<p>La primera sesión es un espacio para conocernos. Quisiera entender mejor quién eres, qué te trae a consulta y qué necesitas. No hay ninguna prisa. Vamos a tu ritmo y no tienes que contar todo ese día.</p>
</div>
</div>

<div class="faq-item">
<button class="faq-question" onclick="toggleFaq(this)">
¿Qué se espera de mí como paciente?
<span class="faq-icon">+</span>
</button>
<div class="faq-answer">
<p>Lo más importante es la honestidad: contigo mismo y con tu terapeuta. El consultorio es un espacio completamente seguro, sin juicios. Si no entiendes algo, pregunta siempre; es tu proceso y mereces claridad en cada momento.</p>
</div>
</div>

<div class="faq-item">
<button class="faq-question" onclick="toggleFaq(this)">
¿Las sesiones son presenciales o en línea?
<span class="faq-icon">+</span>
</button>
<div class="faq-answer">
<p>La terapia individual está disponible tanto presencial como en línea, según lo que sea más cómodo para ti.</p>
</div>
</div>

<div class="faq-item">
<button class="faq-question" onclick="toggleFaq(this)">
¿Qué es la terapia Gestalt? ¿Cómo sé si es para mí?
<span class="faq-icon">+</span>
</button>
<div class="faq-answer">
<p>La terapia Gestalt es para quien quiera escucharse, entenderse mejor y mejorar su relación consigo misma/o y con los demás. Si quieres tratarte con compasión, tomar decisiones más alineadas, o atravesar momentos de crisis, duelo o cambio — esta terapia puede ser para ti. Si tienes dudas, escríbeme.</p>
</div>
</div>

<div class="faq-item open">
<button class="faq-question" onclick="toggleFaq(this)">
¿Ofrece talleres grupales? ¿Quiénes pueden asistir?
<span class="faq-icon">+</span>
</button>
<div class="faq-answer">
<p>Sí, se imparten talleres grupales íntimos, de 5 personas. Existen 3 enfoques: 1.Para personas que han sufrido una pérdida significativa; 2. Para personas que cuidan-prevención del burnout (mamá, papá, cuidadores de adulto mayor, enfermer@s, etc.) y 3.Para personas que buscan un momento para ellas mismas, salir de la rutina y descubrir algo nuevo. PREGUNTA POR PRECIOS, FECHAS Y DISPONIBILIDAD SI TE INTERESA ALGUN TEMA. </p>
</div>
</div>

</div>
</div>
</div>
</section>

<!-- ═══ SOBRE MÍ ═══ -->
<section id="sobre-mi">
<div class="sobre-inner">


<!-- Columna foto -->
<div class="sobre-foto-col">
<div class="sobre-foto-frame">
<!-- IMPORTANTE: reemplaza src por tu foto original (base64) o por la ruta de tu archivo -->
<img src="foto-alejandra.jpg" alt="Ana Alejandra López" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
<div class="sobre-foto-placeholder" style="display:none;">🌿</div>
<div class="sobre-pill">
<strong>Enfoque Gestalt</strong>
Humanista
</div>
</div>
</div>

<!-- Columna texto -->
<div class="sobre-texto-col">
<div class="section-label">Sobre mí</div>
<h2 class="section-title">Hola, soy <em>Alejandra López</em></h2>

<p class="section-desc">
Psicoterapeuta y tanatóloga Humanista Gestalt. En mi trabajo utilizo técnicas de arte
y meditación que se entrelazan con la psicoterapia para apoyar un entendimiento
propio y vivir con más consciencia desde una mirada compasiva y respetuosa.
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
Especializada en depresión, ansiedad, duelo, adaptación cultural y al cambio. 
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
Envíame un mensaje por correo o Google Chat:
</p>
<a href="mailto:psic.alejandralp16@gmail.com" style="display:inline-flex; align-items:center; gap:.85rem; background:rgba(255,255,255,.08); border:1.5px solid rgba(255,255,255,.2); border-radius:1rem; padding:1rem 1.75rem; text-decoration:none; transition: background .3s, border-color .3s;" onmouseover="this.style.background='rgba(255,255,255,.14)'; this.style.borderColor='rgba(255,255,255,.4)'" onmouseout="this.style.background='rgba(255,255,255,.08)'; this.style.borderColor='rgba(255,255,255,.2)'">
<span style="width:44px; height:44px; border-radius:.75rem; background:var(--rose); display:flex; align-items:center; justify-content:center; flex-shrink:0; font-size:1.3rem;">✉️</span>
<span style="text-align:left;">
<span style="display:block; font-size:.7rem; letter-spacing:.15em; text-transform:uppercase; color:rgba(255,255,255,.5); margin-bottom:.2rem;">Correo electrónico</span>
<span style="display:block; color:var(--blush); font-weight:700; font-size:1rem; letter-spacing:.01em;">psic.alejandralp16@gmail.com</span>
</span>
</a>
</div>

<!-- Formulario: las respuestas llegan a aalopp140@gmail.com -->
<form class="contacto-form" action="https://formsubmit.co/aalopp140@gmail.com" method="POST">
<h3>Déjame tus datos y dudas</h3>
<p class="form-intro">Escribe tus preguntas o comentarios sobre las sesiones terapéuticas, mini-talleres o talleres expresivos y te responderé lo antes posible.</p>

<input type="hidden" name="_subject" value="Nuevo mensaje desde Siéntete ConSentido">
<input type="hidden" name="_template" value="table">
<input type="text" name="_honey" style="display:none" tabindex="-1" autocomplete="off">

<div class="form-group">
<label for="nombre">Nombre</label>
<input type="text" id="nombre" name="Nombre" placeholder="Tu nombre" required>
</div>
<div class="form-group">
<label for="correo">Correo electrónico</label>
<input type="email" id="correo" name="email" placeholder="tucorreo@ejemplo.com" required>
</div>
<div class="form-group">
<label for="mensaje">Preguntas o comentarios</label>
<textarea id="mensaje" name="Preguntas o comentarios" placeholder="Sobre sesiones terapéuticas, mini-talleres o talleres expresivos..." required></textarea>
</div>
<button type="submit" class="form-submit">Enviar mensaje</button>
</form>

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
<p>© 2025 Ana Alejandra López — Psicoterapia Gestalt</p>
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
</body>
</html>
