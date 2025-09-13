<!DOCTYPE html>
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
            <a href="#" class="logo">ZYNOVA</a>
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
            <div class="hero-image" style="background: linear-gradient(45deg, rgba(0,0,0,0.3), rgba(0,0,0,0.1)), url('https://th.bing.com/th/id/OIP.57T0QUm7OlAu9bTUAa7xyQHaE7?w=293&h=196&c=7&r=0&o=5&pid=1.7') center/cover;"></div>
        </div>
    </section>

    <!-- Categories Section -->
    <section class="categories" id="collections">
        <div class="container">
            <h2 class="section-title">Shop by Category</h2>
            <div class="category-grid">
                <div class="category-card interactive-element">
                    <div class="category-image" style="background: linear-gradient(45deg, rgba(0,0,0,0.3), rgba(0,0,0,0.1)), url('data:image/webp;base64,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') center/cover;">
                        <div class="category-overlay">
                            <div class="category-name">Women's Collection</div>
                            <div class="category-count">150+ Items</div>
                        </div>
                    </div>
                </div>
                <div class="category-card interactive-element">
                    <div class="category-image" style="background: linear-gradient(45deg, rgba(0,0,0,0.3), rgba(0,0,0,0.1)), url('https://th.bing.com/th/id/OIP.K-VRny2EbZBFgBLqB1yyNwHaLH?w=186&h=279&c=7&r=0&o=7&pid=1.7&rm=3') center/cover;">
                        <div class="category-overlay">
                            <div class="category-name">Men's Collection</div>
                            <div class="category-count">120+ Items</div>
                        </div>
                    </div>
                </div>
                <div class="category-card interactive-element">
                    <div class="category-image" style="background: linear-gradient(45deg, rgba(0,0,0,0.3), rgba(0,0,0,0.1)), url('https://th.bing.com/th/id/OIP.R3fVt8cbjA1rI5hzroD9NwHaE7?w=267&h=180&c=7&r=0&o=7&pid=1.7&rm=3') center/cover;">
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
                    <div class="product-image" style="background: url('https://th.bing.com/th/id/OIP.13XcUY7hA3jr6J0uMyh_fQAAAA?w=186&h=290&c=7&r=0&o=7&pid=1.7&rm=3') center/cover;">
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
                    <div class="product-image" style="background: url('data:image/webp;base64,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') center/cover;">
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
                    <div class="product-image" style="background: url('data:image/webp;base64,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') center/cover;">
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
                    <div class="product-image" style="background: url('https://th.bing.com/th/id/OIP.YBzxeFlOxzuL8ukeHgVEHwHaHa?w=170&h=180&c=7&r=0&o=7&pid=1.7&rm=3') center/cover;">
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
                <div class="about-image" style="background: url('https://img.freepik.com/premium-photo/portrait-woman-standing-against-black-background_1048944-20962292.jpg') center/cover;"></div>
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
                    <p>📧 hello@zynova.com</p>
                    <p>📞 +1 (555) 123-4567</p>
                    <p>📍 123 Fashion Street<br>New York, NY 10001</p>
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
