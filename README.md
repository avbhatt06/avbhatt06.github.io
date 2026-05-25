<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Custom Jewelry Boutique</title>
    <style>
        /* --- Modern Minimalist Styling --- */
        :root {
            --bg-color: #fbfbfd;
            --text-color: #1d1d1f;
            --accent-color: #8e8d8a;
            --card-bg: #ffffff;
            --border-radius: 12px;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            line-height: 1.6;
            padding-bottom: 60px;
        }

        /* --- Navigation --- */
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 5%;
            background: rgba(251, 251, 253, 0.8);
            backdrop-filter: blur(10px);
            position: sticky;
            top: 0;
            z-index: 100;
            border-bottom: 1px solid rgba(0,0,0,0.05);
        }

        .logo-slot {
            display: flex;
            align-items: center;
            gap: 15px;
            cursor: pointer;
        }

        .logo-slot img {
            width: 50px;
            height: 50px;
            object-fit: cover;
            border-radius: 50%;
            background-color: #ddd; /* Fallback placeholder */
        }

        .company-name {
            font-size: 1.2rem;
            font-weight: 600;
            letter-spacing: 1px;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 30px;
        }

        nav a {
            text-decoration: none;
            color: var(--text-color);
            font-weight: 500;
            font-size: 1rem;
            transition: color 0.3s ease;
            cursor: pointer;
        }

        nav a:hover {
            color: var(--accent-color);
        }

        /* --- Page & View Control --- */
        .view-page {
            display: none;
            max-width: 1100px;
            margin: 40px auto;
            padding: 0 20px;
            animation: fadeIn 0.4s ease forwards;
        }

        .view-page.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .back-btn {
            display: inline-block;
            margin-bottom: 20px;
            background: none;
            border: 1px solid var(--text-color);
            padding: 8px 16px;
            border-radius: 20px;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s;
        }

        .back-btn:hover {
            background-color: var(--text-color);
            color: #fff;
        }

        /* --- Hero / Landing Page --- */
        #landing-view {
            text-align: center;
            padding: 100px 20px;
        }

        #landing-view h1 {
            font-size: 3rem;
            font-weight: 300;
            margin-bottom: 20px;
            letter-spacing: -0.5px;
        }

        /* --- About Page --- */
        .about-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }

        .about-image img {
            width: 100%;
            max-height: 500px;
            object-fit: cover;
            border-radius: var(--border-radius);
            box-shadow: 0 10px 30px rgba(0,0,0,0.05);
        }

        .about-text h2 {
            font-size: 2.5rem;
            margin-bottom: 20px;
        }

        /* --- Grid Layouts (Jewelry Categories & Items) --- */
        .grid-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 30px;
            margin-top: 20px;
        }

        .grid-card {
            background: var(--card-bg);
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0,0,0,0.02);
            transition: transform 0.3s, box-shadow 0.3s;
            cursor: pointer;
            border: 1px solid rgba(0,0,0,0.03);
        }

        .grid-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 12px 25px rgba(0,0,0,0.07);
        }

        .grid-card img {
            width: 100%;
            height: 320px;
            object-fit: cover;
        }

        .grid-card-info {
            padding: 20px;
            text-align: center;
        }

        .grid-card-info h3 {
            font-size: 1.1rem;
            font-weight: 600;
        }

        /* --- Product Subpage Layout --- */
        .product-container {
            display: grid;
            grid-template-columns: 1.2fr 1fr;
            gap: 50px;
        }

        /* Dynamic Media Gallery */
        .product-gallery {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .main-product-img {
            width: 100%;
            max-height: 600px;
            object-fit: cover;
            border-radius: var(--border-radius);
        }

        .thumbnail-row {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
        }

        .thumbnail-row img {
            width: calc(20% - 8px);
            height: 80px;
            object-fit: cover;
            border-radius: 6px;
            cursor: pointer;
            border: 2px solid transparent;
            transition: border-color 0.2s;
        }

        .thumbnail-row img:hover, .thumbnail-row img.active {
            border-color: var(--text-color);
        }

        .product-details h2 {
            font-size: 2.2rem;
            margin-bottom: 15px;
            letter-spacing: -0.5px;
        }

        .product-description {
            font-size: 1.05rem;
            color: #424245;
            white-space: pre-line;
        }

        /* --- Contact Page --- */
        .contact-container {
            max-width: 600px;
            margin: 0 auto;
            text-align: center;
            background: var(--card-bg);
            padding: 40px;
            border-radius: var(--border-radius);
            box-shadow: 0 4px 20px rgba(0,0,0,0.02);
        }

        .contact-info {
            font-size: 1.1rem;
            margin-bottom: 30px;
        }

        .contact-info a {
            color: var(--accent-color);
            font-weight: 600;
        }

        .qr-section {
            border-top: 1px solid #eee;
            padding-top: 30px;
        }

        .qr-section img {
            width: 180px;
            height: 180px;
            object-fit: contain;
        }

        /* Responsive Tweak */
        @media (max-width: 768px) {
            header { flex-direction: column; gap: 15px; }
            .about-container, .product-container { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>

    <header>
        <div class="logo-slot" onclick="showView('landing-view')">
            <img src="UY BB Circular logo.JPG" alt="Company Logo" id="header-logo">
            <span class="company-name">UNIQUELY YOU BEADS AND BAUBLES</span>
        </div>
        <nav>
            <ul>
                <li><a onclick="showView('about-view')">About</a></li>
                <li><a onclick="showView('categories-view')">Jewelry</a></li>
                <li><a onclick="showView('contact-view')">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main id="landing-view" class="view-page active">
        <h1>Handcrafted, One-of-a-Kind Masterpieces</h1>
        <p>Explore luxury designed exclusively for you. Click Jewelry above to begin.</p>
    </main>

    <main id="about-view" class="view-page">
        <div class="about-container">
            <div class="about-image">
                <img src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?auto=format&fit=crop&w=600&q=80" alt="Artisan Headshot">
            </div>
            <div class="about-text">
                <h2>Behind the Craft</h2>
                <p>
                I first moved to Florida in 1982 to escape the cold and began working as a nurse. I found that creative pursuits brought me unparalleled joy. Eventually, I met a friend who was retiring from jewelry making. They showed me the ropes and I found it would be a nice pursuit for my retirement.
                As my collection grew, I started to receive many custom orders, and consequently, I now offer a wide variety of jewelry, from wearables like bracelets to accessories like purse charms. I even make jewelry for pets.
                All my jewlery is handmade. Each piece is one-of-a-kind, not just because of the small variations from being handmade, but also due to the unique materials used and patterns shaped.
                During the autumn and winter months, my creations are showcased at local Art and Craft Fairs and Festivals. I have attended Fairs and Festivals in Inverness, Orlando, World Equestrian Center, Crystal River Manatee Festival, Brooksville, The Villages, Altamonte Springs, Micanopy, McIntosh, Cedar Key, and Dunnellon. I have also registered and plan to register for many more.</p>
            </div>
        </div>
    </main>

    <main id="categories-view" class="view-page">
        <h2>Our Collections</h2>
        <div class="grid-container" id="categories-grid"></div>
    </main>

    <main id="category-items-view" class="view-page">
        <button class="back-btn" onclick="showView('categories-view')">← Back to Collections</button>
        <h2 id="current-category-title">Category Name</h2>
        <div class="grid-container" id="items-grid"></div>
    </main>

    <main id="product-subpage-view" class="view-page">
        <button class="back-btn" id="product-back-btn">← Back to Gallery</button>
        <div class="product-container">
            <div class="product-gallery">
                <img src="" alt="Product Display" class="main-product-img" id="mainDisplayImage">
                <div class="thumbnail-row" id="thumbnailRack"></div>
            </div>
            <div class="product-details">
                <h2 id="productTitle">Jewelry Title</h2>
                <div class="product-description" id="productDescription">
                    Jewelry item description text asset goes here.
                </div>
            </div>
        </div>
    </main>

    <main id="contact-view" class="view-page">
        <div class="contact-container">
            <h2>Get In Touch</h2>
            <div class="contact-info">
                <p>Have questions about sizing, pricing, or custom design commissions?</p><br>
                <p>Email: <a href="mailto:Mary.uniquelyubb@gmail.com">Mary.uniquelyubb@gmail.com</a></p>
                <p>Instagram: <a href="https://instagram.com" target="_blank">@AuraCustomJewelry</a></p>
                <p>Phone: (555) 123-4567</p>
            </div>
            <div class="qr-section" id="qrContainer">
                <p style="margin-bottom: 15px; font-size: 0.9rem; color:#777;">Scan to save contact card</p>
                <img src="https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=https://github.com" alt="Contact QR Code" id="contactQrCode">
            </div>
        </div>
    </main>

    <script>
        /* ==========================================
           DATA STORAGE
           ========================================== */
        const jewelryData = {
            categories: [
                {
                    id: "necklaces",
                    name: "Necklaces",
                    image: "https://images.unsplash.com/photo-1599643478518-a784e5dc4c8f?auto=format&fit=crop&w=400&q=80",
                    items: [
                        {
                            id: "n1",
                            title: "Raw Emerald Pendant",
                            description: "A stunning raw Brazilian emerald wrapped beautifully in hand-spun 14k gold fill wire. Hangs on an 18-inch delicate gold chain.",
                            images: [
                                "https://images.unsplash.com/photo-1599643478518-a784e5dc4c8f?auto=format&fit=crop&w=600&q=80",
                                "https://images.unsplash.com/photo-1605100804763-247f67b3557e?auto=format&fit=crop&w=600&q=80"
                            ]
                        }
                    ]
                },
                {
                    id: "bracelets",
                    name: "Bracelets",
                    image: "https://images.unsplash.com/photo-1611591437281-460bfbe1220a?auto=format&fit=crop&w=400&q=80",
                    items: [
                        {
                            id: "b1",
                            title: "Silver Obsidian Cuff",
                            description: "Hand-forged sterling silver featuring a highly polished geometric midnight obsidian stone insert.",
                            images: [
                                "https://images.unsplash.com/photo-1611591437281-460bfbe1220a?auto=format&fit=crop&w=600&q=80"
                            ]
                        }
                    ]
                },
                {
                    id: "canine-necklaces",
                    name: "Canine Necklaces",
                    image: "https://images.unsplash.com/photo-1576201836106-db1758fd1c97?auto=format&fit=crop&w=400&q=80",
                    items: [
                        {
                            id: "cn1",
                            title: "The Regal Leather & Brass Collar",
                            description: "Top-grain genuine custom dyed leather embedded safely with polished solid brass studs and hardware rings.",
                            images: [
                                "https://images.unsplash.com/photo-1576201836106-db1758fd1c97?auto=format&fit=crop&w=600&q=80"
                            ]
                        }
                    ]
                },
                 {
                    id: "earrings",
                    name: "Earrings",
                    image: "https://images.unsplash.com/photo-1599643478518-a784e5dc4c8f?auto=format&fit=crop&w=400&q=80",
                    items: [
                        {
                            id: "e1",
                            title: "Raw Emerald Pendant",
                            description: "A stunning raw Brazilian emerald wrapped beautifully in hand-spun 14k gold fill wire. Hangs on an 18-inch delicate gold chain.",
                            images: [
                                "https://images.unsplash.com/photo-1599643478518-a784e5dc4c8f?auto=format&fit=crop&w=600&q=80",
                                "https://images.unsplash.com/photo-1605100804763-247f67b3557e?auto=format&fit=crop&w=600&q=80"
                            ]
                        }
                    ]
                },
                 {
                    id: "eyeglass-lanyards",
                    name: "Eyeglass Lanyards",
                    image: "https://images.unsplash.com/photo-1576201836106-db1758fd1c97?auto=format&fit=crop&w=400&q=80",
                    items: [
                        {
                            id: "el1",
                            title: "The Regal Leather & Brass Collar",
                            description: "Top-grain genuine custom dyed leather embedded safely with polished solid brass studs and hardware rings.",
                            images: [
                                "https://images.unsplash.com/photo-1576201836106-db1758fd1c97?auto=format&fit=crop&w=600&q=80"
                            ]
                        }
                    ]
                },
                 {
                    id: "id-lanyards",
                    name: "ID Lanyards",
                    image: "https://images.unsplash.com/photo-1576201836106-db1758fd1c97?auto=format&fit=crop&w=400&q=80",
                    items: [
                        {
                            id: "idl1",
                            title: "The Regal Leather & Brass Collar",
                            description: "Top-grain genuine custom dyed leather embedded safely with polished solid brass studs and hardware rings.",
                            images: [
                                "https://images.unsplash.com/photo-1576201836106-db1758fd1c97?auto=format&fit=crop&w=600&q=80"
                            ]
                        }
                    ]
                },
                 {
                    id: "cellphone-lanyards",
                    name: "Cellphone Lanyards",
                    image: "https://images.unsplash.com/photo-1576201836106-db1758fd1c97?auto=format&fit=crop&w=400&q=80",
                    items: [
                        {
                            id: "cl1",
                            title: "The Regal Leather & Brass Collar",
                            description: "Top-grain genuine custom dyed leather embedded safely with polished solid brass studs and hardware rings.",
                            images: [
                                "https://images.unsplash.com/photo-1576201836106-db1758fd1c97?auto=format&fit=crop&w=600&q=80"
                            ]
                        }
                    ]
                },
                 {
                    id: "purse-charms",
                    name: "Purse Charms",
                    image: "https://images.unsplash.com/photo-1576201836106-db1758fd1c97?auto=format&fit=crop&w=400&q=80",
                    items: [
                        {
                            id: "pc1",
                            title: "The Regal Leather & Brass Collar",
                            description: "Top-grain genuine custom dyed leather embedded safely with polished solid brass studs and hardware rings.",
                            images: [
                                "https://images.unsplash.com/photo-1576201836106-db1758fd1c97?auto=format&fit=crop&w=600&q=80"
                            ]
                        }
                    ]
                },
                 {
                    id: "otherbeadedaccessories",
                    name: "Other Beaded Accessories",
                    image: "https://images.unsplash.com/photo-1576201836106-db1758fd1c97?auto=format&fit=crop&w=400&q=80",
                    items: [
                        {
                            id: "oba1",
                            title: "The Regal Leather & Brass Collar",
                            description: "Top-grain genuine custom dyed leather embedded safely with polished solid brass studs and hardware rings.",
                            images: [
                                "https://images.unsplash.com/photo-1576201836106-db1758fd1c97?auto=format&fit=crop&w=600&q=80"
                            ]
                        }
                    ]
                }
            ]
        };

        /* ==========================================
           ROUTING & CORE APP LOGIC
           ========================================== */
        function showView(viewId) {
            document.querySelectorAll('.view-page').forEach(page => {
                page.classList.remove('active');
            });
            document.getElementById(viewId).classList.add('active');
            window.scrollTo(0,0);
        }

        document.addEventListener("DOMContentLoaded", () => {
            renderCategories();
            checkOptionalElements();
        });

        function checkOptionalElements() {
            const qrImg = document.getElementById('contactQrCode');
            const qrContainer = document.getElementById('qrContainer');
            if(!qrImg.getAttribute('src') || qrImg.getAttribute('src') === "") {
                qrContainer.style.display = 'none';
            }
        }

        function renderCategories() {
            const container = document.getElementById('categories-grid');
            container.innerHTML = "";
            
            jewelryData.categories.forEach(cat => {
                const card = document.createElement('div');
                card.className = 'grid-card';
                card.onclick = () => openCategory(cat.id);
                card.innerHTML = `
                    <img src="${cat.image}" alt="${cat.name}">
                    <div class="grid-card-info">
                        <h3>${cat.name}</h3>
                    </div>
                `;
                container.appendChild(card);
            });
        }

        function openCategory(catId) {
            const category = jewelryData.categories.find(c => c.id === catId);
            if(!category) return;

            document.getElementById('current-category-title').innerText = category.name;
            const container = document.getElementById('items-grid');
            container.innerHTML = "";

            category.items.forEach(item => {
                const card = document.createElement('div');
                card.className = 'grid-card';
                card.onclick = () => openProduct(category.id, item.id);
                card.innerHTML = `
                    <img src="${item.images[0]}" alt="${item.title}">
                    <div class="grid-card-info">
                        <h3>${item.title}</h3>
                    </div>
                `;
                container.appendChild(card);
            });

            showView('category-items-view');
        }

        function openProduct(catId, itemId) {
            const category = jewelryData.categories.find(c => c.id === catId);
            const item = category.items.find(i => i.id === itemId);
            if(!item) return;

            document.getElementById('product-back-btn').onclick = () => openCategory(catId);
            document.getElementById('productTitle').innerText = item.title;
            document.getElementById('productDescription').innerText = item.description;

            const mainImg = document.getElementById('mainDisplayImage');
            mainImg.src = item.images[0];

            const thumbRack = document.getElementById('thumbnailRack');
            thumbRack.innerHTML = "";

            const limit = Math.min(item.images.length, 10);
            
            if(limit > 1) {
                for(let i = 0; i < limit; i++) {
                    const thumb = document.createElement('img');
                    thumb.src = item.images[i];
                    if(i === 0) thumb.className = 'active';
                    
                    thumb.onclick = function() {
                        mainImg.src = this.src;
                        document.querySelectorAll('.thumbnail-row img').forEach(img => img.classList.remove('active'));
                        this.classList.add('active');
                    };
                    thumbRack.appendChild(thumb);
                }
            }

            showView('product-subpage-view');
        }
    </script>
</body>
</html>
