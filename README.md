<!DOCTYPE html>
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
    background: rgba(255,255,255,0.95);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid var(--grey-100);
    width: 100%;
    max-width: 100%;
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
    flex-shrink: 0;
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
    flex: 1;
    justify-content: center;
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
    flex-shrink: 0;
  }

  .nav-cta:hover { background: var(--blue-600); }

  /* ---------- HERO ---------- */
  .hero {
    min-height: 100vh;
    padding: 140px 5vw 80px;
    background: var(--off-white);
    position: relative;
    overflow: hidden;
    width: 100%;
    max-width: 100%;
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
    pointer-events: none;
  }

  .hero-content {
    position: relative;
    max-width: 1400px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1.1fr 1fr;
    gap: 60px;
    align-items: center;
    width: 100%;
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
    font-size: clamp(16px, 2vw, 19px);
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

  .btn-primary, .btn-secondary {
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
    white-space: nowrap;
  }

  .btn-primary {
    background: var(--navy-900);
    color: var(--white);
  }

  .btn-primary:hover {
    background: var(--blue-600);
    transform: translateY(-2px);
  }

  .btn-secondary {
    background: transparent;
    color: var(--navy-900);
    border: 1.5px solid var(--navy-900);
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
    flex-wrap: wrap;
  }

  .stat-num {
    font-family: var(--display);
    font-size: clamp(28px, 4vw, 36px);
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
    width: 100%;
    max-width: 100%;
  }

  .section-inner {
    max-width: 1400px;
    margin: 0 auto;
    padding: 0 20px;
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
    font-size: clamp(16px, 2vw, 18px);
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
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
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

  .brand-card h3 {
    font-family: var(--display);
    font-size: clamp(20px, 3vw, 24px);
    font-weight: 600;
    margin-bottom: 12px;
    letter-spacing: -0.02em;
  }

  .brand-card p {
    color: var(--blue-200);
    font-size: 15px;
    line-height: 1.6;
  }

  /* ---------- PRODUCT SECTION ---------- */
  .product {
    background: var(--off-white);
  }

  .product-showcase {
    display: grid;
    grid-template-columns: 1fr 1.2fr;
    gap: clamp(40px, 5vw, 80px);
    align-items: center;
    margin-top: 60px;
  }

  .product-info h3 {
    font-family: var(--display);
    font-size: clamp(32px, 5vw, 48px);
    font-weight: 700;
    letter-spacing: -0.03em;
    margin-bottom: 8px;
    color: var(--navy-950);
  }

  .product-info p {
    font-size: clamp(14px, 1.5vw, 16px);
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
    flex-wrap: wrap;
    gap: 16px;
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
    font-size: clamp(14px, 1.5vw, 16px);
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

  /* ---------- 3 FUNCTIONS ---------- */
  .functions {
    background: var(--white);
  }

  .functions-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
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

  .fn-card h3 {
    font-family: var(--display);
    font-size: clamp(22px, 3vw, 28px);
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
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
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
    font-size: clamp(18px, 2.5vw, 20px);
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
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
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

  .price-title {
    font-family: var(--display);
    font-size: clamp(24px, 3vw, 32px);
    font-weight: 700;
    letter-spacing: -0.02em;
    margin-bottom: 24px;
  }

  .price-value {
    font-family: var(--display);
    font-size: clamp(40px, 6vw, 56px);
    font-weight: 800;
    letter-spacing: -0.04em;
    line-height: 1;
  }

  .price-features li {
    display: flex;
    align-items: flex-start;
    gap: 12px;
    padding: 10px 0;
    font-size: clamp(13px, 1.5vw, 15px);
    color: var(--blue-100);
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
    margin-top: 24px;
  }

  .price-card.featured .price-cta {
    background: var(--navy-950);
    color: var(--white);
  }

  .price-cta:hover {
    transform: translateY(-2px);
    box-shadow: 0 10px 30px rgba(0,0,0,0.2);
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
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: clamp(40px, 5vw, 60px);
    padding-bottom: 60px;
    border-bottom: 1px solid var(--grey-100);
  }

  .footer-col h5 {
    font-family: var(--mono);
    font-size: 12px;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: var(--grey-500);
    margin-bottom: 20px;
  }

  .footer-col ul { list-style: none; }
  .footer-col ul li { margin-bottom: 12px; }

  .footer-col a {
    color: var(--navy-900);
    text-decoration: none;
    font-size: clamp(13px, 1.5vw, 14px);
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
    flex-wrap: wrap;
    gap: 16px;
  }

  /* ---------- RESPONSIVE - TABLET (1200px and below) ---------- */
  @media (max-width: 1200px) {
    .hero-content { gap: 40px; }
    section { padding: 100px 5vw; }
    .product-showcase { grid-template-columns: 1fr; }
  }

  /* ---------- RESPONSIVE - TABLET (900px and below) ---------- */
  @media (max-width: 900px) {
    nav ul { display: none; }
    
    .hero {
      min-height: auto;
      padding: 120px 5vw 60px;
    }

    .hero-content { 
      grid-template-columns: 1fr;
      gap: 40px;
    }
    
    .hero-stats { flex-direction: column; gap: 20px; }
    
    .brand-grid { grid-template-columns: repeat(2, 1fr); }
    
    .functions-grid { grid-template-columns: repeat(2, 1fr); }
    
    .workflow-steps { grid-template-columns: repeat(2, 1fr); }
    .workflow-line { display: none; }
    
    .pricing-grid { grid-template-columns: 1fr; }
    
    .machine-label { display: none; }
    
    section { padding: 80px 5vw; }
  }

  /* ---------- RESPONSIVE - MOBILE (768px and below) ---------- */
  @media (max-width: 768px) {
    nav {
      padding: 14px 4vw;
    }

    .logo { font-size: 18px; }

    .nav-cta {
      padding: 8px 16px;
      font-size: 12px;
    }

    .hero {
      padding: 100px 4vw 40px;
    }

    .hero-actions {
      flex-direction: column;
      gap: 12px;
    }

    .btn-primary, .btn-secondary {
      width: 100%;
      padding: 14px 20px;
      font-size: 14px;
    }

    .badge { font-size: 10px; padding: 5px 10px; }

    section { padding: 60px 4vw; }

    .section-inner { padding: 0 16px; }

    .brand-grid { grid-template-columns: 1fr; }

    .functions-grid { grid-template-columns: 1fr; }

    .workflow-steps { grid-template-columns: 1fr; }

    .pricing-grid { grid-template-columns: 1fr; }

    .footer-top { grid-template-columns: 1fr; gap: 32px; }

    .footer-bottom { flex-direction: column; text-align: center; }
  }

  /* ---------- RESPONSIVE - SMALL MOBILE (480px and below) ---------- */
  @media (max-width: 480px) {
    nav {
      padding: 12px 3vw;
      gap: 8px;
    }

    .logo { font-size: 16px; }

    .nav-cta { 
      width: 100%;
      padding: 10px 12px;
      font-size: 11px;
    }

    .hero { padding: 90px 3vw 30px; }

    .hero h1 { margin-bottom: 16px; }

    .hero p.lead { margin-bottom: 20px; }

    .btn-primary, .btn-secondary {
      padding: 12px 18px;
      font-size: 13px;
      gap: 6px;
    }

    section { padding: 48px 3vw; }

    .section-inner { padding: 0 12px; }

    .brand-card { padding: 20px; }

    .fn-card { padding: 24px 16px; }

    .price-card { padding: 32px 20px; }

    .footer-bottom { font-size: 11px; }
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
        <a href="#tarifs" class="btn-primary">Découvrir les tarifs →</a>
        <a href="#produit" class="btn-secondary">Voir la machine</a>
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

    <div class="machine-vis">
      <svg viewBox="0 0 500 500" xmlns="http://www.w3.org/2000/svg">
        <rect x="40" y="380" width="420" height="50" fill="#0a1733" rx="2"/>
        <rect x="40" y="430" width="420" height="20" fill="#050d1f" rx="2"/>
        <rect x="55" y="450" width="40" height="15" fill="#1a2233"/>
        <rect x="405" y="450" width="40" height="15" fill="#1a2233"/>
        <rect x="55" y="220" width="100" height="160" fill="#ffffff" stroke="#c8d1de" stroke-width="1"/>
        <rect x="345" y="220" width="115" height="160" fill="#ffffff" stroke="#c8d1de" stroke-width="1"/>
        <rect x="170" y="180" width="160" height="200" fill="#1e56e0" rx="4"/>
        <rect x="170" y="140" width="160" height="40" fill="#0a1733" rx="4"/>
        <circle cx="250" cy="160" r="12" fill="#2f6cff"/>
      </svg>
    </div>
  </div>
</section>

<!-- BRAND SECTION -->
<section class="brand">
  <div class="section-inner">
    <div class="section-tag">NOTRE MARQUE</div>
    <h2 class="section-title">Engineered for perfection</h2>
    <p class="section-lead">Découvrez comment KUBIX combine innovation, précision et automatisation.</p>
    <div class="brand-grid">
      <div class="brand-card">
        <h3>Précision</h3>
        <p>Tolérance de ±0.01mm sur toutes les opérations pour une qualité sans compromis.</p>
      </div>
      <div class="brand-card">
        <h3>Autonomie</h3>
        <p>100% automatisée. Chargez votre plan, la machine s'occupe du reste sans intervention.</p>
      </div>
      <div class="brand-card">
        <h3>Performance</h3>
        <p>3 opérations en une. Fraisage, sciage et tournage dans un même espace compact.</p>
      </div>
    </div>
  </div>
</section>

<!-- PRODUCT SECTION -->
<section class="product" id="produit">
  <div class="section-inner">
    <div class="section-tag">LE PRODUIT</div>
    <h2 class="section-title">KUBIX KX-1</h2>
    <div class="product-showcase">
      <div class="product-info">
        <h3>Spécifications</h3>
        <p>La machine tout-en-un pour petits et moyens ateliers.</p>
        <ul class="spec-list">
          <li><span class="spec-key">Capacité</span><span class="spec-val">1500mm³</span></li>
          <li><span class="spec-key">Vitesse</span><span class="spec-val">Jusqu'à 12,000 rpm</span></li>
          <li><span class="spec-key">Précision</span><span class="spec-val">±0.01mm</span></li>
          <li><span class="spec-key">Encombrement</span><span class="spec-val">1.5 m³</span></li>
        </ul>
      </div>
      <div class="product-visual"></div>
    </div>
  </div>
</section>

<!-- FUNCTIONS SECTION -->
<section class="functions" id="fonctions">
  <div class="section-inner">
    <div class="section-tag">FONCTIONNALITÉS</div>
    <h2 class="section-title">Trois opérations, un espace</h2>
    <div class="functions-grid">
      <div class="fn-card">
        <h3>Fraisage</h3>
        <p>Fraisage haute précision avec 5 axes de contrôle pour des géométries complexes.</p>
      </div>
      <div class="fn-card">
        <h3>Sciage</h3>
        <p>Découpe nette et précise sans création de chaleur grâce à la technologie de refroidissement intégrée.</p>
      </div>
      <div class="fn-card">
        <h3>Tournage</h3>
        <p>Tournage automatisé avec changement d'outils rapide pour une productivité maximale.</p>
      </div>
    </div>
  </div>
</section>

<!-- WORKFLOW SECTION -->
<section class="workflow" id="workflow">
  <div class="section-inner">
    <div class="section-tag">PROCESSUS</div>
    <h2 class="section-title">Comment ça marche</h2>
    <div class="workflow-steps">
      <div class="step">
        <div class="step-num">1</div>
        <h4>Importez</h4>
        <p>Chargez votre fichier CATIA, STL ou STEP</p>
      </div>
      <div class="step">
        <div class="step-num">2</div>
        <h4>Configurez</h4>
        <p>Sélectionnez les opérations à effectuer</p>
      </div>
      <div class="step">
        <div class="step-num">3</div>
        <h4>Lancez</h4>
        <p>La machine s'occupe de tout automatiquement</p>
      </div>
      <div class="step">
        <div class="step-num">4</div>
        <h4>Récupérez</h4>
        <p>Récupérez votre pièce usinée et parfaite</p>
      </div>
    </div>
  </div>
</section>

<!-- PRICING SECTION -->
<section class="pricing" id="tarifs">
  <div class="section-inner">
    <div class="section-tag">TARIFS</div>
    <h2 class="section-title">Investissez dans la précision</h2>
    <div class="pricing-grid">
      <div class="price-card">
        <h3 class="price-title">Starter</h3>
        <div class="price-value">149K€</div>
        <p style="color: #b9ceff; margin: 20px 0 24px;">Configuration de base</p>
        <ul class="price-features">
          <li>Fraisage et tournage</li>
          <li>Contrôle automatisé</li>
          <li>Support technique 1 an</li>
          <li>Formation incluse</li>
        </ul>
        <button class="price-cta">Demander un devis</button>
      </div>
      <div class="price-card featured">
        <h3 class="price-title">Pro</h3>
        <div class="price-value">249K€</div>
        <p style="color: rgba(255,255,255,0.9); margin: 20px 0 24px;">Configuration complète</p>
        <ul class="price-features">
          <li>Tous les outils (fraisage, sciage, tournage)</li>
          <li>5 axes de contrôle</li>
          <li>Support technique 3 ans</li>
          <li>Formations avancées incluses</li>
          <li>Garantie pièces</li>
        </ul>
        <button class="price-cta">Demander un devis</button>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-inner">
    <div class="footer-top">
      <div class="footer-brand">
        <div style="font-weight: 700; font-size: 18px;">KUBIX</div>
        <p>Révolutionner l'usinage pour les PME et TPE avec une technologie accessible et performante.</p>
      </div>
      <div class="footer-col">
        <h5>Produit</h5>
        <ul>
          <li><a href="#produit">À propos</a></li>
          <li><a href="#fonctions">Spécifications</a></li>
          <li><a href="#tarifs">Tarifs</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h5>Entreprise</h5>
        <ul>
          <li><a href="#">Blog</a></li>
          <li><a href="#">Carrières</a></li>
          <li><a href="#">Presse</a></li>
        </ul>
      </div>
      <div class="footer-col">
        <h5>Légal</h5>
        <ul>
          <li><a href="#">Confidentialité</a></li>
          <li><a href="#">Conditions</a></li>
          <li><a href="#">Contact</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <span>© 2026 KUBIX. Tous droits réservés.</span>
      <span>Fait avec ❤️ pour les makers</span>
    </div>
  </div>
</footer>

</body>
</html>
