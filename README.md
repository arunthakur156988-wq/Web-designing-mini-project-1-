<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>PhoneZone – Mobile Phones & Accessories</title>
<style>
/* ===== RESET & ROOT ===== */
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0;}
:root{
  --bg:#f0f2f7;
  --surface:#ffffff;
  --card:#ffffff;
  --dark:#0a0f1e;
  --mid:#1e2d5a;
  --accent:#0047ff;
  --accent2:#ff3b3b;
  --accent3:#00c896;
  --text:#0a0f1e;
  --muted:#6b7280;
  --border:#e2e6f0;
  --font-head:'Georgia',serif;
  --font-body:'Trebuchet MS',sans-serif;
  --shadow:0 4px 24px rgba(0,71,255,0.08);
  --shadow-lg:0 12px 48px rgba(0,71,255,0.14);
}
html{scroll-behavior:smooth;}
body{background:var(--bg);color:var(--text);font-family:var(--font-body);font-size:14px;line-height:1.6;overflow-x:hidden;}
a{text-decoration:none;color:inherit;}
button{cursor:pointer;border:none;background:none;font-family:inherit;}
::-webkit-scrollbar{width:4px;}
::-webkit-scrollbar-track{background:var(--bg);}
::-webkit-scrollbar-thumb{background:var(--accent);border-radius:2px;}

/* ===== NAVBAR ===== */
nav{
  position:sticky;top:0;z-index:999;
  background:rgba(255,255,255,0.92);
  backdrop-filter:blur(16px);
  border-bottom:1px solid var(--border);
  padding:0 48px;
  display:flex;align-items:center;justify-content:space-between;
  height:68px;
  box-shadow:0 2px 16px rgba(0,71,255,0.06);
}
.logo{font-family:var(--font-head);font-size:26px;font-weight:700;letter-spacing:-1.5px;color:var(--dark);}
.logo span{color:var(--accent);}
.nav-links{display:flex;gap:32px;list-style:none;}
.nav-links a{font-size:13px;letter-spacing:.5px;color:var(--muted);font-weight:600;transition:color .2s;}
.nav-links a:hover{color:var(--accent);}
.nav-right{display:flex;align-items:center;gap:16px;}
#cart-btn{
  background:var(--accent);color:#fff;
  padding:9px 22px;font-size:13px;font-weight:700;letter-spacing:.5px;
  border-radius:100px;position:relative;transition:background .2s,transform .15s;
  box-shadow:0 4px 16px rgba(0,71,255,0.3);
}
#cart-btn:hover{background:#0035cc;transform:translateY(-1px);}
#cart-count{
  position:absolute;top:-6px;right:-6px;
  background:var(--accent2);color:#fff;
  font-size:10px;font-weight:700;
  width:19px;height:19px;border-radius:50%;
  display:flex;align-items:center;justify-content:center;
}

/* ===== HERO ===== */
#hero{
  min-height:88vh;
  display:grid;grid-template-columns:1fr 1fr;align-items:center;gap:60px;
  padding:80px 48px;
  background:linear-gradient(135deg,#f0f2f7 0%,#e8edff 50%,#f0f2f7 100%);
  position:relative;overflow:hidden;
}
#hero::before{
  content:'';position:absolute;
  width:700px;height:700px;border-radius:50%;
  background:radial-gradient(circle,rgba(0,71,255,0.08) 0%,transparent 70%);
  top:-200px;right:-100px;pointer-events:none;
}
#hero::after{
  content:'';position:absolute;
  width:400px;height:400px;border-radius:50%;
  background:radial-gradient(circle,rgba(0,200,150,0.07) 0%,transparent 70%);
  bottom:-100px;left:100px;pointer-events:none;
}
.hero-left{position:relative;z-index:1;}
.hero-tag{
  display:inline-flex;align-items:center;gap:8px;
  background:rgba(0,71,255,0.08);color:var(--accent);
  border:1px solid rgba(0,71,255,0.2);
  padding:6px 16px;border-radius:100px;font-size:12px;font-weight:700;letter-spacing:1px;
  margin-bottom:24px;animation:fadeUp .5s ease both;
}
.hero-dot{width:7px;height:7px;background:var(--accent3);border-radius:50%;animation:pulse 1.5s infinite;}
@keyframes pulse{0%,100%{opacity:1;transform:scale(1);}50%{opacity:.5;transform:scale(1.4);}}
#hero h1{
  font-family:var(--font-head);font-size:clamp(42px,5.5vw,72px);
  line-height:.96;letter-spacing:-3px;color:var(--dark);
  margin-bottom:24px;animation:fadeUp .6s .1s ease both;
}
#hero h1 em{font-style:italic;color:var(--accent);}
#hero p{
  font-size:15px;color:var(--muted);max-width:420px;
  margin-bottom:36px;line-height:1.75;animation:fadeUp .6s .2s ease both;
}
.hero-btns{display:flex;gap:14px;flex-wrap:wrap;animation:fadeUp .6s .3s ease both;}
.btn-primary{
  background:var(--accent);color:#fff;
  padding:14px 32px;font-size:13px;font-weight:700;letter-spacing:.5px;
  border-radius:100px;transition:background .2s,transform .15s;
  box-shadow:0 6px 24px rgba(0,71,255,0.32);
}
.btn-primary:hover{background:#0035cc;transform:translateY(-2px);}
.btn-outline{
  border:2px solid var(--border);color:var(--dark);
  padding:14px 32px;font-size:13px;font-weight:700;
  border-radius:100px;transition:border-color .2s,color .2s;
}
.btn-outline:hover{border-color:var(--accent);color:var(--accent);}
.hero-stats{
  display:flex;gap:36px;margin-top:48px;
  animation:fadeUp .6s .4s ease both;
}
.stat-item{}
.stat-num{font-family:var(--font-head);font-size:30px;font-weight:700;color:var(--dark);}
.stat-label{font-size:11px;color:var(--muted);letter-spacing:.5px;}

/* Hero Right – Phone Showcase */
.hero-right{
  position:relative;z-index:1;
  display:flex;align-items:center;justify-content:center;
  animation:fadeUp .7s .2s ease both;
}
.phone-showcase{
  position:relative;width:320px;height:480px;
}
.phone-card-hero{
  position:absolute;
  background:var(--surface);
  border-radius:24px;
  padding:24px;
  box-shadow:var(--shadow-lg);
  border:1px solid var(--border);
  transition:transform .3s;
}
.phone-card-hero:hover{transform:translateY(-6px);}
.ph-main{top:20px;left:0;width:200px;z-index:3;}
.ph-sec{top:60px;right:0;width:170px;z-index:2;opacity:.9;}
.ph-tert{bottom:10px;left:30px;width:160px;z-index:1;opacity:.8;}
.phone-emoji-lg{font-size:52px;display:block;text-align:center;margin-bottom:10px;}
.phone-emoji-sm{font-size:38px;display:block;text-align:center;margin-bottom:8px;}
.ph-name{font-family:var(--font-head);font-size:13px;font-weight:700;color:var(--dark);text-align:center;}
.ph-price{font-size:12px;color:var(--accent);font-weight:700;text-align:center;}

/* ===== BRANDS STRIP ===== */
#brands{
  background:var(--surface);
  border-top:1px solid var(--border);
  border-bottom:1px solid var(--border);
  padding:20px 48px;
  display:flex;align-items:center;gap:16px;
  overflow:hidden;
}
.brands-label{font-size:11px;letter-spacing:2px;text-transform:uppercase;color:var(--muted);white-space:nowrap;flex-shrink:0;}
.brands-divider{width:1px;height:28px;background:var(--border);flex-shrink:0;}
.brands-scroll{
  display:flex;gap:40px;align-items:center;
  animation:scrollBrands 18s linear infinite;
  white-space:nowrap;
}
.brands-scroll span{font-family:var(--font-head);font-size:16px;font-weight:700;color:var(--muted);letter-spacing:-0.5px;opacity:.6;transition:opacity .2s;}
.brands-scroll span:hover{opacity:1;color:var(--accent);}
@keyframes scrollBrands{from{transform:translateX(0);}to{transform:translateX(-50%);}}

/* ===== CATEGORIES ===== */
#categories{background:var(--bg);padding:32px 48px;}
.cat-grid{display:flex;gap:10px;flex-wrap:wrap;}
.cat-pill{
  padding:10px 22px;border:1.5px solid var(--border);
  border-radius:100px;font-size:12px;font-weight:700;color:var(--muted);
  background:var(--surface);cursor:pointer;transition:all .2s;
  box-shadow:0 2px 8px rgba(0,0,0,0.04);
}
.cat-pill:hover,.cat-pill.active{background:var(--accent);color:#fff;border-color:var(--accent);box-shadow:0 4px 16px rgba(0,71,255,0.25);}

/* ===== PRODUCTS GRID ===== */
#products{padding:60px 48px;background:var(--bg);}
.section-label{font-size:11px;letter-spacing:3px;text-transform:uppercase;color:var(--accent);margin-bottom:10px;font-weight:700;}
.section-title{font-family:var(--font-head);font-size:clamp(28px,3.5vw,44px);letter-spacing:-1.5px;margin-bottom:40px;color:var(--dark);}
.products-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(268px,1fr));gap:22px;}
.product-card{
  background:var(--card);border:1.5px solid var(--border);
  border-radius:20px;overflow:hidden;
  transition:transform .22s,box-shadow .22s,border-color .22s;
  box-shadow:0 2px 12px rgba(0,0,0,0.05);
  position:relative;
}
.product-card:hover{transform:translateY(-6px);box-shadow:var(--shadow-lg);border-color:rgba(0,71,255,0.3);}
.product-img{
  width:100%;height:210px;
  display:flex;align-items:center;justify-content:center;
  background:linear-gradient(135deg,#f5f7ff,#eef1ff);
  position:relative;font-size:68px;
  overflow:hidden;
}
.product-img::after{content:'';position:absolute;inset:0;background:radial-gradient(circle at 50% 40%,rgba(0,71,255,0.06),transparent 70%);}
.badge{
  position:absolute;top:14px;left:14px;z-index:1;
  font-size:9px;font-weight:700;letter-spacing:.8px;text-transform:uppercase;
  padding:4px 10px;border-radius:100px;
}
.badge-new{background:var(--accent3);color:#fff;}
.badge-hot{background:var(--accent2);color:#fff;}
.badge-sale{background:var(--accent);color:#fff;}
.product-info{padding:20px;}
.product-cat{font-size:10px;letter-spacing:2px;text-transform:uppercase;color:var(--muted);margin-bottom:6px;font-weight:600;}
.product-name{font-family:var(--font-head);font-size:17px;font-weight:700;margin-bottom:6px;line-height:1.2;color:var(--dark);}
.product-desc{font-size:12px;color:var(--muted);margin-bottom:14px;line-height:1.55;}
.product-specs{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:14px;}
.spec-chip{
  font-size:10px;font-weight:600;color:var(--accent);
  background:rgba(0,71,255,0.07);padding:3px 10px;border-radius:100px;
}
.product-footer{display:flex;align-items:center;justify-content:space-between;}
.product-price{font-family:var(--font-head);font-size:20px;font-weight:700;color:var(--dark);}
.product-price s{font-size:13px;color:var(--muted);margin-left:6px;}
.add-btn{
  background:var(--accent);color:#fff;
  padding:9px 18px;font-size:11px;font-weight:700;
  border-radius:100px;transition:background .2s,transform .15s;
  box-shadow:0 4px 14px rgba(0,71,255,0.28);
}
.add-btn:hover{background:#0035cc;transform:translateY(-1px);}

/* ===== MARQUEE ===== */
.marquee-wrap{background:var(--accent);padding:11px 0;overflow:hidden;white-space:nowrap;}
.marquee-inner{display:inline-block;animation:marquee 22s linear infinite;}
.marquee-inner span{font-size:11px;font-weight:700;letter-spacing:3px;text-transform:uppercase;color:#fff;margin:0 30px;opacity:.9;}
@keyframes marquee{from{transform:translateX(0);}to{transform:translateX(-50%);}}

/* ===== FEATURED DEAL ===== */
#deal{background:var(--dark);padding:0;}
.deal-inner{display:grid;grid-template-columns:1fr 1fr;}
.deal-left{
  padding:64px 56px;
  background:linear-gradient(135deg,var(--dark),var(--mid));
}
.deal-tag{display:inline-block;background:var(--accent2);color:#fff;font-size:10px;font-weight:700;letter-spacing:2px;text-transform:uppercase;padding:5px 14px;border-radius:100px;margin-bottom:18px;}
.deal-left h2{font-family:var(--font-head);font-size:36px;color:#fff;margin-bottom:14px;line-height:1.1;letter-spacing:-1px;}
.deal-left p{font-size:14px;color:rgba(255,255,255,.6);margin-bottom:28px;line-height:1.7;}
.deal-price{font-family:var(--font-head);font-size:40px;color:var(--accent3);font-weight:700;margin-bottom:28px;}
.deal-price s{font-size:20px;color:rgba(255,255,255,.4);margin-left:10px;}
.deal-right{
  display:flex;align-items:center;justify-content:center;
  background:linear-gradient(135deg,#0d1535,#1a2b6e);
  font-size:130px;min-height:320px;
}

/* ===== COMPARE TABLE ===== */
#compare{padding:70px 48px;background:var(--surface);}
.compare-table{width:100%;border-collapse:collapse;font-size:13px;}
.compare-table th{background:var(--accent);color:#fff;padding:14px 18px;text-align:left;font-weight:700;letter-spacing:.5px;}
.compare-table th:first-child{border-radius:12px 0 0 0;}
.compare-table th:last-child{border-radius:0 12px 0 0;}
.compare-table td{padding:13px 18px;border-bottom:1px solid var(--border);color:var(--text);}
.compare-table tr:nth-child(even) td{background:var(--bg);}
.compare-table tr:hover td{background:rgba(0,71,255,0.04);}
.check{color:var(--accent3);font-size:16px;}
.cross{color:var(--accent2);font-size:16px;}

/* ===== WHY US ===== */
#why{padding:70px 48px;background:var(--bg);}
.why-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(220px,1fr));gap:20px;}
.why-card{
  background:var(--surface);padding:28px;border-radius:18px;
  border:1.5px solid var(--border);transition:border-color .2s,box-shadow .2s;
  box-shadow:0 2px 10px rgba(0,0,0,0.04);
}
.why-card:hover{border-color:var(--accent);box-shadow:0 6px 24px rgba(0,71,255,0.12);}
.why-icon{font-size:30px;margin-bottom:14px;}
.why-title{font-family:var(--font-head);font-size:17px;font-weight:700;margin-bottom:7px;color:var(--dark);}
.why-text{font-size:12px;color:var(--muted);line-height:1.6;}

/* ===== TESTIMONIALS ===== */
#testimonials{padding:70px 48px;background:var(--dark);}
#testimonials .section-label{color:var(--accent3);}
#testimonials .section-title{color:#fff;}
.testi-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:20px;}
.testi-card{background:rgba(255,255,255,.05);border:1px solid rgba(255,255,255,.1);padding:28px;border-radius:18px;backdrop-filter:blur(6px);}
.stars{color:#f5c518;font-size:14px;margin-bottom:12px;}
.testi-text{font-size:13px;color:rgba(255,255,255,.7);line-height:1.75;margin-bottom:18px;font-style:italic;}
.testi-author{font-size:13px;font-weight:700;color:#fff;}
.testi-role{font-size:11px;color:rgba(255,255,255,.4);}

/* ===== NEWSLETTER ===== */
#newsletter{
  background:linear-gradient(135deg,var(--accent),#0028aa);
  padding:72px 48px;text-align:center;
}
#newsletter h2{font-family:var(--font-head);font-size:36px;color:#fff;margin-bottom:10px;letter-spacing:-1px;}
#newsletter p{font-size:14px;color:rgba(255,255,255,.75);margin-bottom:30px;}
.nl-form{display:flex;gap:10px;justify-content:center;flex-wrap:wrap;}
.nl-input{
  padding:13px 22px;border:2px solid rgba(255,255,255,.3);background:rgba(255,255,255,.1);
  color:#fff;font-family:var(--font-body);font-size:13px;border-radius:100px;
  width:300px;outline:none;backdrop-filter:blur(4px);
}
.nl-input::placeholder{color:rgba(255,255,255,.5);}
.nl-input:focus{border-color:#fff;}
.nl-btn{
  background:#fff;color:var(--accent);padding:13px 28px;font-size:13px;font-weight:700;
  border-radius:100px;transition:background .2s;
}
.nl-btn:hover{background:#e8edff;}

/* ===== FOOTER ===== */
footer{background:#04091a;padding:60px 48px 28px;border-top:1px solid rgba(255,255,255,.06);}
.footer-grid{display:grid;grid-template-columns:2fr 1fr 1fr 1fr;gap:40px;margin-bottom:40px;}
.footer-brand .logo{font-size:22px;margin-bottom:14px;color:#fff;}
.footer-brand p{font-size:12px;color:rgba(255,255,255,.4);line-height:1.7;max-width:240px;}
.footer-col h4{font-size:10px;letter-spacing:2.5px;text-transform:uppercase;color:var(--accent3);margin-bottom:16px;}
.footer-col ul{list-style:none;}
.footer-col li{margin-bottom:10px;}
.footer-col a{font-size:12px;color:rgba(255,255,255,.45);transition:color .2s;}
.footer-col a:hover{color:#fff;}
.footer-bottom{border-top:1px solid rgba(255,255,255,.07);padding-top:22px;display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:10px;}
.footer-bottom p{font-size:11px;color:rgba(255,255,255,.3);}

/* ===== CART SIDEBAR ===== */
#cart-overlay{position:fixed;inset:0;background:rgba(10,15,30,0.55);z-index:1000;display:none;backdrop-filter:blur(5px);}
#cart-overlay.open{display:block;}
#cart-sidebar{
  position:fixed;top:0;right:-440px;width:440px;height:100vh;
  background:var(--surface);border-left:1.5px solid var(--border);
  z-index:1001;display:flex;flex-direction:column;
  transition:right .3s cubic-bezier(.4,0,.2,1);
  box-shadow:-8px 0 40px rgba(0,0,0,0.12);
}
#cart-sidebar.open{right:0;}
.cart-header{padding:24px;border-bottom:1px solid var(--border);display:flex;align-items:center;justify-content:space-between;}
.cart-header h3{font-family:var(--font-head);font-size:20px;color:var(--dark);}
#close-cart{font-size:22px;color:var(--muted);transition:color .2s;}
#close-cart:hover{color:var(--accent2);}
#cart-items{flex:1;overflow-y:auto;padding:20px;}
.cart-empty{text-align:center;color:var(--muted);padding:60px 20px;font-size:13px;}
.cart-empty .empty-icon{font-size:50px;margin-bottom:12px;}
.cart-item{display:flex;gap:14px;padding:16px 0;border-bottom:1px solid var(--border);}
.ci-icon{font-size:34px;width:54px;height:54px;display:flex;align-items:center;justify-content:center;background:var(--bg);border-radius:12px;border:1px solid var(--border);}
.ci-info{flex:1;}
.ci-name{font-size:13px;font-weight:700;margin-bottom:3px;color:var(--dark);}
.ci-price{font-size:12px;color:var(--accent);font-weight:700;}
.ci-qty{display:flex;align-items:center;gap:8px;margin-top:8px;}
.qty-btn{width:26px;height:26px;border:1.5px solid var(--border);background:var(--bg);color:var(--dark);font-size:15px;display:flex;align-items:center;justify-content:center;border-radius:8px;transition:all .2s;}
.qty-btn:hover{background:var(--accent);color:#fff;border-color:var(--accent);}
.qty-num{font-size:13px;font-weight:700;min-width:20px;text-align:center;color:var(--dark);}
.ci-remove{color:var(--muted);font-size:16px;transition:color .2s;align-self:flex-start;}
.ci-remove:hover{color:var(--accent2);}
.cart-footer{padding:20px;border-top:1px solid var(--border);}
.cart-total{display:flex;justify-content:space-between;margin-bottom:16px;font-family:var(--font-head);font-size:18px;}
.total-label{color:var(--dark);}
.total-amount{color:var(--accent);font-weight:700;}
.checkout-btn{
  width:100%;background:var(--accent);color:#fff;
  padding:15px;font-size:13px;font-weight:700;letter-spacing:.5px;
  border-radius:100px;transition:background .2s;
  box-shadow:0 6px 24px rgba(0,71,255,0.3);
}
.checkout-btn:hover{background:#0035cc;}

/* ===== TOAST ===== */
#toast{
  position:fixed;bottom:28px;left:50%;transform:translateX(-50%) translateY(80px);
  background:var(--dark);color:#fff;
  padding:12px 28px;font-size:12px;font-weight:700;
  border-radius:100px;z-index:9999;
  transition:transform .3s ease;pointer-events:none;white-space:nowrap;
  box-shadow:0 8px 32px rgba(0,0,0,0.25);
}
#toast.show{transform:translateX(-50%) translateY(0);}

/* ===== ANIMATIONS ===== */
@keyframes fadeUp{from{opacity:0;transform:translateY(22px);}to{opacity:1;transform:translateY(0);}}

/* ===== RESPONSIVE ===== */
@media(max-width:900px){
  #hero{grid-template-columns:1fr;text-align:center;padding:60px 24px;}
  .hero-right{display:none;}
  .hero-stats{justify-content:center;}
  #hero p{margin:0 auto 36px;}
  .hero-btns{justify-content:center;}
}
@media(max-width:768px){
  nav{padding:0 20px;}
  .nav-links{display:none;}
  #brands,.deal-right{display:none;}
  section,#products,#compare,#why,#testimonials,#newsletter{padding:50px 20px;}
  .deal-left{padding:40px 24px;}
  .deal-inner{grid-template-columns:1fr;}
  .footer-grid{grid-template-columns:1fr 1fr;}
  footer{padding:40px 20px 24px;}
  #cart-sidebar{width:100%;right:-100%;}
}
</style>
</head>
<body>

<!-- NAVBAR -->
<nav>
  <div class="logo">Phone<span>Zone</span></div>
  <ul class="nav-links">
    <li><a href="#hero">Home</a></li>
    <li><a href="#products">Phones</a></li>
    <li><a href="#deal">Deals</a></li>
    <li><a href="#compare">Compare</a></li>
    <li><a href="#why">About</a></li>
  </ul>
  <div class="nav-right">
    <button id="cart-btn">🛒 Cart <span id="cart-count">0</span></button>
  </div>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-left">
    <div class="hero-tag"><span class="hero-dot"></span> New Arrivals Every Week</div>
    <h1>Your Next<br><em>Favourite</em><br>Phone Is Here.</h1>
    <p>India's most trusted online mobile store. Latest smartphones from Apple, Samsung, OnePlus, Xiaomi & more — at the best prices, guaranteed.</p>
    <div class="hero-btns">
      <a href="#products" class="btn-primary">Shop Phones →</a>
      <a href="#deal" class="btn-outline">Today's Deal</a>
    </div>
    <div class="hero-stats">
      <div class="stat-item"><div class="stat-num">200+</div><div class="stat-label">Models</div></div
