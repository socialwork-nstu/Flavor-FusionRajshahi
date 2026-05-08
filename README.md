<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>Flavor-Fusion Rajshahi | অর্ডার করুন</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: system-ui, 'Segoe UI', sans-serif; }
        body { background: #fef7e8; color: #2c3e2b; padding-bottom: 70px; }
        .navbar { background: #ff6b35; color: white; padding: 12px 20px; display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; position: sticky; top: 0; z-index: 100; }
        .logo-area { display: flex; align-items: center; gap: 10px; }
        .logo-img { width: 45px; height: 45px; background: white; border-radius: 50%; display: flex; align-items: center; justify-content: center; }
        .logo-img img { width: 100%; height: 100%; border-radius: 50%; object-fit: cover; }
        .logo-text h2 { font-size: 1.1rem; }
        .logo-text p { font-size: 0.7rem; opacity: 0.9; }
        .nav-buttons { display: flex; gap: 8px; }
        .nav-btn, .cart-icon { background: #2c3e2f; color: white; border: none; padding: 8px 14px; border-radius: 40px; cursor: pointer; font-size: 12px; transition: 0.2s; }
        .cart-icon { display: flex; align-items: center; gap: 5px; }
        .slider-container { background: linear-gradient(135deg, #ff6b35, #ffb88c); padding: 25px 20px; overflow: hidden; transition: background 0.5s; }
        .slider-content { display: flex; align-items: center; justify-content: center; gap: 20px; flex-wrap: wrap; animation: slideInRight 0.6s ease; }
        @keyframes slideInRight { from { opacity: 0; transform: translateX(100px); } to { opacity: 1; transform: translateX(0); } }
        @keyframes slideInLeft { from { opacity: 0; transform: translateX(-100px); } to { opacity: 1; transform: translateX(0); } }
        .slider-text { color: white; text-align: center; }
        .slider-text h2 { font-size: 1.6rem; text-shadow: 2px 2px 4px rgba(0,0,0,0.2); }
        .slider-img { width: 70px; height: 70px; border-radius: 50%; border: 3px solid white; box-shadow: 0 4px 12px rgba(0,0,0,0.2); animation: bounce 1s ease infinite; background: rgba(255,255,255,0.3); display: flex; align-items: center; justify-content: center; font-size: 40px; }
        @keyframes bounce { 0%,100% { transform: translateY(0); } 50% { transform: translateY(-8px); } }
        .hero { background: linear-gradient(105deg, #ffe0b5, #ffb88c); padding: 1rem; text-align: center; }
        .filter-bar { padding: 12px 16px; display: flex; flex-wrap: wrap; gap: 10px; background: white; box-shadow: 0 2px 8px rgba(0,0,0,0.05); }
        .search-box input { padding: 8px 12px; border-radius: 40px; border: 1px solid #ffb88c; width: 200px; }
        .category-filters { display: flex; gap: 8px; flex-wrap: wrap; }
        .filter-btn { background: #fff0e0; border: none; padding: 6px 14px; border-radius: 40px; cursor: pointer; transition: 0.2s; }
        .filter-btn.active, .filter-btn:hover { background: #ff6b35; color: white; }
        .products { padding: 20px 16px; max-width: 1300px; margin: auto; }
        .product-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 20px; }
        .product-card { background: white; border-radius: 24px; overflow: hidden; box-shadow: 0 4px 12px rgba(0,0,0,0.08); transition: 0.2s; position: relative; }
        .product-card:hover { transform: translateY(-4px); }
        .product-card img { width: 100%; height: 180px; object-fit: cover; }
        .product-card h3 { margin: 12px 14px 4px; font-size: 1.2rem; }
        .price { font-size: 1.4rem; font-weight: bold; color: #ff6b35; margin: 4px 14px; }
        .discount-badge { background: #e74c3c; color: white; padding: 5px 12px; border-radius: 40px; font-size: 0.75rem; font-weight: bold; display: inline-block; margin: 0 14px 8px; text-align: center; }
        .discount-badge span { background: #fff; color: #e74c3c; padding: 2px 6px; border-radius: 30px; margin-left: 6px; font-weight: bold; }
        .review-trigger { font-size: 0.75rem; margin: 4px 14px; color: #e67e22; cursor: pointer; display: inline-block; background: #fff1e0; padding: 4px 14px; border-radius: 20px; }
        .card-buttons { display: flex; gap: 10px; margin: 10px 14px 16px; }
        .btn-add, .btn-buy { flex: 1; padding: 10px 0; border-radius: 40px; font-weight: bold; border: none; cursor: pointer; transition: 0.2s; }
        .btn-add { background: #ffedd5; color: #ff6b35; border: 1px solid #ffd7a5; }
        .btn-buy { background: #ff6b35; color: white; }
        .modal { display: none; position: fixed; top:0; left:0; width:100%; height:100%; background: rgba(0,0,0,0.75); justify-content: center; align-items: center; z-index: 1000; }
        .modal-container { background: white; width: 92%; max-width: 550px; border-radius: 32px; padding: 24px; max-height: 85vh; overflow-y: auto; }
        .modal-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 20px; border-bottom: 2px solid #ffe0b5; }
        .close-modal { font-size: 32px; cursor: pointer; color: #999; }
        .form-group { margin-bottom: 18px; }
        .form-group input, .form-group textarea { width: 100%; padding: 12px 16px; border-radius: 40px; border: 1px solid #ffd6b0; font-size: 1rem; }
        .payment-option { display: flex; gap: 12px; background: #faf0e2; padding: 12px; border-radius: 60px; margin: 10px 0; flex-wrap: wrap; }
        .payment-option label { background: white; padding: 6px 18px; border-radius: 50px; cursor: pointer; display: flex; align-items: center; gap: 6px; }
        .confirm-btn { background: #2c6e2f; width: 100%; padding: 14px; border: none; color: white; border-radius: 60px; font-weight: bold; font-size: 1.1rem; margin-top: 12px; cursor: pointer; transition: 0.2s; }
        .confirm-btn:disabled { background: #aaa; cursor: not-allowed; opacity: 0.7; }
        .quantity-input { display: flex; align-items: center; gap: 12px; background: #f5f5f5; padding: 8px 15px; border-radius: 60px; justify-content: center; }
        .quantity-input button { background: #ff6b35; color: white; border: none; width: 40px; height: 40px; border-radius: 50%; font-size: 22px; cursor: pointer; }
        .quantity-input button:disabled { background: #ccc; cursor: not-allowed; }
        .quantity-input span { font-size: 1.3rem; font-weight: bold; min-width: 50px; text-align: center; }
        .price-breakdown { background: #e8f5e9; padding: 10px; border-radius: 16px; margin: 10px 0; font-size: 0.95rem; text-align: center; }
        .saved-amount { color: #27ae60; font-weight: bold; }
        .cart-item { background: #faf0e2; border-radius: 16px; padding: 10px; margin-bottom: 8px; display: flex; justify-content: space-between; align-items: center; }
        .cart-remove { background: none; border: none; color: #ff6b35; font-size: 18px; cursor: pointer; }
        .toast { position: fixed; bottom: 80px; left: 50%; transform: translateX(-50%); background: #2c6e2f; color: white; padding: 10px 24px; border-radius: 40px; z-index: 1100; animation: slideUp 0.3s ease; font-size: 14px; white-space: nowrap; }
        @keyframes slideUp { from { opacity: 0; transform: translateX(-50%) translateY(20px); } to { opacity: 1; transform: translateX(-50%) translateY(0); } }
        .order-card { background: #fef3e2; border-radius: 20px; padding: 12px; margin-bottom: 12px; border-left: 4px solid #ff6b35; }
        .review-item { border-bottom: 1px solid #eee; padding: 12px 0; }
        .star-rating { color: #f7b32b; }
        footer { background: #2d3e2b; color: #efe1c6; text-align: center; padding: 16px; margin-top: 20px; }
        .whatsapp-float { position: fixed; bottom: 20px; right: 20px; background: #25D366; color: white; width: 55px; height: 55px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 28px; text-decoration: none; z-index: 999; box-shadow: 0 4px 12px rgba(0,0,0,0.2); }
        @media (max-width: 600px) { .product-grid { grid-template-columns: 1fr; } .toast { white-space: normal; text-align: center; min-width: 200px; } }
        
        /* হালকা লোডিং স্পিনার */
        .loading-spinner {
            display: inline-block;
            width: 18px;
            height: 18px;
            border: 2px solid white;
            border-radius: 50%;
            border-top-color: transparent;
            animation: spin 0.5s linear infinite;
            margin-right: 6px;
            vertical-align: middle;
        }
        @keyframes spin {
            to { transform: rotate(360deg); }
        }
    </style>
</head>
<body>
<div class="navbar">
    <div class="logo-area">
        <div class="logo-img"><img src="https://i.ibb.co.com/twPGCqvF/FB-IMG-1778220649651-2.jpg" alt="Logo"></div>
        <div class="logo-text"><h2>Flavor-Fusion Rajshahi</h2><p>খামার থেকে বাড়ি</p></div>
    </div>
    <div class="nav-buttons">
        <button class="nav-btn" id="myOrdersBtn">📋 আমার অর্ডার</button>
        <div class="cart-icon" id="viewCartBtn">🛒 <span id="cartCount">0</span></div>
    </div>
</div>
<div class="slider-container" id="sliderContainer"><div class="slider-content" id="sliderContent"></div></div>
<div class="hero"><h1>তাজা ফলের স্বাদ</h1><p>আসল জিনিস চেনেন, ভালো জিনিস কিনেন</p></div>
<div class="filter-bar">
    <div class="search-box"><input type="text" id="searchInput" placeholder="🔍 পণ্য খুঁজুন"></div>
    <div class="category-filters">
        <button class="filter-btn active" data-cat="all">সব</button>
        <button class="filter-btn" data-cat="mango">আম</button>
        <button class="filter-btn" data-cat="lichu">লিচু</button>
        <button class="filter-btn" data-cat="jackfruit">কাঁঠাল</button>
        <button class="filter-btn" data-cat="others">অন্যান্য</button>
    </div>
</div>
<div class="products"><div class="product-grid" id="productList"></div></div>

<!-- মডাল গুলো -->
<div id="cartModal" class="modal"><div class="modal-container"><div class="modal-header"><h3>🛒 আপনার কার্ট</h3><span class="close-modal" id="closeCartBtn">&times;</span></div><div id="cartContent"></div><div class="contact-buttons" style="display:flex; gap:10px; margin-top:15px;"><a href="https://wa.me/8801758418812" target="_blank" style="flex:1; background:#25D366; color:white; padding:10px; text-align:center; border-radius:40px; text-decoration:none;">WhatsApp</a><a href="tel:8801758418812" style="flex:1; background:#2196F3; color:white; padding:10px; text-align:center; border-radius:40px; text-decoration:none;">কল করুন</a></div></div></div>
<div id="orderOptionsModal" class="modal"><div class="modal-container"><div class="modal-header"><h3>📦 অর্ডার পদ্ধতি</h3><span class="close-modal" id="closeOrderOptionsBtn">&times;</span></div><div id="orderOptionsContent"></div></div></div>
<div id="directOrderModal" class="modal"><div class="modal-container"><div class="modal-header"><h3>📦 অর্ডার ফর্ম</h3><span class="close-modal" id="closeDirectOrderBtn">&times;</span></div><div id="directOrderContent"></div></div></div>
<div id="confirmationModal" class="modal"><div class="modal-container"><div class="modal-header"><h3>✅ অর্ডার কনফার্মেশন</h3><span class="close-modal" id="closeConfirmationBtn">&times;</span></div><div id="confirmationContent"></div></div></div>
<div id="reviewModal" class="modal"><div class="modal-container"><div class="modal-header"><h3>📝 রিভিউ লিখুন/দেখুন</h3><span class="close-modal" id="closeReviewModalBtn">&times;</span></div><div id="reviewModalBody"></div></div></div>
<div id="myOrdersModal" class="modal"><div class="modal-container"><div class="modal-header"><h3>📋 আমার অর্ডার</h3><span class="close-modal" id="closeMyOrdersBtn">&times;</span></div><div id="myOrdersContent"><div style="text-align:center; padding:20px"><input type="tel" id="verifyPhoneInput" placeholder="01758418812" style="padding:12px; width:90%; border-radius:40px; border:1px solid #ffb88c;"><button id="verifyPhoneBtn" class="confirm-btn" style="margin-top:10px;">✅ অর্ডার দেখুন</button></div><div id="myOrdersList"></div></div></div></div>

<a href="https://wa.me/8801758418812?text=অর্ডার%20করতে%20চাই" class="whatsapp-float" target="_blank"><i class="fab fa-whatsapp"></i></a>
<footer><p>🍑 Flavor-Fusion Rajshahi — পেমেন্ট: bKash, Nagad, COD</p></footer>

<script>
// ============== কনফিগারেশন ================
const CUSTOM_DISCOUNTS = {
    '1_12_10': '১২+ কেজিতে ১০% ছাড়', '4_12_10': '২০+ কেজিতে ১৫% ছাড়',
    '2_12_10': '১২+ কেজিতে ৮% ছাড়', '3_12_10': '১০+ কেজিতে ১২% ছাড়',
    '5_12_10': '১২+ কেজিতে ৮ % ছাড়', '7_12_10': '১২+ কেজিতে ১০% ছাড়',
    '6_12_10': '১২+ কেজিতে ১০% ছাড়'
};
const GOOGLE_SHEET_URL = "https://script.google.com/macros/s/AKfycbxRWUVfuinB7ZMbQLUI5369QCYvLL-7guMdbE-IjioPzvhfTDUF_yaUvK22dtcEwjf1/exec";

function getDiscount(productId, kg) {
    let best = { percent: 0, minKg: 0 };
    for (let [rule] of Object.entries(CUSTOM_DISCOUNTS)) {
        let [id, minKg, percent] = rule.split('_').map(Number);
        if (id === productId && kg >= minKg && percent > best.percent) best = { percent, minKg };
    }
    return best;
}

// পণ্যের তালিকা
const products = [
    { id:1, name:"হিমসাগর আম", price:130, img:"https://i.ibb.co.com/Lh8PB5X0/Messenger-creation-7-FB83-CD1-3-C63-4-A53-8-F42-0-C8-CD61-A0230.jpg?w=400", category:"mango" },
    { id:2, name:"ল্যাংড়া আম", price:110, img:"https://i.ibb.co.com/Wv0VgwLW/Messenger-creation-F9-CE7560-9169-46-DA-815-F-BFBE1-E2-C8-C9-B.jpg?w=400", category:"mango" },
    { id:3, name:"বারি-৪ আম", price:125, img:"https://i.ibb.co.com/6R2psvd1/Messenger-creation-B4-C523-CA-BA01-4322-9-CDB-E5-AC2-F818260.jpg?w=400", category:"mango" },
    { id:4, name:"তোতাপাহারি আম", price:120, img:"https://i.ibb.co.com/V0fJJBYC/Messenger-creation-43-F0-C07-F-E7-D6-4-D98-AD49-6-D20-ED89-C17-B.jpg?w=400", category:"mango" },
    { id:5, name:"আম্রপালি আম", price:130, img:"https://i.ibb.co.com/mF9dNw7g/Messenger-creation-715-F8764-8620-4-A98-91-E5-C4-E6964-AD847.jpg?w=400", category:"mango" },
    { id:6, name:"গোবিন্দভোগ আম", price:115, img:"https://i.ibb.co.com/sdrFvmy0/Whats-App-Image-2024-05-08-at-6-13-11-PM.jpg?w=400", category:"mango" },
    { id:7, name:"গোপাল্ভোগ আম", price:110, img:"https://i.ibb.co.com/sphmPJjr/images-31.jpg?w=400", category:"mango" }
];

// লোকাল স্টোরেজ
let cart = JSON.parse(localStorage.getItem('flavor_cart')) || [];
let allOrders = JSON.parse(localStorage.getItem('flavor_orders')) || [];
let allReviews = JSON.parse(localStorage.getItem('flavor_reviews')) || {};
if (Object.keys(allReviews).length === 0) allReviews = { 1: [{ name: "রাজিব", rating: 5, comment: "অসাধারণ আম। পাকা ও মিষ্টি।", date: new Date().toLocaleString() }] };

function saveCart() { localStorage.setItem('flavor_cart', JSON.stringify(cart)); updateCartUI(); }
function saveOrders() { localStorage.setItem('flavor_orders', JSON.stringify(allOrders)); }
function saveReviews() { localStorage.setItem('flavor_reviews', JSON.stringify(allReviews)); }
function updateCartUI() { 
    let c = cart.reduce((s,i)=>s+i.kg,0); 
    document.getElementById('cartCount').innerText = c.toFixed(1); 
}

// স্লাইডার
const sliderItems = [
    { text: "🎉 ১০% ছাড়", subtext: "১২ কেজির উপরে ছাড়", icon: "🎉", bgImage: "linear-gradient(135deg,#ff6b35,#ff8c42)" },
    { text: "💰 বেশি কিনুন", subtext: "কম দামে কিনুন", icon: "💰", bgImage: "linear-gradient(135deg,#e55a2b,#ff7e5e)" },
    { text: "📦 সারাদেশে", subtext: "ডেলিভারি ১২ কেজি থেকে", icon: "🚚", bgImage: "linear-gradient(135deg,#ff6b35,#ffb347)" }
];
let slideIdx = 0, animDir = true;
function updateSlider() {
    let it = sliderItems[slideIdx];
    let cont = document.getElementById('sliderContent');
    animDir = !animDir;
    cont.style.animation = 'none';
    cont.offsetHeight;
    cont.style.animation = `${animDir ? 'slideInRight' : 'slideInLeft'} 0.5s ease`;
    cont.innerHTML = `<div class="slider-text"><h2>${it.text}</h2><p>${it.subtext}</p></div><div class="slider-img">${it.icon}</div>`;
    document.getElementById('sliderContainer').style.background = it.bgImage;
    slideIdx = (slideIdx+1)%sliderItems.length;
}
setInterval(updateSlider, 3000); updateSlider();

// পণ্য রেন্ডার
let currentFilter = "all", searchQuery = "";
function renderProducts() {
    let filtered = products.filter(p => (currentFilter==='all' || p.category===currentFilter) && (!searchQuery || p.name.toLowerCase().includes(searchQuery.toLowerCase())));
    document.getElementById('productList').innerHTML = filtered.map(p => {
        let badges = '';
        for (let [rule] of Object.entries(CUSTOM_DISCOUNTS)) {
            let [id, minKg, percent] = rule.split('_');
            if (Number(id) === p.id) badges += `<div class="discount-badge">🎉 ${minKg}+ কেজিতে <span>${percent}% ছাড়</span></div>`;
        }
        return `<div class="product-card"><img src="${p.img}" loading="lazy"><h3>${p.name}</h3><div class="price">৳${p.price}/কেজি</div>${badges}<div class="review-trigger" onclick="openReviewModal(${p.id})">⭐ রিভিউ</div><div class="card-buttons"><button class="btn-add" onclick="addToCart(${p.id})">🛒 কার্টে</button><button class="btn-buy" onclick="startOrder(${p.id})">⚡ অর্ডার</button></div></div>`;
    }).join('');
}

// কার্টে যোগ (সংক্ষিপ্ত সংস্করণ)
window.addToCart = function(pid) {
    let p = products.find(x=>x.id===pid);
    let kg = 3, type = 'campus', minKg = 3;
    let modalDiv = document.createElement('div'); modalDiv.className = 'modal'; modalDiv.style.display = 'flex';
    modalDiv.innerHTML = `<div class="modal-container"><div class="modal-header"><h3>কার্টে যোগ</h3><span class="close-modal" onclick="this.closest('.modal').remove()">&times;</span></div><div style="text-align:center"><h3>${p.name}</h3><p>৳${p.price}/কেজি</p><div style="display:flex;gap:15px;margin:20px 0"><div class="order-option" data-type="campus" style="flex:1;padding:10px;background:#ffe0b5;border-radius:24px;cursor:pointer">🏛️ ক্যাম্পাস (৩কেজি)</div><div class="order-option" data-type="nationwide" style="flex:1;padding:10px;background:#ffe0b5;border-radius:24px;cursor:pointer">🚚 দেশব্যাপী (১২কেজি)</div></div><div class="quantity-input"><button id="cm">−</button><span id="ckg">3</span><button id="cp">+</button></div><div id="cartPriceBreak"></div><button class="confirm-btn" id="cartConfirmBtn">✅ কার্টে যোগ</button></div></div>`;
    document.body.appendChild(modalDiv);
    let upd = () => {
        let disc = getDiscount(p.id, kg);
        let final = p.price * kg * (1 - disc.percent/100);
        document.getElementById('cartPriceBreak').innerHTML = `<div>মোট: ৳${final.toFixed(2)} ${disc.percent ? `(${disc.percent}% ছাড়)` : ''}</div>`;
    };
    let chg = (ch) => { let nk = kg + ch; if(nk >= minKg && nk <= 50) { kg = nk; document.getElementById('ckg').innerText = kg; upd(); } };
    modalDiv.querySelector('#cm').onclick = () => chg(-0.5);
    modalDiv.querySelector('#cp').onclick = () => chg(0.5);
    modalDiv.querySelectorAll('.order-option').forEach(opt => opt.onclick = () => {
        type = opt.dataset.type;
        minKg = (type === 'campus') ? 3 : 12;
        kg = minKg;
        document.getElementById('ckg').innerText = kg;
        upd();
    });
    modalDiv.querySelector('#cartConfirmBtn').onclick = () => {
        let disc = getDiscount(p.id, kg);
        let final = p.price * kg * (1 - disc.percent/100);
        cart.push({ id: p.id, name: p.name, kg, pricePerKg: p.price, total: final, discount: disc.percent, type });
        saveCart(); modalDiv.remove(); showToast('✓ কার্টে যোগ হয়েছে');
    };
    upd();
    modalDiv.querySelectorAll('.order-option')[0].click();
};

// কার্ট দেখানো
function showCart() {
    if(!cart.length) { document.getElementById('cartContent').innerHTML = '<div class="empty-cart">🛒 কার্ট খালি</div>'; }
    else {
        let total = 0;
        let html = cart.map((it,i)=> { total += it.total; return `<div class="cart-item"><div><strong>${it.name}</strong> (${it.kg} কেজি, ${it.type==='campus'?'🏛️ ক্যাম্পাস':'🚚 ডেলিভারি'})<br>৳${it.total} ${it.discount?`(${it.discount}% ছাড়)`:''}</div><button class="cart-remove" onclick="removeFromCart(${i})">🗑️</button></div>`; }).join('');
        html += `<div style="text-align:right; margin-top:10px;"><strong>মোট: ৳${total.toFixed(2)}</strong></div><button class="confirm-btn" onclick="checkoutCart()">✅ অর্ডার কনফার্ম</button>`;
        document.getElementById('cartContent').innerHTML = html;
    }
    document.getElementById('cartModal').style.display = 'flex';
}
window.removeFromCart = (idx) => { cart.splice(idx,1); saveCart(); showCart(); };
function checkoutCart() { if(!cart.length){ showToast('কার্ট খালি'); return; } alert('কার্ট থেকে অর্ডার শীঘ্রই আসছে'); }

// অর্ডার প্রক্রিয়া - অপটিমাইজড সংস্করণ
let currentProduct = null, currentOrderType = null, currentMinKg = 3;
let isSubmitting = false;

function startOrder(pid) { 
    currentProduct = products.find(p=>p.id===pid); 
    showOrderOptions(); 
}
function showOrderOptions() {
    document.getElementById('orderOptionsContent').innerHTML = `<div style="text-align:center"><h2>${currentProduct.name}</h2><p>৳${currentProduct.price}/কেজি</p><div style="display:flex;gap:15px;margin:20px 0"><div class="order-option" data-type="campus" style="flex:1;padding:20px;background:#ffe0b5;border-radius:24px;cursor:pointer"><span style="font-size:48px">🏛️</span><div>ক্যাম্পাস কালেক্ট</div><div>ন্যূনতম ৩ কেজি</div></div><div class="order-option" data-type="nationwide" style="flex:1;padding:20px;background:#ffe0b5;border-radius:24px;cursor:pointer"><span style="font-size:48px">🚚</span><div>দেশব্যাপী ডেলিভারি</div><div>ন্যূনতম ১২ কেজি</div></div></div></div>`;
    document.getElementById('orderOptionsModal').style.display = 'flex';
    document.querySelectorAll('.order-option').forEach(opt => opt.onclick = () => {
        currentOrderType = opt.dataset.type;
        currentMinKg = (currentOrderType === 'campus') ? 3 : 12;
        document.getElementById('orderOptionsModal').style.display = 'none';
        showOrderForm();
    });
}
function showOrderForm() {
    let kg = currentMinKg;
    let disc = getDiscount(currentProduct.id, kg);
    let final = currentProduct.price * kg * (1 - disc.percent/100);
    let html = `<div style="text-align:center"><h2>${currentProduct.name}</h2><p>৳${currentProduct.price}/কেজি</p>${disc.percent ? `<div class="discount-badge" style="background:#e74c3c;display:inline-block;">🎉 ${disc.minKg}+ কেজিতে <span>${disc.percent}% ছাড়</span></div>` : ''}<div style="background:#ff6b35;color:white;padding:8px;border-radius:40px;margin:10px 0">${currentOrderType === 'campus' ? '🏛️ ক্যাম্পাস কালেক্ট' : '🚚 দেশব্যাপী ডেলিভারি'}</div></div>
    <div class="form-group"><label>📦 কেজি (ন্যূনতম ${currentMinKg})</label><div class="quantity-input"><button id="minusBtn">−</button><span id="kgVal">${kg}</span><button id="plusBtn">+</button></div></div>
    <div id="priceBreak" class="price-breakdown"></div>
    <div class="form-group"><input type="text" id="orderName" placeholder="👤 আপনার নাম"></div>
    <div class="form-group"><input type="tel" id="orderPhone" placeholder="📞 মোবাইল নম্বর"></div>
    <div class="form-group"><textarea id="orderAddress" rows="2" placeholder="🏠 সম্পূর্ণ ঠিকানা"></textarea></div>
    <div class="payment-option"><label><input type="radio" name="payMethod" value="cod" checked> 💵 ক্যাশ অন</label><label><input type="radio" name="payMethod" value="bkash"> 📱 bKash/Nagad</label></div>
    <div id="mobilePaySec" style="display:none"><div style="background:#e84393;color:white;padding:15px;border-radius:20px;margin:10px 0"><h4>bKash/Nagad পেমেন্ট</h4><div>bKash/Nagad: 01758418812</div><input type="text" id="trxId" placeholder="TrxID" style="width:100%;margin-top:8px;padding:10px;border-radius:40px;border:none"></div></div>
    <button class="confirm-btn" id="submitOrderBtn">✅ অর্ডার করুন</button>`;
    document.getElementById('directOrderContent').innerHTML = html;
    document.getElementById('directOrderModal').style.display = 'flex';
    
    function updatePrice() {
        let k = parseFloat(document.getElementById('kgVal').innerText);
        let d = getDiscount(currentProduct.id, k);
        let orig = currentProduct.price * k;
        let save = orig * d.percent/100;
        let fin = orig - save;
        document.getElementById('priceBreak').innerHTML = `<div>মূল: ৳${orig.toFixed(2)}</div>${d.percent ? `<div style="color:#e74c3c">ছাড় (${d.percent}%): -৳${save.toFixed(2)}</div><div><strong>ছাড়后的 মূল্য: <span class="saved-amount">৳${fin.toFixed(2)}</span></strong></div><div>আপনি বাঁচাচ্ছেন: ৳${save.toFixed(2)}</div>` : `<div><strong>মোট: ৳${fin.toFixed(2)}</strong></div>`}`;
        document.getElementById('minusBtn').disabled = (k <= currentMinKg);
    }
    window.changeKgOrder = (ch) => {
        let kgSpan = document.getElementById('kgVal');
        let newKg = parseFloat(kgSpan.innerText) + ch;
        if(newKg < currentMinKg) newKg = currentMinKg;
        if(newKg > 50) newKg = 50;
        kgSpan.innerText = newKg;
        updatePrice();
    };
    document.getElementById('minusBtn').onclick = () => changeKgOrder(-0.5);
    document.getElementById('plusBtn').onclick = () => changeKgOrder(0.5);
    updatePrice();
    document.querySelectorAll('input[name="payMethod"]').forEach(r => r.onchange = () => document.getElementById('mobilePaySec').style.display = r.value === 'bkash' ? 'block' : 'none');
    
    const submitBtn = document.getElementById('submitOrderBtn');
    submitBtn.onclick = submitFinalOrder;
}

// ✅ অপটিমাইজড সাবমিট ফাংশন (দ্রুত)
window.submitFinalOrder = async function() {
    if (isSubmitting) {
        showToast('অর্ডার হচ্ছে, একটু অপেক্ষা করুন...');
        return;
    }
    
    let name = document.getElementById('orderName')?.value.trim();
    let phone = document.getElementById('orderPhone')?.value.trim();
    let addr = document.getElementById('orderAddress')?.value.trim();
    let kg = parseFloat(document.getElementById('kgVal').innerText);
    let pay = document.querySelector('input[name="payMethod"]:checked')?.value;
    let trx = '';
    
    if(pay === 'bkash') { 
        trx = document.getElementById('trxId')?.value.trim(); 
        if(!trx){ showToast('TrxID দিন'); return; } 
    } else { trx = 'COD'; }
    
    if(!name || !phone || !addr) { 
        showToast('নাম, মোবাইল ও ঠিকানা দিন'); 
        return; 
    }
    
    isSubmitting = true;
    const submitBtn = document.getElementById('submitOrderBtn');
    const originalText = submitBtn.innerHTML;
    submitBtn.disabled = true;
    submitBtn.innerHTML = '<span class="loading-spinner"></span> অর্ডার হচ্ছে...';
    
    try {
        let disc = getDiscount(currentProduct.id, kg);
        let subtotal = currentProduct.price * kg;
        let finalTotal = subtotal * (1 - disc.percent/100);
        
        let orderData = { 
            id: Date.now(), name, phone, address: addr, 
            items: [{ name: currentProduct.name, quantityKg: kg, pricePerKg: currentProduct.price, totalPrice: finalTotal, discount: disc.percent }], 
            subtotal: subtotal, total: finalTotal, paymentMethod: pay === 'bkash' ? 'bKash' : 'COD', 
            trxId: trx, date: new Date().toLocaleString(), orderType: currentOrderType
        };
        
        // দ্রুত ডাটা পাঠানো (অপেক্ষা না করে)
        fetch(GOOGLE_SHEET_URL, { method:'POST', mode:'no-cors', headers:{'Content-Type':'application/json'}, body: JSON.stringify(orderData) });
        
        allOrders.unshift(orderData); 
        saveOrders();
        
        // কনফার্মেশন দেখানো
        document.getElementById('confirmationContent').innerHTML = `<div class="confirmation-message"><div class="success-icon">✅</div><h3>অর্ডার কনফার্ম হয়েছে!</h3><div>#${orderData.id}</div><div>${name}</div><div>${kg} কেজি</div><div>মোট: ৳${finalTotal}</div><button class="confirm-btn" onclick="closeAllModals()">ঠিক আছে</button></div>`;
        document.getElementById('confirmationModal').style.display = 'flex';
        document.getElementById('directOrderModal').style.display = 'none';
        
        showToast('✅ অর্ডার সফল হয়েছে!');
        
    } catch (error) {
        showToast('⚠️ অর্ডার সংরক্ষণে সমস্যা');
    } finally {
        isSubmitting = false;
        submitBtn.disabled = false;
        submitBtn.innerHTML = originalText;
    }
};

// রিভিউ
window.openReviewModal = function(pid) {
    let prod = products.find(p=>p.id===pid);
    let revs = allReviews[pid] || [];
    document.getElementById('reviewModalBody').innerHTML = `<div><strong>🍑 ${prod.name}</strong></div><div id="reviewsList" style="max-height:200px; overflow:auto;">${revs.map(r=>`<div class="review-item"><b>${r.name}</b> <span class="star-rating">${'★'.repeat(r.rating)}${'☆'.repeat(5-r.rating)}</span><p>${r.comment}</p><small>${r.date}</small></div>`).join('')}</div><hr><h4>আপনার রিভিউ দিন</h4><div><input type="text" id="revName" placeholder="নাম"></div><div id="starSel" style="margin:10px 0"></div><textarea id="revComment" rows="3" placeholder="মন্তব্য"></textarea><button class="confirm-btn" id="submitRevBtn">⭐ পোস্ট করুন</button>`;
    let starDiv = document.getElementById('starSel');
    let selected=0;
    starDiv.innerHTML = [1,2,3,4,5].map(s=>`<span data-rate="${s}" style="font-size:28px;cursor:pointer;color:#ccc;">★</span>`).join('');
    starDiv.querySelectorAll('span').forEach(span => {
        span.onmouseover = () => { let v=parseInt(span.dataset.rate); starDiv.querySelectorAll('span').forEach((s,i)=>s.style.color=i<v ? '#f7b32b':'#ccc'); };
        span.onclick = () => { selected=parseInt(span.dataset.rate); starDiv.querySelectorAll('span').forEach((s,i)=>s.style.color=i<selected ? '#f7b32b':'#ccc'); };
    });
    document.getElementById('submitRevBtn').onclick = () => {
        let name = document.getElementById('revName').value.trim();
        let comment = document.getElementById('revComment').value.trim();
        if(!name||!comment||!selected) { alert('সব ঘর পূরণ করুন'); return; }
        let newRev = { name, rating:selected, comment, date: new Date().toLocaleString() };
        if(!allReviews[pid]) allReviews[pid]=[];
        allReviews[pid].unshift(newRev);
        saveReviews();
        document.getElementById('reviewModal').style.display='none';
        showToast('⭐ রিভিউ পোস্ট হয়েছে');
        renderProducts();
    };
    document.getElementById('reviewModal').style.display='flex';
};

// আমার অর্ডার দেখানো
document.getElementById('verifyPhoneBtn').onclick = () => {
    let phone = document.getElementById('verifyPhoneInput').value.trim();
    let orders = allOrders.filter(o=>o.phone===phone);
    let html = orders.length ? orders.map(o=>`<div class="order-card"><div><strong>#${o.id}</strong> <small>${o.date}</small></div><div>📦 ${o.items.map(i=>`${i.name} (${i.quantityKg} কেজি) ${i.discount?`- ${i.discount}% ছাড়` : ''}`).join(', ')}</div><div>💰 ৳${o.total}</div><div>🔑 ${o.trxId || 'COD'}</div></div>`).join('') : '<div class="empty-cart">কোনো অর্ডার নেই</div>';
    document.getElementById('myOrdersList').innerHTML = html;
};

function showToast(m) { 
    let t=document.createElement('div'); 
    t.className='toast'; 
    t.innerText=m; 
    document.body.appendChild(t); 
    setTimeout(()=>t.remove(), 2000); 
}
function closeAllModals() { 
    document.querySelectorAll('.modal').forEach(m=>m.style.display='none'); 
    isSubmitting = false;
}

// ইভেন্ট লিসেনার
document.getElementById('viewCartBtn').onclick = showCart;
document.getElementById('closeCartBtn').onclick = () => document.getElementById('cartModal').style.display = 'none';
document.getElementById('closeOrderOptionsBtn').onclick = () => document.getElementById('orderOptionsModal').style.display = 'none';
document.getElementById('closeDirectOrderBtn').onclick = () => document.getElementById('directOrderModal').style.display = 'none';
document.getElementById('closeConfirmationBtn').onclick = () => document.getElementById('confirmationModal').style.display = 'none';
document.getElementById('closeReviewModalBtn').onclick = () => document.getElementById('reviewModal').style.display = 'none';
document.getElementById('myOrdersBtn').onclick = () => document.getElementById('myOrdersModal').style.display = 'flex';
document.getElementById('closeMyOrdersBtn').onclick = () => document.getElementById('myOrdersModal').style.display = 'none';
document.querySelectorAll('.filter-btn').forEach(btn => btn.onclick = () => { 
    document.querySelectorAll('.filter-btn').forEach(b=>b.classList.remove('active')); 
    btn.classList.add('active'); 
    currentFilter = btn.dataset.cat; 
    renderProducts(); 
});
document.getElementById('searchInput').oninput = e => { searchQuery = e.target.value; renderProducts(); };

renderProducts(); 
updateCartUI();
</script>
</body>
</html>
