<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ahsan Ismail - Odoo Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0f0c29, #302b63, #24243e);
            color: #fff;
            overflow: hidden;
            height: 100vh;
            position: relative;
        }

        /* Animated Background Particles */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
            pointer-events: none;
        }

        .particle {
            position: absolute;
            width: 3px;
            height: 3px;
            background: rgba(108, 99, 255, 0.6);
            border-radius: 50%;
            animation: float 15s infinite ease-in-out;
            box-shadow: 0 0 10px rgba(108, 99, 255, 0.8);
        }

        @keyframes float {
            0%, 100% { transform: translateY(0) translateX(0); opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { transform: translateY(-100vh) translateX(50px); opacity: 0; }
        }

        /* Glass Container */
        .container {
            position: relative;
            z-index: 2;
            max-width: 1400px;
            margin: 0 auto;
            padding: 40px;
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        /* Header Section */
        .header {
            text-align: center;
            margin-bottom: 40px;
            animation: fadeInDown 1s ease;
        }

        .name {
            font-size: 4rem;
            font-weight: 800;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-shadow: 0 0 30px rgba(102, 126, 234, 0.5);
            margin-bottom: 10px;
            letter-spacing: 2px;
        }

        .tagline {
            font-size: 1.5rem;
            color: #a0aec0;
            font-weight: 300;
            letter-spacing: 3px;
        }

        .typing-container {
            height: 30px;
            margin-top: 15px;
        }

        .typing {
            color: #6c63ff;
            font-size: 1.2rem;
            font-weight: 600;
            border-right: 2px solid #6c63ff;
            white-space: nowrap;
            overflow: hidden;
            display: inline-block;
            animation: blink 0.7s step-end infinite;
        }

        @keyframes blink {
            50% { border-color: transparent; }
        }

        /* Main Grid */
        .main-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            margin-bottom: 30px;
        }

        /* Glass Card */
        .glass-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 30px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
            transition: all 0.3s ease;
            animation: fadeInUp 1s ease;
        }

        .glass-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 12px 48px 0 rgba(108, 99, 255, 0.4);
            border-color: rgba(108, 99, 255, 0.3);
        }

        .card-title {
            font-size: 1.5rem;
            margin-bottom: 20px;
            color: #6c63ff;
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .icon {
            width: 30px;
            height: 30px;
            filter: drop-shadow(0 0 5px rgba(108, 99, 255, 0.5));
        }

        /* Skills Grid */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 15px;
        }

        .skill-item {
            background: linear-gradient(135deg, rgba(108, 99, 255, 0.2), rgba(118, 75, 162, 0.2));
            padding: 15px;
            border-radius: 12px;
            text-align: center;
            transition: all 0.3s ease;
            border: 1px solid rgba(108, 99, 255, 0.3);
            cursor: pointer;
        }

        .skill-item:hover {
            transform: scale(1.05);
            box-shadow: 0 0 20px rgba(108, 99, 255, 0.6);
            background: linear-gradient(135deg, rgba(108, 99, 255, 0.4), rgba(118, 75, 162, 0.4));
        }

        .skill-name {
            font-size: 0.9rem;
            font-weight: 600;
            margin-top: 8px;
        }

        /* Services Grid */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
        }

        .service-item {
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.1), rgba(118, 75, 162, 0.1));
            padding: 20px;
            border-radius: 12px;
            border-left: 4px solid #6c63ff;
            transition: all 0.3s ease;
        }

        .service-item:hover {
            border-left-width: 8px;
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.2), rgba(118, 75, 162, 0.2));
            transform: translateX(5px);
        }

        .service-title {
            font-size: 1.1rem;
            color: #667eea;
            margin-bottom: 8px;
            font-weight: 700;
        }

        .service-desc {
            font-size: 0.85rem;
            color: #a0aec0;
            line-height: 1.5;
        }

        /* Stats */
        .stats-container {
            display: flex;
            justify-content: space-around;
            margin-top: 20px;
        }

        .stat-item {
            text-align: center;
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: 800;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .stat-label {
            font-size: 0.9rem;
            color: #a0aec0;
            margin-top: 5px;
        }

        /* Contact Section */
        .contact-section {
            display: flex;
            justify-content: center;
            gap: 20px;
            animation: fadeInUp 1.2s ease;
        }

        .contact-btn {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 15px 35px;
            border-radius: 50px;
            text-decoration: none;
            color: #fff;
            font-weight: 600;
            font-size: 1rem;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(108, 99, 255, 0.4);
            border: 2px solid transparent;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .contact-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(108, 99, 255, 0.6);
            border-color: rgba(255, 255, 255, 0.3);
        }

        /* Animations */
        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

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

        /* Location Badge */
        .location-badge {
            position: absolute;
            top: 20px;
            right: 20px;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            padding: 10px 20px;
            border-radius: 50px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            font-size: 0.9rem;
            color: #a0aec0;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        /* Glow Effect */
        .glow {
            position: fixed;
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, rgba(108, 99, 255, 0.3), transparent);
            border-radius: 50%;
            pointer-events: none;
            filter: blur(80px);
            z-index: 0;
            animation: moveGlow 10s infinite ease-in-out;
        }

        @keyframes moveGlow {
            0%, 100% { transform: translate(0, 0); }
            50% { transform: translate(100px, 100px); }
        }
    </style>
</head>
<body>
    <!-- Animated Background -->
    <div class="particles" id="particles"></div>
    <div class="glow" style="top: -200px; left: -200px;"></div>
    <div class="glow" style="bottom: -200px; right: -200px; animation-delay: 5s;"></div>

    <!-- Location Badge -->
    <div class="location-badge">
        🇵🇰 Pakistan • Available for Projects
    </div>

    <!-- Main Container -->
    <div class="container">
        <!-- Header -->
        <div class="header">
            <h1 class="name">AHSAN ISMAIL</h1>
            <p class="tagline">ODOO DEVELOPER • ERP ARCHITECT</p>
            <div class="typing-container">
                <span class="typing" id="typing-text"></span>
            </div>
        </div>

        <!-- Main Grid -->
        <div class="main-grid">
            <!-- Left Column -->
            <div>
                <!-- Skills Card -->
                <div class="glass-card">
                    <h3 class="card-title">
                        <span>⚡</span> Technology Stack
                    </h3>
                    <div class="skills-grid">
                        <div class="skill-item">
                            <div class="icon">🔷</div>
                            <div class="skill-name">Odoo 16</div>
                        </div>
                        <div class="skill-item">
                            <div class="icon">🐍</div>
                            <div class="skill-name">Python</div>
                        </div>
                        <div class="skill-item">
                            <div class="icon">🐘</div>
                            <div class="skill-name">PostgreSQL</div>
                        </div>
                        <div class="skill-item">
                            <div class="icon">⚙️</div>
                            <div class="skill-name">QWeb</div>
                        </div>
                        <div class="skill-item">
                            <div class="icon">📄</div>
                            <div class="skill-name">XML</div>
                        </div>
                        <div class="skill-item">
                            <div class="icon">🌐</div>
                            <div class="skill-name">JavaScript</div>
                        </div>
                        <div class="skill-item">
                            <div class="icon">🔗</div>
                            <div class="skill-name">REST API</div>
                        </div>
                        <div class="skill-item">
                            <div class="icon">🔧</div>
                            <div class="skill-name">Git</div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Right Column -->
            <div>
                <!-- Services Card -->
                <div class="glass-card">
                    <h3 class="card-title">
                        <span>🎯</span> Core Expertise
                    </h3>
                    <div class="services-grid">
                        <div class="service-item">
                            <div class="service-title">Portal Development</div>
                            <div class="service-desc">Custom portals, dashboards, authentication & UX</div>
                        </div>
                        <div class="service-item">
                            <div class="service-title">XML Reporting</div>
                            <div class="service-desc">QWeb templates, PDF generation & layouts</div>
                        </div>
                        <div class="service-item">
                            <div class="service-title">Custom Modules</div>
                            <div class="service-desc">Tailored business logic & workflows</div>
                        </div>
                        <div class="service-item">
                            <div class="service-title">Integration</div>
                            <div class="service-desc">Third-party APIs & automation</div>
                        </div>
                    </div>
                    <div class="stats-container">
                        <div class="stat-item">
                            <div class="stat-number">16</div>
                            <div class="stat-label">Odoo Version</div>
                        </div>
                        <div class="stat-item">
                            <div class="stat-number">100%</div>
                            <div class="stat-label">Dedication</div>
                        </div>
                        <div class="stat-item">
                            <div class="stat-number">24/7</div>
                            <div class="stat-label">Support</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Contact Section -->
        <div class="contact-section">
            <a href="https://ahsan-developer.netlify.app" class="contact-btn">
                <span>🌐</span> Portfolio
            </a>
            <a href="https://linkedin.com/in/ahsan-ismail-4b4763281/" class="contact-btn">
                <span>💼</span> LinkedIn
            </a>
            <a href="tel:+923180690159" class="contact-btn">
                <span>📱</span> +92 318 0690159
            </a>
        </div>
    </div>

    <script>
        // Typing Effect
        const texts = [
            "Odoo 16 Expert 🚀",
            "Portal Specialist 🎯",
            "XML Reporting Master 📊",
            "ERP Solutions Architect 💼"
        ];
        let textIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingElement = document.getElementById('typing-text');

        function type() {
            const currentText = texts[textIndex];
            
            if (isDeleting) {
                typingElement.textContent = currentText.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingElement.textContent = currentText.substring(0, charIndex + 1);
                charIndex++;
            }

            if (!isDeleting && charIndex === currentText.length) {
                setTimeout(() => isDeleting = true, 2000);
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                textIndex = (textIndex + 1) % texts.length;
            }

            const speed = isDeleting ? 50 : 100;
            setTimeout(type, speed);
        }

        type();

        // Create Particles
        const particlesContainer = document.getElementById('particles');
        for (let i = 0; i < 50; i++) {
            const particle = document.createElement('div');
            particle.className = 'particle';
            particle.style.left = Math.random() * 100 + '%';
            particle.style.animationDelay = Math.random() * 15 + 's';
            particle.style.animationDuration = (Math.random() * 10 + 10) + 's';
            particlesContainer.appendChild(particle);
        }

        // Mouse Move Glow Effect
        document.addEventListener('mousemove', (e) => {
            const glows = document.querySelectorAll('.glow');
            glows[0].style.left = (e.clientX - 300) + 'px';
            glows[0].style.top = (e.clientY - 300) + 'px';
        });

        // Skill Items Interactive
        const skillItems = document.querySelectorAll('.skill-item');
        skillItems.forEach(item => {
            item.addEventListener('mouseenter', function() {
                this.style.transform = 'scale(1.1) rotate(5deg)';
            });
            item.addEventListener('mouseleave', function() {
                this.style.transform = 'scale(1) rotate(0deg)';
            });
        });

        // Smooth Counter Animation for Stats
        function animateCounter(element, target) {
            let current = 0;
            const increment = target / 50;
            const timer = setInterval(() => {
                current += increment;
                if (current >= target) {
                    element.textContent = target;
                    clearInterval(timer);
                } else {
                    element.textContent = Math.floor(current);
                }
            }, 30);
        }

        // Initialize counters on load
        window.addEventListener('load', () => {
            const statNumbers = document.querySelectorAll('.stat-number');
            animateCounter(statNumbers[0], 16);
            animateCounter(statNumbers[1], 100);
        });
    </script>
</body>
</html>
