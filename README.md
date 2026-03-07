# Sweetflames-website-
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sweetflames | Dessert Candles That Look Real</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --bg-dark: #0f0f0f;
            --bg-card: #1a1a1a;
            --text-primary: #ffffff;
            --text-secondary: #a0a0a0;
            --accent: #ffb6c1;
            --accent-warm: #ffd700;
            --border: #2a2a2a;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--bg-dark);
            color: var(--text-primary);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 1.5rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;
            background: rgba(15, 15, 15, 0.8);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid var(--border);
        }

        .logo {
            font-family: 'Playfair Display', serif;
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--text-primary);
            text-decoration: none;
            letter-spacing: -0.5px;
        }

        .logo span {
            color: var(--accent);
        }

        .nav-links {
            display: flex;
            gap: 2.5rem;
            list-style: none;
        }

        .nav-links a {
            color: var(--text-secondary);
            text-decoration: none;
            font-size: 0.9rem;
            font-weight: 500;
            transition: color 0.3s;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .nav-links a:hover {
            color: var(--text-primary);
        }

        .cart-icon {
            position: relative;
            cursor: pointer;
        }

        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background: var(--accent);
            color: var(--bg-dark);
            font-size: 0.7rem;
            font-weight: 600;
            width: 18px;
            height: 18px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            padding: 0 5%;
            margin-top: 0;
            background: radial-gradient(circle at center, #1a1a1a 0%, #0f0f0f 100%);
        }

        .hero-content {
            text-align: center;
            max-width: 900px;
            z-index: 2;
        }

        .hero-tag {
            display: inline-block;
            padding: 0.5rem 1.5rem;
            border: 1px solid var(--border);
            border-radius: 50px;
            font-size: 0.85rem;
            color: var(--accent);
            margin-bottom: 2rem;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .hero h1 {
            font-family: 'Playfair Display', serif;
            font-size: clamp(3rem, 8vw, 6rem);
            font-weight: 700;
            line-height: 1.1;
            margin-bottom: 1.5rem;
            background: linear-gradient(135deg, #ffffff 0%, #a0a0a0 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero p {
            font-size: 1.25rem;
            color: var(--text-secondary);
            max-width: 600px;
            margin: 0 auto 3rem;
            font-weight: 300;
        }

        .cta-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            padding: 1rem 2.5rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s;
            font-size: 0.95rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .btn-primary {
            background: var(--text-primary);
            color: var(--bg-dark);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(255, 255, 255, 0.1);
        }

        .btn-secondary {
            border: 1px solid var(--border);
            color: var(--text-primary);
        }

        .btn-secondary:hover {
            background: var(--text-primary);
            color: var(--bg-dark);
        }

        /* Floating Images Animation */
        .floating-images {
            position: absolute;
            width: 100%;
            height: 100%;
            overflow: hidden;
            pointer-events: none;
        }

        .float-img {
            position: absolute;
            border-radius: 20px;
            opacity: 0.6;
            filter: blur(1px);
            animation: float 20s infinite ease-in-out;
        }

        .float-img:nth-child(1) {
            top: 20%;
            left: 10%;
            width: 200px;
            animation-delay: 0s;
        }

        .float-img:nth-child(2) {
            top: 60%;
            right: 10%;
            width: 180px;
            animation-delay: -5s;
        }

        .float-img:nth-child(3) {
            bottom: 20%;
            left: 15%;
            width: 150px;
            animation-delay: -10s;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-30px) rotate(5deg); }
        }

        /* Products Section */
        .products {
            padding: 8rem 5%;
            background: var(--bg-dark);
        }

        .section-header {
            text-align: center;
            margin-bottom: 5rem;
        }

        .section-header h2 {
            font-family: 'Playfair Display', serif;
            font-size: clamp(2rem, 5vw, 3.5rem);
            margin-bottom: 1rem;
        }

        .section-header p {
            color: var(--text-secondary);
            font-size: 1.1rem;
        }

        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 3rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .product-card {
            background: var(--bg-card);
            border-radius: 24px;
            overflow: hidden;
            border: 1px solid var(--border);
            transition: all 0.4s;
            position: relative;
        }

        .product-card:hover {
            transform: translateY(-10px);
            border-color: var(--accent);
            box-shadow: 0 20px 40px rgba(255, 182, 193, 0.1);
        }

        .product-image {
            width: 100%;
            height: 400px;
            object-fit: cover;
            display: block;
        }

        .product-info {
            padding: 2rem;
        }

        .product-tag {
            display: inline-block;
            padding: 0.25rem 0.75rem;
            background: rgba(255, 182, 193, 0.1);
            color: var(--accent);
            font-size: 0.75rem;
            border-radius: 50px;
            margin-bottom: 1rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .product-info h3 {
            font-family: 'Playfair Display', serif;
            font-size: 1.75rem;
            margin-bottom: 0.5rem;
        }

        .product-info p {
            color: var(--text-secondary);
            margin-bottom: 1.5rem;
            line-height: 1.6;
        }

        .product-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .price {
            font-size: 1.5rem;
            font-weight: 600;
            color: var(--text-primary);
        }

        .price span {
            font-size: 0.9rem;
            color: var(--text-secondary);
            font-weight: 400;
        }

        .add-to-cart {
            padding: 0.75rem 1.5rem;
            background: transparent;
            border: 1px solid var(--border);
            color: var(--text-primary);
            border-radius: 50px;
            cursor: pointer;
            font-weight: 500;
            transition: all 0.3s;
        }

        .add-to-cart:hover {
            background: var(--text-primary);
            color: var(--bg-dark);
            border-color: var(--text-primary);
        }

        /* Featured Video Section */
        .featured {
            padding: 6rem 5%;
            background: linear-gradient(to bottom, var(--bg-dark), #151515);
        }

        .featured-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
        }

        .featured-text h2 {
            font-family: 'Playfair Display', serif;
            font-size: 3rem;
            margin-bottom: 1.5rem;
            line-height: 1.2;
        }

        .featured-text p {
            color: var(--text-secondary);
            font-size: 1.1rem;
            margin-bottom: 2rem;
            line-height: 1.8;
        }

        .featured-visual {
            position: relative;
            border-radius: 24px;
            overflow: hidden;
            border: 1px solid var(--border);
        }

        .featured-visual img {
            width: 100%;
            height: auto;
            display: block;
        }

        .glow-effect {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 200px;
            height: 200px;
            background: radial-gradient(circle, rgba(255, 182, 193, 0.3) 0%, transparent 70%);
            pointer-events: none;
            animation: pulse 3s infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 0.5; transform: translate(-50%, -50%) scale(1); }
            50% { opacity: 1; transform: translate(-50%, -50%) scale(1.2); }
        }

        /* About Section */
        .about {
            padding: 8rem 5%;
            text-align: center;
            max-width: 800px;
            margin: 0 auto;
        }

        .about h2 {
            font-family: 'Playfair Display', serif;
            font-size: 2.5rem;
            margin-bottom: 2rem;
        }

        .about p {
            color: var(--text-secondary);
            font-size: 1.2rem;
            line-height: 1.8;
        }

        /* Footer */
        footer {
            padding: 4rem 5%;
            border-top: 1px solid var(--border);
            text-align: center;
            color: var(--text-secondary);
        }

        .footer-logo {
            font-family: 'Playfair Display', serif;
            font-size: 2rem;
            color: var(--text-primary);
            margin-bottom: 1rem;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin: 2rem 0;
        }

        .social-links a {
            color: var(--text-secondary);
            text-decoration: none;
            transition: color 0.3s;
        }

        .social-links a:hover {
            color: var(--accent);
        }

        /* Mobile Responsive */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .product-grid {
                grid-template-columns: 1fr;
            }
            
            .featured-content {
                grid-template-columns: 1fr;
            }
            
            .float-img {
                display: none;
            }
        }

        /* Smooth Scroll */
        html {
            scroll-behavior: smooth;
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 10px;
        }

        ::-webkit-scrollbar-track {
            background: var(--bg-dark);
        }

        ::-webkit-scrollbar-thumb {
            background: var(--border);
            border-radius: 5px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: var(--accent);
        }
    </style>
</head>
<body>

    <!-- Navigation -->
    <nav>
        <a href="#" class="logo">Sweet<span>flames</span></a>
        <ul class="nav-links">
            <li><a href="#products">Collection</a></li>
            <li><a href="#about">Our Story</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
        <div class="cart-icon">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <circle cx="9" cy="21" r="1"></circle>
                <circle cx="20" cy="21" r="1"></circle>
                <path d="M1 1h4l2.68 13.39a2 2 0 0 0 2 1.61h9.72a2 2 0 0 0 2-1.61L23 6H6"></path>
            </svg>
            <span class="cart-count">0</span>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero">
        <div class="floating-images">
            <img src="/mnt/kimi/upload/IMG_0421.jpeg" alt="Cake candle" class="float-img">
            <img src="/mnt/kimi/upload/955BEE17-6ADD-496E-8CEF-0021A017967A.jpeg" alt="Lemon candle" class="float-img">
            <img src="/mnt/kimi/upload/IMG_0420.jpeg" alt="Cake candle unlit" class="float-img">
        </div>
        
        <div class="hero-content">
            <div class="hero-tag">Handcrafted in Small Batches</div>
            <h1>Dessert Candles That Look Real</h1>
            <p>Indulge your senses with our hyper-realistic dessert candles. Made with premium soy wax and irresistible fragrances that fill your space with sweetness.</p>
            <div class="cta-buttons">
                <a href="#products" class="btn btn-primary">Shop Collection</a>
                <a href="#about" class="btn btn-secondary">Our Story</a>
            </div>
        </div>
    </section>

    <!-- Products Section -->
    <section class="products" id="products">
        <div class="section-header">
            <h2>The Collection</h2>
            <p>Each piece is handcrafted to perfection, looking and smelling just like your favorite desserts</p>
        </div>

        <div class="product-grid">
            <!-- Product 1: Vanilla Cake -->
            <div class="product-card">
                <img src="/mnt/kimi/upload/IMG_0421.jpeg" alt="Vanilla Cake Candle" class="product-image">
                <div class="product-info">
                    <span class="product-tag">Bestseller</span>
                    <h3>Vanilla Celebration Cake</h3>
                    <p>A stunning vanilla cake candle topped with cream frosting, mini cones, and sweet decorations. Looks so real you'll want to take a bite.</p>
                    <div class="product-footer">
                        <div class="price">15,000 <span>IQD</span></div>
                        <button class="add-to-cart" onclick="addToCart()">Add to Cart</button>
                    </div>
                </div>
            </div>

            <!-- Product 2: Lemon Candle -->
            <div class="product-card">
                <img src="/mnt/kimi/upload/955BEE17-6ADD-496E-8CEF-0021A017967A.jpeg" alt="Lemon Candle" class="product-image">
                <div class="product-info">
                    <span class="product-tag" style="background: rgba(255, 215, 0, 0.1); color: var(--accent-warm);">Fresh & Zesty</span>
                    <h3>Zesty Lemon</h3>
                    <p>Realistic lemon-shaped candles with a fresh, citrusy scent. Perfect for kitchens, bathrooms, or as a unique gift.</p>
                    <div class="product-footer">
                        <div class="price">5,000 <span>IQD</span></div>
                        <button class="add-to-cart" onclick="addToCart()">Add to Cart</button>
                    </div>
                </div>
            </div>

            <!-- Product 3: Non-Decorative -->
            <div class="product-card">
                <div style="height: 400px; background: linear-gradient(135deg, #2a2a2a 0%, #1a1a1a 100%); display: flex; align-items: center; justify-content: center; position: relative; overflow: hidden;">
                    <div style="width: 200px; height: 200px; border-radius: 50%; background: radial-gradient(circle, rgba(255,200,150,0.3) 0%, transparent 70%); position: absolute; animation: pulse 3s infinite;"></div>
                    <svg width="100" height="100" viewBox="0 0 24 24" fill="none" stroke="var(--text-secondary)" stroke-width="1" style="opacity: 0.5;">
                        <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                    </svg>
                </div>
                <div class="product-info">
                    <span class="product-tag" style="background: rgba(255,255,255,0.1); color: var(--text-secondary);">Classic</span>
                    <h3>Classic Scented Candle</h3>
                    <p>Simple elegance. Premium soy wax candle with your choice of fragrance. Clean burning, long lasting, perfectly minimalist.</p>
                    <div class="product-footer">
                        <div class="price">10,000 <span>IQD</span></div>
                        <button class="add-to-cart" onclick="addToCart()">Add to Cart</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Featured Section -->
    <section class="featured">
        <div class="featured-content">
            <div class="featured-text">
                <h2>Handcrafted with Love</h2>
                <p>Every Sweetflames candle is meticulously hand-poured and sculpted in small batches. We use only premium soy wax, lead-free wicks, and high-quality fragrance oils to ensure a clean, long-lasting burn. Our dessert candles are so realistic, they make the perfect conversation starter or gift for any occasion.</p>
                <a href="#products" class="btn btn-primary">Explore All</a>
            </div>
            <div class="featured-visual">
                <img src="/mnt/kimi/upload/IMG_0420.jpeg" alt="Vanilla cake candle detail">
                <div class="glow-effect"></div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section class="about" id="about">
        <h2>Why Sweetflames?</h2>
        <p>We believe candles should be more than just light and scent—they should be art. Our dessert-inspired creations bring joy, warmth, and a touch of whimsy to any space. Whether you're treating yourself or surprising someone special, Sweetflames delivers moments of sweetness without the calories.</p>
    </section>

    <!-- Footer -->
    <footer id="contact">
        <div class="footer-logo">Sweetflames</div>
        <p>Handcrafted dessert candles that look and smell incredible</p>
        <div class="social-links">
            <a href="#">Instagram</a>
            <a href="#">TikTok</a>
            <a href="#">WhatsApp</a>
        </div>
        <p style="margin-top: 2rem; font-size: 0.9rem;">© 2024 Sweetflames. All rights reserved.</p>
    </footer>

    <script>
        let cartCount = 0;
        
        function addToCart() {
            cartCount++;
            document.querySelector('.cart-count').textContent = cartCount;
            
            // Simple animation feedback
            const btn = event.target;
            const originalText = btn.textContent;
            btn.textContent = 'Added!';
            btn.style.background = 'var(--accent)';
            btn.style.color = 'var(--bg-dark)';
            btn.style.borderColor = 'var(--accent)';
            
            setTimeout(() => {
                btn.textContent = originalText;
                btn.style.background = '';
                btn.style.color = '';
                btn.style.borderColor = '';
            }, 1500);
        }

        // Smooth reveal on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: "0px 0px -50px 0px"
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = "1";
                    entry.target.style.transform = "translateY(0)";
                }
            });
        }, observerOptions);

        document.querySelectorAll('.product-card').forEach((el) => {
            el.style.opacity = "0";
            el.style.transform = "translateY(30px)";
            el.style.transition = "all 0.6s ease-out";
            observer.observe(el);
        });
    </script>

</body>
</html>
