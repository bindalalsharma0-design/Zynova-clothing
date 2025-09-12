<!DOCTYPE HTML>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Zynova - Premium Fashion Brand</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Playfair+Display:wght@400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-color: #1a1a1a;
            --secondary-color: #f8f8f8;
            --accent-color: #d4af37;
            --text-color: #333;
            --light-gray: #e5e5e5;
            --white: #ffffff;
            --gradient: linear-gradient(135deg, #1a1a1a 0%, #333 100%);
        }

        body {
            font-family: 'Inter', sans-serif;
            line-height: 1.6;
            color: var(--text-color);
            overflow-x: hidden;
        }

        /* Navigation */
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            padding: 15px 0;
            transition: all 0.3s ease;
            border-bottom: 1px solid var(--light-gray);
        }

        .nav-container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-family: 'Playfair Display', serif;
            font-size: 2rem;
            font-weight: 700;
            color: var(--primary-color);
            text-decoration: none;
            letter-spacing: -1px;
        }

        .nav-menu {
            display: flex;
            list-style: none;
            gap: 40px;
        }

        .nav-menu a {
            text-decoration: none;
            color: var(--text-color);
            font-weight: 500;
            font-size: 0.95rem;
            position: relative;
            transition: color 0.3s ease;
        }

        .nav-menu a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--accent-color);
            transition: width 0.3s ease;
        }

        .nav-menu a:hover::after {
            width: 100%;
        }

        .nav-actions {
            display: flex;
            align-items: center;
            gap: 25px;
        }

        .nav-actions i {
            font-size: 1.2rem;
            cursor: pointer;
            transition: color 0.3s ease;
        }

        .nav-actions i:hover {
            color: var(--accent-color);
        }

        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background: var(--accent-color);
            color: white;
            border-radius: 50%;
            width: 18px;
            height: 18px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.7rem;
            font-weight: 600;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: var(--gradient);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .hero-content {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 20px;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }

        .hero-text {
            color: white;
        }

        .hero-title {
            font-family: 'Playfair Display', serif;
            font-size: 4.5rem;
            font-weight: 700;
            line-height: 1.1;
            margin-bottom: 20px;
            letter-spacing: -2px;
        }

        .hero-subtitle {
            font-size: 1.3rem;
            font-weight: 300;
            margin-bottom: 30px;
            opacity: 0.9;
            line-height: 1.5;
        }

        .cta-button {
            display: inline-block;
            background: var(--accent-color);
            color: white;
            padding: 18px 40px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1rem;
            border-radius: 50px;
            transition: all 0.3s ease;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-top: 20px;
        }

        .cta-button:hover {
            background: #b8941f;
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(212, 175, 55, 0.3);
        }

        .hero-image {
            position: relative;
            height: 600px;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
        }

        .hero-image::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(45deg, rgba(0,0,0,0.1), transparent);
            z-index: 1;
        }

        /* Categories Section */
        .categories {
            padding: 100px 0;
            background: var(--secondary-color);
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .section-title {
            text-align: center;
            font-family: 'Playfair Display', serif;
            font-size: 3rem;
            font-weight: 600;
            margin-bottom: 60px;
            color: var(--primary-color);
        }

        .category-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
        }

        .category-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            position: relative;
        }

        .category-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.15);
        }

        .category-image {
            height: 300px;
            background-size: cover;
            background-position: center;
            position: relative;
        }

        .category-overlay {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background: linear-gradient(transparent, rgba(0, 0, 0, 0.7));
            color: white;
            padding: 30px;
            text-align: center;
        }

        .category-name {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 10px;
        }

        .category-count {
            font-size: 0.9rem;
            opacity: 0.8;
        }

        /* Featured Products */
        .featured-products {
            padding: 100px 0;
            background: white;
        }

        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 40px;
            margin-top: 60px;
        }

        .product-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            transition: all 0.3s ease;
            position: relative;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.08);
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.15);
        }

        .product-image {
            height: 350px;
            background-size: cover;
            background-position: center;
            position: relative;
            overflow: hidden;
        }

        .product-overlay {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.3);
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transition: all 0.3s ease;
        }

        .product-card:hover .product-overlay {
            opacity: 1;
        }

        .quick-view {
            background: white;
            color: var(--primary-color);
            padding: 12px 25px;
            border: none;
            border-radius: 25px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .quick-view:hover {
            background: var(--accent-color);
            color: white;
        }

        .product-info {
            padding: 25px;
        }

        .product-name {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 8px;
            color: var(--primary-color);
        }

        .product-price {
            font-size: 1.1rem;
            font-weight: 700;
            color: var(--accent-color);
        }

        .product-rating {
            display: flex;
            align-items: center;
            gap: 5px;
            margin-top: 10px;
        }

        .stars {
            color: #ffd700;
        }

        .rating-count {
            font-size: 0.9rem;
            color: #666;
        }

        /* About Section */
        .about {
            padding: 100px 0;
            background: var(--secondary-color);
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 80px;
            align-items: center;
        }

        .about-text {
            padding: 20px 0;
        }

        .about-title {
            font-family: 'Playfair Display', serif;
            font-size: 2.5rem;
            font-weight: 600;
            margin-bottom: 30px;
            color: var(--primary-color);
        }

        .about-description {
            font-size: 1.1rem;
            line-height: 1.8;
            margin-bottom: 30px;
            color: #666;
        }

        .about-features {
            list-style: none;
            margin-top: 30px;
        }

        .about-features li {
            padding: 10px 0;
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .about-features i {
            color: var(--accent-color);
            font-size: 1.2rem;
        }

        .about-image {
            height: 500px;
            border-radius: 20px;
            background-size: cover;
            background-position: center;
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.1);
        }

        /* Newsletter */
        .newsletter {
            padding: 80px 0;
            background: var(--primary-color);
            color: white;
            text-align: center;
        }

        .newsletter-title {
            font-family: 'Playfair Display', serif;
            font-size: 2.5rem;
            font-weight: 600;
            margin-bottom: 20px;
        }

        .newsletter-subtitle {
            font-size: 1.1rem;
            opacity: 0.8;
            margin-bottom: 40px;
        }

        .newsletter-form {
            display: flex;
            max-width: 500px;
            margin: 0 auto;
            gap: 15px;
            flex-wrap: wrap;
            justify-content: center;
        }

        .newsletter-input {
            flex: 1;
            min-width: 250px;
            padding: 15px 20px;
            border: none;
            border-radius: 50px;
            font-size: 1rem;
            outline: none;
        }

        .newsletter-button {
            background: var(--accent-color);
            color: white;
            border: none;
            padding: 15px 30px;
            border-radius: 50px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .newsletter-button:hover {
            background: #b8941f;
        }

        /* Footer */
        .footer {
            background: #111;
            color: white;
            padding: 60px 0 30px;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-section h3 {
            font-family: 'Playfair Display', serif;
            font-size: 1.5rem;
            margin-bottom: 20px;
            color: var(--accent-color);
        }

        .footer-section p,
        .footer-section li {
            line-height: 1.8;
            opacity: 0.8;
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section a {
            color: white;
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-section a:hover {
            color: var(--accent-color);
        }

        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

        .social-links i {
            font-size: 1.5rem;
            cursor: pointer;
            transition: color 0.3s ease;
        }

        .social-links i:hover {
            color: var(--accent-color);
        }

        .footer-bottom {
            border-top: 1px solid #333;
            padding-top: 30px;
            text-align: center;
            opacity: 0.6;
        }

        /* Mobile Responsiveness */
        @media (max-width: 768px) {
            .nav-menu {
                display: none;
            }

            .hero-content {
                grid-template-columns: 1fr;
                text-align: center;
                gap: 40px;
            }

            .hero-title {
                font-size: 3rem;
            }

            .about-content {
                grid-template-columns: 1fr;
                gap: 40px;
            }

            .newsletter-form {
                flex-direction: column;
                align-items: center;
            }

            .newsletter-input {
                min-width: 100%;
            }
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .fade-in {
            animation: fadeInUp 0.8s ease-out;
        }

        /* Interactive Elements */
        .interactive-element {
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .interactive-element:hover {
            transform: scale(1.02);
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav class="navbar">
        <div class="nav-container">
            <a href="#" class="logo">Zynova</a>
            <ul class="nav-menu">
                <li><a href="#home">Home</a></li>
                <li><a href="#collections">Collections</a></li>
                <li><a href="#women">Women</a></li>
                <li><a href="#men">Men</a></li>
                <li><a href="#accessories">Accessories</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <div class="nav-actions">
                <i class="fas fa-search"></i>
                <i class="fas fa-heart"></i>
                <div style="position: relative;">
                    <i class="fas fa-shopping-bag"></i>
                    <span class="cart-count">0</span>
                </div>
                <i class="fas fa-user"></i>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-content">
            <div class="hero-text fade-in">
                <h1 class="hero-title">Elevate Your Style</h1>
                <p class="hero-subtitle">Discover premium fashion that speaks to your individuality. Zynova brings you carefully curated collections that blend contemporary design with timeless elegance.</p>
                <a href="#collections" class="cta-button">Explore Collection</a>
            </div>
            <div class="hero-image" style="background: linear-gradient(45deg, rgba(0,0,0,0.3), rgba(0,0,0,0.1)), url('https://dusty-amaranth-io8x7qiba0.edgeone.app/Gemini_Generated_Image_3ig1ok3ig1ok3ig1.png') center/cover;"></div>
            
        </div>
    </section>

    <!-- Categories Section -->
    <section class="categories" id="collections">
        <div class="container">
            <h2 class="section-title">Shop by Category</h2>
            <div class="category-grid">
                <div class="category-card interactive-element">
                    <div class="category-image" style="background: linear-gradient(45deg, rgba(0,0,0,0.3), rgba(0,0,0,0.1)), url('https://img.freepik.com/premium-photo/girl-branded-clothes-is-walking-autumn-park_128442-1413.jpg') center/cover;">
                        <div class="category-overlay">
                            <div class="category-name">Women's Collection</div>
                            <div class="category-count">150+ Items</div>
                        </div>
                    </div>
                </div>
                <div class="category-card interactive-element">
                    <div class="category-image" style="background: linear-gradient(45deg, rgba(0,0,0,0.3), rgba(0,0,0,0.1)), url('https://img.freepik.com/premium-photo/girl-branded-clothes-is-walking-autumn-park_128442-1413.jpg') center/cover;">
                        <div class="category-overlay">
                            <div class="category-name">Men's Collection</div>
                            <div class="category-count">120+ Items</div>
                        </div>
                    </div>
                </div>
                <div class="category-card interactive-element">
                    <div class="category-image" style="background: linear-gradient(45deg, rgba(0,0,0,0.3), rgba(0,0,0,0.1)), url('https://tse1.mm.bing.net/th/id/OIP.AiV-Bqo99p5DAaEAElgn3gHaHa?r=0&rs=1&pid=ImgDetMain&o=7&rm=3') center/cover;">
                        <div class="category-overlay">
                            <div class="category-name">Accessories</div>
                            <div class="category-count">80+ Items</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Featured Products -->
    <section class="featured-products">
        <div class="container">
            <h2 class="section-title">Featured Products</h2>
            <div class="product-grid">
                <div class="product-card interactive-element">
                    <div class="product-image" style="background: url('data:image/webp;base64,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') center/cover;">
                        <div class="product-overlay">
                            <button class="quick-view">Quick View</button>
                        </div>
                    </div>
                    <div class="product-info">
                         
                        <h3 class="product-name">Premium Business Blazer</h3>
                       
                        <p class="product-price">$299</p>
                        <div class="product-rating">
                            <div class="stars">★★★★★</div>
                            <span class="rating-count">(24 reviews)</span>
                        </div>
                    </div>
                </div>
                
                <div class="product-card interactive-element">
                    <div class="product-image" style="background: url('https://th.bing.com/th/id/OIP.iSZtsNCYPTwFZX1As8aUGAHaJ4?w=186&h=248&c=7&r=0&o=7&pid=1.7&rm=3') center/cover;">
                        <div class="product-overlay">
                            <button class="quick-view">Quick View</button>
                        </div>
                    </div>
                    <div class="product-info">
                        
                        <h3 class="product-name">Elegant Evening Dress</h3>
                        
                        <p class="product-price">$459</p>
                        <div class="product-rating">
                            <div class="stars">★★★★★</div>
                            <span class="rating-count">(18 reviews)</span>
                        </div>
                    </div>
                </div>
                
                <div class="product-card interactive-element">
                    <div class="product-image" style="background: url('https://th.bing.com/th/id/OIP.YV9WTw1XpUSl-R45-NpHiAHaIt?w=157&h=185&c=7&r=0&o=7&dpr=1.3&pid=1.7&rm=3') center/cover;">
                        <div class="product-overlay">
                            <button class="quick-view">Quick View</button>
                        </div>
                    </div>
                    <div class="product-info">
                        
                        <h3 class="product-name">Designer Leather Jacket</h3>
                        <p class="product-price">$599</p>
                        <div class="product-rating">
                            <div class="stars">★★★★☆</div>
                            <span class="rating-count">(31 reviews)</span>
                        </div>
                    </div>
                </div>
                
                <div class="product-card interactive-element">
                    <div class="product-image" style="background: url('https://th.bing.com/th/id/OIP.cby-lt3wb9JPdqAyN6QPewHaEc?w=277&h=180&c=7&r=0&o=7&pid=1.7&rm=3') center/cover;">
                        <div class="product-overlay">
                            <button class="quick-view">Quick View</button>
                        </div>
                    </div>
                    <div class="product-info">
                        
                        <h3 class="product-name">Luxury Handbag</h3>
                        <p class="product-price">$399</p>
                        <div class="product-rating">
                            <div class="stars">★★★★★</div>
                            <span class="rating-count">(42 reviews)</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section class="about" id="about">
        <div class="container">
            <div class="about-content">
                <div class="about-text">
                    <h2 class="about-title">About Zynova</h2>
                    <p class="about-description">
                        At Zynova, we believe fashion is more than just clothing—it's a form of self-expression. Founded with a vision to create premium, sustainable fashion that transcends trends, we curate collections that speak to the modern individual who values both style and substance.
                    </p>
                    <p class="about-description">
                        Our commitment to excellence extends beyond design to encompass ethical manufacturing practices, sustainable materials, and exceptional craftsmanship that ensures each piece tells a story worth sharing.
                    </p>
                    <ul class="about-features">
                        <li><i class="fas fa-leaf"></i> Sustainable Materials</li>
                        <li><i class="fas fa-award"></i> Premium Quality</li>
                        <li><i class="fas fa-shipping-fast"></i> Fast & Free Shipping</li>
                        <li><i class="fas fa-undo"></i> Easy Returns</li>
                    </ul>
                </div>
                <div class="about-image" style="background: url('data:image/webp;base64,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') center/cover;"></div>
            </div>
        </div>
    </section>

    <!-- Newsletter -->
    <section class="newsletter">
        <div class="container">
            <h2 class="newsletter-title">Stay in Style</h2>
            <p class="newsletter-subtitle">Subscribe to our newsletter for exclusive offers, style tips, and first access to new collections.</p>
            <form class="newsletter-form">
                <input type="email" class="newsletter-input" placeholder="Enter your email address" required>
                <button type="submit" class="newsletter-button">Subscribe</button>
            </form>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>Zynova</h3>
                    <p>Elevating fashion through premium design, sustainable practices, and exceptional craftsmanship. Your style, our passion.</p>
                    <div class="social-links">
                        <i class="fab fa-instagram"></i>
                        <i class="fab fa-facebook"></i>
                        <i class="fab fa-twitter"></i>
                        <i class="fab fa-pinterest"></i>
                    </div>
                </div>
                <div class="footer-section">
                    <h3>Quick Links</h3>
                    <ul>
                        <li><a href="#collections">Collections</a></li>
                        <li><a href="#women">Women</a></li>
                        <li><a href="#men">Men</a></li>
                        <li><a href="#accessories">Accessories</a></li>
                        <li><a href="#sale">Sale</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h3>Customer Care</h3>
                    <ul>
                        <li><a href="#">Size Guide</a></li>
                        <li><a href="#">Shipping Info</a></li>
                        <li><a href="#">Returns & Exchanges</a></li>
                        <li><a href="#">FAQ</a></li>
                        <li><a href="#">Contact Us</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h3>Contact Info</h3>
                    <p>📧 raju09sharma.101@gmail.com</p>
                    <p>📞 +91 8178069755</p>
                    <p>📍 1 fashion street<br>New Delhi, 110037</p>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2025 Zynova. All rights reserved. | Privacy Policy | Terms of Service</p>
            </div>
        </div>
    </footer>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Navbar scroll effect
        window.addEventListener('scroll', () => {
            const navbar = document.querySelector('.navbar');
            if (window.scrollY > 100) {
                navbar.style.background = 'rgba(255, 255, 255, 0.98)';
                navbar.style.boxShadow = '0 2px 20px rgba(0, 0, 0, 0.1)';
            } else {
                navbar.style.background = 'rgba(255, 255, 255, 0.95)';
                navbar.style.boxShadow = 'none';
            }
        });

        // Cart functionality
        let cartCount = 0;
        const cartCountElement = document.querySelector('.cart-count');
        
        document.querySelectorAll('.quick-view').forEach(button => {
            button.addEventListener('click', () => {
                cartCount++;
                cartCountElement.textContent = cartCount;
                cartCountElement.style.transform = 'scale(1.2)';
                setTimeout(() => {
                    cartCountElement.style.transform = 'scale(1)';
                }, 200);
            });
        });

        // Newsletter form
        document.querySelector('.newsletter-form').addEventListener('submit', (e) => {
            e.preventDefault();
            const email = document.querySelector('.newsletter-input').value;
            if (email) {
                alert('Thank you for subscribing to Zynova newsletter!');
                document.querySelector('.newsletter-input').value = '';
            }
        });

        // Animation on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('fade-in');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.product-card, .category-card, .about-text').forEach(el => {
            observer.observe(el);
        });
    </script>
</body>
</html>
