<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Designers Hero – Fresh Finds, Best Prices</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=Inter:wght@400;500;600&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --ink:    #1a1a2e;
      --cream:  #fdf6ee;
      --gold:   #c9953a;
      --gold-lt:#f0c97a;
      --rose:   #e8533f;
      --white:  #ffffff;
      --muted:  #6b6b7b;
      --card-bg:#fff9f4;
      --radius: 14px;
      --shadow: 0 4px 24px rgba(26,26,46,.10);
    }

    html { scroll-behavior: smooth; }
    body { font-family: 'Inter', sans-serif; background: var(--cream); color: var(--ink); }

    /* ── NAV ── */
    nav {
      position: fixed; top: 0; left: 0; right: 0; z-index: 100;
      display: flex; align-items: center; justify-content: space-between;
      padding: 0 5%; height: 64px;
      background: rgba(253,246,238,.92); backdrop-filter: blur(12px);
      border-bottom: 1px solid rgba(201,149,58,.18);
    }
    .nav-logo {
      font-family: 'Playfair Display', serif; font-size: 1.35rem;
      color: var(--ink); letter-spacing: .02em;
    }
    .nav-logo span { color: var(--gold); }
    .nav-right { display: flex; gap: 14px; align-items: center; }
    .nav-link { font-size: .88rem; font-weight: 500; color: var(--ink); text-decoration: none; }
    .nav-link:hover { color: var(--gold); }

    /* ── HERO ── */
    #hero {
      position: relative; width: 100%; min-height: 100vh;
      display: flex; align-items: center; justify-content: center;
      overflow: hidden; padding-top: 64px;
    }
    .hero-bg {
      position: absolute; inset: 0;
      background: url('https://i.ibb.co/zW6tQnTB') center/cover no-repeat;
    }
    .hero-overlay {
      position: absolute; inset: 0;
      background: linear-gradient(135deg, rgba(26,26,46,.72) 0%, rgba(26,26,46,.38) 60%, transparent 100%);
    }
    .hero-content {
      position: relative; z-index: 2; text-align: center;
      padding: 0 20px; max-width: 700px;
    }
    .hero-eyebrow {
      display: inline-block; margin-bottom: 18px;
      padding: 6px 18px; border: 1px solid var(--gold-lt);
      border-radius: 40px; color: var(--gold-lt);
      font-size: .78rem; font-weight: 600; letter-spacing: .14em; text-transform: uppercase;
    }
    .hero-title {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2.4rem, 7vw, 5rem); font-weight: 900;
      line-height: 1.08; color: var(--white); margin-bottom: 18px;
    }
    .hero-title em { color: var(--gold-lt); font-style: normal; }
    .hero-sub { color: rgba(255,255,255,.78); font-size: 1.05rem; margin-bottom: 36px; }
    .btn-primary {
      display: inline-block; padding: 15px 38px; border-radius: 50px;
      background: var(--gold); color: var(--white);
      font-weight: 600; font-size: 1rem; text-decoration: none;
      transition: background .2s, transform .15s;
      border: none; cursor: pointer;
    }
    .btn-primary:hover { background: #b8842e; transform: translateY(-2px); }

    /* ── SECTION COMMON ── */
    section { padding: 80px 5%; }
    .section-label {
      font-size: .75rem; font-weight: 600; letter-spacing: .16em;
      text-transform: uppercase; color: var(--gold); margin-bottom: 10px;
    }
    .section-title {
      font-family: 'Playfair Display', serif; font-size: clamp(1.7rem, 4vw, 2.6rem);
      font-weight: 700; color: var(--ink); margin-bottom: 10px;
    }
    .section-sub { color: var(--muted); font-size: .95rem; max-width: 520px; }

    /* ── PRODUCTS ── */
    #products { background: var(https://ibb.co/Z1LBmHCc); }
    .products-header { display: flex; justify-content: space-between; align-items: flex-end; flex-wrap: wrap; gap: 16px; margin-bottom: 40px; }

    .carousel-wrap { position: relative; }
    .carousel {
      display: flex; gap: 22px;
      overflow-x: auto; scroll-snap-type: x mandatory;
      padding-bottom: 12px; scrollbar-width: thin; scrollbar-color: var(--gold-lt) transparent;
    }
    .carousel::-webkit-scrollbar { height: 5px; }
    .carousel::-webkit-scrollbar-thumb { background: var(--gold-lt); border-radius: 10px; }

    .product-card {
      flex: 0 0 270px; scroll-snap-align: start;
      background: var(--card-bg); border-radius: var(--radius);
      overflow: hidden; box-shadow: var(--shadow);
      transition: transform .22s, box-shadow .22s;
      display: flex; flex-direction: column;
    }
    .product-card:hover { transform: translateY(-5px); box-shadow: 0 12px 36px rgba(26,26,46,.16); }
    .product-img-wrap { position: relative; overflow: hidden; aspect-ratio: 4/3; }
    .product-img-wrap img { width: 100%; height: 100%; object-fit: cover; transition: transform .4s; }
    .product-card:hover .product-img-wrap img { transform: scale(1.06); }
    .badge {
      position: absolute; top: 12px; left: 12px;
      background: var(--rose); color: #fff;
      font-size: .7rem; font-weight: 700; padding: 4px 10px; border-radius: 20px;
      text-transform: uppercase; letter-spacing: .06em;
    }
    .product-body { padding: 18px; flex: 1; display: flex; flex-direction: column; gap: 8px; }
    .product-name { font-weight: 600; font-size: .97rem; color: var(--ink); }
    .product-price { font-family: 'Playfair Display', serif; font-size: 1.2rem; color: var(--gold); font-weight: 700; }
    .product-old { font-size: .8rem; color: var(--muted); text-decoration: line-through; margin-left: 6px; }
    .btn-cart {
      margin-top: auto; padding: 10px 0; border-radius: 8px;
      background: var(--ink); color: var(--white);
      font-weight: 600; font-size: .88rem; border: none; cursor: pointer;
      transition: background .2s;
    }
    .btn-cart:hover { background: var(--gold); }

    /* ── ABOUT STRIP ── */
    #about { background: var(--ink); color: var(--white); }
    #about .section-title { color: var(--white); }
    #about .section-sub { color: rgba(255,255,255,.65); }
    .about-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 32px; margin-top: 48px; }
    .about-stat { text-align: center; }
    .about-stat .num { font-family: 'Playfair Display', serif; font-size: 2.8rem; font-weight: 900; color: var(--gold); }
    .about-stat p { font-size: .88rem; color: rgba(255,255,255,.6); margin-top: 6px; }

    /* ── CONTACT ── */
    #contact { background: var(--cream); }
    .contact-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 48px; align-items: start; }
    @media (max-width: 700px) { .contact-grid { grid-template-columns: 1fr; } }
    .contact-info p { color: var(--muted); margin-top: 14px; line-height: 1.7; }
    .contact-info a { color: var(--gold); font-weight: 600; text-decoration: none; }

    /* ── FORM ── */
    .order-form { background: var(--white); border-radius: var(--radius); padding: 32px; box-shadow: var(--shadow); }
    .order-form h3 { font-family: 'Playfair Display', serif; font-size: 1.4rem; margin-bottom: 22px; }
    .form-group { margin-bottom: 18px; display: flex; flex-direction: column; gap: 6px; }
    .form-group label { font-size: .83rem; font-weight: 600; color: var(--ink); }
    .form-group input, .form-group textarea {
      padding: 12px 14px; border: 1.5px solid #e0d8cf; border-radius: 8px;
      font-size: .95rem; font-family: 'Inter', sans-serif;
      background: var(--cream); color: var(--ink);
      transition: border .2s;
    }
    .form-group input:focus, .form-group textarea:focus { outline: none; border-color: var(--gold); }
    .form-group textarea { resize: vertical; min-height: 80px; }
    .form-cart-preview { background: #fdf0e0; border-radius: 8px; padding: 12px 14px; font-size: .88rem; color: var(--muted); min-height: 48px; }
    .form-cart-preview ul { list-style: none; }
    .form-cart-preview li { padding: 3px 0; border-bottom: 1px dashed #e8ddd0; }
    .form-cart-preview li:last-child { border: none; }
    .btn-submit {
      width: 100%; padding: 14px; border-radius: 50px;
      background: var(--gold); color: #fff; font-weight: 700; font-size: 1rem;
      border: none; cursor: pointer; transition: background .2s;
    }
    .btn-submit:hover { background: #b8842e; }
    .form-success { display: none; text-align: center; padding: 24px 0; color: #2d8a5e; font-weight: 600; font-size: 1rem; }

    /* ── CART DRAWER ── */
    .cart-overlay {
      display: none; position: fixed; inset: 0; background: rgba(0,0,0,.45); z-index: 200;
    }
    .cart-overlay.open { display: block; }
    .cart-drawer {
      position: fixed; top: 0; right: -380px; bottom: 0; width: 360px; max-width: 95vw;
      background: var(--white); z-index: 201; box-shadow: -8px 0 40px rgba(0,0,0,.18);
      display: flex; flex-direction: column; transition: right .3s cubic-bezier(.4,0,.2,1);
      padding: 0;
    }
    .cart-drawer.open { right: 0; }
    .cart-head {
      display: flex; align-items: center; justify-content: space-between;
      padding: 22px 24px; border-bottom: 1px solid #f0e8de;
    }
    .cart-head h2 { font-family: 'Playfair Display', serif; font-size: 1.35rem; }
    .cart-close { background: none; border: none; font-size: 1.5rem; cursor: pointer; color: var(--muted); }
    .cart-items { flex: 1; overflow-y: auto; padding: 20px 24px; display: flex; flex-direction: column; gap: 14px; }
    .cart-empty { text-align: center; color: var(--muted); margin-top: 60px; font-size: .95rem; }
    .cart-item {
      display: flex; gap: 14px; align-items: center;
      background: var(--cream); border-radius: 10px; padding: 12px;
    }
    .cart-item img { width: 62px; height: 62px; object-fit: cover; border-radius: 8px; }
    .cart-item-info { flex: 1; }
    .cart-item-name { font-weight: 600; font-size: .9rem; }
    .cart-item-price { color: var(--gold); font-weight: 700; font-size: .9rem; }
    .cart-item-qty {
      display: flex; align-items: center; gap: 8px; margin-top: 6px;
    }
    .qty-btn {
      width: 26px; height: 26px; border-radius: 50%;
      background: var(--ink); color: #fff; border: none; cursor: pointer; font-size: .95rem;
      display: flex; align-items: center; justify-content: center;
    }
    .qty-num { font-size: .9rem; font-weight: 600; min-width: 20px; text-align: center; }
    .cart-remove { background: none; border: none; color: var(--rose); font-size: 1.1rem; cursor: pointer; }
    .cart-foot {
      padding: 22px 24px; border-top: 1px solid #f0e8de;
    }
    .cart-total { display: flex; justify-content: space-between; margin-bottom: 16px; font-weight: 700; font-size: 1rem; }
    .cart-total span:last-child { color: var(--gold); font-family: 'Playfair Display', serif; font-size: 1.15rem; }
    .btn-checkout { width: 100%; padding: 14px; border-radius: 50px; background: var(--gold); color: #fff; font-weight: 700; font-size: 1rem; border: none; cursor: pointer; }
    .btn-checkout:hover { background: #b8842e; }

    /* ── FLOATING BUTTONS ── */
    .floating-group { position: fixed; bottom: 28px; right: 22px; z-index: 150; display: flex; flex-direction: column; gap: 14px; align-items: flex-end; }
    .fab {
      width: 56px; height: 56px; border-radius: 50%;
      display: flex; align-items: center; justify-content: center;
      box-shadow: 0 4px 18px rgba(0,0,0,.22); cursor: pointer; border: none;
      text-decoration: none; transition: transform .18s;
    }
    .fab:hover { transform: scale(1.1); }
    .fab-whatsapp { background: #25D366; }
    .fab-whatsapp svg { width: 28px; height: 28px; }
    .fab-cart { background: var(--ink); position: relative; }
    .fab-cart svg { width: 26px; height: 26px; fill: none; stroke: #fff; stroke-width: 2; stroke-linecap: round; stroke-linejoin: round; }
    .cart-badge {
      position: absolute; top: -4px; right: -4px;
      background: var(--rose); color: #fff; border-radius: 50%;
      width: 22px; height: 22px; font-size: .7rem; font-weight: 700;
      display: flex; align-items: center; justify-content: center;
    }

    /* ── FOOTER ── */
    footer { background: #0f0f1c; color: rgba(255,255,255,.5); text-align: center; padding: 28px 5%; font-size: .82rem; }
    footer span { color: var(--gold); }

    /* ── TOAST ── */
    .toast {
      position: fixed; bottom: 100px; left: 50%; transform: translateX(-50%) translateY(30px);
      background: var(--ink); color: #fff; padding: 12px 26px; border-radius: 40px;
      font-size: .9rem; font-weight: 600; z-index: 300;
      opacity: 0; transition: opacity .25s, transform .25s; pointer-events: none;
    }
    .toast.show { opacity: 1; transform: translateX(-50%) translateY(0); }

    @media (max-width: 600px) {
      section { padding: 60px 4%; }
      .product-card { flex: 0 0 230px; }
    }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">Designers <span>Hero</span></div>
  <div class="nav-right">
    <a href="#products" class="nav-link">Shop</a>
    <a href="#about" class="nav-link">About</a>
    <a href="#contact" class="nav-link">Contact</a>
  </div>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-bg"></div>
  <div class="hero-overlay"></div>
  <div class="hero-content">
    <span class="hero-eyebrow">Welcome to Designers Hero</span>
    <h1 class="hero-title">Fresh Finds,<br/><em>Best Prices.</em></h1>
    <p class="hero-sub">Curated designer picks for the discerning shopper — quality you can see, prices you'll love.</p>
    <a href="#products" class="btn-primary">Shop Now ↓</a>
  </div>
</section>

<!-- PRODUCTS -->
<section id="products">
  <div class="products-header">
    <div>
      <p class="section-label">Our Collection</p>
      <h2 class="section-title">Featured Products</h2>
      <p class="section-sub">Scroll through our handpicked selection — tap "Add to Cart" to get started.</p>
    </div>
  </div>
  <div class="carousel-wrap">
    <div class="carousel" id="carousel">

      <div class="product-card">
        <div class="product-img-wrap">
          <img src="https://i.ibb.co/Z1LBmHCc" alt="Designer Item 1" loading="lazy"/>
          <span class="badge">Hot Pick</span>
        </div>
        <div class="product-body">
          <div class="product-name">Designer Collection A</div>
          <div><span class="product-price">₹1,299</span><span class="product-old">₹1,799</span></div>
          <button class="btn-cart" onclick="addToCart('Designer Collection A','₹1,299','https://i.ibb.co/Z1LBmHCc',1299)">Add to Cart</button>
        </div>
      </div>

      <div class="product-card">
        <div class="product-img-wrap">
          <img src="https://i.ibb.co/YFMc6vVF" alt="Designer Item 2" loading="lazy"/>
          <span class="badge">New</span>
        </div>
        <div class="product-body">
          <div class="product-name">Designer Collection B</div>
          <div><span class="product-price">₹999</span><span class="product-old">₹1,499</span></div>
          <button class="btn-cart" onclick="addToCart('Designer Collection B','₹999','https://i.ibb.co/YFMc6vVF',999)">Add to Cart</button>
        </div>
      </div>

      <div class="product-card">
        <div class="product-img-wrap">
          <img src="https://i.ibb.co/Z1LBmHCc" alt="Designer Item 3" loading="lazy"/>
          <span class="badge">Sale</span>
        </div>
        <div class="product-body">
          <div class="product-name">Designer Collection C</div>
          <div><span class="product-price">₹1,599</span><span class="product-old">₹2,199</span></div>
          <button class="btn-cart" onclick="addToCart('Designer Collection C','₹1,599','https://i.ibb.co/Z1LBmHCc',1599)">Add to Cart</button>
        </div>
      </div>

      <div class="product-card">
        <div class="product-img-wrap">
          <img src="https://i.ibb.co/YFMc6vVF" alt="Designer Item 4" loading="lazy"/>
          <span class="badge">Popular</span>
        </div>
        <div class="product-body">
          <div class="product-name">Designer Collection D</div>
          <div><span class="product-price">₹749</span><span class="product-old">₹999</span></div>
          <button class="btn-cart" onclick="addToCart('Designer Collection D','₹749','https://i.ibb.co/YFMc6vVF',749)">Add to Cart</button>
        </div>
      </div>

      <div class="product-card">
        <div class="product-img-wrap">
          <img src="https://i.ibb.co/Z1LBmHCc" alt="Designer Item 5" loading="lazy"/>
        </div>
        <div class="product-body">
          <div class="product-name">Designer Collection E</div>
          <div><span class="product-price">₹2,099</span><span class="product-old">₹2,799</span></div>
          <button class="btn-cart" onclick="addToCart('Designer Collection E','₹2,099','https://i.ibb.co/Z1LBmHCc',2099)">Add to Cart</button>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <p class="section-label" style="color:var(--gold-lt)">Who We Are</p>
  <h2 class="section-title">Built on Style, Backed by Value</h2>
  <p class="section-sub">Designers Hero was built for people who refuse to compromise — on aesthetics or price. Every item is hand-sourced to ensure you get the best.</p>
  <div class="about-grid">
    <div class="about-stat"><div class="num">500+</div><p>Products Available</p></div>
    <div class="about-stat"><div class="num">2K+</div><p>Happy Customers</p></div>
    <div class="about-stat"><div class="num">4.9★</div><p>Average Rating</p></div>
    <div class="about-stat"><div class="num">100%</div><p>Authentic Products</p></div>
  </div>
</section>

<!-- CONTACT + ORDER FORM -->
<section id="contact">
  <div class="contact-grid">
    <div class="contact-info">
      <p class="section-label">Get In Touch</p>
      <h2 class="section-title">Place Your Order</h2>
      <p>Add items to your cart, fill in your details, and send us your order. We'll confirm it over WhatsApp or email within hours.</p>
      <p style="margin-top:20px">
        📧 <a href="mailto:shrijomde0@gmail.com">shrijomde0@gmail.com</a><br/>
        📱 <a href="https://wa.me/9423703503" target="_blank">WhatsApp: +91 94237 03503</a>
      </p>
      <p style="margin-top:18px; font-size:.85rem; color:var(--muted)">We typically respond within 1–2 hours during business hours.</p>
    </div>

    <div class="order-form">
      <h3>🛒 Order Form</h3>

      <div class="form-group">
        <label for="cust-name">Your Name *</label>
        <input type="text" id="cust-name" placeholder="e.g. Priya Sharma" required/>
      </div>
      <div class="form-group">
        <label for="cust-phone">Phone Number *</label>
        <input type="tel" id="cust-phone" placeholder="+91 9876543210" required/>
      </div>
      <div class="form-group">
        <label for="cust-email">Your Email (optional)</label>
        <input type="email" id="cust-email" placeholder="you@example.com"/>
      </div>
      <div class="form-group">
        <label for="cust-address">Delivery Address *</label>
        <textarea id="cust-address" placeholder="House no, Street, City, PIN…" required></textarea>
      </div>
      <div class="form-group">
        <label>Items in Cart</label>
        <div class="form-cart-preview" id="form-cart-preview">
          <span style="color:var(--muted);font-style:italic">No items yet — add from the shop above.</span>
        </div>
      </div>
      <div class="form-group">
        <label for="cust-note">Special Instructions (optional)</label>
        <textarea id="cust-note" placeholder="Size, colour preference, delivery notes…"></textarea>
      </div>

      <button class="btn-submit" onclick="submitOrder()">📨 Send Order to Shop</button>
      <div class="form-success" id="form-success">
        ✅ Order sent! We'll contact you shortly on WhatsApp or email.
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  © 2024 <span>Designers Hero</span> · Fresh Finds, Best Prices · Made with ❤️ in India
</footer>

<!-- CART OVERLAY + DRAWER -->
<div class="cart-overlay" id="cartOverlay" onclick="closeCart()"></div>
<div class="cart-drawer" id="cartDrawer">
  <div class="cart-head">
    <h2>Your Cart</h2>
    <button class="cart-close" onclick="closeCart()">✕</button>
  </div>
  <div class="cart-items" id="cartItems">
    <div class="cart-empty">Your cart is empty.<br/>Start shopping above!</div>
  </div>
  <div class="cart-foot">
    <div class="cart-total"><span>Total</span><span id="cartTotal">₹0</span></div>
    <button class="btn-checkout" onclick="closeCart(); document.getElementById('contact').scrollIntoView({behavior:'smooth'})">Proceed to Order →</button>
  </div>
</div>

<!-- FLOATING BUTTONS -->
<div class="floating-group">
  <a href="https://wa.me/9423703503" target="_blank" class="fab fab-whatsapp" title="Chat on WhatsApp">
    <svg viewBox="0 0 32 32" fill="white" xmlns="http://www.w3.org/2000/svg">
      <path d="M16 3C9.373 3 4 8.373 4 15c0 2.385.665 4.61 1.818 6.502L4 29l7.752-1.795A11.94 11.94 0 0016 28c6.627 0 12-5.373 12-12S22.627 3 16 3zm0 21.9a9.88 9.88 0 01-5.07-1.395l-.363-.215-4.6 1.065 1.094-4.487-.236-.369A9.9 9.9 0 016.1 15c0-5.47 4.43-9.9 9.9-9.9 5.47 0 9.9 4.43 9.9 9.9 0 5.47-4.43 9.9-9.9 9.9zm5.44-7.41c-.298-.15-1.765-.87-2.038-.97-.272-.1-.47-.15-.67.15-.197.298-.77.97-.944 1.17-.173.197-.346.22-.644.075-.298-.15-1.257-.463-2.393-1.476-.884-.787-1.48-1.76-1.655-2.056-.173-.298-.018-.46.13-.608.133-.133.298-.347.447-.52.148-.174.197-.298.298-.497.1-.198.05-.372-.025-.52-.075-.15-.67-1.612-.917-2.207-.242-.58-.487-.5-.67-.51-.173-.008-.372-.01-.57-.01-.197 0-.52.074-.793.372-.272.298-1.04 1.017-1.04 2.48 0 1.463 1.065 2.876 1.213 3.074.148.198 2.096 3.2 5.077 4.487.71.307 1.263.49 1.695.627.712.226 1.36.194 1.872.118.571-.085 1.765-.72 2.014-1.415.247-.695.247-1.29.173-1.414-.074-.124-.272-.198-.57-.347z"/>
    </svg>
  </a>
  <button class="fab fab-cart" onclick="openCart()" title="View Cart">
    <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
      <path d="M6 2L3 6v14a2 2 0 002 2h14a2 2 0 002-2V6l-3-4z"/><line x1="3" y1="6" x2="21" y2="6"/><path d="M16 10a4 4 0 01-8 0"/>
    </svg>
    <span class="cart-badge" id="cartBadge">0</span>
  </button>
</div>

<!-- TOAST -->
<div class="toast" id="toast"></div>

<script>
  let cart = [];

  function addToCart(name, priceStr, img, priceNum) {
    const existing = cart.find(i => i.name === name);
    if (existing) {
      existing.qty++;
    } else {
      cart.push({ name, priceStr, img, priceNum, qty: 1 });
    }
    updateCartUI();
    showToast(`"${name}" added to cart!`);
  }

  function removeFromCart(name) {
    cart = cart.filter(i => i.name !== name);
    updateCartUI();
  }

  function changeQty(name, delta) {
    const item = cart.find(i => i.name === name);
    if (!item) return;
    item.qty += delta;
    if (item.qty <= 0) cart = cart.filter(i => i.name !== name);
    updateCartUI();
  }

  function updateCartUI() {
    const count = cart.reduce((s, i) => s + i.qty, 0);
    document.getElementById('cartBadge').textContent = count;

    const container = document.getElementById('cartItems');
    if (cart.length === 0) {
      container.innerHTML = '<div class="cart-empty">Your cart is empty.<br/>Start shopping above!</div>';
      document.getElementById('cartTotal').textContent = '₹0';
    } else {
      container.innerHTML = cart.map(item => `
        <div class="cart-item">
          <img src="${item.img}" alt="${item.name}"/>
          <div class="cart-item-info">
            <div class="cart-item-name">${item.name}</div>
            <div class="cart-item-price">${item.priceStr}</div>
            <div class="cart-item-qty">
              <button class="qty-btn" onclick="changeQty('${item.name}',-1)">−</button>
              <span class="qty-num">${item.qty}</span>
              <button class="qty-btn" onclick="changeQty('${item.name}',1)">+</button>
            </div>
          </div>
          <button class="cart-remove" onclick="removeFromCart('${item.name}')" title="Remove">🗑</button>
        </div>
      `).join('');
      const total = cart.reduce((s, i) => s + i.priceNum * i.qty, 0);
      document.getElementById('cartTotal').textContent = `₹${total.toLocaleString('en-IN')}`;
    }

    // update form preview
    const preview = document.getElementById('form-cart-preview');
    if (cart.length === 0) {
      preview.innerHTML = '<span style="color:var(--muted);font-style:italic">No items yet — add from the shop above.</span>';
    } else {
      const total = cart.reduce((s, i) => s + i.priceNum * i.qty, 0);
      preview.innerHTML = `<ul>${cart.map(i => `<li>• ${i.name} × ${i.qty} — ${i.priceStr}</li>`).join('')}</ul><div style="margin-top:8px;font-weight:700;color:var(--ink)">Total: ₹${total.toLocaleString('en-IN')}</div>`;
    }
  }

  function openCart() {
    document.getElementById('cartDrawer').classList.add('open');
    document.getElementById('cartOverlay').classList.add('open');
  }
  function closeCart() {
    document.getElementById('cartDrawer').classList.remove('open');
    document.getElementById('cartOverlay').classList.remove('open');
  }

  function showToast(msg) {
    const t = document.getElementById('toast');
    t.textContent = msg;
    t.classList.add('show');
    setTimeout(() => t.classList.remove('show'), 2800);
  }

  function submitOrder() {
    const name    = document.getElementById('cust-name').value.trim();
    const phone   = document.getElementById('cust-phone').value.trim();
    const email   = document.getElementById('cust-email').value.trim();
    const address = document.getElementById('cust-address').value.trim();
    const note    = document.getElementById('cust-note').value.trim();

    if (!name)    { showToast('Please enter your name.'); return; }
    if (!phone)   { showToast('Please enter your phone number.'); return; }
    if (!address) { showToast('Please enter your delivery address.'); return; }
    if (cart.length === 0) { showToast('Your cart is empty! Add some products first.'); return; }

    const total = cart.reduce((s, i) => s + i.priceNum * i.qty, 0);
    const itemList = cart.map(i => `${i.name} x${i.qty} (${i.priceStr})`).join('\n');

    const subject = encodeURIComponent(`New Order from ${name} — Designers Hero`);
    const body = encodeURIComponent(
`New Order Received — Designers Hero
=====================================
Customer Name  : ${name}
Phone Number   : ${phone}
Email          : ${email || 'Not provided'}
Delivery Address: ${address}

ORDER ITEMS:
${itemList}

Order Total    : ₹${total.toLocaleString('en-IN')}

Special Notes  : ${note || 'None'}
=====================================
This order was placed via the Designers Hero website.`
    );

    window.location.href = `mailto:shrijomde0@gmail.com?subject=${subject}&body=${body}`;

    document.getElementById('form-success').style.display = 'block';
    setTimeout(() => document.getElementById('form-success').style.display = 'none', 6000);
  }

  // auto-slide carousel every 3.5s
  const carousel = document.getElementById('carousel');
  let autoSlide = setInterval(() => {
    if (carousel.scrollLeft + carousel.clientWidth >= carousel.scrollWidth - 10) {
      carousel.scrollTo({ left: 0, behavior: 'smooth' });
    } else {
      carousel.scrollBy({ left: 292, behavior: 'smooth' });
    }
  }, 3500);
  carousel.addEventListener('mouseenter', () => clearInterval(autoSlide));
  carousel.addEventListener('mouseleave', () => {
    autoSlide = setInterval(() => {
      if (carousel.scrollLeft + carousel.clientWidth >= carousel.scrollWidth - 10) {
        carousel.scrollTo({ left: 0, behavior: 'smooth' });
      } else {
        carousel.scrollBy({ left: 292, behavior: 'smooth' });
      }
    }, 3500);
  });
</script>
</body>
</html>
