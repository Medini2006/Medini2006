<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Medini Thrishala | Nature-Inspired Developer Portfolio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Quicksand:wght@400;500;600;700&display=swap" rel="stylesheet">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.11.4/gsap.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.11.4/ScrollTrigger.min.js"></script>
    <style>
        :root {
            --color-primary: #2e8b57;
            --color-secondary: #8fbc8f;
            --color-accent: #66cdaa;
            --color-dark: #2f4f4f;
            --color-light: #f5fffa;
            --color-background: #f8fbf8;
            --transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--color-background);
            color: var(--color-dark);
            line-height: 1.6;
            overflow-x: hidden;
            background-image: 
                radial-gradient(var(--color-secondary) 1px, transparent 1px),
                radial-gradient(var(--color-accent) 1px, transparent 1px);
            background-size: 40px 40px;
            background-position: 0 0, 20px 20px;
            background-attachment: fixed;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header & Navigation */
        header {
            background: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(10px);
            position: fixed;
            width: 100%;
            z-index: 1000;
            box-shadow: 0 5px 20px rgba(46, 139, 87, 0.1);
            padding: 15px 0;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-family: 'Quicksand', sans-serif;
            font-weight: 700;
            font-size: 1.5rem;
            color: var(--color-primary);
        }

        .logo i {
            color: var(--color-accent);
        }

        .nav-links {
            display: flex;
            gap: 30px;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--color-dark);
            font-weight: 500;
            position: relative;
            transition: var(--transition);
        }

        .nav-links a:after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background-color: var(--color-primary);
            transition: var(--transition);
        }

        .nav-links a:hover {
            color: var(--color-primary);
        }

        .nav-links a:hover:after {
            width: 100%;
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding-top: 80px;
            position: relative;
            overflow: hidden;
        }

        .hero-content {
            max-width: 700px;
            z-index: 2;
        }

        .hero h1 {
            font-family: 'Quicksand', sans-serif;
            font-size: 3.5rem;
            margin-bottom: 20px;
            color: var(--color-dark);
        }

        .hero h1 span {
            color: var(--color-primary);
            display: block;
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 30px;
            color: var(--color-dark);
        }

        .hero-btns {
            display: flex;
            gap: 15px;
        }

        .btn {
            padding: 12px 25px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .btn-primary {
            background: var(--color-primary);
            color: white;
        }

        .btn-primary:hover {
            background: var(--color-dark);
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(46, 139, 87, 0.3);
        }

        .btn-secondary {
            background: transparent;
            color: var(--color-primary);
            border: 2px solid var(--color-primary);
        }

        .btn-secondary:hover {
            background: rgba(46, 139, 87, 0.1);
            transform: translateY(-3px);
        }

        .hero-bg {
            position: absolute;
            top: 0;
            right: 0;
            width: 50%;
            height: 100%;
            z-index: 1;
            overflow: hidden;
        }

        .floating-icon {
            position: absolute;
            font-size: 2rem;
            color: var(--color-accent);
            opacity: 0.7;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(10deg); }
            100% { transform: translateY(0) rotate(0deg); }
        }

        .floating-icon:nth-child(1) { top: 20%; left: 10%; animation-delay: 0s; }
        .floating-icon:nth-child(2) { top: 60%; left: 15%; animation-delay: 1s; }
        .floating-icon:nth-child(3) { top: 40%; right: 20%; animation-delay: 2s; }
        .floating-icon:nth-child(4) { bottom: 30%; right: 15%; animation-delay: 3s; }
        .floating-icon:nth-child(5) { top: 25%; right: 30%; animation-delay: 4s; }

        /* About Section */
        .section {
            padding: 100px 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 60px;
            position: relative;
        }

        .section-title h2 {
            font-family: 'Quicksand', sans-serif;
            font-size: 2.5rem;
            color: var(--color-primary);
            display: inline-block;
        }

        .section-title h2:after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: var(--color-accent);
            border-radius: 2px;
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }

        .about-text h3 {
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: var(--color-dark);
        }

        .about-text p {
            margin-bottom: 15px;
        }

        .about-stats {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            margin-top: 30px;
        }

        .stat-box {
            background: white;
            padding: 20px;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);
            transition: var(--transition);
            border-bottom: 4px solid var(--color-accent);
        }

        .stat-box:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }

        .stat-box i {
            font-size: 2rem;
            color: var(--color-primary);
            margin-bottom: 15px;
        }

        .stat-box h4 {
            font-size: 2.5rem;
            color: var(--color-dark);
            margin-bottom: 5px;
        }

        .stat-box p {
            font-size: 0.9rem;
            color: var(--color-dark);
        }

        /* Skills Section */
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 30px;
        }

        .skill-category {
            background: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);
            transition: var(--transition);
        }

        .skill-category:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }

        .skill-category h3 {
            color: var(--color-primary);
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .skill-category h3 i {
            color: var(--color-accent);
        }

        .skill-item {
            margin-bottom: 15px;
        }

        .skill-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 8px;
        }

        .skill-bar {
            height: 8px;
            background: #e0e0e0;
            border-radius: 4px;
            overflow: hidden;
        }

        .skill-progress {
            height: 100%;
            background: var(--color-primary);
            border-radius: 4px;
            width: 0;
            transition: width 1.5s ease-in-out;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
        }

        .project-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);
            transition: var(--transition);
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }

        .project-img {
            height: 200px;
            background: linear-gradient(120deg, var(--color-secondary), var(--color-accent));
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
        }

        .project-content {
            padding: 20px;
        }

        .project-content h3 {
            color: var(--color-dark);
            margin-bottom: 10px;
        }

        .project-content p {
            color: #666;
            margin-bottom: 15px;
            font-size: 0.9rem;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 15px;
        }

        .project-tag {
            background: rgba(46, 139, 87, 0.1);
            color: var(--color-primary);
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 0.8rem;
        }

        .project-links {
            display: flex;
            gap: 15px;
        }

        .project-links a {
            color: var(--color-primary);
            text-decoration: none;
            font-size: 0.9rem;
            display: flex;
            align-items: center;
            gap: 5px;
            transition: var(--transition);
        }

        .project-links a:hover {
            color: var(--color-accent);
        }

        /* Contact Section */
        .contact-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
        }

        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 25px;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .contact-icon {
            width: 50px;
            height: 50px;
            background: var(--color-primary);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.2rem;
        }

        .contact-details h4 {
            color: var(--color-dark);
            margin-bottom: 5px;
        }

        .contact-details p {
            color: #666;
        }

        .contact-form {
            background: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.05);
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            color: var(--color-dark);
            font-weight: 500;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-family: 'Poppins', sans-serif;
            transition: var(--transition);
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--color-primary);
            box-shadow: 0 0 0 3px rgba(46, 139, 87, 0.2);
        }

        .form-group textarea {
            min-height: 120px;
            resize: vertical;
        }

        /* Footer */
        footer {
            background: var(--color-dark);
            color: white;
            padding: 60px 0 30px;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-logo {
            font-family: 'Quicksand', sans-serif;
            font-size: 1.8rem;
            font-weight: 700;
            color: white;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .footer-about p {
            color: #ccc;
            margin-bottom: 20px;
        }

        .social-links {
            display: flex;
            gap: 15px;
        }

        .social-links a {
            width: 40px;
            height: 40px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            text-decoration: none;
            transition: var(--transition);
        }

        .social-links a:hover {
            background: var(--color-primary);
            transform: translateY(-5px);
        }

        .footer-links h3 {
            color: white;
            margin-bottom: 20px;
            font-size: 1.2rem;
        }

        .footer-links ul {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 10px;
        }

        .footer-links a {
            color: #ccc;
            text-decoration: none;
            transition: var(--transition);
        }

        .footer-links a:hover {
            color: var(--color-accent);
            padding-left: 5px;
        }

        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #ccc;
            font-size: 0.9rem;
        }

        /* Animations */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s ease, transform 0.8s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Responsive Design */
        @media (max-width: 992px) {
            .about-content,
            .contact-container {
                grid-template-columns: 1fr;
            }

            .hero h1 {
                font-size: 2.8rem;
            }
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero-bg {
                display: none;
            }

            .hero {
                text-align: center;
            }

            .hero-btns {
                justify-content: center;
            }

            .about-stats {
                grid-template-columns: 1fr 1fr;
            }
        }

        @media (max-width: 576px) {
            .hero h1 {
                font-size: 2.2rem;
            }

            .section-title h2 {
                font-size: 2rem;
            }

            .about-stats {
                grid-template-columns: 1fr;
            }

            .stat-box {
                padding: 15px;
            }
        }
    </style>
</head>
<body>
    <!-- Header & Navigation -->
    <header>
        <div class="container">
            <nav>
                <div class="logo">
                    <i class="fas fa-leaf"></i>
                    <span>Medini</span>
                </div>
                <div class="nav-links">
                    <a href="#home">Home</a>
                    <a href="#about">About</a>
                    <a href="#skills">Skills</a>
                    <a href="#projects">Projects</a>
                    <a href="#contact">Contact</a>
                </div>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content">
                <h1>Hi, I'm <span>Medini Thrishala</span></h1>
                <p>A passionate frontend developer from Sri Lanka, blending technology with nature-inspired design to create beautiful, functional digital experiences.</p>
                <div class="hero-btns">
                    <a href="#projects" class="btn btn-primary">
                        <i class="fas fa-code-branch"></i> View My Work
                    </a>
                    <a href="#contact" class="btn btn-secondary">
                        <i class="fas fa-paper-plane"></i> Contact Me
                    </a>
                </div>
            </div>
        </div>
        <div class="hero-bg">
            <div class="floating-icon"><i class="fas fa-code"></i></div>
            <div class="floating-icon"><i class="fas fa-leaf"></i></div>
            <div class="floating-icon"><i class="fas fa-database"></i></div>
            <div class="floating-icon"><i class="fas fa-mobile-alt"></i></div>
            <div class="floating-icon"><i class="fas fa-cloud"></i></div>
        </div>
    </section>

    <!-- About Section -->
    <section class="section" id="about">
        <div class="container">
            <div class="section-title">
                <h2>About Me</h2>
            </div>
            <div class="about-content">
                <div class="about-text fade-in">
                    <h3>Frontend Developer & Nature Enthusiast</h3>
                    <p>I'm a passionate frontend developer from Sri Lanka, currently working on Business Analysis at StackNet Pvt Ltd and Research Projects with the National Science Foundation (NSF). I'm an Undergraduate Software Engineering Student at NIBM.</p>
                    <p>I believe in creating digital experiences that are not only functional but also beautiful and harmonious, much like nature itself. My work combines technical expertise with an aesthetic inspired by the natural world.</p>
                    <p>When I'm not coding, you can find me exploring nature, reading about sustainable technology, or contributing to open-source projects.</p>
                </div>
                <div class="about-stats">
                    <div class="stat-box fade-in">
                        <i class="fas fa-code"></i>
                        <h4 class="counter" data-target="50">0</h4>
                        <p>Projects Completed</p>
                    </div>
                    <div class="stat-box fade-in">
                        <i class="fas fa-clock"></i>
                        <h4 class="counter" data-target="2500">0</h4>
                        <p>Hours Coded</p>
                    </div>
                    <div class="stat-box fade-in">
                        <i class="fas fa-coffee"></i>
                        <h4 class="counter" data-target="500">0</h4>
                        <p>Cups of Coffee</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section class="section" id="skills">
        <div class="container">
            <div class="section-title">
                <h2>My Skills</h2>
            </div>
            <div class="skills-container">
                <div class="skill-category fade-in">
                    <h3><i class="fas fa-code"></i> Frontend Development</h3>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span>HTML/CSS</span>
                            <span>95%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-width="95%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span>JavaScript</span>
                            <span>90%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-width="90%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span>React</span>
                            <span>85%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-width="85%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span>Vue.js</span>
                            <span>80%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-width="80%"></div>
                        </div>
                    </div>
                </div>

                <div class="skill-category fade-in">
                    <h3><i class="fas fa-server"></i> Backend Development</h3>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span>Node.js</span>
                            <span>85%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-width="85%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span>PHP</span>
                            <span>75%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-width="75%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span>Java</span>
                            <span>80%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-width="80%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span>Python</span>
                            <span>70%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-width="70%"></div>
                        </div>
                    </div>
                </div>

                <div class="skill-category fade-in">
                    <h3><i class="fas fa-database"></i> Database & Tools</h3>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span>MySQL</span>
                            <span>85%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-width="85%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span>MongoDB</span>
                            <span>75%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-width="75%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span>Git</span>
                            <span>90%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-width="90%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-header">
                            <span>Figma</span>
                            <span>80%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-width="80%"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section class="section" id="projects">
        <div class="container">
            <div class="section-title">
                <h2>My Projects</h2>
            </div>
            <div class="projects-grid">
                <div class="project-card fade-in">
                    <div class="project-img">
                        <i class="fas fa-leaf"></i>
                    </div>
                    <div class="project-content">
                        <h3>Eco-Friendly App</h3>
                        <p>A sustainability-focused web application that helps users track their environmental impact.</p>
                        <div class="project-tags">
                            <span class="project-tag">React</span>
                            <span class="project-tag">Node.js</span>
                            <span class="project-tag">MongoDB</span>
                        </div>
                        <div class="project-links">
                            <a href="#"><i class="fab fa-github"></i> Code</a>
                            <a href="#"><i class="fas fa-external-link-alt"></i> Live Demo</a>
                        </div>
                    </div>
                </div>

                <div class="project-card fade-in">
                    <div class="project-img">
                        <i class="fas fa-chart-line"></i>
                    </div>
                    <div class="project-content">
                        <h3>Data Visualization Tool</h3>
                        <p>An interactive data visualization platform for analyzing complex datasets with beautiful charts.</p>
                        <div class="project-tags">
                            <span class="project-tag">Vue.js</span>
                            <span class="project-tag">D3.js</span>
                            <span class="project-tag">Python</span>
                        </div>
                        <div class="project-links">
                            <a href="#"><i class="fab fa-github"></i> Code</a>
                            <a href="#"><i class="fas fa-external-link-alt"></i> Live Demo</a>
                        </div>
                    </div>
                </div>

                <div class="project-card fade-in">
                    <div class="project-img">
                        <i class="fas fa-mobile-alt"></i>
                    </div>
                    <div class="project-content">
                        <h3>Weather App</h3>
                        <p>A beautiful weather application with nature-inspired design and accurate forecasts.</p>
                        <div class="project-tags">
                            <span class="project-tag">React Native</span>
                            <span class="project-tag">API</span>
                            <span class="project-tag">UI/UX</span>
                        </div>
                        <div class="project-links">
                            <a href="#"><i class="fab fa-github"></i> Code</a>
                            <a href="#"><i class="fas fa-external-link-alt"></i> Live Demo</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="section" id="contact">
        <div class="container">
            <div class="section-title">
                <h2>Get In Touch</h2>
            </div>
            <div class="contact-container">
                <div class="contact-info">
                    <div class="contact-item fade-in">
                        <div class="contact-icon">
                            <i class="fas fa-envelope"></i>
                        </div>
                        <div class="contact-details">
                            <h4>Email</h4>
                            <p>medini3425@gmail.com</p>
                        </div>
                    </div>
                    <div class="contact-item fade-in">
                        <div class="contact-icon">
                            <i class="fas fa-map-marker-alt"></i>
                        </div>
                        <div class="contact-details">
                            <h4>Location</h4>
                            <p>Sri Lanka</p>
                        </div>
                    </div>
                    <div class="contact-item fade-in">
                        <div class="contact-icon">
                            <i class="fas fa-link"></i>
                        </div>
                        <div class="contact-details">
                            <h4>Social Media</h4>
                            <div class="social-links">
                                <a href="#"><i class="fab fa-linkedin-in"></i></a>
                                <a href="#"><i class="fab fa-github"></i></a>
                                <a href="#"><i class="fab fa-twitter"></i></a>
                                <a href="#"><i class="fab fa-instagram"></i></a>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="contact-form fade-in">
                    <form>
                        <div class="form-group">
                            <label for="name">Your Name</label>
                            <input type="text" id="name" placeholder="Enter your name">
                        </div>
                        <div class="form-group">
                            <label for="email">Your Email</label>
                            <input type="email" id="email" placeholder="Enter your email">
                        </div>
                        <div class="form-group">
                            <label for="message">Your Message</label>
                            <textarea id="message" placeholder="Enter your message"></textarea>
                        </div>
                        <button type="submit" class="btn btn-primary">Send Message</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-about">
                    <div class="footer-logo">
                        <i class="fas fa-leaf"></i>
                        <span>Medini Thrishala</span>
                    </div>
                    <p>Creating beautiful, nature-inspired digital experiences with clean code and innovative design.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#"><i class="fab fa-github"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-youtube"></i></a>
                    </div>
                </div>
                <div class="footer-links">
                    <h3>Quick Links</h3>
                    <ul>
                        <li><a href="#home">Home</a></li>
                        <li><a href="#about">About</a></li>
                        <li><a href="#skills">Skills</a></li>
                        <li><a href="#projects">Projects</a></li>
                        <li><a href="#contact">Contact</a></li>
                    </ul>
                </div>
                <div class="footer-links">
                    <h3>Skills</h3>
                    <ul>
                        <li><a href="#">Frontend Development</a></li>
                        <li><a href="#">Backend Development</a></li>
                        <li><a href="#">UI/UX Design</a></li>
                        <li><a href="#">Database Management</a></li>
                        <li><a href="#">Business Analysis</a></li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 Medini Thrishala. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // Initialize GSAP ScrollTrigger
        gsap.registerPlugin(ScrollTrigger);

        // Fade-in animation for elements
        document.addEventListener('DOMContentLoaded', function() {
            const fadeElements = document.querySelectorAll('.fade-in');
            
            fadeElements.forEach(element => {
                gsap.to(element, {
                    opacity: 1,
                    y: 0,
                    duration: 1,
                    scrollTrigger: {
                        trigger: element,
                        start: 'top 80%',
                        toggleActions: 'play none none none'
                    }
                });
            });

            // Animate skill bars
            const skillBars = document.querySelectorAll('.skill-progress');
            skillBars.forEach(bar => {
                const width = bar.getAttribute('data-width');
                gsap.to(bar, {
                    width: width,
                    duration: 2,
                    ease: 'power3.out',
                    scrollTrigger: {
                        trigger: bar,
                        start: 'top 80%',
                        toggleActions: 'play none none none'
                    }
                });
            });

            // Counter animation for stats
            const counters = document.querySelectorAll('.counter');
            counters.forEach(counter => {
                const target = +counter.getAttribute('data-target');
                const duration = 2000; // ms
                const step = target / (duration / 16); // 16ms per frame
                let current = 0;
                
                const updateCounter = () => {
                    current += step;
                    if (current < target) {
                        counter.textContent = Math.ceil(current);
                        requestAnimationFrame(updateCounter);
                    } else {
                        counter.textContent = target;
                    }
                };
                
                ScrollTrigger.create({
                    trigger: counter,
                    start: 'top 80%',
                    onEnter: updateCounter,
                    once: true
                });
            });

            // Floating icons animation
            gsap.to('.floating-icon', {
                y: 20,
                rotation: 5,
                duration: 3,
                repeat: -1,
                yoyo: true,
                ease: 'power1.inOut',
                stagger: 0.5
            });
        });
    </script>
</body>
</html>
