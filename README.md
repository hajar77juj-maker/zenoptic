<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Zenoptic — Voir. Comprendre. Sublimer.</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Lato:wght@300;400;700&display=swap" rel="stylesheet" />

  <!-- ============================================================
       STYLES — Easy to edit: change colors in :root section below
       ============================================================ -->
  <style>

    /* ─────────────────────────────────────
       COLORS & FONTS — Edit these to change
       the whole site look instantly
    ───────────────────────────────────── */
    :root {
      --color-bg:        #faf8f5;      /* Page background */
      --color-dark:      #1a1a1a;      /* Text & nav */
      --color-gold:      #b8943f;      /* Accent / brand gold */
      --color-gold-soft: #f0e6cc;      /* Light gold for backgrounds */
      --color-white:     #ffffff;
      --color-gray:      #6b6b6b;      /* Muted text */
      --color-border:    #e8e2d9;      /* Dividers */

      --font-heading: 'Playfair Display', Georgia, serif;
      --font-body:    'Lato', sans-serif;

      --radius: 12px;
      --shadow: 0 4px 24px rgba(0,0,0,0.10);
      --shadow-hover: 0 12px 40px rgba(0,0,0,0.16);
    }

    /* ─────────────────────────────────────
       RESET & BASE
    ───────────────────────────────────── */
    *, *::before, *::after {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html { scroll-behavior: smooth; }

    body {
      background-color: var(--color-bg);
      color: var(--color-dark);
      font-family: var(--font-body);
      font-weight: 300;
      line-height: 1.7;
      font-size: 16px;
    }

    img {
      display: block;
      max-width: 100%;
      height: auto;
    }

    a { text-decoration: none; color: inherit; }

    /* ─────────────────────────────────────
       REUSABLE HELPERS
    ───────────────────────────────────── */

    /* Centered page wrapper */
    .container {
      width: 90%;
      max-width: 1160px;
      margin: 0 auto;
    }

    /* Gold accent line above section titles */
    .section-label {
      display: inline-block;
      font-family: var(--font-body);
      font-size: 0.7rem;
      font-weight: 700;
      letter-spacing: 0.3em;
      text-transform: uppercase;
      color: var(--color-gold);
      margin-bottom: 1rem;
    }

    /* Big section title */
    .section-title {
      font-family: var(--font-heading);
      font-size: clamp(2rem, 5vw, 3rem);
      font-weight: 700;
      line-height: 1.15;
      color: var(--color-dark);
      margin-bottom: 1rem;
    }

    .section-title em {
      font-style: italic;
      color: var(--color-gold);
    }

    /* Subtitle paragraph */
    .section-subtitle {
      font-size: 1rem;
      color: var(--color-gray);
      max-width: 520px;
      line-height: 1.8;
    }

    /* Gold button (main CTA) */
    .btn-primary {
      display: inline-block;
      background-color: var(--color-gold);
      color: var(--color-white);
      font-family: var(--font-body);
      font-weight: 700;
      font-size: 0.85rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      padding: 1rem 2.4rem;
      border-radius: 4px;
      border: 2px solid var(--color-gold);
      transition: background-color 0.3s, color 0.3s, transform 0.2s;
      cursor: pointer;
    }

    .btn-primary:hover {
      background-color: transparent;
      color: var(--color-gold);
      transform: translateY(-2px);
    }

    /* Outline button (secondary) */
    .btn-outline {
      display: inline-block;
      background-color: transparent;
      color: var(--color-white);
      font-family: var(--font-body);
      font-weight: 700;
      font-size: 0.85rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      padding: 1rem 2.4rem;
      border-radius: 4px;
      border: 2px solid rgba(255,255,255,0.6);
      transition: background-color 0.3s, transform 0.2s;
      cursor: pointer;
    }

    .btn-outline:hover {
      background-color: rgba(255,255,255,0.15);
      transform: translateY(-2px);
    }

    /* Thin gold divider line */
    .divider {
      width: 60px;
      height: 2px;
      background-color: var(--color-gold);
      margin: 1.5rem 0;
    }

    /* ─────────────────────────────────────
       NAVIGATION BAR
    ───────────────────────────────────── */
    .navbar {
      position: fixed;          /* Sticks to top while scrolling */
      top: 0;
      left: 0;
      right: 0;
      z-index: 100;
      background-color: rgba(250, 248, 245, 0.95);
      backdrop-filter: blur(10px);
      border-bottom: 1px solid var(--color-border);
      padding: 1.1rem 0;
      transition: box-shadow 0.3s;
    }

    .navbar.scrolled {
      box-shadow: 0 2px 20px rgba(0,0,0,0.08);
    }

    /* Nav inner layout: logo left, links right */
    .navbar-inner {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 2rem;
    }

    /* Logo text */
    .navbar-logo {
      font-family: var(--font-heading);
      font-size: 1.5rem;
      font-weight: 700;
      color: var(--color-dark);
      letter-spacing: 0.05em;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .navbar-logo span {
      color: var(--color-gold);
    }

    /* Nav links list */
    .navbar-links {
      display: flex;
      list-style: none;
      gap: 2.5rem;
      align-items: center;
    }

    .navbar-links a {
      font-size: 0.82rem;
      font-weight: 400;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--color-gray);
      transition: color 0.2s;
    }

    .navbar-links a:hover {
      color: var(--color-gold);
    }

    /* Mobile: hide nav links on small screens */
    @media (max-width: 680px) {
      .navbar-links { display: none; }
    }

    /* ─────────────────────────────────────
       HERO SECTION
       Big first impression block
    ───────────────────────────────────── */
    .hero {
      min-height: 100vh;
      padding-top: 80px;           /* offset for fixed navbar */
      display: flex;
      align-items: center;
      position: relative;
      overflow: hidden;
      background-color: var(--color-dark);
    }

    /* Blurred gold circle — decorative background glow */
    .hero::before {
      content: '';
      position: absolute;
      top: -20%;
      right: -10%;
      width: 600px;
      height: 600px;
      background: radial-gradient(circle, rgba(184,148,63,0.2) 0%, transparent 65%);
      border-radius: 50%;
      pointer-events: none;
    }

    /* Two-column layout inside hero */
    .hero-inner {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 4rem;
      align-items: center;
      width: 90%;
      max-width: 1160px;
      margin: 0 auto;
      padding: 6rem 0;
    }

    /* Left column: text */
    .hero-text {
      position: relative;
      z-index: 2;
    }

    .hero-eyebrow {
      font-size: 0.7rem;
      font-weight: 700;
      letter-spacing: 0.35em;
      text-transform: uppercase;
      color: var(--color-gold);
      margin-bottom: 1.5rem;
      opacity: 0;
      animation: fadeUp 0.8s 0.2s forwards;
    }

    /* Main headline — edit this text in the HTML */
    .hero-headline {
      font-family: var(--font-heading);
      font-size: clamp(2.8rem, 6vw, 4.5rem);
      font-weight: 700;
      line-height: 1.1;
      color: var(--color-white);
      margin-bottom: 1.5rem;
      opacity: 0;
      animation: fadeUp 0.8s 0.4s forwards;
    }

    .hero-headline em {
      font-style: italic;
      color: var(--color-gold);
    }

    /* Subheadline */
    .hero-sub {
      font-size: 1.05rem;
      color: rgba(255,255,255,0.65);
      line-height: 1.8;
      max-width: 430px;
      margin-bottom: 2.5rem;
      opacity: 0;
      animation: fadeUp 0.8s 0.6s forwards;
    }

    /* CTA buttons row */
    .hero-buttons {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
      opacity: 0;
      animation: fadeUp 0.8s 0.8s forwards;
    }

    /* Right column: glasses image */
    .hero-image {
      position: relative;
      z-index: 2;
      opacity: 0;
      animation: fadeIn 1.2s 0.6s forwards;
    }

    .hero-image img {
      width: 100%;
      border-radius: var(--radius);
      box-shadow: 0 20px 60px rgba(0,0,0,0.4);
      object-fit: cover;
      height: 480px;
    }

    /* Floating badge on the image */
    .hero-badge {
      position: absolute;
      bottom: -20px;
      left: -20px;
      background-color: var(--color-gold);
      color: var(--color-white);
      font-family: var(--font-heading);
      font-style: italic;
      font-size: 0.95rem;
      padding: 1rem 1.5rem;
      border-radius: var(--radius);
      box-shadow: var(--shadow);
    }

    /* Slogan strip at bottom of hero */
    .hero-slogan {
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      background-color: var(--color-gold);
      padding: 0.9rem 0;
      overflow: hidden;
    }

    .hero-slogan-track {
      display: flex;
      gap: 5rem;
      white-space: nowrap;
      animation: marquee 18s linear infinite;
    }

    .hero-slogan-track span {
      font-size: 0.75rem;
      font-weight: 700;
      letter-spacing: 0.3em;
      text-transform: uppercase;
      color: rgba(255,255,255,0.85);
      flex-shrink: 0;
    }

    /* ─────────────────────────────────────
       GLASSES SHOWCASE — image strip
    ───────────────────────────────────── */
    .showcase {
      padding: 5rem 0;
      background-color: var(--color-white);
      border-bottom: 1px solid var(--color-border);
    }

    .showcase-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 1.5rem;
    }

    .showcase-item {
      position: relative;
      border-radius: var(--radius);
      overflow: hidden;
      cursor: pointer;
    }

    .showcase-item img {
      width: 100%;
      height: 220px;
      object-fit: cover;
      transition: transform 0.5s;
    }

    .showcase-item:hover img {
      transform: scale(1.06);
    }

    .showcase-item-label {
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      background: linear-gradient(transparent, rgba(0,0,0,0.75));
      color: var(--color-white);
      font-family: var(--font-heading);
      font-size: 1rem;
      font-style: italic;
      padding: 1.5rem 1rem 1rem;
    }

    /* ─────────────────────────────────────
       FEATURES SECTION — 3 key benefits
    ───────────────────────────────────── */
    .features {
      padding: 7rem 0;
      background-color: var(--color-bg);
    }

    /* Section header: label + title + subtitle */
    .features-header {
      text-align: center;
      margin-bottom: 4rem;
    }

    .features-header .divider {
      margin: 1rem auto;
    }

    .features-header .section-subtitle {
      margin: 0 auto;
      text-align: center;
    }

    /* 3-column grid for benefit cards */
    .features-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 2rem;
    }

    /* Single benefit card */
    .feature-card {
      background-color: var(--color-white);
      border: 1px solid var(--color-border);
      border-radius: var(--radius);
      padding: 2.5rem 2rem;
      text-align: center;
      transition: box-shadow 0.3s, transform 0.3s;
    }

    .feature-card:hover {
      box-shadow: var(--shadow-hover);
      transform: translateY(-6px);
    }

    /* Icon circle */
    .feature-icon {
      width: 72px;
      height: 72px;
      border-radius: 50%;
      background-color: var(--color-gold-soft);
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 0 auto 1.5rem;
      font-size: 2rem;
    }

    /* Benefit title */
    .feature-title {
      font-family: var(--font-heading);
      font-size: 1.4rem;
      font-weight: 700;
      margin-bottom: 0.8rem;
      color: var(--color-dark);
    }

    /* Benefit description */
    .feature-text {
      font-size: 0.9rem;
      color: var(--color-gray);
      line-height: 1.8;
    }

    /* ─────────────────────────────────────
       COLLECTIONS SECTION — 3 images
    ───────────────────────────────────── */
    .collections {
      padding: 7rem 0;
      background-color: var(--color-dark);
    }

    .collections-header {
      margin-bottom: 3.5rem;
    }

    .collections-header .section-title {
      color: var(--color-white);
    }

    .collections-header .section-subtitle {
      color: rgba(255,255,255,0.55);
    }

    /* Large + 2 small layout */
    .collections-grid {
      display: grid;
      grid-template-columns: 1.3fr 1fr;
      grid-template-rows: auto auto;
      gap: 1.5rem;
    }

    .collection-card {
      position: relative;
      border-radius: var(--radius);
      overflow: hidden;
      cursor: pointer;
    }

    /* Big card spans 2 rows */
    .collection-card.big {
      grid-row: 1 / 3;
    }

    .collection-card img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      min-height: 280px;
      transition: transform 0.5s;
    }

    .collection-card.big img {
      min-height: 560px;
    }

    .collection-card:hover img {
      transform: scale(1.04);
    }

    /* Overlay text on collection card */
    .collection-overlay {
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      padding: 2rem 1.5rem 1.5rem;
      background: linear-gradient(transparent, rgba(0,0,0,0.8));
    }

    .collection-name {
      font-family: var(--font-heading);
      font-size: 1.5rem;
      font-style: italic;
      color: var(--color-white);
      margin-bottom: 0.3rem;
    }

    .collection-tag {
      font-size: 0.7rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--color-gold);
      font-weight: 700;
    }

    /* ─────────────────────────────────────
       TESTIMONIALS — 3 social proof blocks
    ───────────────────────────────────── */
    .testimonials {
      padding: 7rem 0;
      background-color: var(--color-white);
    }

    .testimonials-header {
      text-align: center;
      margin-bottom: 4rem;
    }

    .testimonials-header .divider {
      margin: 1rem auto;
    }

    /* 3-column grid */
    .testimonials-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 2rem;
    }

    /* Single review card */
    .testimonial-card {
      background-color: var(--color-bg);
      border: 1px solid var(--color-border);
      border-radius: var(--radius);
      padding: 2rem;
      position: relative;
    }

    /* Big quote mark decoration */
    .testimonial-quote-mark {
      font-family: var(--font-heading);
      font-size: 5rem;
      line-height: 1;
      color: var(--color-gold-soft);
      position: absolute;
      top: 1rem;
      right: 1.5rem;
      font-style: italic;
      pointer-events: none;
    }

    /* Star rating */
    .testimonial-stars {
      display: flex;
      gap: 4px;
      margin-bottom: 1.2rem;
    }

    .star {
      color: var(--color-gold);
      font-size: 1rem;
    }

    /* Review text */
    .testimonial-text {
      font-size: 0.95rem;
      line-height: 1.8;
      color: var(--color-dark);
      margin-bottom: 1.5rem;
      font-style: italic;
    }

    /* Reviewer info row */
    .testimonial-author {
      display: flex;
      align-items: center;
      gap: 0.8rem;
    }

    /* Avatar circle with initials */
    .testimonial-avatar {
      width: 42px;
      height: 42px;
      border-radius: 50%;
      background-color: var(--color-gold);
      color: var(--color-white);
      font-weight: 700;
      font-size: 0.9rem;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-shrink: 0;
    }

    .testimonial-name {
      font-weight: 700;
      font-size: 0.9rem;
      color: var(--color-dark);
    }

    .testimonial-location {
      font-size: 0.78rem;
      color: var(--color-gray);
    }

    /* ─────────────────────────────────────
       CONTACT CTA — Final call to action
    ───────────────────────────────────── */
    .cta-section {
      padding: 7rem 0;
      background: linear-gradient(135deg, #1a1a1a 0%, #2a2218 100%);
      text-align: center;
      position: relative;
      overflow: hidden;
    }

    /* Decorative circle behind CTA */
    .cta-section::before {
      content: '';
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      width: 700px;
      height: 700px;
      background: radial-gradient(circle, rgba(184,148,63,0.12) 0%, transparent 65%);
      border-radius: 50%;
      pointer-events: none;
    }

    .cta-inner {
      position: relative;
      z-index: 2;
    }

    .cta-label {
      font-size: 0.7rem;
      font-weight: 700;
      letter-spacing: 0.35em;
      text-transform: uppercase;
      color: var(--color-gold);
      margin-bottom: 1.5rem;
      display: block;
    }

    .cta-title {
      font-family: var(--font-heading);
      font-size: clamp(2.5rem, 6vw, 4rem);
      font-weight: 700;
      color: var(--color-white);
      line-height: 1.15;
      margin-bottom: 1.5rem;
    }

    .cta-title em {
      font-style: italic;
      color: var(--color-gold);
    }

    .cta-sub {
      font-size: 1rem;
      color: rgba(255,255,255,0.55);
      max-width: 480px;
      margin: 0 auto 2.5rem;
      line-height: 1.8;
    }

    /* Info boxes row under CTA buttons */
    .cta-info {
      display: flex;
      justify-content: center;
      gap: 3rem;
      margin-top: 3rem;
      flex-wrap: wrap;
    }

    .cta-info-item {
      text-align: center;
    }

    .cta-info-icon {
      font-size: 1.5rem;
      margin-bottom: 0.5rem;
    }

    .cta-info-label {
      font-size: 0.68rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--color-gold);
      font-weight: 700;
      margin-bottom: 0.3rem;
    }

    .cta-info-value {
      font-size: 0.9rem;
      color: rgba(255,255,255,0.7);
    }

    /* ─────────────────────────────────────
       FOOTER
    ───────────────────────────────────── */
    .footer {
      background-color: #111;
      padding: 3rem 0 2rem;
      border-top: 1px solid rgba(255,255,255,0.07);
    }

    .footer-inner {
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 1.5rem;
    }

    .footer-logo {
      font-family: var(--font-heading);
      font-size: 1.4rem;
      font-weight: 700;
      color: var(--color-white);
    }

    .footer-logo span {
      color: var(--color-gold);
    }

    .footer-tagline {
      font-size: 0.75rem;
      color: rgba(255,255,255,0.35);
      letter-spacing: 0.2em;
      text-transform: uppercase;
      margin-top: 0.3rem;
    }

    .footer-links {
      display: flex;
      gap: 2rem;
      list-style: none;
    }

    .footer-links a {
      font-size: 0.8rem;
      color: rgba(255,255,255,0.45);
      transition: color 0.2s;
    }

    .footer-links a:hover {
      color: var(--color-gold);
    }

    .footer-copy {
      font-size: 0.75rem;
      color: rgba(255,255,255,0.25);
    }

    /* ─────────────────────────────────────
       ANIMATIONS
    ───────────────────────────────────── */

    /* Fade up: used for hero text entrance */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(25px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    /* Simple fade in */
    @keyframes fadeIn {
      from { opacity: 0; }
      to   { opacity: 1; }
    }

    /* Scrolling text marquee */
    @keyframes marquee {
      from { transform: translateX(0); }
      to   { transform: translateX(-50%); }
    }

    /* Scroll reveal: elements start invisible, JS adds .visible */
    .reveal {
      opacity: 0;
      transform: translateY(30px);
      transition: opacity 0.8s ease, transform 0.8s ease;
    }

    .reveal.visible {
      opacity: 1;
      transform: translateY(0);
    }

    /* Stagger delays for reveal groups */
    .reveal-delay-1 { transition-delay: 0.1s; }
    .reveal-delay-2 { transition-delay: 0.2s; }
    .reveal-delay-3 { transition-delay: 0.3s; }

    /* ─────────────────────────────────────
       RESPONSIVE — Mobile adjustments
    ───────────────────────────────────── */
    @media (max-width: 900px) {
      .hero-inner {
        grid-template-columns: 1fr;
        text-align: center;
        gap: 3rem;
        padding: 4rem 0 3rem;
      }

      .hero-sub { margin: 0 auto 2rem; }
      .hero-buttons { justify-content: center; }
      .hero-badge { left: 50%; transform: translateX(-50%); }

      .features-grid {
        grid-template-columns: 1fr;
        gap: 1.5rem;
      }

      .collections-grid {
        grid-template-columns: 1fr;
      }

      .collection-card.big { grid-row: auto; }

      .testimonials-grid {
        grid-template-columns: 1fr;
        gap: 1.5rem;
      }

      .showcase-grid {
        grid-template-columns: repeat(2, 1fr);
      }

      .footer-inner {
        flex-direction: column;
        text-align: center;
      }

      .footer-links { justify-content: center; }
    }

    @media (max-width: 500px) {
      .showcase-grid { grid-template-columns: 1fr; }
      .cta-info { gap: 1.5rem; }
    }

  </style>
</head>
<body>

  <!-- ================================================
       NAVIGATION BAR
       Edit: logo name, links, button text
  ================================================ -->
  <nav class="navbar" id="navbar">
    <div class="container">
      <div class="navbar-inner">

        <!-- Logo — change "Zen" and "optic" to your brand name -->
        <a href="#" class="navbar-logo">
          👁 Zen<span>optic</span>
        </a>

        <!-- Navigation links — add or remove <li> items -->
        <ul class="navbar-links">
          <li><a href="#collections">Collections</a></li>
          <li><a href="#services">Services</a></li>
          <li><a href="#testimonials">Avis</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>

        <!-- CTA button in nav -->
        <a href="#contact" class="btn-primary">Prendre RDV</a>

      </div>
    </div>
  </nav>


  <!-- ================================================
       HERO SECTION
       Edit: headline, subheadline, button text, image
  ================================================ -->
  <section class="hero" id="accueil">

    <div class="hero-inner">

      <!-- LEFT: Text content -->
      <div class="hero-text">

        <!-- Small label above headline -->
        <p class="hero-eyebrow">Opticien Premium · Tanger, Maroc</p>

        <!-- MAIN HEADLINE — Edit this! -->
        <h1 class="hero-headline">
          Votre regard,<br>
          notre <em>œuvre.</em>
        </h1>

        <!-- SUBHEADLINE — Edit this! -->
        <p class="hero-sub">
          Chez Zenoptic, chaque monture est choisie pour révéler votre personnalité.
          Bilan visuel, conseil sur-mesure et collections premium — tout pour sublimer votre vision.
        </p>

        <!-- CTA BUTTONS — Edit button text -->
        <div class="hero-buttons">
          <a href="#contact" class="btn-primary">Réserver un RDV gratuit</a>
          <a href="#collections" class="btn-outline">Voir les collections</a>
        </div>

      </div>

      <!-- RIGHT: Glasses image -->
      <div class="hero-image">
        <img
          src="https://images.unsplash.com/photo-1574258495973-f010dfbb5371?w=700&q=80"
          alt="Lunettes premium Zenoptic"
        />
        <!-- Floating badge on image -->
        <div class="hero-badge">+ de 500 modèles en boutique</div>
      </div>

    </div>

    <!-- Scrolling slogan strip at bottom of hero -->
    <div class="hero-slogan">
      <div class="hero-slogan-track">
        <span>Voir</span>
        <span>·</span>
        <span>Comprendre</span>
        <span>·</span>
        <span>Sublimer</span>
        <span>·</span>
        <span>Zenoptic</span>
        <span>·</span>
        <span>Voir</span>
        <span>·</span>
        <span>Comprendre</span>
        <span>·</span>
        <span>Sublimer</span>
        <span>·</span>
        <span>Zenoptic</span>
        <span>·</span>
        <span>Voir</span>
        <span>·</span>
        <span>Comprendre</span>
        <span>·</span>
        <span>Sublimer</span>
        <span>·</span>
        <span>Zenoptic</span>
        <span>·</span>
        <span>Voir</span>
        <span>·</span>
        <span>Comprendre</span>
        <span>·</span>
        <span>Sublimer</span>
        <span>·</span>
        <span>Zenoptic</span>
        <span>·</span>
      </div>
    </div>

  </section>


  <!-- ================================================
       GLASSES SHOWCASE — 4 product images
       Edit: image URLs and labels
  ================================================ -->
  <section class="showcase" id="vitrine">
    <div class="container">
      <div class="showcase-grid">

        <div class="showcase-item reveal">
          <img src="https://images.unsplash.com/photo-1508296695146-257a814070b4?w=400&q=75" alt="Montures solaires" />
          <div class="showcase-item-label">Solaires</div>
        </div>

        <div class="showcase-item reveal reveal-delay-1">
          <img src="https://images.unsplash.com/photo-1556306535-38febf6782e7?w=400&q=75" alt="Montures optiques" />
          <div class="showcase-item-label">Optiques</div>
        </div>

        <div class="showcase-item reveal reveal-delay-2">
          <img src="https://images.unsplash.com/photo-1473496169904-658ba7574b0d?w=400&q=75" alt="Montures luxe" />
          <div class="showcase-item-label">Luxe</div>
        </div>

        <div class="showcase-item reveal reveal-delay-3">
          <img src="https://images.unsplash.com/photo-1577803645773-f96470509666?w=400&q=75" alt="Montures sport" />
          <div class="showcase-item-label">Sport</div>
        </div>

      </div>
    </div>
  </section>


  <!-- ================================================
       FEATURES SECTION — 3 key benefits
       Edit: icon (emoji), title, text for each card
  ================================================ -->
  <section class="features" id="services">
    <div class="container">

      <!-- Section heading -->
      <div class="features-header">
        <span class="section-label">Pourquoi Zenoptic</span>
        <div class="divider"></div>
        <h2 class="section-title reveal">
          Trois raisons de nous<br><em>faire confiance</em>
        </h2>
        <p class="section-subtitle reveal">
          Nous combinons expertise médicale, soin personnalisé et style pour une expérience optique unique à Tanger.
        </p>
      </div>

      <!-- 3 benefit cards -->
      <div class="features-grid">

        <!-- BENEFIT 1 — Edit icon, title, text -->
        <div class="feature-card reveal">
          <div class="feature-icon">👁</div>
          <h3 class="feature-title">Bilan visuel précis</h3>
          <p class="feature-text">
            Nos opticiens certifiés utilisent des équipements de dernière génération pour un diagnostic complet et fiable. Résultats détaillés, explications claires — vous repartez avec une ordonnance parfaite.
          </p>
        </div>

        <!-- BENEFIT 2 — Edit icon, title, text -->
        <div class="feature-card reveal reveal-delay-1">
          <div class="feature-icon">✨</div>
          <h3 class="feature-title">Conseil sur-mesure</h3>
          <p class="feature-text">
            Chaque visage est unique. Notre équipe vous guide dans le choix de la monture idéale selon votre morphologie, votre style de vie et votre personnalité. Pas de vente forcée — juste le bon choix pour vous.
          </p>
        </div>

        <!-- BENEFIT 3 — Edit icon, title, text -->
        <div class="feature-card reveal reveal-delay-2">
          <div class="feature-icon">💎</div>
          <h3 class="feature-title">Collections premium</h3>
          <p class="feature-text">
            Plus de 500 montures sélectionnées pour leur qualité, leur durabilité et leur style. Des grandes marques aux créateurs indépendants — il y en a pour tous les goûts et tous les budgets.
          </p>
        </div>

      </div>
    </div>
  </section>


  <!-- ================================================
       COLLECTIONS SECTION — featured glasses images
       Edit: image URLs, collection names, tags
  ================================================ -->
  <section class="collections" id="collections">
    <div class="container">

      <!-- Section heading -->
      <div class="collections-header reveal">
        <span class="section-label">Nos collections</span>
        <div class="divider"></div>
        <h2 class="section-title">Trouvez votre <em>signature.</em></h2>
        <p class="section-subtitle">Des lunettes qui ne corrigent pas seulement — elles transforment votre regard.</p>
      </div>

      <!-- Grid: 1 big + 2 smaller -->
      <div class="collections-grid">

        <!-- Big featured card -->
        <div class="collection-card big reveal">
          <img
            src="https://images.unsplash.com/photo-1509695507497-903c140c43b0?w=600&q=80"
            alt="Collection Signature Zenoptic"
          />
          <div class="collection-overlay">
            <div class="collection-name">Collection Signature</div>
            <div class="collection-tag">Acétate · Luxe · Exclusif</div>
          </div>
        </div>

        <!-- Smaller card 1 -->
        <div class="collection-card reveal reveal-delay-1">
          <img
            src="https://images.unsplash.com/photo-1572635196237-14b3f281503f?w=500&q=75"
            alt="Collection Solaires"
          />
          <div class="collection-overlay">
            <div class="collection-name">Solaires</div>
            <div class="collection-tag">Été · Protection UV 400</div>
          </div>
        </div>

        <!-- Smaller card 2 -->
        <div class="collection-card reveal reveal-delay-2">
          <img
            src="https://images.unsplash.com/photo-1529339017-3655d28ac283?w=500&q=75"
            alt="Collection Sport"
          />
          <div class="collection-overlay">
            <div class="collection-name">Lifestyle</div>
            <div class="collection-tag">Quotidien · Légèreté · Confort</div>
          </div>
        </div>

      </div>
    </div>
  </section>


  <!-- ================================================
       TESTIMONIALS — 3 social proof blocks
       Edit: stars, text, name, location for each
  ================================================ -->
  <section class="testimonials" id="testimonials">
    <div class="container">

      <!-- Section heading -->
      <div class="testimonials-header">
        <span class="section-label">Avis clients</span>
        <div class="divider"></div>
        <h2 class="section-title reveal">
          Ils nous font <em>confiance</em>
        </h2>
        <p class="section-subtitle reveal" style="margin:0 auto; text-align:center;">
          Plus de 1 200 clients satisfaits à Tanger et dans la région.
        </p>
      </div>

      <!-- 3 testimonial cards -->
      <div class="testimonials-grid">

        <!-- REVIEW 1 — Edit stars, text, name, location -->
        <div class="testimonial-card reveal">
          <div class="testimonial-quote-mark">"</div>

          <!-- Stars: add or remove .star spans -->
          <div class="testimonial-stars">
            <span class="star">★</span>
            <span class="star">★</span>
            <span class="star">★</span>
            <span class="star">★</span>
            <span class="star">★</span>
          </div>

          <!-- Review text -->
          <p class="testimonial-text">
            "Une expérience extraordinaire. L'équipe Zenoptic a su comprendre exactement ce que je cherchais. Ma nouvelle monture est une vraie révélation — tout le monde me demande où je l'ai trouvée !"
          </p>

          <!-- Author -->
          <div class="testimonial-author">
            <div class="testimonial-avatar">YB</div>
            <div>
              <div class="testimonial-name">Yasmine B.</div>
              <div class="testimonial-location">Tanger, Maroc</div>
            </div>
          </div>
        </div>

        <!-- REVIEW 2 -->
        <div class="testimonial-card reveal reveal-delay-1">
          <div class="testimonial-quote-mark">"</div>
          <div class="testimonial-stars">
            <span class="star">★</span>
            <span class="star">★</span>
            <span class="star">★</span>
            <span class="star">★</span>
            <span class="star">★</span>
          </div>
          <p class="testimonial-text">
            "Jamais je n'aurais pensé qu'un opticien pouvait autant changer mon quotidien. Le conseil était précis, humain, sans pression. Les verres sont parfaits et la monture me va à merveille."
          </p>
          <div class="testimonial-author">
            <div class="testimonial-avatar">KA</div>
            <div>
              <div class="testimonial-name">Karim A.</div>
              <div class="testimonial-location">Tétouan, Maroc</div>
            </div>
          </div>
        </div>

        <!-- REVIEW 3 -->
        <div class="testimonial-card reveal reveal-delay-2">
          <div class="testimonial-quote-mark">"</div>
          <div class="testimonial-stars">
            <span class="star">★</span>
            <span class="star">★</span>
            <span class="star">★</span>
            <span class="star">★</span>
            <span class="star">★</span>
          </div>
          <p class="testimonial-text">
            "Le cadre est élégant, le service impeccable. Je me suis sentie vraiment prise en charge, pas juste cliente. Zenoptic, c'est une autre vision de l'optique — je ne retournerai nulle part ailleurs."
          </p>
          <div class="testimonial-author">
            <div class="testimonial-avatar">NM</div>
            <div>
              <div class="testimonial-name">Nadia M.</div>
              <div class="testimonial-location">Tanger, Maroc</div>
            </div>
          </div>
        </div>

      </div>
    </div>
  </section>


  <!-- ================================================
       CONTACT CTA — Final call to action
       Edit: title, subtitle, info items, button text
  ================================================ -->
  <section class="cta-section" id="contact">
    <div class="container">
      <div class="cta-inner">

        <span class="cta-label">Prendre rendez-vous</span>

        <!-- Edit this headline -->
        <h2 class="cta-title reveal">
          Prêt à voir<br><em>autrement ?</em>
        </h2>

        <!-- Edit this subtext -->
        <p class="cta-sub reveal">
          Réservez votre bilan visuel gratuit dès aujourd'hui. Notre équipe vous accueille du lundi au samedi, de 9h à 19h30.
        </p>

        <!-- CTA buttons — edit text and links -->
        <div class="hero-buttons" style="justify-content: center;" >
          <a href="tel:+212600000000" class="btn-primary reveal">📞 Appeler maintenant</a>
          <a href="https://wa.me/212600000000" class="btn-outline reveal reveal-delay-1">💬 WhatsApp</a>
        </div>

        <!-- Info blocks: address, hours, phone -->
        <div class="cta-info">

          <div class="cta-info-item reveal">
            <div class="cta-info-icon">📍</div>
            <div class="cta-info-label">Adresse</div>
            <!-- Edit your address -->
            <div class="cta-info-value">Boulevard Mohammed V, Tanger</div>
          </div>

          <div class="cta-info-item reveal reveal-delay-1">
            <div class="cta-info-icon">🕘</div>
            <div class="cta-info-label">Horaires</div>
            <!-- Edit your hours -->
            <div class="cta-info-value">Lun – Sam · 9h00 – 19h30</div>
          </div>

          <div class="cta-info-item reveal reveal-delay-2">
            <div class="cta-info-icon">📱</div>
            <div class="cta-info-label">Téléphone</div>
            <!-- Edit your phone number -->
            <div class="cta-info-value">+212 6XX XXX XXX</div>
          </div>

          <div class="cta-info-item reveal reveal-delay-3">
            <div class="cta-info-icon">✉️</div>
            <div class="cta-info-label">Email</div>
            <!-- Edit your email -->
            <div class="cta-info-value">contact@zenoptic.ma</div>
          </div>

        </div>
      </div>
    </div>
  </section>


  <!-- ================================================
       FOOTER
       Edit: links, copyright text
  ================================================ -->
  <footer class="footer">
    <div class="container">
      <div class="footer-inner">

        <div>
          <div class="footer-logo">👁 Zen<span>optic</span></div>
          <div class="footer-tagline">Voir · Comprendre · Sublimer</div>
        </div>

        <ul class="footer-links">
          <li><a href="#collections">Collections</a></li>
          <li><a href="#services">Services</a></li>
          <li><a href="#testimonials">Avis</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>

        <!-- Edit year and name -->
        <p class="footer-copy">© 2025 Zenoptic · Tanger, Maroc</p>

      </div>
    </div>
  </footer>


  <!-- ================================================
       JAVASCRIPT — Scroll effects
       No need to edit this section
  ================================================ -->
  <script>

    // ── Navbar: add shadow when page is scrolled
    window.addEventListener('scroll', function () {
      var navbar = document.getElementById('navbar');
      if (window.scrollY > 60) {
        navbar.classList.add('scrolled');
      } else {
        navbar.classList.remove('scrolled');
      }
    });

    // ── Scroll reveal: make elements visible when they enter the viewport
    var revealElements = document.querySelectorAll('.reveal');

    var revealObserver = new IntersectionObserver(function (entries) {
      entries.forEach(function (entry) {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
        }
      });
    }, {
      threshold: 0.12  // element is 12% visible before animating
    });

    revealElements.forEach(function (el) {
      revealObserver.observe(el);
    });

  </script>

</body>
</html># zenoptic
