<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mogra Inspired Designs | Modern Silhouette</title>
    <style>
        /* --- RESET & VARIABLES --- */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Playfair Display', 'Didot', 'Georgia', serif;
        }

        :root {
            --primary-color: #1a1a1a;
            --accent-color: #8c765c;
            --bg-light: #fbf9f6;
            --text-muted: #666;
            --white: #ffffff;
            --transition: all 0.3s ease;
        }

        body {
            background-color: var(--bg-light);
            color: var(--primary-color);
            overflow-x: hidden;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        /* --- ANNOUNCEMENT BAR --- */
        .announcement-bar {
            background-color: var(--primary-color);
            color: var(--white);
            text-align: center;
            padding: 8px 10px;
            font-size: 0.8rem;
            letter-spacing: 2px;
            text-transform: uppercase;
        }

        /* --- HEADER & NAVIGATION --- */
        header {
            background: rgba(251, 249, 246, 0.95);
            position: sticky;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid rgba(0,0,0,0.05);
            backdrop-filter: blur(5px);
        }

        .nav-container {
            max-width: 1300px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            letter-spacing: 3px;
            text-transform: uppercase;
        }

        .logo span {
            font-weight: 300;
            color: var(--accent-color);
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 30px;
        }

        .nav-links a {
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1.5px;
            font-weight: 500;
            transition: var(--transition);
        }

        .nav-links a:hover {
            color: var(--accent-color);
        }

        .nav-icons {
            display: flex;
            gap: 20px;
            font-size: 1.2rem;
            cursor: pointer;
        }

        /* --- HERO SECTION --- */
        .hero {
            height: 75vh;
            background: linear-gradient(rgba(0,0,0,0.2), rgba(0,0,0,0.3)), url('https://images.unsplash.com/photo-1610030469668-93535c17b6b3?auto=format&fit=crop&w=1600&q=80') center/cover no-repeat;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: var(--white);
            padding: 0 20px;
        }

        .hero-content h1 {
            font-size: 3.5rem;
            margin-bottom: 15px;
            font-weight: 400;
            letter-spacing: 2px;
        }

        .hero-content p {
            font-size: 1.2rem;
            margin-bottom: 30px;
            font-weight: 300;
            letter-spacing: 1px;
        }

        .btn {
            display: inline-block;
            padding: 12px 35px;
            background-color: var(--white);
            color: var(--primary-color);
            text-transform: uppercase;
            font-size: 0.85rem;
            letter-spacing: 2px;
            font-weight: 600;
            border: 1px solid transparent;
            transition: var(--transition);
            cursor: pointer;
        }

        .btn:hover {
            background-color: transparent;
            color: var(--white);
            border-color: var(--white);
        }

        /* --- CATEGORIES SECTION --- */
        .section-title {
            text-align: center;
            margin: 60px 0 40px;
        }

        .section-title h2 {
            font-size: 2.2rem;
            font-weight: 400;
            letter-spacing: 1px;
            position: relative;
            display: inline-block;
            padding-bottom: 10px;
        }

        .section-title h2::after {
            content: '';
            position: absolute;
            width: 50%;
            height: 1px;
            background: var(--accent-color);
            bottom: 0;
            left: 25%;
        }

        .categories-grid {
            max-width: 1300px;
            margin: 0 auto 60px;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
            padding: 0 20px;
        }

        .category-card {
            position: relative;
            height: 400px;
            overflow: hidden;
            cursor: pointer;
        }

        .category-card img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.7s ease;
        }

        .category-card:hover img {
            transform: scale(1.05);
        }

        .category-overlay {
            position: absolute;
            inset: 0;
            background: linear-gradient(to top, rgba(0,0,0,0.6), transparent);
            display: flex;
            align-items: flex-end;
            padding: 30px;
        }

        .category-overlay h3 {
            color: var(--white);
            font-size: 1.5rem;
            font-weight: 400;
            letter-spacing: 1px;
        }

        /* --- PRODUCT GRID --- */
        .product-container {
            max-width: 1300px;
            margin: 0 auto 80px;
            padding: 0 20px;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }

        .product-card {
            background: var(--white);
            border: 1px solid rgba(0,0,0,0.02);
            transition: var(--transition);
        }

        .product-image-wrapper {
            position: relative;
            overflow: hidden;
            height: 380px;
        }

        .product-image-wrapper img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .product-card:hover .product-image-wrapper img {
            transform: scale(1.02);
        }

        .add-to-cart-btn {
            position: absolute;
            bottom: -50px;
            left: 0;
            width: 100%;
            background: rgba(26, 26, 26, 0.9);
            color: var(--white);
            text-align: center;
            padding: 15px;
            text-transform: uppercase;
            font-size: 0.8rem;
            letter-spacing: 1px;
            transition: var(--transition);
        }

        .product-card:hover .add-to-cart-btn {
            bottom: 0;
        }

        .product-info {
            padding: 20px;
            text-align: center;
        }

        .product-title {
            font-size: 1.1rem;
            font-weight: 400;
            margin-bottom: 8px;
        }

        .product-price {
            font-family: sans-serif;
            color: var(--accent-color);
            font-size: 1rem;
            font-weight: 600;
        }

        /* --- FOOTER --- */
        footer {
            background-color: var(--primary-color);
            color: #ccc;
            padding: 60px 20px 20px;
            font-size: 0.9rem;
        }

        .footer-content {
            max-width: 1300px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            border-bottom: 1px solid #333;
            padding-bottom: 40px;
        }

        .footer-section h4 {
            color: var(--white);
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 20px;
            font-size: 1rem;
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section ul li {
            margin-bottom: 10px;
        }

        .footer-section ul li a:hover {
            color: var(--white);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 20px;
            font-size: 0.8rem;
            letter-spacing: 1px;
        }

        /* --- RESPONSIVE --- */
        @media (max-width: 768px) {
            .nav-links { display: none; }
            .hero-content h1 { font-size: 2.2rem; }
            .hero-content p { font-size: 1rem; }
        }
    </style>
</head>
<body>

    <div class="announcement-bar">
        Bringing Craft to your Wardrobe — Worldwide Shipping Available
    </div>

    <header>
        <div class="nav-container">
            <div class="logo"><a href="#">Mogra<span>Studio</span></a></div>
            <ul class="nav-links">
                <li><a href="#">Shop All</a></li>
                <li><a href="#">New Arrivals</a></li>
                <li><a href="#">Corsets</a></li>
                <li><a href="#">Lehengas & Sarees</a></li>
                <li><a href="#">Our Story</a></li>
            </ul>
            <div class="nav-icons">
                <span onclick="alert('Search functionality coming soon!')">🔍</span>
                <span onclick="alert('Cart is empty!')">🛒</span>
            </div>
        </div>
    </header>

    <section class="hero">
        <div class="hero-content">
            <h1>Handcrafted Elegance</h1>
            <p>Curated Indian aesthetics designed for the modern wardrobe.</p>
            <a href="#shop" class="btn">Explore Collections</a>
        </div>
    </section>

    <div class="section-title">
        <h2>Browse Collections</h2>
    </div>
    <section class="categories-grid">
        <div class="category-card">
            <img src="https://images.unsplash.com/photo-1583391733956-3750e0ff4e8b?auto=format&fit=crop&w=600&q=80" alt="Corsets">
            <div class="category-overlay"><h3>Everything Corset</h3></div>
        </div>
        <div class="category-card">
            <img src="https://images.unsplash.com/photo-1610030469983-98e550d6193c?auto=format&fit=crop&w=600&q=80" alt="Sarees">
            <div class="category-overlay"><h3>Liberate the Saree</h3></div>
        </div>
        <div class="category-card">
            <img src="https://images.unsplash.com/photo-1595777457583-95e059d581b8?auto=format&fit=crop&w=600&q=80" alt="Jewellery">
            <div class="category-overlay"><h3>Glitter Away Jewellery</h3></div>
        </div>
    </section>

    <div class="section-title" id="shop">
        <h2>Featured Drops</h2>
    </div>
    <section class="product-container">
        <div class="products-grid">
            <div class="product-card">
                <div class="product-image-wrapper">
                    <img src="https://images.unsplash.com/photo-1596783074918-c84cb06531ca?auto=format&fit=crop&w=500&q=80" alt="Product 1">
                    <div class="add-to-cart-btn" onclick="alert('Added to cart!')">Add to Cart</div>
                </div>
                <div class="product-info">
                    <div class="product-title">Bakudi Bindi Set</div>
                    <div class="product-price">₹1,900 INR</div>
                </div>
            </div>
            <div class="product-card">
                <div class="product-image-wrapper">
                    <img src="https://images.unsplash.com/photo-1617627143750-d86bc21e42bb?auto=format&fit=crop&w=500&q=80" alt="Product 2">
                    <div class="add-to-cart-btn" onclick="alert('Added to cart!')">Add to Cart</div>
                </div>
                <div class="product-info">
                    <div class="product-title">Royal Blue Corset Top</div>
                    <div class="product-price">₹4,500 INR</div>
                </div>
            </div>
            <div class="product-card">
                <div class="product-image-wrapper">
                    <img src="https://images.unsplash.com/photo-1609357605129-26f69add5d6e?auto=format&fit=crop&w=500&q=80" alt="Product 3">
                    <div class="add-to-cart-btn" onclick="alert('Added to cart!')">Add to Cart</div>
                </div>
                <div class="product-info">
                    <div class="product-title">Sundara Linen Set</div>
                    <div class="product-price">₹7,000 INR</div>
                </div>
            </div>
            <div class="product-card">
                <div class="product-image-wrapper">
                    <img src="https://images.unsplash.com/photo-1618244972963-dbee1a7edc95?auto=format&fit=crop&w=500&q=80" alt="Product 4">
                    <div class="add-to-cart-btn" onclick="alert('Added to cart!')">Add to Cart</div>
                </div>
                <div class="product-info">
                    <div class="product-title">Structured Chic Box Bag</div>
                    <div class="product-price">₹8,800 INR</div>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h4>About Us</h4>
                <p>Rooted in Indian craftsmanship, recreating modern dressing to create silhouettes that transcend trends.</p>
            </div>
            <div class="footer-section">
                <h4>Quick Links</h4>
                <ul>
                    <li><a href="#">Search</a></li>
                    <li><a href="#">Shipping Policy</a></li>
                    <li><a href="#">Terms of Service</a></li>
                </ul>
            </div>
            <div class="footer-section">
                <h4>Contact</h4>
                <p>Email: info@mogradesigns.com</p>
                <p>WhatsApp: +91 92112 31236</p>
            </div>
        </div>
        <div class="footer-bottom">
            &copy; 2026 Mogra Studio Clone. Powered by Creativity.
        </div>
    </footer>

</body>
</html># shop
