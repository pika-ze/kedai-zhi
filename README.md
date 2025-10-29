<!doctype html>
<html lang="ms">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Z.H.I | Kedai Pakaian Online</title>
  <meta name="description" content="Z.H.I — Kedai baju demo (HTML/CSS/JS) siap untuk GitHub Pages" />
  <style>
    :root{
      --bg:#0b1220; --panel:#0f1724; --muted:#9aa6b2; --accent:#0ea5e9; --accent-2:#60a5fa;
      --glass: rgba(255,255,255,0.03); --card:#0b1624; --text:#e6eef6; --success:#10b981; --danger:#ef4444;
      font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Poppins", Arial;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0; background: linear-gradient(180deg,var(--bg),#071025); color:var(--text);
      -webkit-font-smoothing:antialiased; -moz-osx-font-smoothing:grayscale; padding-bottom:90px;
    }
    a{color:inherit;text-decoration:none}
    .wrap{max-width:1120px;margin:18px auto;padding:16px}
    header{display:flex;align-items:center;justify-content:space-between;gap:12px;padding:6px 0}
    .brand{display:flex;gap:12px;align-items:center}
    .logo {
      width:56px;height:56px;border-radius:10px;
      background: linear-gradient(135deg,var(--accent),var(--accent-2));
      display:flex;align-items:center;justify-content:center;font-weight:800;font-size:18px;color:#022;
      box-shadow:0 8px 28px rgba(2,6,23,0.6);
    }
    nav{display:flex;gap:8px;align-items:center;flex-wrap:wrap}
    .nav-btn{background:transparent;border:0;color:var(--muted);padding:8px 12px;border-radius:10px;cursor:pointer}
    .nav-btn.active{background:var(--glass);color:var(--text)}
    .small{font-size:13px}
    main{margin-top:14px}
    .hero{background:linear-gradient(90deg, rgba(255,255,255,0.02), transparent);border-radius:12px;padding:18px;border:1px solid rgba(255,255,255,0.03);display:flex;gap:18px;align-items:center}
    .grid{display:grid;grid-template-columns:repeat(3,1fr);gap:16px;margin-top:14px}
    .card{background:linear-gradient(180deg, rgba(255,255,255,0.02), transparent);padding:12px;border-radius:12px;border:1px solid rgba(255,255,255,0.03)}
    .thumb{height:220px;border-radius:10px;background-size:cover;background-position:center;box-shadow:0 10px 30px rgba(2,6,23,0.6)}
    .muted{color:var(--muted);font-size:13px}
    .pill{background:rgba(255,255,255,0.02);padding:6px 8px;border-radius:999px;border:1px solid rgba(255,255,255,0.02)}
    .page{display:none}
    .page.active{display:block}
    button.primary{background:linear-gradient(90deg,var(--accent),var(--accent-2));border:0;color:#022;padding:8px 12px;border-radius:10px;font-weight:700;cursor:pointer}
    button.ghost{background:transparent;border:1px solid rgba(255,255,255,0.03);color:var(--muted);padding:6px 10px;border-radius:8px;cursor:pointer}
    input,select,textarea{width:100%;padding:10px;border-radius:8px;border:1px solid rgba(255,255,255,0.06);background:transparent;color:var(--text);margin-top:8px}
    textarea{min-height:90px;resize:vertical}
    .cart-list{display:flex;flex-direction:column;gap:12px}
    .cart-row{display:flex;gap:12px;align-items:center;padding:10px;border-radius:8px;background:rgba(255,255,255,0.02)}
    .cart-row img{width:72px;height:72px;border-radius:8px;object-fit:cover}
    .order-card{padding:12px;border-radius:10px;background:rgba(255,255,255,0.02);border:1px solid rgba(255,255,255,0.03)}
    .receipt{background:linear-gradient(180deg,#071126,#081427);padding:12px;border-radius:8px;border:1px solid rgba(255,255,255,0.04)}
    .table{background:rgba(255,255,255,0.02);padding:12px;border-radius:8px;max-height:380px;overflow:auto}
    footer{margin-top:20px;color:var(--muted);font-size:13px}
    .whatsapp{position:fixed;right:18px;bottom:18px;background:linear-gradient(45deg,#25D366,#12b886);width:64px;height:64px;border-radius:999px;display:flex;align-items:center;justify-content:center;box-shadow:0 8px 24px rgba(2,6,23,0.6);z-index:70;cursor:pointer}
    @media (max-width:980px){.grid{grid-template-columns:repeat(2,1fr)}}
    @media (max-width:640px){.grid{grid-template-columns:1fr};header{flex-direction:column;align-items:stretch}}
    .right{margin-left:auto}
    .text-muted{color:var(--muted)}
    .hidden{display:none}
    /* small tweaks for upload to GitHub Pages */
    .container-center{max-width:1120px;margin:0 auto;padding:12px}
  </style>
</head>
<body>
  <div class="wrap container-center">
    <header>
      <div class="brand">
        <div class="logo">Z.H.I</div>
        <div>
          <div style="font-weight:800">Z.H.I</div>
          <div class="small muted">Kedai Baju</div>
        </div>
      </div>

      <nav id="nav">
        <button class="nav-btn active" data-page="home">Home</button>
        <button class="nav-btn" data-page="shop">Shop</button>
        <button class="nav-btn" data-page="cart">My Order <span id="nav-count" class="pill" style="margin-left:8px">0</span></button>
        <button class="nav-btn" data-page="orders">Orders</button>
        <button class="nav-btn" data-page="admin">Admin</button>
        <button id="btn-login" class="nav-btn">Login / Register</button>
      </nav>
    </header>

    <main>
      <!-- HOME -->
      <section id="home" class="page active">
        <div class="hero">
          <div style="flex:1">
            <h2 style="margin:0">Selamat Datang ke Z.H.I — Koleksi Moden</h2>
            <div class="small muted" style="margin-top:6px">Tambah ke troli & checkout (simulasi) — FPX / Online Banking / Touch 'n Go</div>
            <div style="margin-top:12px"><button class="primary" id="shop-now">Shop Sekarang</button></div>
          </div>
          <div style="width:320px">
            <div class="card">
              <div style="display:flex;gap:12px;align-items:center">
                <div style="width:64px;height:64px;border-radius:8px;background:url('https://images.unsplash.com/photo-1520975692532-2f5f1c6f2a93?q=80&w=600&auto=format&fit=crop') center/cover"></div>
                <div>
                  <div style="font-weight:700">Promo Istimewa</div>
                  <div class="muted small">Diskaun & penghantaran pantas</div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <h3 style="margin-top:18px">Koleksi</h3>
        <div id="product-grid" class="grid"></div>
      </section>

      <!-- SHOP -->
      <section id="shop" class="page">
        <h3>Semua Produk</h3>
        <div id="product-grid-2" class="grid"></div>
      </section>

      <!-- CART -->
      <section id="cart" class="page">
        <h3>Troli Anda</h3>
        <div style="display:flex;gap:12px;flex-wrap:wrap">
          <div style="flex:2">
            <div id="cart-list" class="cart-list"></div>
          </div>
          <div style="flex:1">
            <div class="order-card">
              <div style="font-weight:700">Ringkasan</div>
              <div class="small muted" id="summary-items">0 item</div>
              <div style="display:flex;justify-content:space-between;margin-top:8px"><div class="small muted">Subtotal</div><div id="summary-sub">RM0.00</div></div>
              <div style="display:flex;justify-content:space-between;margin-top:6px"><div class="small muted">Penghantaran</div><div id="summary-ship">RM5.00</div></div>
              <hr style="margin:12px 0;border-color:rgba(255,255,255,0.03)" />
              <div style="display:flex;justify-content:space-between;font-weight:700"><div>Jumlah</div><div id="summary-total">RM0.00</div></div>
              <div style="margin-top:12px">
                <div class="small muted">Pilih Pembayaran</div>
                <select id="checkout-method" style="margin-top:8px">
                  <option value="fpx">FPX</option>
                  <option value="bank">Online Banking</option>
                  <option value="tng">Touch 'n Go</option>
                </select>
                <button class="primary" id="btn-checkout" style="width:100%;margin-top:12px">Bayar & Hantar Pesanan</button>
                <div id="receipt-area" style="margin-top:12px"></div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- CHECKOUT -->
      <section id="checkout" class="page">
        <h3>Butiran Penghantaran</h3>
        <div style="display:flex;gap:12px;flex-wrap:wrap">
          <div style="flex:1;min-width:280px">
            <label>Nama Penuh</label>
            <input id="ship-name" placeholder="Nama penuh" />
            <label>Email</label>
            <input id="ship-email" placeholder="email@contoh.com" />
            <label>Telefon</label>
            <input id="ship-phone" placeholder="+60 12 345 6789" />
            <label>Alamat</label>
            <textarea id="ship-address" placeholder="Alamat lengkap"></textarea>
            <label>Catatan (optional)</label>
            <input id="ship-note" placeholder="Catatan" />
          </div>
          <div style="width:360px">
            <div class="order-card">
              <div style="font-weight:700">Sahkan Pesanan</div>
              <div class="small muted" id="co-subitems">0 item</div>
              <div style="display:flex;justify-content:space-between;margin-top:8px"><div class="small muted">Jumlah</div><div id="co-total">RM0.00</div></div>
              <div style="margin-top:12px">
                <button class="primary" id="co-pay" style="width:100%">Bayar Sekarang</button>
              </div>
              <div id="co-receipt" style="margin-top:12px"></div>
            </div>
          </div>
        </div>
      </section>

      <!-- ORDERS -->
      <section id="orders" class="page">
        <h3>Pesanan (Sejarah)</h3>
        <div id="orders-list" class="table"></div>
      </section>

      <!-- ADMIN -->
      <section id="admin" class="page">
        <h3>Admin Panel</h3>
        <div class="order-card">
          <div style="display:flex;gap:8px;align-items:center;flex-wrap:wrap">
            <div class="small muted">Log masuk admin</div>
            <input id="admin-user" placeholder="admin" style="width:140px" />
            <input id="admin-pass" placeholder="password" style="width:160px" type="password" />
            <button class="ghost" id="admin-login-btn">Log Masuk Admin</button>
            <button class="ghost" id="admin-logout-btn" style="display:none">Logout Admin</button>
            <div class="right" id="admin-actions" style="display:none">
              <button class="ghost" id="export-csv">Export CSV</button>
              <button class="ghost" id="export-json">Export JSON</button>
              <button class="ghost" id="clear-orders">Clear Orders</button>
            </div>
          </div>
          <div id="admin-orders" style="margin-top:12px" class="table"></div>
        </div>
      </section>
    </main>

    <footer>
      <div style="display:flex;justify-content:space-between;align-items:center;gap:12px">
        <div>© <span id="year"></span> Z.H.I</div>
        <div class="small muted">Dibuat oleh anda</div>
      </div>
    </footer>
  </div>

  <!-- Modal -->
  <div id="modal" style="display:none;position:fixed;inset:0;background:rgba(8, 15, 53, 0.6);align-items:center;justify-content:center;z-index:80">
    <div style="width:920px;max-width:96%;background:linear-gradient(180deg,#071126,#081427);padding:16px;border-radius:12px;border:1px solid rgba(255,255,255,0.04);display:flex;gap:14px;color:var(--text)">
      <div style="flex:1">
        <div id="modal-img" style="height:320px;border-radius:8px;background-size:cover;background-position:center"></div>
      </div>
      <div style="width:360px">
        <div style="display:flex;justify-content:space-between;align-items:center"><div id="modal-title" style="font-weight:700"></div><button id="modal-close" class="ghost">✕</button></div>
        <div class="small muted" id="modal-cat"></div>
        <div style="margin-top:12px;font-weight:800" id="modal-price"></div>
        <div class="small muted" id="modal-desc" style="margin-top:8px"></div>
        <div style="margin-top:12px">
          <label>Saiz</label>
          <select id="modal-size"><option>S</option><option>M</option><option>L</option><option>XL</option></select>
        </div>
        <div style="margin-top:12px;display:flex;gap:8px;align-items:center">
          <div style="display:flex;gap:8px;align-items:center">
            <button id="qty-decr" class="ghost">−</button>
            <div id="qty-num" class="pill">1</div>
            <button id="qty-incr" class="ghost">+</button>
          </div>
          <button class="primary" id="modal-add" style="margin-left:auto">Tambah ke Troli</button>
        </div>
      </div>
    </div>
  </div>

  <!-- WhatsApp quick link -->
  <a class="whatsapp" id="wa-link" title="WhatsApp Customer Service" target="_blank" rel="noreferrer">
    <svg width="28" height="28" viewBox="0 0 24 24" fill="none"><path d="M21 11.5A9.5 9.5 0 1 1 11.5 2 9.5 9.5 0 0 1 21 11.5z" stroke="#fff" stroke-width="1.2" stroke-linecap="round" stroke-linejoin="round"/><path d="M17.5 17.5L15 15" stroke="#fff" stroke-width="1.2" stroke-linecap="round"/></svg>
  </a>

<script>
/* -------------------------
  Single-file Z.H.I store
  Client-only (localStorage)
  Simulated payments only
  ------------------------- */

const WHATSAPP_NUMBER_RAW = '01136114911';
const WHATSAPP_INTL = '60' + WHATSAPP_NUMBER_RAW.replace(/^0+/, '');
const WHATSAPP_MESSAGE = encodeURIComponent('Hai, saya perlukan bantuan mengenai pesanan di Z.H.I Store.');
const WHATSAPP_URL = `https://wa.me/${WHATSAPP_INTL}?text=${WHATSAPP_MESSAGE}`;

const ADMIN_CREDENTIALS = { user:'pika', pass:'pika-ze' };

const SAMPLE_PRODUCTS = [
  { id:'p1', title:'T-Shirt Classic', price:49.90, category:'T-Shirt', img:'https://images.unsplash.com/photo-1520975692532-2f5f1c6f2a93?q=80&w=800&auto=format&fit=crop', desc:'Material cotton lembut.'},
  { id:'p2', title:'Blouse Elegant', price:59.90, category:'Blouse', img:'https://images.unsplash.com/photo-1520975973792-44a6f9b2a2a6?q=80&w=800&auto=format&fit=crop', desc:'Potongan moden.'},
  { id:'p3', title:'Hoodie Cozy', price:99.90, category:'Hoodie', img:'https://images.unsplash.com/photo-1541099649105-f69ad21f3246?q=80&w=800&auto=format&fit=crop', desc:'Hoodie zip yang selesa.'},
  { id:'p4', title:'Dress Floral', price:89.90, category:'Dress', img:'https://images.unsplash.com/photo-1503342452485-86f7b4a0b6a4?q=80&w=800&auto=format&fit=crop', desc:'Elegant untuk majlis.'},
  { id:'p5', title:'Jeans Slim Fit', price:79.90, category:'Jeans', img:'https://images.unsplash.com/photo-1514996937319-344454492b37?q=80&w=800&auto=format&fit=crop', desc:'Jeans berkualiti.'},
  { id:'p6', title:'Cap Casual', price:29.90, category:'Aksesori', img:'https://images.unsplash.com/photo-1540574163026-643ea20ade25?q=80&w=800&auto=format&fit=crop', desc:'Topi adjustable.'}
];

const KEYS = { CART:'zhi_cart', ORDERS:'zhi_orders', ADMIN:'zhi_admin' };
const state = {
  products: SAMPLE_PRODUCTS.slice(),
  cart: JSON.parse(localStorage.getItem(KEYS.CART) || '[]'),
  orders: JSON.parse(localStorage.getItem(KEYS.ORDERS) || '[]'),
  adminLogged: (localStorage.getItem(KEYS.ADMIN) === '1')
};

const $ = (s, r=document) => r.querySelector(s);
const $$ = (s, r=document) => Array.from(r.querySelectorAll(s));
const money = v => 'RM' + Number(v).toFixed(2);
const save = ()=> { localStorage.setItem(KEYS.CART, JSON.stringify(state.cart)); localStorage.setItem(KEYS.ORDERS, JSON.stringify(state.orders)); localStorage.setItem(KEYS.ADMIN, state.adminLogged ? '1' : '0'); };

function init(){
  $('#year').textContent = new Date().getFullYear();
  $('#wa-link').href = WHATSAPP_URL;
  renderProducts('#product-grid'); renderProducts('#product-grid-2');
  renderCart(); renderOrders(); renderAdminOrders(); refreshNavCount();
  attachEvents(); setAdminUI();
}

function renderProducts(target='#product-grid'){
  const root = $(target); if(!root) return; root.innerHTML = '';
  state.products.forEach(p=>{
    const d = document.createElement('div'); d.className='card';
    d.innerHTML = `
      <div class="thumb" style="background-image:url('${p.img}')"></div>
      <h4 style="margin:8px 0 4px">${escapeHtml(p.title)}</h4>
      <div class="small muted">${escapeHtml(p.category)}</div>
      <div style="display:flex;justify-content:space-between;align-items:center;margin-top:8px">
        <div style="font-weight:800">${money(p.price)}</div>
        <div style="display:flex;gap:8px">
          <button class="ghost view" data-id="${p.id}">Lihat</button>
          <button class="primary add" data-id="${p.id}">+Troli</button>
        </div>
      </div>`;
    root.appendChild(d);
  });
}

/* modal */
let modalProduct=null, modalQty=1;
function openModal(id){
  modalProduct = state.products.find(x=>x.id===id); if(!modalProduct) return;
  $('#modal').style.display='flex';
  $('#modal-img').style.backgroundImage = `url('${modalProduct.img}')`;
  $('#modal-title').textContent = modalProduct.title;
  $('#modal-cat').textContent = modalProduct.category;
  $('#modal-price').textContent = money(modalProduct.price);
  $('#modal-desc').textContent = modalProduct.desc;
  modalQty=1; $('#qty-num').textContent=modalQty; $('#modal-size').value='M';
}
function closeModal(){ $('#modal').style.display='none'; }

/* cart */
function addToCart(id, size='M', qty=1){
  const p = state.products.find(x=>x.id===id); if(!p) return;
  const key = id+'::'+size;
  const ex = state.cart.find(i=>i.key===key);
  if(ex) ex.qty += qty; else state.cart.push({ key, id, title:p.title, price:p.price, size, qty, img:p.img });
  save(); refreshNavCount(); renderCart();
}
function removeFromCart(key){ state.cart = state.cart.filter(i=>i.key!==key); save(); refreshNavCount(); renderCart(); }
function updateCartQty(key, qty){ const it = state.cart.find(i=>i.key===key); if(!it) return; it.qty = Math.max(1, qty); save(); refreshNavCount(); renderCart(); }
function cartSubtotal(){ return state.cart.reduce((s,i)=>s + i.qty*i.price, 0); }
function refreshNavCount(){ const q = state.cart.reduce((s,i)=>s+i.qty,0); $('#nav-count').textContent = q; }

/* render cart */
function renderCart(){
  const list = $('#cart-list'); list.innerHTML=''; $('#receipt-area').innerHTML='';
  if(state.cart.length===0){ list.innerHTML = '<div class="small muted">Troli kosong.</div>'; $('#summary-sub').textContent=money(0); $('#summary-ship').textContent=money(0); $('#summary-total').textContent=money(0); $('#summary-items').textContent='0 item'; return; }
  state.cart.forEach(item=>{
    const row = document.createElement('div'); row.className='cart-row';
    row.innerHTML = `
      <img src="${item.img}" alt="${escapeHtml(item.title)}" />
      <div style="flex:1">
        <div style="font-weight:700">${escapeHtml(item.title)}</div>
        <div class="small muted">Saiz: ${escapeHtml(item.size)}</div>
        <div class="small muted">Harga: ${money(item.price)}</div>
      </div>
      <div style="text-align:right">
        <div style="display:flex;align-items:center;gap:8px;justify-content:flex-end">
          <button class="ghost decr" data-key="${item.key}">−</button>
          <div class="pill">${item.qty}</div>
          <button class="ghost incr" data-key="${item.key}">+</button>
        </div>
        <div style="margin-top:8px;font-weight:700">${money(item.qty*item.price)}</div>
        <div style="margin-top:8px"><button class="ghost remove" data-key="${item.key}">Buang</button></div>
      </div>`;
    list.appendChild(row);
  });
  const subtotal = cartSubtotal(); const shipping = subtotal>0?5.00:0.00;
  $('#summary-sub').textContent=money(subtotal); $('#summary-ship').textContent=money(shipping); $('#summary-total').textContent=money(subtotal+shipping);
  $('#summary-items').textContent = `${state.cart.length} item`;
}

/* checkout & orders */
function openCheckout(){
  if(state.cart.length===0){ navigateTo('shop'); return; }
  $('#co-subitems').textContent = `${state.cart.length} item`;
  $('#co-total').textContent = money(cartSubtotal() + (cartSubtotal()>0?5:0));
  navigateTo('checkout');
}
function placeOrder(){
  if(state.cart.length===0) return;
  const name = $('#ship-name').value.trim(); const phone = $('#ship-phone').value.trim(); const address = $('#ship-address').value.trim();
  if(!name||!phone||!address){ $('#co-receipt').innerHTML = '<div class="small muted">Sila lengkapkan Nama, Telefon & Alamat.</div>'; return; }
  const payMethod = $('#checkout-method').value || 'fpx'; const subtotal = cartSubtotal(); const shipping = subtotal>0?5:0; const total = subtotal+shipping;
  const order = { id:'ZHI'+Date.now(), date:new Date().toISOString(), items: JSON.parse(JSON.stringify(state.cart)), subtotal, shipping, total, payMethod, name, phone, address, note: $('#ship-note').value||'', status:'pending' };
  $('#co-receipt').innerHTML = `<div class="small muted">Memproses pembayaran (${payMethod.toUpperCase()})... Sila tunggu.</div>`;
  setTimeout(()=> {
    order.status = 'paid'; state.orders.push(order); save();
    $('#co-receipt').innerHTML = renderReceipt(order); $('#receipt-area').innerHTML = renderReceipt(order);
    setTimeout(()=> { state.cart = []; save(); refreshNavCount(); renderCart(); navigateTo('orders'); renderOrders(); }, 1200);
  }, 900);
}
function renderReceipt(order){
  const itemsHtml = order.items.map(it=>`<div style="display:flex;justify-content:space-between"><div>${escapeHtml(it.title)} x ${it.qty}</div><div>${money(it.price*it.qty)}</div></div>`).join('');
  return `<div class="receipt"><div style="font-weight:800">Resit — ${order.id}</div><div class="small muted">${new Date(order.date).toLocaleString()}</div><div style="margin-top:8px">${itemsHtml}</div><hr style="margin:8px 0;border-color:rgba(255,255,255,0.03)"/><div style="display:flex;justify-content:space-between"><div class="small muted">Subtotal</div><div>${money(order.subtotal)}</div></div><div style="display:flex;justify-content:space-between"><div class="small muted">Penghantaran</div><div>${money(order.shipping)}</div></div><div style="display:flex;justify-content:space-between;font-weight:800"><div>Jumlah</div><div>${money(order.total)}</div></div><div style="margin-top:8px" class="small muted">Kaedah: ${order.payMethod.toUpperCase()}</div></div>`;
}
function renderOrders(){ const out = $('#orders-list'); out.innerHTML=''; if(state.orders.length===0){ out.innerHTML='<div class="small muted">Tiada pesanan dibuat lagi.</div>'; return; } state.orders.slice().reverse().forEach(o=>{ const node = document.createElement('div'); node.className='order-card'; node.style.marginBottom='10px'; node.innerHTML = `<div style="display:flex;justify-content:space-between;align-items:center"><div><div style="font-weight:700">Pesanan: ${o.id}</div><div class="small muted">${new Date(o.date).toLocaleString()}</div></div><div style="text-align:right"><div style="font-weight:700">${money(o.total)}</div><div class="small muted">Status: ${o.status}</div></div></div><div style="margin-top:8px" class="small muted">Nama: ${escapeHtml(o.name)} • Tel: ${escapeHtml(o.phone)}</div><div style="margin-top:8px">${ o.items.map(it=>`<div style="display:flex;justify-content:space-between"><div>${escapeHtml(it.title)} x ${it.qty}</div><div>${money(it.price*it.qty)}</div></div>`).join('') }</div>`; out.appendChild(node); }); }

/* admin */
function setAdminUI(){ if(state.adminLogged){ $('#admin-logout-btn').style.display='inline-block'; $('#admin-login-btn').style.display='none'; $('#admin-user').style.display='none'; $('#admin-pass').style.display='none'; $('#admin-actions').style.display='inline-block'; } else { $('#admin-logout-btn').style.display='none'; $('#admin-login-btn').style.display='inline-block'; $('#admin-user').style.display='inline-block'; $('#admin-pass').style.display='inline-block'; $('#admin-actions').style.display='none'; } renderAdminOrders(); }
function adminLogin(){ const u = $('#admin-user').value.trim(); const p = $('#admin-pass').value; if(u===ADMIN_CREDENTIALS.user && p===ADMIN_CREDENTIALS.pass){ state.adminLogged=true; save(); setAdminUI(); navigateTo('admin'); } else { $('#admin-orders').innerHTML = '<div class="small muted">Kredensial admin tidak betul.</div>'; } }
function adminLogout(){ state.adminLogged=false; save(); setAdminUI(); $('#admin-orders').innerHTML=''; }
function renderAdminOrders(){ const root = $('#admin-orders'); root.innerHTML=''; if(!state.adminLogged){ root.innerHTML='<div class="small muted">Sila log masuk sebagai admin untuk lihat pesanan.</div>'; return; } if(state.orders.length===0){ root.innerHTML='<div class="small muted">Tiada pesanan.</div>'; return; } const frag = document.createElement('div'); state.orders.slice().reverse().forEach(o=>{ const r = document.createElement('div'); r.style.borderBottom='1px solid rgba(255,255,255,0.03)'; r.style.padding='8px 4px'; r.innerHTML = `<div style="display:flex;justify-content:space-between;align-items:center"><div><div style="font-weight:700">${o.id} • ${new Date(o.date).toLocaleString()}</div><div class="small muted">Nama: ${escapeHtml(o.name)} • Tel: ${escapeHtml(o.phone)} • Kaedah: ${escapeHtml(o.payMethod)}</div></div><div style="text-align:right"><div style="font-weight:700">${money(o.total)}</div><div style="display:flex;gap:8px;margin-top:6px;justify-content:flex-end"><button class="ghost admin-view" data-id="${o.id}">View</button><button class="ghost admin-delete" data-id="${o.id}">Padam</button></div></div></div>`; frag.appendChild(r); }); root.appendChild(frag); }
function adminDeleteOrder(id){ state.orders = state.orders.filter(o=>o.id!==id); save(); renderAdminOrders(); renderOrders(); }
function adminViewOrder(id){ const ord = state.orders.find(o=>o.id===id); if(!ord) return; const root = $('#admin-orders'); root.insertAdjacentHTML('afterbegin', renderReceipt(ord)); setTimeout(()=>{ const el = root.querySelector('.receipt'); if(el) el.remove(); }, 2600); }

/* export */
function exportOrdersCSV(){ if(state.orders.length===0) return; const rows=[]; state.orders.forEach(o=> o.items.forEach(it=> rows.push({order_id:o.id,date:o.date,name:o.name,phone:o.phone,address:o.address,pay_method:o.payMethod,product:it.title,qty:it.qty,price_each:it.price,line_total:it.price*it.qty,subtotal:o.subtotal,shipping:o.shipping,total:o.total,status:o.status, note:o.note||''}))); const header = Object.keys(rows[0]); const csv = [header.join(',')].concat(rows.map(r=> header.map(h=>`"${String(r[h]||'').replace(/"/g,'""')}"`).join(','))).join('\n'); const blob=new Blob([csv],{type:'text/csv;charset=utf-8;'}); const url=URL.createObjectURL(blob); const a=document.createElement('a'); a.href=url; a.download=`zhi_orders_${Date.now()}.csv`; document.body.appendChild(a); a.click(); a.remove(); URL.revokeObjectURL(url); }
function exportOrdersJSON(){ if(state.orders.length===0) return; const data=JSON.stringify(state.orders,null,2); const blob=new Blob([data],{type:'application/json'}); const url=URL.createObjectURL(blob); const a=document.createElement('a'); a.href=url; a.download=`zhi_orders_${Date.now()}.json`; document.body.appendChild(a); a.click(); a.remove(); URL.revokeObjectURL(url); }
function clearAllOrders(){ state.orders=[]; save(); renderAdminOrders(); renderOrders(); }

/* events */
function attachEvents(){
  $$('#nav .nav-btn').forEach(btn=> btn.addEventListener('click', ()=>{ $$('#nav .nav-btn').forEach(b=>b.classList.remove('active')); btn.classList.add('active'); const pg=btn.dataset.page; if(pg) showPage(pg); }));
  $('#shop-now').addEventListener('click', ()=> navigateTo('shop'));
  document.body.addEventListener('click', e=> {
    const t = e.target;
    if(t.matches('.view')) openModal(t.dataset.id);
    if(t.matches('.add')) addToCart(t.dataset.id,'M',1);
    if(t.id==='modal-close') closeModal();
    if(t.id==='qty-incr') { modalQty++; $('#qty-num').textContent=modalQty; }
    if(t.id==='qty-decr') { modalQty=Math.max(1,modalQty-1); $('#qty-num').textContent=modalQty; }
    if(t.id==='modal-add') { if(modalProduct) { addToCart(modalProduct.id, $('#modal-size').value||'M', modalQty); closeModal(); } }
    if(t.matches('.incr')) { updateCartQty(t.dataset.key, (state.cart.find(i=>i.key===t.dataset.key).qty||1)+1); }
    if(t.matches('.decr')) { updateCartQty(t.dataset.key, (state.cart.find(i=>i.key===t.dataset.key).qty||1)-1); }
    if(t.matches('.remove')) { removeFromCart(t.dataset.key); }
    if(t.id==='btn-checkout') openCheckout();
    if(t.id==='co-pay') placeOrder();
    if(t.id==='btn-login') navigateTo('orders');
    if(t.id==='admin-login-btn') adminLogin();
    if(t.id==='admin-logout-btn') adminLogout();
    if(t.id==='export-csv') exportOrdersCSV();
    if(t.id==='export-json') exportOrdersJSON();
    if(t.id==='clear-orders') clearAllOrders();
    if(t.matches('.admin-delete')) adminDeleteOrder(t.dataset.id);
    if(t.matches('.admin-view')) adminViewOrder(t.dataset.id);
  });
  $('#modal').addEventListener('click', (e)=> { if(e.target === $('#modal')) closeModal(); });
  $('#admin-pass').addEventListener('keydown', (e)=> { if(e.key==='Enter') adminLogin(); });
  $('#btn-checkout').addEventListener('click', ()=> { /* copy method to checkout page */ const method = $('#checkout-method').value; /* prefill checkout form with empty or first user info */ $('#ship-name').value=''; $('#ship-phone').value=''; $('#ship-address').value=''; $('#ship-email').value=''; openCheckout(); });
  $('#co-pay').addEventListener('click', placeOrder);
  $('#export-csv').addEventListener('click', exportOrdersCSV);
  $('#export-json').addEventListener('click', exportOrdersJSON);
  $('#clear-orders').addEventListener('click', clearAllOrders);
  window.addEventListener('beforeunload', ()=> save());
}

/* navigation */
function showPage(id){ $$('.page').forEach(p=>p.classList.remove('active')); const el = document.getElementById(id); if(el) el.classList.add('active'); if(id==='cart') renderCart(); if(id==='orders') renderOrders(); if(id==='admin') renderAdminOrders(); }
function navigateTo(page){ const btn = $$('#nav .nav-btn').find(b=>b.dataset.page===page); if(btn){ $$('#nav .nav-btn').forEach(b=>b.classList.remove('active')); btn.classList.add('active'); showPage(page); } }

/* util */
function escapeHtml(str){ return String(str||'').replace(/[&<>"']/g, s=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":"&#39;"}[s])); }

/* init app */
init();
</script>
</body>
</html>
