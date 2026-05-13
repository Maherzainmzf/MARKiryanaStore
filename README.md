# MARKiryanaStore
Utility Store For Everything
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Abdul Razzaq Kiryana Store | Bahawalpur's Trusted Grocer since 2009</title>
    <meta name="description" content="Your neighbourhood kiryana store in Main Bazaar, Bahawalpur. Fresh groceries, authentic spices, basmati rice, daily essentials with free delivery above Rs. 5,000.">
    <meta name="keywords" content="kiryana store bahawalpur, grocery delivery, basmati rice, chakki atta, desi ghee, online grocery">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: system-ui, 'Segoe UI', 'Roboto', 'Helvetica Neue', sans-serif;
        }

        body {
            background-color: #fefaf5;
            color: #2c2518;
            scroll-behavior: smooth;
        }

        /* header / top bar */
        .top-bar {
            background-color: #2a5c3e;
            color: #fef7e0;
            padding: 8px 20px;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
            font-size: 14px;
            gap: 10px;
        }
        .top-bar span {
            display: inline-flex;
            align-items: center;
            gap: 6px;
        }
        .delivery-badge {
            background-color: #e67e22;
            padding: 4px 12px;
            border-radius: 30px;
            font-weight: bold;
            font-size: 13px;
        }

        /* main header */
        .main-header {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: space-between;
            padding: 15px 25px;
            background: white;
            border-bottom: 1px solid #f0e2cf;
            box-shadow: 0 2px 8px rgba(0,0,0,0.02);
            position: sticky;
            top: 0;
            z-index: 100;
            background-color: #ffffffdd;
            backdrop-filter: blur(4px);
        }
        .logo h1 {
            font-size: 1.8rem;
            color: #2a5c3e;
            letter-spacing: -0.5px;
        }
        .logo p {
            font-size: 0.75rem;
            color: #b87333;
            font-weight: 500;
        }
        .cart-icon {
            position: relative;
            cursor: pointer;
            background: #fdf3e6;
            padding: 8px 18px;
            border-radius: 50px;
            display: flex;
            align-items: center;
            gap: 8px;
            font-weight: bold;
            border: 1px solid #e9dacb;
            transition: all 0.2s;
        }
        .cart-count {
            background: #e67e22;
            color: white;
            border-radius: 30px;
            padding: 2px 8px;
            font-size: 14px;
        }
        /* cart sidebar */
        .cart-sidebar {
            position: fixed;
            top: 0;
            right: -420px;
            width: 380px;
            max-width: 90vw;
            height: 100vh;
            background: white;
            box-shadow: -5px 0 20px rgba(0,0,0,0.15);
            z-index: 1000;
            transition: right 0.3s ease;
            display: flex;
            flex-direction: column;
            padding: 20px;
            border-left: 1px solid #eedcc7;
        }
        .cart-sidebar.open {
            right: 0;
        }
        .cart-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 2px solid #f3e1cf;
            padding-bottom: 12px;
            font-size: 1.5rem;
            font-weight: bold;
        }
        .close-cart {
            font-size: 28px;
            cursor: pointer;
        }
        .cart-items-list {
            flex: 1;
            overflow-y: auto;
            margin: 15px 0;
        }
        .cart-item {
            display: flex;
            justify-content: space-between;
            padding: 12px 0;
            border-bottom: 1px solid #f5e8dc;
        }
        .cart-total {
            font-size: 1.3rem;
            font-weight: bold;
            border-top: 2px dashed #f0dbc8;
            padding-top: 15px;
            margin-top: 10px;
        }
        .checkout-btn {
            background: #2a5c3e;
            color: white;
            border: none;
            padding: 14px;
            font-size: 1.1rem;
            border-radius: 40px;
            margin-top: 15px;
            cursor: pointer;
            font-weight: bold;
        }
        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.4);
            z-index: 999;
            display: none;
        }
        nav {
            padding: 12px 25px;
            background: #fff7ef;
            display: flex;
            gap: 28px;
            flex-wrap: wrap;
            border-bottom: 1px solid #f0e2cf;
        }
        nav a {
            text-decoration: none;
            color: #3e2a1f;
            font-weight: 600;
        }
        .hero {
            background: linear-gradient(95deg, #f8efdf 0%, #fff5ea 100%);
            padding: 35px 25px;
            text-align: center;
        }
        .hero h2 {
            font-size: 2.2rem;
            color: #1f4d34;
        }
        .badges {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 28px;
            margin-top: 25px;
        }
        .badge-item {
            background: white;
            padding: 8px 20px;
            border-radius: 40px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.03);
            font-weight: 500;
        }
        .category-title {
            font-size: 2rem;
            margin: 35px 25px 15px 25px;
            border-left: 8px solid #e67e22;
            padding-left: 18px;
        }
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
            gap: 24px;
            padding: 15px 25px 40px 25px;
        }
        .product-card {
            background: white;
            border-radius: 28px;
            padding: 18px 14px 18px 14px;
            box-shadow: 0 6px 14px rgba(0,0,0,0.05);
            transition: transform 0.1s ease;
            border: 1px solid #f3e5d7;
        }
        .product-title {
            font-weight: 800;
            font-size: 1.15rem;
        }
        .product-unit {
            font-size: 0.75rem;
            color: #9b7a5c;
            margin: 5px 0;
        }
        .price {
            font-weight: bold;
            font-size: 1.3rem;
            color: #2a5c3e;
            margin-top: 8px;
        }
        .add-btn {
            background: #e67e22;
            border: none;
            color: white;
            padding: 8px 18px;
            border-radius: 32px;
            font-weight: bold;
            margin-top: 12px;
            cursor: pointer;
            width: 100%;
        }
        .about {
            background: #f7efe4;
            margin: 20px 25px 30px 25px;
            padding: 30px 25px;
            border-radius: 48px;
            display: flex;
            flex-wrap: wrap;
            gap: 30px;
            justify-content: space-between;
        }
        .footer {
            background: #1f3c2c;
            color: #eedbc8;
            padding: 30px 20px;
            text-align: center;
        }
        @media (max-width: 680px) {
            .main-header { flex-direction: column; gap: 12px; }
            .cart-icon { align-self: flex-end; }
        }
        button { cursor: pointer; }
        .whatsapp-order {
            background: #25d366;
            color: white;
            border-radius: 40px;
            padding: 10px 20px;
            border: none;
            font-weight: bold;
            margin-left: 10px;
        }
        .trust-badge {
            background: #fef0e3;
            display: inline-block;
            padding: 6px 18px;
            border-radius: 60px;
            font-size: 13px;
        }
    </style>
</head>
<body>

<div class="overlay" id="overlay"></div>
<div class="cart-sidebar" id="cartSidebar">
    <div class="cart-header">
        <span>🛒 Your Cart</span>
        <span class="close-cart" id="closeCartBtn">&times;</span>
    </div>
    <div class="cart-items-list" id="cartItemsList">
        <div style="text-align:center; color:#b87333;">Your cart is empty</div>
    </div>
    <div class="cart-total" id="cartTotal">Total: Rs. 0</div>
    <button class="checkout-btn" id="checkoutBtn">📞 Proceed to Order (WhatsApp)</button>
    <p style="font-size: 12px; margin-top: 10px; text-align:center;">Free delivery above Rs. 5,000</p>
</div>

<div class="top-bar">
    <span>📍 Main Bazaar, Bahawalpur</span>
    <span>⏰ Open: 7am – 11pm Daily</span>
    <span>📞 0301-1234567</span>
    <span class="delivery-badge">🚚 Free Delivery above Rs.5,000</span>
</div>

<div class="main-header">
    <div class="logo">
        <h1>عبدالرزاق عبدالرزاق<br><span style="font-size:1.2rem;">Abdul Razzaq Kiryana Store</span></h1>
        <p>روزانہ کی ضروریات، بہترین قیمت پر</p>
    </div>
    <div class="cart-icon" id="cartIcon">
        <span>🛒</span>
        <span>Cart</span>
        <span class="cart-count" id="cartItemCount">0</span>
    </div>
</div>

<nav>
    <a href="#">Home</a>
    <a href="#products">Shop by Category</a>
    <a href="#about">About Us</a>
    <a href="#contact">Contact</a>
    <span class="trust-badge">✅ 100% Fresh & Quality Guaranteed</span>
</nav>

<div class="hero">
    <h2>Your neighbourhood grocery store — fresh stock, honest prices, fast service</h2>
    <div class="badges">
        <div class="badge-item">📦 200+ Products</div>
        <div class="badge-item">👨‍👩‍👧‍👦 500+ Daily Customers</div>
        <div class="badge-item">⭐ 15+ Years Serving</div>
        <div class="badge-item">🏆 Best Prices in Bahawalpur</div>
    </div>
</div>

<h2 class="category-title" id="products">🛍️ Shop by Category · 22 products</h2>

<div class="products-grid" id="productsGrid">
    <!-- products will be injected from JS, also static fallback -->
</div>

<div class="about" id="about">
    <div><strong>📖 About Our Store</strong><br>Abdul Razzaq Kiryana Store has been serving the families of Bahawalpur for over 15 years. Located in Main Bazaar, we offer the freshest groceries, finest spices, and daily essentials at prices you can trust.</div>
    <div>🕌 <strong>Serving Since 2009</strong><br>A trusted name in Bahawalpur</div>
    <div>🤝 <strong>Honest Pricing</strong><br>Transparent prices, no hidden charges</div>
    <div>🚚 <strong>Home Delivery</strong><br>Quick delivery within Bahawalpur city</div>
</div>

<div class="footer" id="contact">
    <p>📍 Main Bazaar, Bahawalpur, Punjab &nbsp;|&nbsp; 📞 0301-1234567 &nbsp;|&nbsp; ⏰ Open 7am–11pm</p>
    <p>⭐ Trusted by 10,000+ families in Bahawalpur ⭐</p>
    <p style="margin-top: 12px;">© 2026 Abdul Razzaq Kiryana Store — Freshness & honesty since 2009</p>
</div>

<script>
    // ---------- PRODUCT DATABASE (exactly the same items shown on original page)
    const products = [
        { id: 1, name: "Basmati Rice (Super Kernel)", unit: "Premium aged Super Kernel Basmati – 5kg", price: 1450, tag: "Best Seller" },
        { id: 2, name: "Wheat Flour (Chakki Atta)", unit: "Whole wheat chakki atta – 10kg", price: 1100, tag: "" },
        { id: 3, name: "Fine White Sugar", unit: "Pure granulated sugar – 5kg", price: 700, tag: "" },
        { id: 4, name: "Iodized Salt (Pink Himalayan)", unit: "Pink Himalayan rock salt – 1kg", price: 120, tag: "Local Pride" },
        { id: 5, name: "Moong Dal (Yellow)", unit: "Yellow split moong lentils – 1kg", price: 280, tag: "" },
        { id: 6, name: "Chana Dal (Split Chickpeas)", unit: "Split chickpea dal – 1kg", price: 240, tag: "" },
        { id: 7, name: "Masoor Dal (Red Lentils)", unit: "Red split lentils – 1kg", price: 260, tag: "" },
        { id: 8, name: "Cooking Oil (Canola)", unit: "Pure canola cooking oil – 5 litre", price: 2800, tag: "New Stock" },
        { id: 9, name: "Pure Desi Ghee", unit: "Buffalo milk desi ghee – 1kg", price: 1800, tag: "Premium" },
        { id: 10, name: "Tapal Danedar Black Tea", unit: "Bold black tea – 500g", price: 580, tag: "Popular" },
        { id: 11, name: "Nido Milk Powder (Full Cream)", unit: "Full cream milk powder – 400g", price: 850, tag: "" },
        { id: 12, name: "Turmeric Powder (Haldi)", unit: "Pure ground turmeric – 200g", price: 90, tag: "" },
        { id: 13, name: "Red Chilli Powder (Lal Mirch)", unit: "Ground red chilli powder – 200g", price: 110, tag: "" },
        { id: 14, name: "Garam Masala Mix", unit: "Whole spice blend – 100g", price: 150, tag: "" },
        { id: 15, name: "Surf Excel Detergent", unit: "Stain-removing detergent powder – 1kg", price: 370, tag: "Daily Need" },
        { id: 16, name: "Safeguard Soap Bar", unit: "Antibacterial soap – Pack of 4", price: 480, tag: "" },
        { id: 17, name: "Parle-G Biscuits", unit: "Classic glucose biscuits – 500g pack", price: 130, tag: "" },
        { id: 18, name: "Lays Classic Chips (Salty)", unit: "Salted potato chips – 48g", price: 50, tag: "" },
        { id: 19, name: "National Ketchup", unit: "Tomato ketchup – 800g", price: 290, tag: "" },
        { id: 20, name: "Shaan Biryani Masala", unit: "Ready-mix biryani spice – 60g", price: 65, tag: "Fan Favourite" },
        { id: 21, name: "Nestle Fruita Vitals (Mango)", unit: "Mango juice drink – 1 litre", price: 120, tag: "" },
        { id: 22, name: "Maida (All-Purpose Flour)", unit: "All-purpose white flour – 5kg", price: 720, tag: "" }
    ];

    let cart = [];

    // Helper Functions
    function saveCart() {
        localStorage.setItem('kiryanaCart', JSON.stringify(cart));
    }
    function loadCart() {
        const saved = localStorage.getItem('kiryanaCart');
        if(saved) {
            try {
                cart = JSON.parse(saved);
            } catch(e) { cart = []; }
        }
        renderCartUI();
        updateCartIcon();
    }

    function updateCartIcon() {
        const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);
        document.getElementById('cartItemCount').innerText = totalItems;
    }

    function addToCart(product, quantity = 1) {
        const existing = cart.find(item => item.id === product.id);
        if(existing) {
            existing.quantity += quantity;
        } else {
            cart.push({ ...product, quantity: quantity });
        }
        saveCart();
        renderCartUI();
        updateCartIcon();
    }

    function removeFromCart(productId) {
        cart = cart.filter(item => item.id !== productId);
        saveCart();
        renderCartUI();
        updateCartIcon();
    }

    function updateQuantity(productId, newQty) {
        if(newQty <= 0) {
            removeFromCart(productId);
            return;
        }
        const item = cart.find(i => i.id === productId);
        if(item) item.quantity = newQty;
        saveCart();
        renderCartUI();
        updateCartIcon();
    }

    function renderCartUI() {
        const container = document.getElementById('cartItemsList');
        const totalSpan = document.getElementById('cartTotal');
        if(!container) return;
        if(cart.length === 0) {
            container.innerHTML = '<div style="text-align:center; padding: 20px; color:#b87333;">🛒 Your cart is empty<br>Add some items from the store!</div>';
            totalSpan.innerText = 'Total: Rs. 0';
            return;
        }
        let total = 0;
        let html = '';
        cart.forEach(item => {
            const itemTotal = item.price * item.quantity;
            total += itemTotal;
            html += `
                <div class="cart-item">
                    <div><strong>${item.name}</strong><br>${item.unit}<br>Rs. ${item.price} x ${item.quantity}</div>
                    <div style="display: flex; gap: 8px; align-items:center;">
                        <button style="background:#f0d8c2; border:none; border-radius:20px; padding:4px 8px;" onclick="window.updateQuantityExternal(${item.id}, ${item.quantity-1})">-</button>
                        <span>${item.quantity}</span>
                        <button style="background:#e67e22; border:none; border-radius:20px; padding:4px 8px; color:white;" onclick="window.updateQuantityExternal(${item.id}, ${item.quantity+1})">+</button>
                        <button style="background:#ac3e2f; border:none; border-radius:30px; padding:4px 8px; color:white;" onclick="window.removeFromCartExternal(${item.id})">🗑️</button>
                    </div>
                    <div>Rs. ${itemTotal}</div>
                </div>
            `;
        });
        container.innerHTML = html;
        totalSpan.innerText = `Total: Rs. ${total}`;
    }

    window.updateQuantityExternal = function(id, newQty) {
        updateQuantity(id, newQty);
    };
    window.removeFromCartExternal = function(id) {
        removeFromCart(id);
    };

    function renderProducts() {
        const grid = document.getElementById('productsGrid');
        if(!grid) return;
        let html = '';
        products.forEach(p => {
            let tagHtml = p.tag ? `<span style="background: #fbd5a2; padding: 2px 12px; border-radius: 30px; font-size: 0.7rem; font-weight:bold;">${p.tag}</span><br>` : '';
            html += `
                <div class="product-card">
                    ${tagHtml}
                    <div class="product-title">${p.name}</div>
                    <div class="product-unit">${p.unit}</div>
                    <div class="price">Rs. ${p.price}</div>
                    <button class="add-btn" data-id="${p.id}" data-name="${p.name.replace(/'/g, "\\'")}" data-unit="${p.unit.replace(/'/g, "\\'")}" data-price="${p.price}">➕ Add to Cart</button>
                </div>
            `;
        });
        grid.innerHTML = html;
        // attach events
        document.querySelectorAll('.add-btn').forEach(btn => {
            btn.addEventListener('click', (e) => {
                const id = parseInt(btn.dataset.id);
                const name = btn.dataset.name;
                const unit = btn.dataset.unit;
                const price = parseInt(btn.dataset.price);
                const product = { id, name, unit, price };
                addToCart(product, 1);
                // give subtle feedback
                btn.innerText = '✓ Added!';
                setTimeout(() => { btn.innerText = '➕ Add to Cart'; }, 800);
            });
        });
    }

    // Cart sidebar logic
    const cartIconBtn = document.getElementById('cartIcon');
    const cartSidebar = document.getElementById('cartSidebar');
    const overlayDiv = document.getElementById('overlay');
    const closeBtn = document.getElementById('closeCartBtn');

    function openCart() {
        cartSidebar.classList.add('open');
        overlayDiv.style.display = 'block';
    }
    function closeCart() {
        cartSidebar.classList.remove('open');
        overlayDiv.style.display = 'none';
    }
    cartIconBtn?.addEventListener('click', openCart);
    closeBtn?.addEventListener('click', closeCart);
    overlayDiv?.addEventListener('click', closeCart);

    // whatsapp order integration
    const checkoutButton = document.getElementById('checkoutBtn');
    checkoutButton?.addEventListener('click', () => {
        if(cart.length === 0) {
            alert('Your cart is empty. Add items first!');
            return;
        }
        let message = "🛒 *Abdul Razzaq Kiryana Store Order*%0A";
        let total = 0;
        cart.forEach(item => {
            const itemTotal = item.price * item.quantity;
            total += itemTotal;
            message += `✓ ${item.name} (${item.unit}) x ${item.quantity} = Rs. ${itemTotal}%0A`;
        });
        message += `%0A📦 *Total Amount: Rs. ${total}*%0A`;
        message += `🚚 Delivery: ${total >= 5000 ? 'FREE (above Rs.5000)' : 'Rs. 150 (below 5000)'}%0A`;
        message += `📍 Address: Main Bazaar, Bahawalpur%0A`;
        message += `📞 Contact: 0301-1234567%0A`;
        message += `_Order via Abdul Razzaq Store_`;
        const phone = "923001234567"; // pakistan format without + (replace with actual 0301-1234567 -> 923011234567 but the store number 0301-1234567)
        const whatsappNumber = "923011234567";
        const url = `https://wa.me/${whatsappNumber}?text=${message}`;
        window.open(url, '_blank');
    });
    
    // initial load
    loadCart();
    renderProducts();
    // fix external functions for global access again
    window.renderCartUI = renderCartUI;
    window.updateCartIcon = updateCartIcon;

    // handle anchor links for nav
    document.querySelectorAll('nav a').forEach(link => {
        link.addEventListener('click', (e) => {
            const href = link.getAttribute('href');
            if(href && href.startsWith('#')) {
                e.preventDefault();
                const targetId = href.substring(1);
                const target = document.getElementById(targetId);
                if(target) target.scrollIntoView({ behavior: 'smooth' });
            }
        });
    });
</script>
</body>
</html>
