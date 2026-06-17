# cravio-cafe-
I built modern and responsive website designed for Carvio Cafe, featuring an elegant user interface, smooth navigation, and a visually appealing layout that highlights the cafe's brand and atmosphere.
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Cravio – The Real Crave | Premium Café in Rawalpindi</title>
<meta name="description" content="Cravio is Rawalpindi's most-loved premium café. Signature cold coffees, decadent waffles, artisan drinks & an aesthetic vibe you'll want to share. Located inside Ranchers, Tamiz-ud-Din Road. Rated 4.8/5.">
<meta name="keywords" content="café Rawalpindi, best coffee Rawalpindi, Cravio café, cold coffee Rawalpindi, waffles Rawalpindi, aesthetic café Pakistan, coffee shop near me, Ranchers Rawalpindi">
<meta property="og:title" content="Cravio – The Real Crave">
<meta property="og:description" content="Rawalpindi's premium café experience. Cold coffees, signature waffles & good vibes.">
<meta property="og:type" content="website">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=DM+Sans:wght@300;400;500;600&family=DM+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --espresso:   #1A0F08;
    --roast:      #2C1A0E;
    --mahogany:   #4A2B1A;
    --copper:     #B5622A;
    --amber:      #D4883C;
    --cream:      #F5EDD8;
    --latte:      #E8D5B0;
    --smoke:      #9A8A78;
    --white:      #FFFDF8;
    --gold:       #C9963A;
    --gold-light: #E8B95A;
    --red-accent: #8B2020;

    --font-display: 'Playfair Display', Georgia, serif;
    --font-body: 'DM Sans', system-ui, sans-serif;
    --font-mono: 'DM Mono', monospace;

    --section-pad: clamp(4rem, 8vw, 8rem) clamp(1.25rem, 6vw, 7rem);
    --radius: 4px;
    --radius-lg: 10px;
    --transition: 0.3s ease;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--espresso);
    color: var(--cream);
    font-family: var(--font-body);
    font-size: 16px;
    line-height: 1.7;
    overflow-x: hidden;
  }

  /* ── NAV ─────────────────────────────────────────── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 1.25rem clamp(1.25rem, 6vw, 7rem);
    background: rgba(26, 15, 8, 0.92);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(181,98,42,0.15);
    transition: background var(--transition);
  }
  .nav-logo {
    display: flex; flex-direction: column; gap: 0;
    text-decoration: none;
  }
  .nav-logo .wordmark {
    font-family: var(--font-display);
    font-size: 1.6rem; font-weight: 700;
    color: var(--gold-light);
    letter-spacing: 0.05em;
    line-height: 1;
  }
  .nav-logo .tagline {
    font-family: var(--font-mono);
    font-size: 0.6rem; letter-spacing: 0.25em;
    color: var(--copper); text-transform: uppercase;
  }
  .nav-links {
    display: flex; gap: 2.5rem; list-style: none;
    align-items: center;
  }
  .nav-links a {
    color: var(--latte); text-decoration: none;
    font-size: 0.85rem; font-weight: 500; letter-spacing: 0.05em;
    transition: color var(--transition);
  }
  .nav-links a:hover { color: var(--gold-light); }
  .nav-cta {
    background: var(--copper);
    color: var(--white) !important;
    padding: 0.5rem 1.25rem;
    border-radius: var(--radius);
    transition: background var(--transition) !important;
  }
  .nav-cta:hover { background: var(--amber) !important; }
  .nav-toggle {
    display: none; background: none; border: none;
    cursor: pointer; padding: 0.25rem;
    flex-direction: column; gap: 5px;
  }
  .nav-toggle span {
    display: block; width: 24px; height: 2px;
    background: var(--cream); transition: var(--transition);
  }

  /* ── HERO ─────────────────────────────────────────── */
  #home {
    min-height: 100vh;
    display: grid; place-items: center;
    position: relative; overflow: hidden;
    padding: 7rem clamp(1.25rem, 6vw, 7rem) 5rem;
  }
  .hero-bg {
    position: absolute; inset: 0;
    background:
      radial-gradient(ellipse 80% 60% at 60% 40%, rgba(74,43,26,0.6) 0%, transparent 70%),
      radial-gradient(ellipse 60% 80% at 20% 70%, rgba(181,98,42,0.15) 0%, transparent 60%),
      linear-gradient(160deg, #2C1A0E 0%, #1A0F08 50%, #0D0804 100%);
    z-index: 0;
  }
  .hero-grain {
    position: absolute; inset: 0; z-index: 1; opacity: 0.035;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
    background-size: 200px;
  }
  .hero-deco {
    position: absolute; z-index: 1;
    border-radius: 50%; filter: blur(60px); opacity: 0.12;
  }
  .hero-deco.a { width: 500px; height: 500px; background: var(--copper); top: -10%; right: -5%; }
  .hero-deco.b { width: 300px; height: 300px; background: var(--gold); bottom: 10%; left: 5%; }
  .hero-content {
    position: relative; z-index: 2;
    max-width: 800px;
    animation: fadeUp 0.9s ease both;
  }
  .hero-badge {
    display: inline-flex; align-items: center; gap: 0.5rem;
    background: rgba(181,98,42,0.2); border: 1px solid rgba(181,98,42,0.4);
    padding: 0.4rem 1rem; border-radius: 2rem;
    font-size: 0.75rem; letter-spacing: 0.15em; text-transform: uppercase;
    color: var(--amber); margin-bottom: 2rem;
  }
  .hero-badge::before {
    content: ''; width: 6px; height: 6px;
    background: var(--amber); border-radius: 50%;
    animation: pulse 2s ease infinite;
  }
  h1 {
    font-family: var(--font-display);
    font-size: clamp(3.2rem, 8vw, 6.5rem);
    line-height: 1.05; font-weight: 700;
    color: var(--white);
    margin-bottom: 1.5rem;
  }
  h1 em {
    font-style: italic; color: var(--gold-light);
    display: block;
  }
  .hero-sub {
    font-size: clamp(1rem, 2vw, 1.2rem);
    color: var(--smoke); max-width: 520px;
    margin-bottom: 2.5rem; font-weight: 300;
  }
  .hero-actions {
    display: flex; gap: 1rem; flex-wrap: wrap;
    align-items: center;
  }
  .btn-primary {
    display: inline-flex; align-items: center; gap: 0.5rem;
    background: var(--copper); color: var(--white);
    padding: 0.85rem 2rem; border-radius: var(--radius);
    font-weight: 600; font-size: 0.9rem; letter-spacing: 0.03em;
    text-decoration: none; border: none; cursor: pointer;
    transition: background var(--transition), transform var(--transition);
  }
  .btn-primary:hover { background: var(--amber); transform: translateY(-2px); }
  .btn-ghost {
    display: inline-flex; align-items: center; gap: 0.5rem;
    background: transparent; color: var(--cream);
    padding: 0.85rem 2rem; border-radius: var(--radius);
    font-weight: 500; font-size: 0.9rem;
    text-decoration: none; border: 1px solid rgba(245,237,216,0.25);
    cursor: pointer; transition: border-color var(--transition), color var(--transition);
  }
  .btn-ghost:hover { border-color: var(--gold-light); color: var(--gold-light); }
  .hero-stats {
    display: flex; gap: 3rem; margin-top: 4rem;
    padding-top: 2.5rem; border-top: 1px solid rgba(245,237,216,0.1);
    flex-wrap: wrap;
  }
  .hero-stat .num {
    font-family: var(--font-display);
    font-size: 2rem; font-weight: 700; color: var(--gold-light);
    line-height: 1;
  }
  .hero-stat .label {
    font-size: 0.75rem; color: var(--smoke);
    letter-spacing: 0.08em; text-transform: uppercase;
    margin-top: 0.25rem;
  }
  .hero-scroll {
    position: absolute; bottom: 2rem; left: 50%;
    transform: translateX(-50%); z-index: 2;
    display: flex; flex-direction: column; align-items: center; gap: 0.5rem;
  }
  .hero-scroll span {
    font-size: 0.65rem; letter-spacing: 0.2em; text-transform: uppercase;
    color: var(--smoke);
  }
  .scroll-line {
    width: 1px; height: 40px;
    background: linear-gradient(to bottom, var(--copper), transparent);
    animation: scrollDown 1.5s ease infinite;
  }

  /* ── SECTIONS ─────────────────────────────────────── */
  section { padding: var(--section-pad); }

  .section-label {
    font-family: var(--font-mono);
    font-size: 0.7rem; letter-spacing: 0.25em; text-transform: uppercase;
    color: var(--copper); margin-bottom: 1rem;
  }
  h2 {
    font-family: var(--font-display);
    font-size: clamp(2rem, 4vw, 3.2rem);
    font-weight: 700; line-height: 1.15;
    color: var(--white);
  }
  h2 em { font-style: italic; color: var(--gold-light); }
  .section-intro {
    font-size: 1.05rem; color: var(--smoke);
    max-width: 560px; margin-top: 1rem;
    font-weight: 300;
  }
  .section-header { margin-bottom: 4rem; }

  /* divider */
  .divider {
    width: 48px; height: 2px;
    background: linear-gradient(to right, var(--copper), transparent);
    margin: 1.5rem 0;
  }

  /* ── ABOUT ─────────────────────────────────────────── */
  #about { background: var(--roast); }
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 5rem; align-items: center;
  }
  .about-visual {
    position: relative;
  }
  .about-img-frame {
    width: 100%; aspect-ratio: 4/5;
    background: linear-gradient(135deg, var(--mahogany) 0%, var(--espresso) 100%);
    border-radius: var(--radius-lg);
    overflow: hidden; position: relative;
    border: 1px solid rgba(181,98,42,0.2);
  }
  .about-img-inner {
    position: absolute; inset: 20px;
    display: flex; align-items: center; justify-content: center;
    flex-direction: column; gap: 1rem;
  }
  .coffee-ring {
    width: 120px; height: 120px;
    border: 3px solid rgba(181,98,42,0.4);
    border-radius: 50%; position: relative;
    display: flex; align-items: center; justify-content: center;
  }
  .coffee-ring::after {
    content: '';
    position: absolute; inset: 10px;
    border: 1px solid rgba(201,150,58,0.3);
    border-radius: 50%;
  }
  .coffee-ring-icon {
    font-size: 2.5rem;
  }
  .about-badge-float {
    position: absolute; bottom: -1rem; right: -1rem;
    background: var(--copper);
    padding: 1.25rem 1.5rem;
    border-radius: var(--radius-lg);
    text-align: center;
    box-shadow: 0 20px 40px rgba(0,0,0,0.4);
  }
  .about-badge-float .num {
    font-family: var(--font-display);
    font-size: 2.2rem; font-weight: 700;
    color: var(--white); line-height: 1;
  }
  .about-badge-float .label {
    font-size: 0.7rem; color: rgba(255,255,255,0.8);
    letter-spacing: 0.1em; text-transform: uppercase;
  }
  .about-text h2 { margin-bottom: 1.5rem; }
  .about-text p { color: var(--smoke); margin-bottom: 1.25rem; font-weight: 300; }
  .about-pillars {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 1rem; margin-top: 2.5rem;
  }
  .pillar {
    background: rgba(26,15,8,0.5);
    border: 1px solid rgba(181,98,42,0.15);
    padding: 1.25rem; border-radius: var(--radius-lg);
  }
  .pillar-icon { font-size: 1.4rem; margin-bottom: 0.5rem; }
  .pillar h4 {
    font-family: var(--font-display); font-size: 1rem;
    color: var(--gold-light); margin-bottom: 0.35rem;
  }
  .pillar p { font-size: 0.82rem; color: var(--smoke); margin: 0; }

  /* ── FEATURED DRINKS ──────────────────────────────── */
  #drinks { background: var(--espresso); }
  .drinks-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 1.5rem;
  }
  .drink-card {
    background: var(--roast);
    border: 1px solid rgba(181,98,42,0.15);
    border-radius: var(--radius-lg);
    padding: 1.75rem;
    transition: border-color var(--transition), transform var(--transition);
    cursor: pointer; position: relative; overflow: hidden;
  }
  .drink-card::before {
    content: '';
    position: absolute; top: 0; left: 0; right: 0; height: 3px;
    background: linear-gradient(to right, var(--copper), var(--gold-light));
    opacity: 0; transition: opacity var(--transition);
  }
  .drink-card:hover { border-color: rgba(181,98,42,0.4); transform: translateY(-4px); }
  .drink-card:hover::before { opacity: 1; }
  .drink-emoji { font-size: 2rem; margin-bottom: 1rem; }
  .drink-card h3 {
    font-family: var(--font-display);
    font-size: 1.15rem; color: var(--white);
    margin-bottom: 0.4rem;
  }
  .drink-card p { font-size: 0.82rem; color: var(--smoke); margin-bottom: 1.25rem; }
  .drink-price {
    font-family: var(--font-mono);
    font-size: 0.95rem; color: var(--amber);
    display: flex; align-items: center; gap: 0.4rem;
  }
  .drink-star { color: var(--gold); font-size: 0.7rem; }
  .bestseller-tag {
    position: absolute; top: 1rem; right: 1rem;
    background: rgba(181,98,42,0.2); border: 1px solid rgba(181,98,42,0.3);
    padding: 0.2rem 0.6rem; border-radius: 2rem;
    font-size: 0.6rem; letter-spacing: 0.1em; text-transform: uppercase;
    color: var(--amber);
  }

  /* ── WAFFLES SECTION ──────────────────────────────── */
  #waffles { background: var(--mahogany); }
  .waffles-hero {
    display: grid; grid-template-columns: 1.2fr 1fr;
    gap: 5rem; align-items: center;
    margin-bottom: 4rem;
  }
  .waffles-text h2 { margin-bottom: 1.5rem; }
  .waffles-text p { color: var(--smoke); margin-bottom: 1.5rem; }
  .waffle-sizes {
    display: flex; gap: 0.75rem; margin-top: 1.5rem;
  }
  .waffle-size {
    flex: 1; text-align: center;
    background: rgba(26,15,8,0.4);
    border: 1px solid rgba(181,98,42,0.2);
    padding: 0.75rem; border-radius: var(--radius);
  }
  .waffle-size .size-label {
    font-size: 0.65rem; letter-spacing: 0.15em;
    text-transform: uppercase; color: var(--smoke);
  }
  .waffle-size .size-price {
    font-family: var(--font-display);
    font-size: 1.1rem; color: var(--gold-light);
    font-weight: 700;
  }
  .waffles-visual {
    background: linear-gradient(135deg, rgba(181,98,42,0.1), rgba(26,15,8,0.6));
    border: 1px solid rgba(181,98,42,0.2);
    border-radius: var(--radius-lg);
    padding: 2.5rem;
    display: flex; align-items: center; justify-content: center;
    flex-direction: column; gap: 1rem;
    aspect-ratio: 1/1;
  }
  .waffle-art { font-size: 5rem; }
  .waffle-art-caption {
    font-family: var(--font-display);
    font-style: italic; font-size: 1.2rem;
    color: var(--gold-light); text-align: center;
  }
  .waffle-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 1rem;
  }
  .waffle-item {
    background: rgba(26,15,8,0.5);
    border: 1px solid rgba(181,98,42,0.12);
    border-radius: var(--radius);
    padding: 1.25rem;
    transition: border-color var(--transition);
  }
  .waffle-item:hover { border-color: rgba(181,98,42,0.35); }
  .waffle-item h4 {
    font-family: var(--font-display);
    font-size: 1rem; color: var(--white);
    margin-bottom: 0.3rem;
  }
  .waffle-item .ingredients {
    font-size: 0.76rem; color: var(--smoke);
    line-height: 1.5; margin-bottom: 0.75rem;
  }
  .waffle-item .price {
    font-family: var(--font-mono);
    font-size: 0.82rem; color: var(--amber);
  }

  /* ── FULL MENU ─────────────────────────────────────── */
  #menu { background: var(--espresso); }
  .menu-tabs {
    display: flex; gap: 0.5rem; flex-wrap: wrap; margin-bottom: 3rem;
  }
  .menu-tab {
    padding: 0.5rem 1.25rem; border-radius: 2rem;
    font-size: 0.8rem; font-weight: 500;
    border: 1px solid rgba(181,98,42,0.3);
    background: transparent; color: var(--smoke);
    cursor: pointer; transition: all var(--transition);
  }
  .menu-tab.active, .menu-tab:hover {
    background: var(--copper); color: var(--white); border-color: var(--copper);
  }
  .menu-panel { display: none; }
  .menu-panel.active { display: block; }
  .menu-list {
    display: grid; gap: 0.75rem;
  }
  .menu-item {
    display: flex; align-items: center; justify-content: space-between;
    padding: 1rem 1.25rem;
    background: var(--roast); border: 1px solid rgba(181,98,42,0.1);
    border-radius: var(--radius);
    transition: border-color var(--transition);
  }
  .menu-item:hover { border-color: rgba(181,98,42,0.3); }
  .menu-item-info { flex: 1; }
  .menu-item-name {
    font-size: 0.95rem; color: var(--cream); font-weight: 500;
    display: flex; align-items: center; gap: 0.5rem;
  }
  .menu-star { color: var(--gold); font-size: 0.8rem; }
  .menu-item-desc { font-size: 0.78rem; color: var(--smoke); margin-top: 0.2rem; }
  .menu-item-price {
    font-family: var(--font-mono);
    font-size: 0.9rem; color: var(--amber);
    white-space: nowrap; margin-left: 1rem;
  }

  /* ── WHY CRAVIO ────────────────────────────────────── */
  #why { background: var(--roast); }
  .why-grid {
    display: grid; grid-template-columns: repeat(3, 1fr);
    gap: 2rem;
  }
  .why-card {
    text-align: center; padding: 2.5rem 1.5rem;
    border: 1px solid rgba(181,98,42,0.12);
    border-radius: var(--radius-lg);
    background: rgba(26,15,8,0.4);
    transition: border-color var(--transition), transform var(--transition);
  }
  .why-card:hover { border-color: rgba(181,98,42,0.4); transform: translateY(-4px); }
  .why-icon { font-size: 2.5rem; margin-bottom: 1.25rem; }
  .why-card h3 {
    font-family: var(--font-display); font-size: 1.2rem;
    color: var(--white); margin-bottom: 0.75rem;
  }
  .why-card p { font-size: 0.85rem; color: var(--smoke); }

  /* ── REVIEWS ───────────────────────────────────────── */
  #reviews { background: var(--espresso); }
  .rating-hero {
    display: flex; align-items: center; gap: 3rem;
    margin-bottom: 4rem; flex-wrap: wrap;
  }
  .rating-big {
    text-align: center;
  }
  .rating-num {
    font-family: var(--font-display);
    font-size: 5rem; font-weight: 700;
    color: var(--gold-light); line-height: 1;
  }
  .stars-row { color: var(--gold); font-size: 1.5rem; letter-spacing: 0.1em; margin: 0.5rem 0; }
  .rating-count { font-size: 0.8rem; color: var(--smoke); }
  .rating-bars { flex: 1; min-width: 240px; }
  .rating-bar-row {
    display: flex; align-items: center; gap: 1rem; margin-bottom: 0.6rem;
  }
  .bar-label { font-size: 0.8rem; color: var(--smoke); width: 20px; }
  .bar-track {
    flex: 1; height: 6px; background: rgba(255,255,255,0.08);
    border-radius: 3px; overflow: hidden;
  }
  .bar-fill {
    height: 100%; background: var(--amber); border-radius: 3px;
    transition: width 1s ease;
  }
  .bar-count { font-size: 0.75rem; color: var(--smoke); width: 20px; text-align: right; }
  .reviews-grid {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.5rem;
  }
  .review-card {
    background: var(--roast); border: 1px solid rgba(181,98,42,0.15);
    border-radius: var(--radius-lg); padding: 1.75rem;
    transition: border-color var(--transition);
  }
  .review-card:hover { border-color: rgba(181,98,42,0.35); }
  .review-stars { color: var(--gold); font-size: 0.9rem; margin-bottom: 1rem; }
  .review-text {
    font-size: 0.9rem; color: var(--cream); font-style: italic;
    line-height: 1.7; margin-bottom: 1.25rem;
  }
  .review-text::before { content: '\201C'; color: var(--copper); font-size: 1.4rem; line-height: 0; vertical-align: -0.4rem; margin-right: 2px; }
  .review-text::after  { content: '\201D'; color: var(--copper); font-size: 1.4rem; line-height: 0; vertical-align: -0.4rem; margin-left: 2px; }
  .review-author {
    display: flex; align-items: center; gap: 0.75rem;
  }
  .author-avatar {
    width: 38px; height: 38px; border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-weight: 700; font-size: 0.9rem;
    color: var(--white);
  }
  .author-name { font-size: 0.85rem; color: var(--white); font-weight: 500; }
  .author-handle { font-size: 0.72rem; color: var(--smoke); }

  /* ── INSTAGRAM ─────────────────────────────────────── */
  #instagram { background: var(--mahogany); }
  .insta-header {
    display: flex; align-items: flex-end; justify-content: space-between;
    margin-bottom: 3rem; flex-wrap: wrap; gap: 1.5rem;
  }
  .i
