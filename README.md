
<html lang="fr">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>KUBIX — Le distributeur d'usinage. Fraisage, Sciage, Tournage.</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:opsz,wght@12..96,400;12..96,500;12..96,600;12..96,700;12..96,800&family=Manrope:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --navy-950: #050d1f;
    --navy-900: #0a1733;
    --navy-800: #102347;
    --navy-700: #1a3366;
    --blue-600: #1e56e0;
    --blue-500: #2f6cff;
    --blue-400: #5b8cff;
    --blue-200: #b9ceff;
    --blue-100: #e3edff;
    --blue-50: #f1f6ff;
    --white: #ffffff;
    --off-white: #f7f9fc;
    --grey-100: #eef1f6;
    --grey-300: #c8d1de;
    --grey-500: #6b7a8f;
    --grey-700: #364152;
    --grey-900: #1a2233;
    --display: 'Bricolage Grotesque', sans-serif;
    --body: 'Manrope', sans-serif;
    --mono: 'JetBrains Mono', monospace;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    font-family: var(--body);
    color: var(--navy-900);
    background: var(--white);
    line-height: 1.6;
    overflow-x: hidden;
  }

  ::selection { background: var(--blue-500); color: var(--white); }

  /* ---------- NAV ---------- */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    padding: 18px 5vw;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: rgba(255,255,255,0.85);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid var(--grey-100);
  }

  .logo {
    font-family: var(--display);
    font-weight: 800;
    font-size: 24px;
    letter-spacing: -0.03em;
    color: var(--navy-900);
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .logo-mark {
    width: 32px; height: 32px;
    background: var(--navy-900);
    position: relative;
    display: inline-block;
  }
  .logo-mark::before, .logo-mark::after {
    content: '';
    position: absolute;
    background: var(--blue-500);
  }
  .logo-mark::before {
    top: 4px; left: 4px;
    width: 10px; height: 10px;
  }
  .logo-mark::after {
    bottom: 4px; right: 4px;
    width: 6px; height: 6px;
    background: var(--white);
  }

  nav ul {
    display: flex;
    gap: 36px;
    list-style: none;
  }

  nav ul a {
    text-decoration: none;
    color: var(--grey-700);
    font-size: 14px;
    font-weight: 500;
    transition: color 0.2s;
  }

  nav ul a:hover { color: var(--blue-600); }

  .nav-cta {
    background: var(--navy-900);
    color: var(--white);
    padding: 10px 22px;
    border-radius: 100px;
    font-size: 14px;
    font-weight: 600;
    text-decoration: none;
    transition: background 0.2s;
  }

  .nav-cta:hover { background: var(--blue-600); }

  /* ---------- HERO ---------- */
  .hero {
    min-height: 100vh;
    padding: 140px 5vw 80px;
    background: var(--off-white);
    position: relative;
    overflow: hidden;
  }

  .hero-grid {
    position: absolute;
    inset: 0;
    background-image:
      linear-gradient(var(--grey-100) 1px, transparent 1px),
      linear-gradient(90deg, var(--grey-100) 1px, transparent 1px);
    background-size: 80px 80px;
    mask-image: radial-gradient(ellipse at center, black 30%, transparent 75%);
    opacity: 0.6;
  }

  .hero-content {
    position: relative;
    max-width: 1400px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1.1fr 1fr;
    gap: 60px;
    align-items: center;
  }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 6px 14px;
    background: var(--blue-100);
    color: var(--blue-600);
    border-radius: 100px;
    font-size: 12px;
    font-weight: 600;
    font-family: var(--mono);
    letter-spacing: 0.05em;
    text-transform: uppercase;
    margin-bottom: 28px;
  }

  .badge-dot {
    width: 6px; height: 6px;
    background: var(--blue-500);
    border-radius: 50%;
    animation: pulse 2s infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.5; transform: scale(1.3); }
  }

  .hero h1 {
    font-family: var(--display);
    font-size: clamp(44px, 6vw, 88px);
    font-weight: 700;
    line-height: 0.95;
    letter-spacing: -0.04em;
    color: var(--navy-950);
    margin-bottom: 28px;
  }

  .hero h1 .accent {
    color: var(--blue-600);
    font-style: italic;
    font-weight: 500;
  }

  .hero h1 .strike {
    position: relative;
    display: inline-block;
  }

  .hero h1 .strike::after {
    content: '';
    position: absolute;
    left: -2%;
    right: -2%;
    top: 52%;
    height: 8px;
    background: var(--blue-500);
    transform: rotate(-2deg);
  }

  .hero p.lead {
    font-size: 19px;
    color: var(--grey-700);
    margin-bottom: 40px;
    max-width: 540px;
    line-height: 1.5;
  }

  .hero-actions {
    display: flex;
    gap: 16px;
    flex-wrap: wrap;
  }

  .btn-primary {
    background: var(--navy-900);
    color: var(--white);
    padding: 16px 32px;
    border-radius: 100px;
    font-size: 15px;
    font-weight: 600;
    text-decoration: none;
    display: inline-flex;
    align-items: center;
    gap: 10px;
    transition: all 0.2s;
    border: none;
    cursor: pointer;
  }

  .btn-primary:hover {
    background: var(--blue-600);
    transform: translateY(-2px);
  }

  .btn-secondary {
    background: transparent;
    color: var(--navy-900);
    padding: 16px 32px;
    border-radius: 100px;
    font-size: 15px;
    font-weight: 600;
    text-decoration: none;
    border: 1.5px solid var(--navy-900);
    display: inline-flex;
    align-items: center;
    gap: 10px;
    transition: all 0.2s;
  }

  .btn-secondary:hover {
    background: var(--navy-900);
    color: var(--white);
  }

  .hero-stats {
    display: flex;
    gap: 48px;
    margin-top: 64px;
    padding-top: 40px;
    border-top: 1px solid var(--grey-300);
  }

  .stat-num {
    font-family: var(--display);
    font-size: 36px;
    font-weight: 700;
    color: var(--navy-900);
    letter-spacing: -0.02em;
  }

  .stat-label {
    font-size: 12px;
    color: var(--grey-500);
    font-family: var(--mono);
    text-transform: uppercase;
    letter-spacing: 0.08em;
    margin-top: 4px;
  }

  /* ---------- MACHINE ILLUSTRATION ---------- */
  .machine-vis {
    position: relative;
    width: 100%;
    aspect-ratio: 1/1;
    max-width: 560px;
    margin: 0 auto;
  }

  .machine-vis svg {
    width: 100%;
    height: 100%;
    filter: drop-shadow(0 30px 60px rgba(10, 23, 51, 0.15));
  }

  .machine-label {
    position: absolute;
    background: var(--white);
    border: 1px solid var(--grey-300);
    padding: 8px 14px;
    border-radius: 6px;
    font-family: var(--mono);
    font-size: 11px;
    font-weight: 500;
    color: var(--grey-700);
    box-shadow: 0 4px 20px rgba(10,23,51,0.08);
  }

  .machine-label::before {
    content: '';
    position: absolute;
    width: 30px;
    height: 1px;
    background: var(--navy-900);
  }

  .label-1 { top: 8%; right: -10%; }
  .label-1::before { right: 100%; top: 50%; }
  .label-2 { top: 45%; left: -15%; }
  .label-2::before { left: 100%; top: 50%; }
  .label-3 { bottom: 18%; right: -8%; }
  .label-3::before { right: 100%; top: 50%; }

  /* ---------- SECTION GENERIC ---------- */
  section {
    padding: 120px 5vw;
  }

  .section-inner {
    max-width: 1400px;
    margin: 0 auto;
  }

  .section-tag {
    font-family: var(--mono);
    font-size: 12px;
    text-transform: uppercase;
    letter-spacing: 0.15em;
    color: var(--blue-600);
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 14px;
  }

  .section-tag::before {
    content: '';
    width: 32px;
    height: 1px;
    background: var(--blue-600);
  }

  .section-title {
    font-family: var(--display);
    font-size: clamp(36px, 4.5vw, 64px);
    font-weight: 700;
    line-height: 1;
    letter-spacing: -0.03em;
    color: var(--navy-950);
    margin-bottom: 24px;
    max-width: 900px;
  }

  .section-lead {
    font-size: 18px;
    color: var(--grey-700);
    max-width: 680px;
    margin-bottom: 64px;
    line-height: 1.6;
  }

  /* ---------- BRAND SECTION ---------- */
  .brand {
    background: var(--navy-950);
    color: var(--white);
    position: relative;
    overflow: hidden;
  }

  .brand .section-title { color: var(--white); }
  .brand .section-tag { color: var(--blue-400); }
  .brand .section-tag::before { background: var(--blue-400); }
  .brand .section-lead { color: var(--blue-200); }

  .brand-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 40px;
    margin-top: 80px;
  }

  .brand-card {
    padding: 32px;
    border: 1px solid var(--navy-700);
    background: var(--navy-900);
    border-radius: 12px;
    transition: all 0.3s;
  }

  .brand-card:hover {
    border-color: var(--blue-500);
    transform: translateY(-4px);
  }

  .brand-num {
    font-family: var(--mono);
    font-size: 13px;
    color: var(--blue-400);
    margin-bottom: 16px;
  }

  .brand-card h3 {
    font-family: var(--display);
    font-size: 24px;
    font-weight: 600;
    margin-bottom: 12px;
    letter-spacing: -0.02em;
  }

  .brand-card p {
    color: var(--blue-200);
    font-size: 15px;
    line-height: 1.6;
  }

  .brand-decor {
    position: absolute;
    bottom: -100px;
    right: -100px;
    width: 400px;
    height: 400px;
    border: 1px solid var(--navy-700);
    border-radius: 50%;
  }

  .brand-decor::before {
    content: '';
    position: absolute;
    inset: 60px;
    border: 1px solid var(--navy-700);
    border-radius: 50%;
  }

  /* ---------- PRODUCT SECTION ---------- */
  .product {
    background: var(--off-white);
  }

  .product-showcase {
    display: grid;
    grid-template-columns: 1fr 1.2fr;
    gap: 80px;
    align-items: center;
    margin-top: 60px;
  }

  .product-info h3 {
    font-family: var(--display);
    font-size: 48px;
    font-weight: 700;
    letter-spacing: -0.03em;
    margin-bottom: 8px;
    color: var(--navy-950);
  }

  .product-info .ref {
    font-family: var(--mono);
    font-size: 13px;
    color: var(--grey-500);
    text-transform: uppercase;
    letter-spacing: 0.1em;
    margin-bottom: 32px;
  }

  .product-info p {
    font-size: 16px;
    color: var(--grey-700);
    margin-bottom: 32px;
  }

  .spec-list {
    list-style: none;
    border-top: 1px solid var(--grey-300);
  }

  .spec-list li {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 18px 0;
    border-bottom: 1px solid var(--grey-300);
    font-size: 14px;
  }

  .spec-list .spec-key {
    color: var(--grey-500);
    font-family: var(--mono);
    text-transform: uppercase;
    letter-spacing: 0.05em;
    font-size: 12px;
  }

  .spec-list .spec-val {
    color: var(--navy-900);
    font-weight: 600;
    font-family: var(--display);
    font-size: 16px;
  }

  .product-visual {
    background: var(--white);
    border-radius: 24px;
    padding: 40px;
    position: relative;
    aspect-ratio: 1/1;
    border: 1px solid var(--grey-100);
    box-shadow: 0 20px 60px rgba(10,23,51,0.06);
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .product-corner {
    position: absolute;
    width: 24px;
    height: 24px;
    border: 2px solid var(--blue-600);
  }
  .corner-tl { top: 16px; left: 16px; border-right: none; border-bottom: none; }
  .corner-tr { top: 16px; right: 16px; border-left: none; border-bottom: none; }
  .corner-bl { bottom: 16px; left: 16px; border-right: none; border-top: none; }
  .corner-br { bottom: 16px; right: 16px; border-left: none; border-top: none; }

  /* ---------- 3 FUNCTIONS ---------- */
  .functions {
    background: var(--white);
  }

  .functions-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 24px;
    margin-top: 60px;
  }

  .fn-card {
    background: var(--off-white);
    border-radius: 16px;
    padding: 40px 32px;
    position: relative;
    overflow: hidden;
    transition: all 0.3s;
    border: 1px solid var(--grey-100);
  }

  .fn-card:hover {
    background: var(--navy-950);
    color: var(--white);
    transform: translateY(-6px);
  }

  .fn-card:hover .fn-num,
  .fn-card:hover h3 { color: var(--white); }
  .fn-card:hover p { color: var(--blue-200); }
  .fn-card:hover .fn-icon { border-color: var(--blue-400); }
  .fn-card:hover .fn-icon svg { stroke: var(--blue-400); }

  .fn-icon {
    width: 64px;
    height: 64px;
    border: 1.5px solid var(--navy-900);
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 32px;
    transition: all 0.3s;
  }

  .fn-icon svg {
    width: 32px;
    height: 32px;
    stroke: var(--navy-900);
    fill: none;
    stroke-width: 1.5;
    transition: all 0.3s;
  }

  .fn-num {
    position: absolute;
    top: 24px;
    right: 28px;
    font-family: var(--mono);
    font-size: 13px;
    color: var(--grey-500);
    transition: color 0.3s;
  }

  .fn-card h3 {
    font-family: var(--display);
    font-size: 28px;
    font-weight: 600;
    letter-spacing: -0.02em;
    margin-bottom: 16px;
    color: var(--navy-950);
    transition: color 0.3s;
  }

  .fn-card p {
    font-size: 15px;
    color: var(--grey-700);
    line-height: 1.6;
    transition: color 0.3s;
  }

  /* ---------- WORKFLOW ---------- */
  .workflow {
    background: linear-gradient(180deg, var(--blue-50) 0%, var(--white) 100%);
  }

  .workflow-steps {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 24px;
    margin-top: 60px;
    position: relative;
  }

  .workflow-line {
    position: absolute;
    top: 32px;
    left: 12.5%;
    right: 12.5%;
    height: 1px;
    background: var(--blue-200);
    z-index: 0;
  }

  .step {
    position: relative;
    z-index: 1;
    text-align: left;
  }

  .step-num {
    width: 64px;
    height: 64px;
    background: var(--white);
    border: 1.5px solid var(--blue-600);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: var(--display);
    font-size: 24px;
    font-weight: 700;
    color: var(--blue-600);
    margin-bottom: 24px;
  }

  .step h4 {
    font-family: var(--display);
    font-size: 20px;
    font-weight: 600;
    letter-spacing: -0.02em;
    margin-bottom: 10px;
    color: var(--navy-950);
  }

  .step p {
    font-size: 14px;
    color: var(--grey-700);
    line-height: 1.6;
  }

  /* ---------- PRICING ---------- */
  .pricing {
    background: var(--navy-950);
    color: var(--white);
    position: relative;
    overflow: hidden;
  }

  .pricing .section-title { color: var(--white); }
  .pricing .section-tag { color: var(--blue-400); }
  .pricing .section-tag::before { background: var(--blue-400); }
  .pricing .section-lead { color: var(--blue-200); }

  .pricing-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 24px;
    margin-top: 60px;
  }

  .price-card {
    background: var(--navy-900);
    border: 1px solid var(--navy-700);
    border-radius: 20px;
    padding: 48px;
    position: relative;
    overflow: hidden;
    transition: all 0.3s;
  }

  .price-card.featured {
    background: linear-gradient(135deg, var(--blue-600) 0%, var(--blue-500) 100%);
    border-color: transparent;
  }

  .price-card:hover {
    transform: translateY(-6px);
  }

  .price-label {
    font-family: var(--mono);
    font-size: 12px;
    text-transform: uppercase;
    letter-spacing: 0.15em;
    color: var(--blue-400);
    margin-bottom: 12px;
  }

  .price-card.featured .price-label {
    color: rgba(255,255,255,0.8);
  }

  .price-title {
    font-family: var(--display);
    font-size: 32px;
    font-weight: 700;
    letter-spacing: -0.02em;
    margin-bottom: 24px;
  }

  .price-amount {
    display: flex;
    align-items: baseline;
    gap: 8px;
    margin-bottom: 8px;
  }

  .price-value {
    font-family: var(--display);
    font-size: 56px;
    font-weight: 800;
    letter-spacing: -0.04em;
    line-height: 1;
  }

  .price-period {
    font-family: var(--mono);
    font-size: 14px;
    color: var(--blue-200);
  }

  .price-card.featured .price-period {
    color: rgba(255,255,255,0.9);
  }

  .price-desc {
    color: var(--blue-200);
    font-size: 15px;
    margin: 24px 0 32px;
    padding-bottom: 32px;
    border-bottom: 1px solid var(--navy-700);
  }

  .price-card.featured .price-desc {
    color: rgba(255,255,255,0.9);
    border-bottom-color: rgba(255,255,255,0.2);
  }

  .price-features {
    list-style: none;
    margin-bottom: 32px;
  }

  .price-features li {
    display: flex;
    align-items: flex-start;
    gap: 12px;
    padding: 10px 0;
    font-size: 15px;
    color: var(--blue-100);
  }

  .price-card.featured .price-features li {
    color: var(--white);
  }

  .price-features li::before {
    content: '→';
    color: var(--blue-400);
    font-weight: 700;
    flex-shrink: 0;
  }

  .price-card.featured .price-features li::before {
    color: var(--white);
  }

  .price-cta {
    display: block;
    width: 100%;
    padding: 16px;
    text-align: center;
    background: var(--white);
    color: var(--navy-950);
    border-radius: 100px;
    font-weight: 600;
    text-decoration: none;
    font-size: 15px;
    transition: all 0.2s;
    border: none;
    cursor: pointer;
  }

  .price-card.featured .price-cta {
    background: var(--navy-950);
    color: var(--white);
  }

  .price-cta:hover {
    transform: translateY(-2px);
    box-shadow: 0 10px 30px rgba(0,0,0,0.2);
  }

  .pricing-note {
    text-align: center;
    margin-top: 40px;
    color: var(--blue-200);
    font-size: 13px;
    font-family: var(--mono);
  }

  /* ---------- FOOTER ---------- */
  footer {
    background: var(--white);
    padding: 80px 5vw 32px;
    border-top: 1px solid var(--grey-100);
  }

  .footer-inner {
    max-width: 1400px;
    margin: 0 auto;
  }

  .footer-top {
    display: grid;
    grid-template-columns: 1.5fr 1fr 1fr 1fr;
    gap: 60px;
    padding-bottom: 60px;
    border-bottom: 1px solid var(--grey-100);
  }

  .footer-brand p {
    color: var(--grey-700);
    font-size: 14px;
    margin-top: 20px;
    line-height: 1.6;
    max-width: 320px;
  }

  .footer-col h5 {
    font-family: var(--mono);
    font-size: 12px;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: var(--grey-500);
    margin-bottom: 20px;
  }

  .footer-col ul {
    list-style: none;
  }

  .footer-col ul li {
    margin-bottom: 12px;
  }

  .footer-col a {
    color: var(--navy-900);
    text-decoration: none;
    font-size: 14px;
    transition: color 0.2s;
  }

  .footer-col a:hover { color: var(--blue-600); }

  .footer-bottom {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding-top: 32px;
    font-size: 13px;
    color: var(--grey-500);
    font-family: var(--mono);
  }

  /* ---------- RESPONSIVE ---------- */
  @media (max-width: 900px) {
    nav ul { display: none; }
    .hero-content { grid-template-columns: 1fr; }
    .hero-stats { flex-wrap: wrap; gap: 24px; }
    .brand-grid { grid-template-columns: 1fr; }
    .product-showcase { grid-template-columns: 1fr; gap: 40px; }
    .functions-grid { grid-template-columns: 1fr; }
    .workflow-steps { grid-template-columns: 1fr; }
    .workflow-line { display: none; }
    .pricing-grid { grid-template-columns: 1fr; }
    .footer-top { grid-template-columns: 1fr 1fr; gap: 40px; }
    .machine-label { display: none; }
    section { padding: 80px 5vw; }
  }
</style>
</head>
<body>

<!-- NAVIGATION -->
<nav>
  <a href="#" class="logo">
    <span class="logo-mark"></span>
    KUBIX
  </a>
  <ul>
    <li><a href="#produit">Le produit</a></li>
    <li><a href="#fonctions">Fonctions</a></li>
    <li><a href="#workflow">Fonctionnement</a></li>
    <li><a href="#tarifs">Tarifs</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a href="#tarifs" class="nav-cta">Demander un devis</a>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-grid"></div>
  <div class="hero-content">
    <div>
      <div class="badge">
        <span class="badge-dot"></span>
        Nouvelle génération — Disponible 2026
      </div>
      <h1>
        L'atelier d'usinage <span class="accent">tient désormais</span> dans <span class="strike">une pièce</span> un mètre carré.
      </h1>
      <p class="lead">
        KUBIX KX-1 réunit le fraisage, le sciage et le tournage dans un seul distributeur compact et 100% automatisé. Importez votre plan CATIA, la pièce sort usinée.
      </p>
      <div class="hero-actions">
        <a href="#tarifs" class="btn-primary">
          Découvrir les tarifs →
        </a>
        <a href="#produit" class="btn-secondary">
          Voir la machine
        </a>
      </div>
      <div class="hero-stats">
        <div>
          <div class="stat-num">3-en-1</div>
          <div class="stat-label">Fraisage · Sciage · Tournage</div>
        </div>
        <div>
          <div class="stat-num">1,5 m³</div>
          <div class="stat-label">Encombrement total</div>
        </div>
        <div>
          <div class="stat-num">100%</div>
          <div class="stat-label">Automatisée</div>
        </div>
      </div>
    </div>

    <!-- MACHINE SVG ILLUSTRATION -->
    <div class="machine-vis">
      <svg viewBox="0 0 500 500" xmlns="http://www.w3.org/2000/svg">
        <!-- Base -->
        <rect x="40" y="380" width="420" height="50" fill="#0a1733" rx="2"/>
        <rect x="40" y="430" width="420" height="20" fill="#050d1f" rx="2"/>
        <!-- Feet -->
        <rect x="55" y="450" width="40" height="15" fill="#1a2233"/>
        <rect x="405" y="450" width="40" height="15" fill="#1a2233"/>

        <!-- Main body left/right white -->
        <rect x="55" y="220" width="100" height="160" fill="#ffffff" stroke="#c8d1de" stroke-width="1"/>
        <rect x="345" y="220" width="115" height="160" fill="#ffffff" stroke="#c8d1de" stroke-width="1"/>

        <!-- Center dark frame -->
        <rect x="155" y="200" width="190" height="180" fill="#1a2233"/>

        <!-- Glass doors -->
        <rect x="170" y="240" width="75" height="120" fill="#5b8cff" fill-opacity="0.15" stroke="#364152" stroke-width="1.5"/>
        <rect x="255" y="240" width="75" height="120" fill="#5b8cff" fill-opacity="0.15" stroke="#364152" stroke-width="1.5"/>

        <!-- Door handles -->
        <line x1="240" y1="260" x2="240" y2="340" stroke="#c8d1de" stroke-width="2"/>
        <line x1="260" y1="260" x2="260" y2="340" stroke="#c8d1de" stroke-width="2"/>

        <!-- Spindle column (red) -->
        <rect x="210" y="50" width="80" height="180" fill="#1e56e0"/>
        <rect x="220" y="60" width="60" height="10" fill="#ffffff" fill-opacity="0.2"/>
        <!-- Logo on column -->
        <text x="250" y="140" font-family="JetBrains Mono" font-size="14" font-weight="700" fill="#ffffff" text-anchor="middle" transform="rotate(-90 250 140)">TRIAXE</text>

        <!-- Top housing -->
        <rect x="155" y="170" width="190" height="35" fill="#0a1733"/>
        <rect x="155" y="170" width="190" height="8" fill="#050d1f"/>

        <!-- Side vent left -->
        <rect x="65" y="240" width="80" height="120" fill="none" stroke="#c8d1de" stroke-width="0.5"/>
        <text x="95" y="310" font-family="Bricolage Grotesque" font-size="36" font-weight="800" fill="#2f6cff" text-anchor="middle" transform="rotate(-90 95 310)">BM-1</text>

        <!-- Right window -->
        <rect x="370" y="240" width="70" height="120" fill="#5b8cff" fill-opacity="0.15" stroke="#c8d1de" stroke-width="1"/>

        <!-- Control panel -->
        <rect x="335" y="240" width="65" height="90" fill="#1a2233" rx="3"/>
        <rect x="342" y="248" width="50" height="32" fill="#2f6cff" fill-opacity="0.3" stroke="#5b8cff" stroke-width="0.5"/>
        <!-- Screen lines -->
        <line x1="346" y1="256" x2="378" y2="256" stroke="#b9ceff" stroke-width="0.5"/>
        <line x1="346" y1="262" x2="372" y2="262" stroke="#b9ceff" stroke-width="0.5"/>
        <line x1="346" y1="268" x2="380" y2="268" stroke="#b9ceff" stroke-width="0.5"/>
        <line x1="346" y1="274" x2="368" y2="274" stroke="#b9ceff" stroke-width="0.5"/>
        <!-- Buttons -->
        <circle cx="350" cy="292" r="3" fill="#ef4444"/>
        <circle cx="362" cy="292" r="3" fill="#22c55e"/>
        <circle cx="374" cy="292" r="3" fill="#facc15"/>
        <circle cx="386" cy="292" r="3" fill="#5b8cff"/>
        <rect x="345" y="302" width="45" height="20" fill="#050d1f" stroke="#364152" stroke-width="0.3"/>
        <line x1="350" y1="308" x2="385" y2="308" stroke="#6b7a8f" stroke-width="0.3"/>
        <line x1="350" y1="313" x2="385" y2="313" stroke="#6b7a8f" stroke-width="0.3"/>
        <line x1="350" y1="318" x2="385" y2="318" stroke="#6b7a8f" stroke-width="0.3"/>

        <!-- Inside workspace -->
        <rect x="180" y="295" width="120" height="50" fill="#050d1f"/>
        <circle cx="240" cy="320" r="8" fill="#5b8cff" fill-opacity="0.3"/>
        <rect x="235" y="313" width="10" height="6" fill="#c8d1de"/>

        <!-- Coordinate dimensions -->
        <line x1="40" y1="475" x2="460" y2="475" stroke="#6b7a8f" stroke-width="0.5" stroke-dasharray="3,3"/>
        <text x="250" y="490" font-family="JetBrains Mono" font-size="9" fill="#6b7a8f" text-anchor="middle">1500 mm</text>
      </svg>

      <div class="machine-label label-1">CN multi-axes</div>
      <div class="machine-label label-2">Bras robotisé intégré</div>
      <div class="machine-label label-3">Écran tactile · CATIA</div>
    </div>
  </div>
</section>

<!-- BRAND -->
<section class="brand" id="marque">
  <div class="brand-decor"></div>
  <div class="section-inner">
    <div class="section-tag">À propos de TRIAXE</div>
    <h2 class="section-title">L'usinage de précision, démocratisé.</h2>
    <p class="section-lead">
      Né en 2024 à Bordeaux, TRIAXE est une jeune entreprise française qui pense l'industrie autrement : faire entrer une cellule d'usinage complète dans le format d'une borne automatique, pour la rendre accessible aux ateliers, laboratoires de recherche et bureaux d'ingénierie.
    </p>

    <div class="brand-grid">
      <div class="brand-card">
        <div class="brand-num">01 / Mission</div>
        <h3>Compacité radicale</h3>
        <p>Un atelier d'usinage tient dans 1,5 m³. Plus besoin de hall industriel : la machine s'installe partout où il y a une prise électrique adaptée.</p>
      </div>
      <div class="brand-card">
        <div class="brand-num">02 / Vision</div>
        <h3>Zéro intermédiaire</h3>
        <p>Du plan CATIA à la pièce finie, sans opérateur expérimenté. L'IA convertit votre fichier en gamme d'usinage et la machine exécute.</p>
      </div>
      <div class="brand-card">
        <div class="brand-num">03 / Engagement</div>
        <h3>Made in France</h3>
        <p>Conception et assemblage en Nouvelle-Aquitaine. Service après-vente sous 48h, garantie 5 ans pièces et main d'œuvre.</p>
      </div>
    </div>
  </div>
</section>

<!-- PRODUCT -->
<section class="product" id="produit">
  <div class="section-inner">
    <div class="section-tag">Le produit</div>
    <h2 class="section-title">TRIAXE BM-1, l'usine en kit.</h2>
    <p class="section-lead">
      Pensée pour la production en petite série de pièces de précision — visserie, micro-mécanique, prototypage — la BM-1 réunit dans un châssis monobloc tout ce qui était auparavant disséminé sur trois machines distinctes.
    </p>

    <div class="product-showcase">
      <div class="product-info">
        <h3>BM-1</h3>
        <div class="ref">RÉF. TRX-BM1-2026</div>
        <p>
          Conçue pour usiner principalement l'acier et l'aluminium, la BM-1 produit des pièces jusqu'à 10×10×15 mm avec une tolérance de ±0,01 mm. L'ensemble du processus — chargement du brut, mise en position, usinage, évacuation — est piloté par bras robotisé intégré et mandrins motorisés.
        </p>

        <ul class="spec-list">
          <li><span class="spec-key">Encombrement</span><span class="spec-val">1500 × 1000 × 2000 mm</span></li>
          <li><span class="spec-key">Pièces produites</span><span class="spec-val">jusqu'à 10×10×15 mm</span></li>
          <li><span class="spec-key">Matériaux</span><span class="spec-val">Acier · Aluminium</span></li>
          <li><span class="spec-key">Précision</span><span class="spec-val">± 0,01 mm</span></li>
          <li><span class="spec-key">Format plan</span><span class="spec-val">CATIA V5 / V6 · STEP</span></li>
          <li><span class="spec-key">Cadence</span><span class="spec-val">Jusqu'à 120 pièces/h</span></li>
          <li><span class="spec-key">Garantie</span><span class="spec-val">5 ans</span></li>
        </ul>
      </div>

      <div class="product-visual">
        <span class="product-corner corner-tl"></span>
        <span class="product-corner corner-tr"></span>
        <span class="product-corner corner-bl"></span>
        <span class="product-corner corner-br"></span>

        <svg viewBox="0 0 400 400" width="100%" height="100%" xmlns="http://www.w3.org/2000/svg">
          <!-- Base -->
          <rect x="30" y="300" width="340" height="40" fill="#0a1733"/>
          <rect x="30" y="340" width="340" height="14" fill="#050d1f"/>
          <rect x="45" y="354" width="30" height="10" fill="#1a2233"/>
          <rect x="325" y="354" width="30" height="10" fill="#1a2233"/>

          <!-- Left/right white panels -->
          <rect x="45" y="170" width="80" height="130" fill="#ffffff" stroke="#c8d1de" stroke-width="1"/>
          <rect x="275" y="170" width="95" height="130" fill="#ffffff" stroke="#c8d1de" stroke-width="1"/>

          <!-- Center frame -->
          <rect x="125" y="155" width="150" height="145" fill="#1a2233"/>

          <!-- Glass -->
          <rect x="138" y="190" width="60" height="95" fill="#5b8cff" fill-opacity="0.15" stroke="#364152" stroke-width="1.5"/>
          <rect x="206" y="190" width="60" height="95" fill="#5b8cff" fill-opacity="0.15" stroke="#364152" stroke-width="1.5"/>

          <!-- Spindle column blue -->
          <rect x="170" y="40" width="60" height="140" fill="#1e56e0"/>
          <text x="200" y="115" font-family="JetBrains Mono" font-size="11" font-weight="700" fill="#ffffff" text-anchor="middle" transform="rotate(-90 200 115)">TRIAXE</text>

          <!-- Top housing -->
          <rect x="125" y="130" width="150" height="28" fill="#0a1733"/>

          <!-- Side vent left BM-1 label -->
          <text x="85" y="245" font-family="Bricolage Grotesque" font-size="28" font-weight="800" fill="#2f6cff" text-anchor="middle" transform="rotate(-90 85 245)">BM-1</text>

          <!-- Control panel -->
          <rect x="266" y="190" width="55" height="78" fill="#1a2233" rx="2"/>
          <rect x="272" y="196" width="42" height="28" fill="#2f6cff" fill-opacity="0.3" stroke="#5b8cff" stroke-width="0.5"/>
          <line x1="276" y1="203" x2="306" y2="203" stroke="#b9ceff" stroke-width="0.4"/>
          <line x1="276" y1="209" x2="300" y2="209" stroke="#b9ceff" stroke-width="0.4"/>
          <line x1="276" y1="215" x2="308" y2="215" stroke="#b9ceff" stroke-width="0.4"/>
          <circle cx="279" cy="235" r="2.5" fill="#ef4444"/>
          <circle cx="289" cy="235" r="2.5" fill="#22c55e"/>
          <circle cx="299" cy="235" r="2.5" fill="#facc15"/>
          <circle cx="309" cy="235" r="2.5" fill="#5b8cff"/>
          <rect x="273" y="245" width="40" height="18" fill="#050d1f"/>

          <!-- Window right -->
          <rect x="296" y="190" width="60" height="95" fill="#5b8cff" fill-opacity="0.15" stroke="#c8d1de" stroke-width="1"/>
        </svg>
      </div>
    </div>
  </div>
</section>

<!-- FUNCTIONS -->
<section class="functions" id="fonctions">
  <div class="section-inner">
    <div class="section-tag">Trois machines, un seul châssis</div>
    <h2 class="section-title">Fraisage. Sciage. Tournage.</h2>
    <p class="section-lead">
      La BM-1 commute automatiquement entre trois modes d'usinage sans intervention humaine. Le bras robotisé interne change d'outil, repositionne le brut, et lance l'opération suivante.
    </p>

    <div class="functions-grid">
      <div class="fn-card">
        <span class="fn-num">/ 01</span>
        <div class="fn-icon">
          <svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="3"/><circle cx="12" cy="12" r="8"/><line x1="12" y1="2" x2="12" y2="6"/><line x1="12" y1="18" x2="12" y2="22"/><line x1="2" y1="12" x2="6" y2="12"/><line x1="18" y1="12" x2="22" y2="12"/></svg>
        </div>
        <h3>Fraisage</h3>
        <p>Fraise multi-axes haute vitesse jusqu'à 24 000 tr/min. Idéal pour les surfaces complexes, perçages et taraudages sur acier comme aluminium.</p>
      </div>

      <div class="fn-card">
        <span class="fn-num">/ 02</span>
        <div class="fn-icon">
          <svg viewBox="0 0 24 24"><path d="M3 12h18"/><path d="M5 9l2 3-2 3"/><path d="M9 9l2 3-2 3"/><path d="M13 9l2 3-2 3"/><path d="M17 9l2 3-2 3"/></svg>
        </div>
        <h3>Sciage</h3>
        <p>Module de découpe pour barres et profilés. Coupes nettes à ±0,05 mm, refroidissement automatique, évacuation des copeaux par convoyeur intégré.</p>
      </div>

      <div class="fn-card">
        <span class="fn-num">/ 03</span>
        <div class="fn-icon">
          <svg viewBox="0 0 24 24"><ellipse cx="12" cy="12" rx="9" ry="3"/><path d="M3 12v4c0 1.7 4 3 9 3s9-1.3 9-3v-4"/><path d="M3 12V8c0-1.7 4-3 9-3s9 1.3 9 3v4"/></svg>
        </div>
        <h3>Tournage</h3>
        <p>Mandrin motorisé jusqu'à 6 000 tr/min, mors auto-centrant, tourelle 8 outils. Production de pièces de révolution en série continue.</p>
      </div>
    </div>
  </div>
</section>

<!-- WORKFLOW -->
<section class="workflow" id="workflow">
  <div class="section-inner">
    <div class="section-tag">Comment ça marche</div>
    <h2 class="section-title">Du plan à la pièce, en quatre étapes.</h2>
    <p class="section-lead">
      Aucune compétence d'opérateur CN requise. L'écran tactile guide l'utilisateur, le logiciel embarqué fait le reste.
    </p>

    <div class="workflow-steps">
      <div class="workflow-line"></div>
      <div class="step">
        <div class="step-num">1</div>
        <h4>Importez</h4>
        <p>Téléchargez votre plan CATIA V5/V6 ou STEP directement depuis l'écran tactile ou via USB / réseau.</p>
      </div>
      <div class="step">
        <div class="step-num">2</div>
        <h4>Validez</h4>
        <p>Le logiciel embarqué convertit le plan en programme d'usinage et propose une gamme optimisée. Vous confirmez.</p>
      </div>
      <div class="step">
        <div class="step-num">3</div>
        <h4>Chargez</h4>
        <p>Insérez le brut dans le sas. Le bras robotisé prend le relais, met en position et serre dans le mandrin motorisé.</p>
      </div>
      <div class="step">
        <div class="step-num">4</div>
        <h4>Récupérez</h4>
        <p>La pièce finie sort dans le bac de sortie. Cycle suivant déclenché automatiquement si série programmée.</p>
      </div>
    </div>
  </div>
</section>

<!-- PRICING -->
<section class="pricing" id="tarifs">
  <div class="section-inner">
    <div class="section-tag">Tarifs</div>
    <h2 class="section-title">Achetez-la. Ou louez-la.</h2>
    <p class="section-lead">
      Deux modalités d'accès pensées pour s'adapter à votre cycle de production : acquisition pour les ateliers stables, location longue durée pour les projets et bureaux d'étude.
    </p>

    <div class="pricing-grid">
      <div class="price-card">
        <div class="price-label">Acquisition</div>
        <div class="price-title">Achat TRIAXE BM-1</div>
        <div class="price-amount">
          <span class="price-value">98 789,99 €</span>
        </div>
        <span class="price-period">HT · Livraison & installation incluses</span>
        <p class="price-desc">La machine devient votre actif. Idéal pour une utilisation intensive et un amortissement sur 5 à 7 ans.</p>
        <ul class="price-features">
          <li>Garantie pièces & main d'œuvre 5 ans</li>
          <li>Installation et formation sur site (2 jours)</li>
          <li>Mises à jour logicielles à vie</li>
          <li>Hotline technique 6j/7</li>
          <li>Pack 50 outils premier équipement offert</li>
        </ul>
        <a href="#contact" class="price-cta">Acheter la BM-1</a>
      </div>

      <div class="price-card featured">
        <div class="price-label">Location longue durée</div>
        <div class="price-title">TRIAXE BM-1 en LOA</div>
        <div class="price-amount">
          <span class="price-value">4 987,98 €</span>
        </div>
        <span class="price-period">/ mois HT · Engagement 36 mois min.</span>
        <p class="price-desc">Sans apport, machine récente, maintenance incluse. La formule la plus souple pour démarrer ou tester une nouvelle ligne de production.</p>
        <ul class="price-features">
          <li>Maintenance préventive & curative incluse</li>
          <li>Échange standard sous 48h en cas de panne</li>
          <li>Formation continue des opérateurs</li>
          <li>Option d'achat à terme (valeur résiduelle 15%)</li>
          <li>Upgrade vers nouvelle génération possible</li>
        </ul>
        <a href="#contact" class="price-cta">Louer la BM-1</a>
      </div>
    </div>

    <p class="pricing-note">Tarifs valables jusqu'au 31/12/2026 · Devis personnalisé sur demande pour flotte ≥ 3 unités</p>
  </div>
</section>

<!-- FOOTER -->
<footer id="contact">
  <div class="footer-inner">
    <div class="footer-top">
      <div class="footer-brand">
        <a href="#" class="logo">
          <span class="logo-mark"></span>
          TRIAXE
        </a>
        <p>L'atelier d'usinage compact, automatisé, made in France. Bordeaux · Nouvelle-Aquitaine.</p>
      </div>

      <div class="footer-col">
        <h5>Produit</h5>
        <ul>
          <li><a href="#produit">TRIAXE BM-1</a></li>
          <li><a href="#fonctions">Fonctions</a></li>
          <li><a href="#workflow">Fonctionnement</a></li>
          <li><a href="#tarifs">Tarifs</a></li>
        </ul>
      </div>

      <div class="footer-col">
        <h5>Société</h5>
        <ul>
          <li><a href="#marque">À propos</a></li>
          <li><a href="#">Carrières</a></li>
          <li><a href="#">Presse</a></li>
          <li><a href="#">Partenaires</a></li>
        </ul>
      </div>

      <div class="footer-col">
        <h5>Contact</h5>
        <ul>
          <li><a href="mailto:contact@triaxe.fr">contact@triaxe.fr</a></li>
          <li><a href="tel:+33556000000">+33 5 56 00 00 00</a></li>
          <li><a href="#">12 rue de l'Industrie<br/>33000 Bordeaux</a></li>
        </ul>
      </div>
    </div>

    <div class="footer-bottom">
      <span>© 2026 TRIAXE SAS — Tous droits réservés</span>
      <span>Site fictif — Projet d'étude</span>
    </div>
  </div>
</footer>

</body>
</html>
