# Eco-spark
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EcoSpark </title>
    <link rel="icon" href="C:\Users\Gowrishankar\Desktop\Eco Spark\arrow.png">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }


        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            overflow-x: hidden;
            background: #0a0a0a;
            color: #fff;
        }


        /* Navigation */
        nav {
            position: fixed;
            width: 100%;
            padding: 20px 50px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;
            background: rgba(10, 10, 10, 0.8);
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }


        nav.scrolled {
            padding: 15px 50px;
            background: rgba(10, 10, 10, 0.95);
        }


        .logo {
            font-size: 28px;
            font-weight: bold;
            background: linear-gradient(135deg, #00ff88, #00cc66);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }


        .nav-links {
            display: flex;
            gap: 40px;
            list-style: none;
        }


        .nav-links a {
            color: #fff;
            text-decoration: none;
            font-size: 16px;
            transition: color 0.3s;
            position: relative;
        }


        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: #00ff88;
            transition: width 0.3s;
        }


        .nav-links a:hover::after {
            width: 100%;
        }


        /* Hero Section */
        .hero {
            height: 100vh;
            position: relative;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
        }


        .parallax-bg {
            position: absolute;
            width: 100%;
            height: 100%;
        }


        .parallax-layer {
            position: absolute;
            width: 100%;
            height: 100%;
        }


        .layer-1 {
            background: radial-gradient(circle at 20% 50%, rgba(0, 255, 136, 0.1) 0%, transparent 50%);
            transform: translateZ(0);
        }


        .layer-2 {
            background: radial-gradient(circle at 80% 50%, rgba(0, 204, 102, 0.15) 0%, transparent 50%);
            transform: translateZ(0);
        }


        .floating-shapes {
            position: absolute;
            width: 100%;
            height: 100%;
        }


        .shape {
            position: absolute;
            border-radius: 50%;
            background: linear-gradient(135deg, rgba(0, 255, 136, 0.1), rgba(0, 204, 102, 0.1));
            backdrop-filter: blur(2px);
        }


        .shape-1 { width: 300px; height: 300px; top: 10%; left: 10%; }
        .shape-2 { width: 200px; height: 200px; top: 60%; right: 15%; }
        .shape-3 { width: 150px; height: 150px; bottom: 20%; left: 20%; }


        .hero-content {
            text-align: center;
            z-index: 10;
            max-width: 900px;
            padding: 0 20px;
        }


        .hero h1 {
            font-size: 80px;
            font-weight: 900;
            margin-bottom: 20px;
            background: linear-gradient(135deg, #00ff88, #00cc66, #fff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            line-height: 1.2;
        }


        .hero p {
            font-size: 24px;
            color: #aaa;
            margin-bottom: 40px;
        }


        .cta-button {
            display: inline-block;
            padding: 18px 45px;
            background: linear-gradient(135deg, #00ff88, #00cc66);
            color: #000;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            font-size: 18px;
            transition: all 0.3s;
            box-shadow: 0 10px 30px rgba(0, 255, 136, 0.3);
        }


        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(0, 255, 136, 0.5);
        }


        /* Section Styles */
        section {
            padding: 120px 50px;
            position: relative;
        }


        .section-title {
            font-size: 60px;
            font-weight: 900;
            margin-bottom: 20px;
            background: linear-gradient(135deg, #00ff88, #fff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }


        .section-subtitle {
            font-size: 20px;
            color: #888;
            margin-bottom: 60px;
        }


        /* About Section */
        .about {
            background: linear-gradient(180deg, #0a0a0a 0%, #0f1f0f 100%);
        }


        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
        }


        .about-text {
            font-size: 18px;
            line-height: 1.8;
            color: #ccc;
        }


        .about-image {
            width: 100%;
            height: 400px;
            background: linear-gradient(135deg, rgba(0, 255, 136, 0.2), rgba(0, 204, 102, 0.2));
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 80px;
            backdrop-filter: blur(10px);
            border: 2px solid rgba(0, 255, 136, 0.3);
        }


        /* Services Section */
        .services {
            background: #0a0a0a;
        }


        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
            max-width: 1200px;
            margin: 0 auto;
        }


        .service-card {
            background: linear-gradient(135deg, rgba(0, 255, 136, 0.05), rgba(0, 204, 102, 0.05));
            padding: 40px;
            border-radius: 20px;
            border: 2px solid rgba(0, 255, 136, 0.2);
            transition: all 0.3s;
            backdrop-filter: blur(10px);
        }


        .service-card:hover {
            transform: translateY(-10px);
            border-color: rgba(0, 255, 136, 0.5);
            box-shadow: 0 20px 40px rgba(0, 255, 136, 0.2);
        }


        .service-icon {
            font-size: 50px;
            margin-bottom: 20px;
        }


        .service-card h3 {
            font-size: 24px;
            margin-bottom: 15px;
            color: #00ff88;
        }


        .service-card p {
            color: #aaa;
            line-height: 1.6;
        }


        /* Portfolio Section */
        .portfolio {
            background: linear-gradient(180deg, #0a0a0a 0%, #0f1f0f 100%);
        }


        .waste-types {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            max-width: 1200px;
            margin: 0 auto;
        }


        .waste-card {
            background: rgba(0, 255, 136, 0.05);
            padding: 40px;
            border-radius: 20px;
            text-align: center;
            border: 2px solid rgba(0, 255, 136, 0.2);
            transition: all 0.3s;
        }


        .waste-card:hover {
            background: rgba(0, 255, 136, 0.1);
            transform: scale(1.05);
        }


        .waste-icon {
            font-size: 60px;
            margin-bottom: 20px;
        }


        .waste-card h3 {
            font-size: 22px;
            margin-bottom: 10px;
            color: #00ff88;
        }


        /* Map Section */
        .map-section {
            background: #0a0a0a;
            text-align: center;
        }


        .map-container {
            max-width: 1200px;
            margin: 0 auto;
            height: 500px;
            background: linear-gradient(135deg, rgba(0, 255, 136, 0.1), rgba(0, 204, 102, 0.1));
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            border: 2px solid rgba(0, 255, 136, 0.3);
            position: relative;
            overflow: hidden;
        }


        .map-placeholder {
            text-align: center;
        }


        .map-placeholder h3 {
            font-size: 30px;
            margin-bottom: 20px;
            color: #00ff88;
        }


        .dustbin-alert {
            position: absolute;
            top: 20%;
            left: 30%;
            background: #ff4444;
            color: #fff;
            padding: 15px 25px;
            border-radius: 50px;
            font-weight: bold;
            animation: pulse 2s infinite;
        }


        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }


        /* ES coin Section */
        
        /* ES Coins Section - YOUR NEW SECTION! */
        .ES {
            background: linear-gradient(180deg, #0f1f0f 0%, #0a0a0a 100%);
            text-align: center;
        }


        .ES-section-title {
            font-size: 60px;
            font-weight: 900;
            margin-bottom: 20px;
            background: linear-gradient(135deg, #FFD700, #FFA500, #00ff88);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }


        .ES-para {
            font-size: 24px;
            color: #aaa;
            margin-bottom: 40px;
        }


        .APK-link {
            margin-top: 30px;
        }


        .APK-link button {
            padding: 18px 45px;
            background: linear-gradient(135deg, #FFD700, #FFA500);
            color: #000;
            border: none;
            border-radius: 50px;
            font-weight: bold;
            font-size: 18px;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 10px 30px rgba(255, 215, 0, 0.3);
        }


        .APK-link button:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(255, 215, 0, 0.5);
        }


        /* Rotating Coin Styles */
        .coin-wrapper {
            perspective: 1000px;
            display: inline-block;
            margin: 40px 20px;
        }
        
        .coin {
            width: 200px;
            height: 200px;
            position: relative;
            transform-style: preserve-3d;
            animation: rotate 3s linear infinite;
        }
        
        .coin-side {
            position: absolute;
            width: 100%;
            height: 100%;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 72px;
            font-weight: bold;
            backface-visibility: hidden;
            box-shadow: 0 10px 40px rgba(255, 215, 0, 0.3);
        }
        
        .coin-front {
            background: linear-gradient(135deg, #FFD700, #FFA500);
            color: #000;
            border: 8px solid #d4af37;
            z-index: 2;
        }
        
        .coin-back {
            background: linear-gradient(135deg, #FFA500, #FFD700);
            color: #000;
            border: 8px solid #d4af37;
            transform: rotateY(180deg);
        }
        
        @keyframes rotate {
            0% {
                transform: rotateY(0deg);
            }
            100% {
                transform: rotateY(360deg);
            }
        }
        
        .coin-controls {
            margin-top: 30px;
            display: flex;
            justify-content: center;
            gap: 15px;
            flex-wrap: wrap;
        }
        
        .coin-controls button {
            background: linear-gradient(135deg, #FFD700, #FFA500);
            color: #000;
            border: none;
            padding: 12px 24px;
            font-size: 16px;
            border-radius: 25px;
            cursor: pointer;
            font-weight: bold;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(255, 215, 0, 0.2);
        }
        
        .coin-controls button:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(255, 215, 0, 0.4);
        }
        
        .coin-controls button:active {
            transform: translateY(0);
        }
        
        .speed-control {
            margin-top: 30px;
            color: #aaa;
        }
        
        .speed-control input[type="range"] {
            width: 200px;
            margin: 10px;
            accent-color: #FFD700;
        }
        
        #speedValue {
            color: #FFD700;
            font-weight: bold;
            margin-top: 10px;
        }


        /* Contact Section */
        .contact {
            background: linear-gradient(180deg, #0a0a0a 0%, #0f1f0f 100%);
        }


        .contact-content {
            max-width: 600px;
            margin: 0 auto;
        }


        .contact-form {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }


        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 15px;
            background: rgba(0, 255, 136, 0.05);
            border: 2px solid rgba(0, 255, 136, 0.2);
            border-radius: 10px;
            color: #fff;
            font-size: 16px;
            transition: all 0.3s;
        }


        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #00ff88;
            background: rgba(0, 255, 136, 0.1);
        }


        .form-group textarea {
            resize: vertical;
            min-height: 150px;
        }


        .submit-btn {
            padding: 18px 45px;
            background: linear-gradient(135deg, #00ff88, #00cc66);
            color: #000;
            border: none;
            border-radius: 50px;
            font-weight: bold;
            font-size: 18px;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 10px 30px rgba(0, 255, 136, 0.3);
        }


        .submit-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(0, 255, 136, 0.5);
        }


        /* Footer */
        footer {
            background: #000;
            padding: 40px 50px;
            text-align: center;
            color: #888;
        }


        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 { font-size: 50px; }
            .hero p { font-size: 18px; }
            .section-title { font-size: 40px; }
            .about-content { grid-template-columns: 1fr; }
            nav { padding: 15px 20px; }
            .nav-links { gap: 20px; }
            section { padding: 80px 20px; }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav id="navbar">
        <div class="logo">EcoSpark ⚡</div>
        <ul class="nav-links">
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#services">Services</a></li>
            <li><a href="#portfolio">Portfolio</a></li>
            <li><a href="#ES">ES Coins</a></li>
            <li><a href="#map"> Map </a></li>
            <li><a href="#contact">Contact</a></li>
            <li><a href="">Profile</a></li>
            <li><a href="C:\Users\Gowrishankar\Desktop\Eco Spark\ai.html"> EcoSpark AI</a></li>
        </ul>
    </nav>


    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="parallax-bg">
            <div class="parallax-layer layer-1"></div>
            <div class="parallax-layer layer-2"></div>
        </div>
        <div class="floating-shapes">
            <div class="shape shape-1"></div>
            <div class="shape shape-2"></div>
            <div class="shape shape-3"></div>
        </div>
        <div class="hero-content">
            <h1>EcoSpark</h1>
            <p>Waste is only wasted when we fail to manage it</p>
            <a href="#about" class="cta-button">Find More</a>
        </div>
    </section>


    <!-- About Section -->
    <section class="about" id="about">
        <h2 class="section-title">About EcoSpark</h2>
        <p class="section-subtitle">Revolutionizing Waste Collection with AI&IoT Technology</p>
        <div class="about-content">
            <div class="about-text">
                <p>EcoSpark is a cutting-edge smart waste management system that uses IoT-enabled dustbins to monitor waste levels in real-time. Our intelligent sensors detect when bins are full and automatically alert collection teams, optimizing routes and reducing unnecessary trips.</p>
                <br>
                <p>By leveraging technology, we're making cities cleaner, which reducing the dumbing and burning waste by our electric vehical, and creating a more sustainable future for communities worldwide.</p>
            </div>
            <div class="about-image">
               🌍
            </div>
        </div>
    </section>


    <!-- Services Section -->
    <section class="services" id="services">
        <h2 class="section-title">Our Services</h2>
        <p class="section-subtitle">Comprehensive Waste Management Solutions</p>
        <div class="services-grid">
            <div class="service-card">
                <div class="service-icon">📍</div>
                <h3>Real-Time Monitoring</h3>
                <p>Track dustbins which alerts in real-time through our smart sensors and dashboard when it filled.</p>
            </div>
            <div class="service-card">
                <div class="service-icon">🚛</div>
                <h3>Optimized Collection</h3>
                <p>AI-powered route optimization ensures efficient pickup schedules and reduced fuel consumption.</p>
            </div>
            <div class="service-card">
                <div class="service-icon">🔔</div>
                <h3>Smart Alerts</h3>
                <p>Instant notifications when bins reach capacity, preventing overflow and maintaining cleanliness.</p>
            </div>
            <div class="service-card">
                <div class="service-icon">📊</div>
                <h3>Analytics Dashboard</h3>
                <p>Comprehensive data insights to improve waste management strategies and efficiency.</p>
            </div>
            <div class="service-card">
                <div class="service-icon">♻️</div>
                <h3>Sustainability focus</h3>
                <p>Reduce the environment pollution and promote eco-friendly practices in our community.</p>
            </div>
            <div class="service-card">
                <div class="service-icon">🤑</div>
                <h3>Waste-To-Cash</h3>
                <p>That anyone can collect the waste and give to us and get the cash.</p>
            </div>
        </div>
    </section>


    <!-- Portfolio Section -->
    <section class="portfolio" id="portfolio">
        <h2 class="section-title">Types of Waste We Handle</h2>
        <p class="section-subtitle">Comprehensive Waste Segregation</p>
        <div class="waste-types">
            <div class="waste-card">
                <div class="waste-icon">🗑️</div>
                <h3>General Waste</h3>
                <p>Non-recyclable household waste</p>
            </div>
            <div class="waste-card">
                <div class="waste-icon">♻️</div>
                <h3>Recyclable</h3>
                <p>Paper, plastic, glass, and metals</p>
            </div>
            <div class="waste-card">
                <div class="waste-icon">🍃</div>
                <h3>Organic</h3>
                <p>Food waste and compostable materials</p>
            </div>
            <div class="waste-card">
                <div class="waste-icon">⚡</div>
                <h3>E-Waste</h3>
                <p>Electronic and electrical equipment</p>
            </div>
            <div class="waste-card">
                <div class="waste-icon">⚠️</div>
                <h3>Hazardous</h3>
                <p>Batteries, chemicals, and toxic materials</p>
            </div>
            <div class="waste-card">
                <div class="waste-icon">🏗️</div>
                <h3>Construction</h3>
                <p>Building debris and materials</p>
            </div>
        </div>
    </section>


    <!-- Map Section -->
    <section class="map-section" id="map">
        <h2 class="section-title">Live Dustbin Monitoring</h2>
        <p class="section-subtitle">Real-Time Location Tracking & Alerts</p>
        <div class="map-container">
            <div class="map-placeholder">
                 <a href="https://www.google.com/maps/@10.9368346,76.9758269,15z?entry=ttu&g_ep=EgoyMDI1MTExNy4wIKXMDSoASAFQAw%3D%3D" target="_blank">
                <h3>🗺️ Interactive Map</h3>
                 </a>
                <p style="color: #aaa;">Smart dustbins with real-time fill-level monitoring</p>
            </div>
            <div class="dustbin-alert">🔴 Bin Full Alert!</div>
        </div>
    </section>


    <!--ES coin section-->
    <section class="ES" id="ES">
        <h2 class="ES-section-title">ES COINS 💰 </h2>
        <p class="ES-para">Let's Make it Together</p>
        
        <!-- Rotating Coin -->
        <div class="coin-wrapper">
            <div class="coin" id="coin">
                <div class="coin-side coin-front">
                    <span>ES</span>
                </div>
                <div class="coin-side coin-back">
                    <span>ES</span>
                </div>
            </div>
        </div>


        <div class="about-content" style="max-width: 1200px; margin: 40px auto;">
            <div class="about-text">
                <p>Earn ES Coins by participating in our waste collection program! Every time you properly segregate and dispose of waste through our system, you earn coins that can be redeemed for rewards, discounts, or cash.</p>
                <br>
                <p>Download our mobile app to track your ES Coins, find nearby smart dustbins, get collection schedules, and participate in our green rewards program. Join thousands of users making a difference!</p>
            </div>
            <div class="about-image" style="background: linear-gradient(135deg, rgba(255, 215, 0, 0.2), rgba(255, 165, 0, 0.2));">
                💰
            </div>
        </div>
        <div class="APK-link">
            <button onclick="alert('Click ok to see detials of ES Coin💰')"><a href="C:\Users\Gowrishankar\Desktop\Eco Spark\escoin.html">ES Coin Detials</a></button>
        </div>
    </section>


    <!-- Contact Section -->
    <section class="contact" id="contact">
        <h2 class="section-title">Get In Touch</h2>
        <p class="section-subtitle">Let's Make Your City Cleaner Together</p>
        <div class="contact-content">
            <form class="contact-form">
                <div class="form-group">
                    <input type="text" placeholder="Your Name" required>
                </div>
                <div class="form-group">
                    <input type="email" placeholder="Your Email" required>
                </div>
                <div class="form-group">
                    <input type="number" placeholder="Phone-no">
                </div>
                <div class="form-group">
                    <input type="text" placeholder="EcoSpark Code">
                </div>
                <div class="form-group">
                    <input type="text" placeholder="Type your Query" required>
                </div>
                <button type="submit" class="submit-btn">Send Message</button>
            </form>
        </div>
    </section>


    <!-- Footer -->
    <footer>
        <p>&copy; 2025 EcoSpark. All rights reserved. Making cities cleaner, one bin at a time. </p>
    </footer>


    <script>
        // Parallax Effect on Scroll
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            
            // Parallax layers
            const layer1 = document.querySelector('.layer-1');
            const layer2 = document.querySelector('.layer-2');
            
            if (layer1 && layer2) {
                layer1.style.transform = `translateY(${scrolled * 0.5}px)`;
                layer2.style.transform = `translateY(${scrolled * 0.3}px)`;
            }
            
            // Floating shapes
            const shapes = document.querySelectorAll('.shape');
            shapes.forEach((shape, index) => {
                const speed = 0.1 + (index * 0.05);
                shape.style.transform = `translateY(${scrolled * speed}px)`;
            });
            
            // Navbar scroll effect
            const navbar = document.getElementById('navbar');
            if (scrolled > 100) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });


        // Mouse parallax effect
        document.addEventListener('mousemove', (e) => {
            const shapes = document.querySelectorAll('.shape');
            const mouseX = e.clientX / window.innerWidth;
            const mouseY = e.clientY / window.innerHeight;
            
            shapes.forEach((shape, index) => {
                const speed = 20 + (index * 10);
                const x = (mouseX - 0.5) * speed;
                const y = (mouseY - 0.5) * speed;
                shape.style.transform += ` translate(${x}px, ${y}px)`;
            });
        });


        // Smooth scrolling
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


        // ES coin


        // Form submission
        document.querySelector('.contact-form').addEventListener('submit', (e) => {
            e.preventDefault();
            alert('Thank you for your message! We\'ll get back to you soon. by team Eco spark ♻️');
            e.target.reset();
        });


        // Scroll animations for cards
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };


        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);


        document.querySelectorAll('.service-card, .waste-card').forEach(card => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(30px)';
            card.style.transition = 'all 0.6s ease';
            observer.observe(card);
        });
    </script>
</body>


</html>\\\

