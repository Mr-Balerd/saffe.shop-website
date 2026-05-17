<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Saffe Shop — الکترونیک وارداتی پریمیوم</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;700;800&family=Vazirmatn:wght@300;400;500;700;800&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg:        #08111c;
    --bg-1:      #0d1a28;
    --bg-2:      #112235;
    --bg-3:      #1a3048;
    --bondi:     #0095b6;
    --bondi-lt:  #00b8d9;
    --bondi-glow:rgba(0,149,182,0.15);
    --ivory:     #f0e8d8;
    --ivory-dim: #c4b89a;
    --muted:     #5a7a8e;
    --white:     #f0e8d8;
    --font-display: 'Vazirmatn', sans-serif;
    --font-body:    'Vazirmatn', sans-serif;
    --font-latin:   'Syne', sans-serif;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--ivory);
    font-family: var(--font-body);
    font-weight: 300;
    line-height: 1.8;
    overflow-x: hidden;
    direction: rtl;
  }

  /* ── NAV ── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 1.1rem 3rem;
    border-bottom: 1px solid rgba(0,149,182,0.15);
    background: rgba(8,17,28,0.88);
    backdrop-filter: blur(14px);
  }

  .nav-logo {
    font-family: var(--font-latin);
    font-weight: 800;
    font-size: 1.45rem;
    letter-spacing: -0.02em;
    color: var(--ivory);
    text-decoration: none;
    display: flex; align-items: center; gap: 0.1em;
  }

  .nav-logo .logo-accent { color: var(--bondi); }
  .nav-logo .logo-dot {
    width: 7px; height: 7px; border-radius: 50%;
    background: var(--bondi);
    margin-right: 3px; margin-top: 2px;
    display: inline-block;
  }

  .nav-links { display: flex; gap: 2rem; list-style: none; }

  .nav-links a {
    color: var(--muted);
    text-decoration: none;
    font-size: 0.9rem;
    transition: color 0.2s;
  }

  .nav-links a:hover { color: var(--ivory); }

  .nav-cta {
    background: var(--bondi) !important;
    color: var(--bg) !important;
    padding: 0.5rem 1.3rem;
    border-radius: 100px;
    font-weight: 500 !important;
    transition: opacity 0.2s, transform 0.2s !important;
  }

  .nav-cta:hover { opacity: 0.88; transform: translateY(-1px); }

  /* ── HERO ── */
  .hero {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr 1fr;
    align-items: center;
    padding: 8rem 3rem 4rem;
    gap: 4rem;
    position: relative;
    overflow: hidden;
  }

  .hero::before {
    content: '';
    position: absolute;
    top: -180px; left: -180px;
    width: 650px; height: 650px;
    border-radius: 50%;
    background: radial-gradient(circle, var(--bondi-glow) 0%, transparent 68%);
    pointer-events: none;
  }

  .hero::after {
    content: '';
    position: absolute;
    bottom: -100px; right: 10%;
    width: 300px; height: 300px;
    border-radius: 50%;
    background: radial-gradient(circle, rgba(240,232,216,0.04) 0%, transparent 70%);
    pointer-events: none;
  }

  .hero-eyebrow {
    display: inline-flex; align-items: center; gap: 0.6rem;
    font-size: 0.78rem;
    color: var(--bondi-lt);
    margin-bottom: 1.5rem;
    letter-spacing: 0.04em;
  }

  .hero-eyebrow::after {
    content: '';
    display: block; width: 28px; height: 1px;
    background: var(--bondi);
  }

  .hero-title {
    font-family: var(--font-display);
    font-weight: 800;
    font-size: clamp(2.4rem, 5vw, 4.8rem);
    line-height: 1.18;
    margin-bottom: 1.5rem;
    color: var(--ivory);
  }

  .hero-title .highlight {
    color: var(--bondi-lt);
    position: relative;
  }

  .hero-desc {
    font-size: 1rem;
    color: var(--ivory-dim);
    max-width: 440px;
    margin-bottom: 2.5rem;
    line-height: 2;
  }

  .hero-actions { display: flex; gap: 1rem; align-items: center; flex-wrap: wrap; }

  .btn-primary {
    background: var(--bondi);
    color: var(--bg);
    padding: 0.9rem 2rem;
    border-radius: 100px;
    font-family: var(--font-body);
    font-weight: 500;
    font-size: 0.95rem;
    border: none; cursor: pointer;
    text-decoration: none;
    display: inline-block;
    transition: transform 0.2s, box-shadow 0.2s;
    box-shadow: 0 0 0 0 rgba(0,149,182,0);
  }

  .btn-primary:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 28px rgba(0,149,182,0.35);
  }

  .btn-ghost {
    color: var(--ivory-dim);
    font-size: 0.875rem;
    text-decoration: none;
    display: inline-flex; align-items: center; gap: 0.4rem;
    border-bottom: 1px solid rgba(240,232,216,0.2);
    padding-bottom: 2px;
    transition: color 0.2s, border-color 0.2s;
  }

  .btn-ghost:hover { color: var(--ivory); border-color: var(--ivory); }

  .hero-stats {
    display: flex; gap: 2.5rem; margin-top: 3rem;
    padding-top: 2rem;
    border-top: 1px solid var(--bg-3);
  }

  .stat-num {
    font-family: var(--font-latin);
    font-size: 2rem;
    font-weight: 800;
    color: var(--ivory);
    line-height: 1;
    margin-bottom: 0.25rem;
  }

  .stat-num span { color: var(--bondi-lt); }
  .stat-label { font-size: 0.82rem; color: var(--muted); }

  /* Hero visual */
  .hero-visual {
    display: flex; align-items: center; justify-content: center;
    position: relative;
    order: -1;
  }

  .hero-phone-frame {
    width: 275px; height: 535px;
    border-radius: 36px;
    border: 1.5px solid var(--bg-3);
    background: var(--bg-1);
    position: relative;
    overflow: hidden;
    box-shadow: 0 0 0 1px rgba(0,149,182,0.12), 0 40px 80px rgba(0,0,0,0.55);
  }

  .phone-screen {
    width: 100%; height: 100%;
    background: linear-gradient(160deg, var(--bg-2) 0%, var(--bg) 100%);
    display: flex; flex-direction: column; align-items: center;
    padding: 2rem 1rem;
    gap: 1rem;
    direction: rtl;
  }

  .phone-img-placeholder {
    width: 178px; height: 198px;
    background: var(--bg-3);
    border-radius: 18px;
    display: flex; align-items: center; justify-content: center;
    font-size: 5rem;
    border: 1px solid rgba(0,149,182,0.2);
  }

  .phone-product-name {
    font-size: 1rem; font-weight: 700;
    color: var(--ivory); text-align: center;
  }

  .phone-price { color: var(--bondi-lt); font-size: 0.875rem; font-weight: 500; }

  .phone-btn {
    width: 100%; background: var(--bondi); color: var(--bg);
    border: none; border-radius: 100px; padding: 0.65rem;
    font-weight: 500; cursor: pointer; font-size: 0.85rem;
    font-family: var(--font-body);
  }

  .badge-floating {
    position: absolute;
    background: var(--bg-2);
    border: 1px solid rgba(0,149,182,0.25);
    border-radius: 12px;
    padding: 0.6rem 0.9rem;
    font-size: 0.78rem;
    display: flex; align-items: center; gap: 0.4rem;
    white-space: nowrap;
    color: var(--ivory-dim);
  }

  .badge-floating .dot { width: 8px; height: 8px; border-radius: 50%; background: var(--bondi-lt); }
  .badge-top { top: 10%; left: -28%; }
  .badge-bot { bottom: 20%; right: -22%; }

  /* ── MARQUEE ── */
  .marquee-band {
    border-top: 1px solid var(--bg-3);
    border-bottom: 1px solid var(--bg-3);
    padding: 0.85rem 0;
    overflow: hidden;
    background: var(--bg-1);
  }

  .marquee-track {
    display: flex; gap: 3rem;
    width: max-content;
    animation: marquee 24s linear infinite;
  }

  .marquee-item {
    font-size: 0.8rem;
    color: var(--muted); display: flex; align-items: center; gap: 0.75rem;
    white-space: nowrap;
  }

  .marquee-item::before { content: '◆'; color: var(--bondi); font-size: 0.5rem; }

  @keyframes marquee { from { transform: translateX(0); } to { transform: translateX(-50%); } }

  /* ── SECTIONS ── */
  section { padding: 6rem 3rem; }

  .section-label {
    font-size: 0.75rem;
    color: var(--bondi-lt); margin-bottom: 0.75rem;
    letter-spacing: 0.06em;
  }

  .section-title {
    font-family: var(--font-display);
    font-size: clamp(1.8rem, 3.5vw, 2.8rem);
    font-weight: 800;
    line-height: 1.3;
    margin-bottom: 1rem;
    color: var(--ivory);
  }

  .section-sub {
    color: var(--ivory-dim); font-size: 1rem; max-width: 500px; line-height: 2;
  }

  /* ── PRODUCTS ── */
  .products-header {
    display: flex; justify-content: space-between; align-items: flex-end;
    margin-bottom: 3rem; flex-wrap: wrap; gap: 1rem;
  }

  .products-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 1.25rem;
  }

  .product-card {
    background: var(--bg-1);
    border: 1px solid var(--bg-3);
    border-radius: 20px;
    overflow: hidden;
    transition: transform 0.25s, border-color 0.25s, box-shadow 0.25s;
    cursor: pointer;
  }

  .product-card:hover {
    transform: translateY(-6px);
    border-color: rgba(0,149,182,0.4);
    box-shadow: 0 16px 40px rgba(0,0,0,0.3), 0 0 0 1px rgba(0,149,182,0.1);
  }

  .product-card:first-child {
    grid-row: span 2;
    background: linear-gradient(160deg, #091f2e 0%, var(--bg-1) 65%);
    border-color: rgba(0,149,182,0.2);
  }

  .product-img {
    height: 180px;
    display: flex; align-items: center; justify-content: center;
    font-size: 4rem;
    background: var(--bg-2);
  }

  .product-card:first-child .product-img { height: 260px; font-size: 5.5rem; }

  .product-info { padding: 1.25rem; }

  .product-origin { font-size: 0.75rem; color: var(--muted); margin-bottom: 0.35rem; }

  .product-name {
    font-weight: 700;
    font-size: 1rem;
    margin-bottom: 0.5rem; line-height: 1.4;
    color: var(--ivory);
  }

  .product-card:first-child .product-name { font-size: 1.2rem; }

  .product-footer {
    display: flex; justify-content: space-between; align-items: center;
    margin-top: 1rem;
  }

  .product-price { font-size: 1rem; font-weight: 500; color: var(--ivory); }
  .product-price .old {
    text-decoration: line-through; color: var(--muted);
    font-size: 0.8rem; margin-left: 0.4rem;
  }

  .add-btn {
    width: 36px; height: 36px; border-radius: 50%;
    background: var(--bondi); border: none; cursor: pointer;
    display: flex; align-items: center; justify-content: center;
    font-size: 1.2rem; color: var(--bg);
    transition: transform 0.15s, box-shadow 0.15s;
  }

  .add-btn:hover {
    transform: scale(1.12);
    box-shadow: 0 4px 16px rgba(0,149,182,0.45);
  }

  .product-badge {
    display: inline-block;
    background: rgba(0,149,182,0.12);
    color: var(--bondi-lt);
    border: 1px solid rgba(0,149,182,0.2);
    font-size: 0.72rem;
    padding: 0.22rem 0.65rem; border-radius: 100px;
    margin-bottom: 0.75rem;
  }

  /* ── WHY US ── */
  .why-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 1px;
    background: var(--bg-3);
    border: 1px solid var(--bg-3);
    border-radius: 20px;
    overflow: hidden;
    margin-top: 3.5rem;
  }

  .why-card {
    background: var(--bg);
    padding: 2.5rem 2rem;
    transition: background 0.25s;
  }

  .why-card:hover { background: var(--bg-1); }

  .why-icon {
    font-size: 1.8rem; margin-bottom: 1.25rem;
    width: 50px; height: 50px;
    background: var(--bg-2);
    border: 1px solid rgba(0,149,182,0.15);
    border-radius: 12px;
    display: flex; align-items: center; justify-content: center;
  }

  .why-title { font-weight: 700; font-size: 1rem; margin-bottom: 0.5rem; color: var(--ivory); }
  .why-text { font-size: 0.875rem; color: var(--ivory-dim); line-height: 1.9; }

  /* ── ORIGINS ── */
  .origins-section {
    background: var(--bg-1);
    border: 1px solid var(--bg-3);
    border-radius: 28px;
    margin: 0 3rem;
    padding: 5rem 4rem;
  }

  .origins-grid {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 4rem; align-items: center;
    margin-top: 3rem;
  }

  .origin-tags { display: flex; flex-wrap: wrap; gap: 0.75rem; margin-top: 2rem; }

  .origin-tag {
    padding: 0.45rem 1rem;
    border: 1px solid var(--bg-3);
    border-radius: 100px;
    font-size: 0.85rem;
    color: var(--muted);
    cursor: default;
    transition: all 0.2s;
  }

  .origin-tag:hover { border-color: var(--bondi); color: var(--bondi-lt); }
  .origin-tag.active { border-color: var(--bondi); color: var(--bondi-lt); background: rgba(0,149,182,0.07); }

  .origin-visual { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }

  .origin-block {
    background: var(--bg);
    border: 1px solid var(--bg-3);
    border-radius: 16px;
    padding: 1.5rem;
    transition: transform 0.2s, border-color 0.2s;
  }

  .origin-block:hover { transform: scale(1.03); border-color: rgba(0,149,182,0.3); }
  .origin-block:first-child { grid-column: span 2; }

  .origin-block-flag { font-size: 2rem; margin-bottom: 0.5rem; }
  .origin-block-name { font-weight: 700; font-size: 0.95rem; color: var(--ivory); }
  .origin-block-items { font-size: 0.75rem; color: var(--muted); margin-top: 0.25rem; }

  /* ── NEWSLETTER ── */
  .newsletter-section {
    text-align: center; max-width: 560px; margin: 0 auto;
    padding: 6rem 2rem;
  }

  .newsletter-form {
    display: flex; gap: 0.75rem; margin-top: 2rem;
    background: var(--bg-1);
    border: 1px solid rgba(0,149,182,0.2);
    border-radius: 100px;
    padding: 0.35rem 1.25rem 0.35rem 0.35rem;
  }

  .newsletter-form input {
    flex: 1; background: none; border: none; outline: none;
    color: var(--ivory); font-family: var(--font-body);
    font-size: 0.9rem; min-width: 0; text-align: right;
    direction: rtl;
  }

  .newsletter-form input::placeholder { color: var(--muted); }

  /* ── FOOTER ── */
  footer {
    border-top: 1px solid var(--bg-3);
    padding: 2.5rem 3rem;
    display: flex; align-items: center; justify-content: space-between;
    flex-wrap: wrap; gap: 1rem;
  }

  .footer-copy { font-size: 0.8rem; color: var(--muted); }
  .footer-links { display: flex; gap: 1.5rem; }
  .footer-links a { font-size: 0.8rem; color: var(--muted); text-decoration: none; transition: color 0.2s; }
  .footer-links a:hover { color: var(--bondi-lt); }

  /* ── RESPONSIVE ── */
  @media (max-width: 800px) {
    nav { padding: 1rem 1.5rem; }
    .nav-links { display: none; }
    .hero { grid-template-columns: 1fr; padding: 7rem 1.5rem 3rem; gap: 3rem; }
    .hero-visual { order: -1; }
    .hero-phone-frame { width: 220px; height: 420px; }
    .badge-top, .badge-bot { display: none; }
    section { padding: 4rem 1.5rem; }
    .origins-section { margin: 0 1.5rem; padding: 3rem 2rem; }
    .origins-grid { grid-template-columns: 1fr; gap: 2rem; }
    footer { flex-direction: column; text-align: center; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="#" class="nav-logo">
    <span class="logo-dot"></span>saffe<span class="logo-accent">shop</span>
  </a>
  <ul class="nav-links">
    <li><a href="#products">فروشگاه</a></li>
    <li><a href="#origins">منشأ کالا</a></li>
    <li><a href="#">درباره ما</a></li>
    <li><a href="#" class="nav-cta">خرید کنید</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-content">
    <div class="hero-eyebrow">واردات اصل · از سال ۱۴۰۳</div>
    <h1 class="hero-title">
      تکنولوژی از<br>
      <span class="highlight">سراسر دنیا</span><br>
      برای شما
    </h1>
    <p class="hero-desc">
      ما محصولات الکترونیکی پریمیوم را مستقیماً از تولیدکنندگان در ژاپن، کره جنوبی و آلمان تهیه می‌کنیم — تا کیفیت واقعی را با قیمتی منصفانه به شما برسانیم.
    </p>
    <div class="hero-actions">
      <a href="#products" class="btn-primary">مشاهده محصولات</a>
      <a href="#origins" class="btn-ghost">← منشأ کالاها</a>
    </div>
    <div class="hero-stats">
      <div>
        <div class="stat-num">۸۰۰<span>+</span></div>
        <div class="stat-label">محصول</div>
      </div>
      <div>
        <div class="stat-num">۱۲</div>
        <div class="stat-label">کشور</div>
      </div>
      <div>
        <div class="stat-num">۴.۹<span>★</span></div>
        <div class="stat-label">میانگین امتیاز</div>
      </div>
    </div>
  </div>

  <div class="hero-visual">
    <div class="hero-phone-frame">
      <div class="phone-screen">
        <div class="phone-img-placeholder">🎧</div>
        <div class="phone-product-name">Sony WH-1000XM6</div>
        <div style="font-size:0.75rem; color:var(--muted); margin-top:-0.5rem;">واردات مستقیم از ژاپن</div>
        <div class="phone-price">۱۲،۸۰۰،۰۰۰ تومان</div>
        <button class="phone-btn">افزودن به سبد خرید</button>
      </div>
    </div>
    <div class="badge-floating badge-top"><div class="dot"></div> تازه موجود شد</div>
    <div class="badge-floating badge-bot">🇯🇵 ارسال از توکیو</div>
  </div>
</section>

<!-- MARQUEE -->
<div class="marquee-band">
  <div class="marquee-track">
    <span class="marquee-item">ارسال رایگان برای خریدهای بالای ۵ میلیون تومان</span>
    <span class="marquee-item">کالای اصل · بدون واسطه</span>
    <span class="marquee-item">۳۰ روز ضمانت بازگشت</span>
    <span class="marquee-item">گارانتی معتبر سازنده</span>
    <span class="marquee-item">محصولات جدید هر هفته</span>
    <span class="marquee-item">پرداخت امن</span>
    <span class="marquee-item">ارسال رایگان برای خریدهای بالای ۵ میلیون تومان</span>
    <span class="marquee-item">کالای اصل · بدون واسطه</span>
    <span class="marquee-item">۳۰ روز ضمانت بازگشت</span>
    <span class="marquee-item">گارانتی معتبر سازنده</span>
    <span class="marquee-item">محصولات جدید هر هفته</span>
    <span class="marquee-item">پرداخت امن</span>
  </div>
</div>

<!-- PRODUCTS -->
<section id="products">
  <div class="products-header">
    <div>
      <div class="section-label">محصولات ویژه</div>
      <h2 class="section-title">تازه‌واردها</h2>
    </div>
    <a href="#" class="btn-ghost">← مشاهده همه</a>
  </div>

  <div class="products-grid">
    <div class="product-card">
      <div class="product-img">🎧</div>
      <div class="product-info">
        <div class="product-badge">پرفروش‌ترین</div>
        <div class="product-origin">🇯🇵 ژاپن · Sony</div>
        <div class="product-name">هدفون نویز کنسلینگ WH-1000XM6</div>
        <p style="font-size:0.8rem; color:var(--muted); margin-top:0.5rem; line-height:1.9;">باتری ۳۰ ساعته · کدک LDAC · حذف نویز هوشمند</p>
        <div class="product-footer">
          <div class="product-price"><span class="old">۱۵،۲۰۰،۰۰۰</span> ۱۲،۸۰۰،۰۰۰ تومان</div>
          <button class="add-btn">+</button>
        </div>
      </div>
    </div>

    <div class="product-card">
      <div class="product-img">⌚</div>
      <div class="product-info">
        <div class="product-origin">🇰🇷 کره · Samsung</div>
        <div class="product-name">Galaxy Watch Ultra</div>
        <div class="product-footer">
          <div class="product-price">۱۸،۴۰۰،۰۰۰ تومان</div>
          <button class="add-btn">+</button>
        </div>
      </div>
    </div>

    <div class="product-card">
      <div class="product-img">📷</div>
      <div class="product-info">
        <div class="product-origin">🇩🇪 آلمان · Zeiss</div>
        <div class="product-name">دوربین کامپکت ZX1</div>
        <div class="product-footer">
          <div class="product-price">۲۹،۹۰۰،۰۰۰ تومان</div>
          <button class="add-btn">+</button>
        </div>
      </div>
    </div>

    <div class="product-card">
      <div class="product-img">🔌</div>
      <div class="product-info">
        <div class="product-origin">🇯🇵 ژاپن · Anker</div>
        <div class="product-name">شارژر GaNPrime 140W</div>
        <div class="product-footer">
          <div class="product-price"><span class="old">۴،۱۰۰،۰۰۰</span> ۳،۰۰۰،۰۰۰ تومان</div>
          <button class="add-btn">+</button>
        </div>
      </div>
    </div>

    <div class="product-card">
      <div class="product-img">🖊️</div>
      <div class="product-info">
        <div class="product-origin">🇩🇪 آلمان · Lamy</div>
        <div class="product-name">قلم دیجیتال Pro 2024</div>
        <div class="product-footer">
          <div class="product-price">۵،۹۵۰،۰۰۰ تومان</div>
          <button class="add-btn">+</button>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- WHY US -->
<section style="padding-top: 0;">
  <div>
    <div class="section-label">چرا Saffe Shop؟</div>
    <h2 class="section-title">تفاوت واردات مستقیم</h2>
    <p class="section-sub">ما واسطه‌ها را حذف می‌کنیم و مستقیم از مبدأ خرید می‌کنیم — شما کمتر می‌پردازید و بیشتر می‌گیرید.</p>
  </div>
  <div class="why-grid">
    <div class="why-card">
      <div class="why-icon">🌍</div>
      <div class="why-title">مستقیم از مبدأ</div>
      <div class="why-text">ما مستقیماً با تولیدکنندگان و توزیع‌کنندگان مجاز در ۱۲ کشور همکاری داریم.</div>
    </div>
    <div class="why-card">
      <div class="why-icon">✅</div>
      <div class="why-title">۱۰۰٪ اصل</div>
      <div class="why-text">هر محصول تأیید اصالت دارد. هیچ کالای تقلبی یا بازار خاکستری جایی ندارد.</div>
    </div>
    <div class="why-card">
      <div class="why-icon">🚀</div>
      <div class="why-title">ارسال سریع</div>
      <div class="why-text">انبار ما تحویل ۱ تا ۳ روزه را برای اغلب شهرها ممکن می‌کند.</div>
    </div>
    <div class="why-card">
      <div class="why-icon">🔄</div>
      <div class="why-title">بازگشت آسان</div>
      <div class="why-text">۳۰ روز بازگشت بدون هیچ سؤالی. گارانتی کامل سازنده روی هر سفارش.</div>
    </div>
  </div>
</section>

<!-- ORIGINS -->
<div style="padding: 0 0 6rem;">
  <div class="origins-section" id="origins">
    <div class="section-label">شبکه ما</div>
    <h2 class="section-title">تهیه‌شده از<br>بهترین‌ها</h2>
    <div class="origins-grid">
      <div>
        <p class="section-sub">ما روابط مستقیمی با تولیدکنندگان آسیا و اروپا برقرار کرده‌ایم تا به محصولاتی دسترسی داشته باشید که هرگز به بازار محلی نرسیده‌اند.</p>
        <div class="origin-tags">
          <span class="origin-tag active">🇯🇵 ژاپن</span>
          <span class="origin-tag">🇰🇷 کره جنوبی</span>
          <span class="origin-tag">🇩🇪 آلمان</span>
          <span class="origin-tag">🇸🇪 سوئد</span>
          <span class="origin-tag">🇹🇼 تایوان</span>
          <span class="origin-tag">🇸🇬 سنگاپور</span>
        </div>
      </div>
      <div class="origin-visual">
        <div class="origin-block">
          <div class="origin-block-flag">🇯🇵</div>
          <div class="origin-block-name">ژاپن</div>
          <div class="origin-block-items">صوتی · دوربین · رباتیک · ابزار دقیق</div>
        </div>
        <div class="origin-block">
          <div class="origin-block-flag">🇰🇷</div>
          <div class="origin-block-name">کره جنوبی</div>
          <div class="origin-block-items">نمایشگر · موبایل · پوشیدنی</div>
        </div>
        <div class="origin-block">
          <div class="origin-block-flag">🇩🇪</div>
          <div class="origin-block-name">آلمان</div>
          <div class="origin-block-items">اپتیک · ابزار مهندسی · صوتی</div>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- NEWSLETTER -->
<div class="newsletter-section">
  <div class="section-label">یک قدم جلوتر باشید</div>
  <h2 class="section-title">اول بدانید.<br>اول بخرید.</h2>
  <p style="color:var(--ivory-dim); font-size:0.9rem; margin-top:1rem;">محصولات جدید، آفرهای ویژه و اخبار واردات — مستقیم به صندوق ورودی شما.</p>
  <div class="newsletter-form">
    <button class="btn-primary" style="white-space: nowrap; padding: 0.75rem 1.5rem;">عضو شوید</button>
    <input type="email" placeholder="ایمیل شما">
  </div>
</div>

<!-- FOOTER -->
<footer>
  <a href="#" class="nav-logo" style="font-size:1.2rem;">
    <span class="logo-dot" style="width:6px;height:6px;"></span>saffe<span class="logo-accent">shop</span>
  </a>
  <div class="footer-copy">© ۱۴۰۳ Saffe Shop — همه حقوق محفوظ است</div>
  <div class="footer-links">
    <a href="#">حریم خصوصی</a>
    <a href="#">شرایط استفاده</a>
    <a href="#">تماس با ما</a>
  </div>
</footer>

</body>
</html>
