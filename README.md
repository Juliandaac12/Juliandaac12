<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tu Nombre - GitHub</title>
    <style>
        /* Variables CSS para colores y fuentes */
        :root {
            --primary-color: #2d3436;
            --secondary-color: #0984e3;
            --accent-color: #00b894;
            --light-color: #f5f6fa;
            --dark-color: #2d3436;
            --text-color: #2d3436;
            --text-light: #636e72;
            --shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }

        /* Estilos base */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--text-color);
            background-color: var(--light-color);
        }

        a {
            text-decoration: none;
            color: var(--secondary-color);
            transition: var(--transition);
        }

        a:hover {
            color: var(--accent-color);
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        section {
            padding: 80px 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 50px;
            font-size: 2.5rem;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background-color: var(--accent-color);
        }

        .btn {
            display: inline-block;
            padding: 12px 30px;
            background-color: var(--secondary-color);
            color: white;
            border-radius: 5px;
            font-weight: 600;
            transition: var(--transition);
            border: none;
            cursor: pointer;
        }

        .btn:hover {
            background-color: var(--accent-color);
            transform: translateY(-3px);
            box-shadow: var(--shadow);
            color: white;
        }

        /* Header */
        header {
            background-color: var(--primary-color);
            color: white;
            padding: 20px 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: var(--shadow);
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
        }

        .logo span {
            color: var(--accent-color);
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 30px;
        }

        .nav-links a {
            color: white;
            font-weight: 500;
        }

        .nav-links a:hover {
            color: var(--accent-color);
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: white;
            padding: 150px 0 100px;
            text-align: center;
        }

        .hero-content h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
        }

        .hero-content p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 30px;
            opacity: 0.9;
        }

        .hero-btns {
            display: flex;
            justify-content: center;
            gap: 15px;
        }

        .hero-btns .btn {
            background-color: transparent;
            border: 2px solid white;
        }

        .hero-btns .btn:hover {
            background-color: white;
            color: var(--primary-color);
        }

        /* About Section */
        .about-content {
            display: flex;
            align-items: center;
            gap: 50px;
        }

        .about-text {
            flex: 1;
        }

        .about-text h2 {
            margin-bottom: 20px;
        }

        .about-text p {
            margin-bottom: 15px;
            color: var(--text-light);
        }

        .about-image {
            flex: 1;
            text-align: center;
        }

        .about-image img {
            max-width: 100%;
            border-radius: 10px;
            box-shadow: var(--shadow);
        }

        /* Skills Section */
        .skills {
            background-color: #f8f9fa;
        }

        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }

        .skill-card {
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: var(--shadow);
            text-align: center;
            transition: var(--transition);
        }

        .skill-card:hover {
            transform: translateY(-10px);
        }

        .skill-icon {
            font-size: 2.5rem;
            color: var(--secondary-color);
            margin-bottom: 15px;
        }

        .skill-card h3 {
            margin-bottom: 15px;
        }

        /* Projects Section */
        .projects-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .project-card {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .project-card:hover {
            transform: translateY(-10px);
        }

        .project-img {
            height: 200px;
            background-color: #ddd;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--text-light);
        }

        .project-content {
            padding: 20px;
        }

        .project-content h3 {
            margin-bottom: 10px;
        }

        .project-content p {
            color: var(--text-light);
            margin-bottom: 15px;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 15px;
        }

        .tech-tag {
            background-color: #e9ecef;
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 0.8rem;
            color: var(--text-light);
        }

        /* Contact Section */
        .contact {
            background-color: var(--primary-color);
            color: white;
            text-align: center;
        }

        .contact .section-title::after {
            background-color: white;
        }

        .contact p {
            max-width: 600px;
            margin: 0 auto 30px;
            opacity: 0.9;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
        }

        .social-link {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 50px;
            height: 50px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            transition: var(--transition);
        }

        .social-link:hover {
            background-color: var(--accent-color);
            transform: translateY(-5px);
        }

        /* Footer */
        footer {
            background-color: var(--dark-color);
            color: white;
            text-align: center;
            padding: 20px 0;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .navbar {
                flex-direction: column;
            }

            .nav-links {
                margin-top: 20px;
            }

            .nav-links li {
                margin: 0 10px;
            }

            .hero-content h1 {
                font-size: 2.5rem;
            }

            .about-content {
                flex-direction: column;
            }

            .hero-btns {
                flex-direction: column;
                align-items: center;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <nav class="navbar">
                <div class="logo">Tu<span>Nombre</span></div>
                <ul class="nav-links">
                    <li><a href="#about">Sobre mí</a></li>
                    <li><a href="#skills">Habilidades</a></li>
                    <li><a href="#projects">Proyectos</a></li>
                    <li><a href="#contact">Contacto</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <h1>Hola, soy <span style="color: var(--accent-color);">Tu Nombre</span></h1>
                <p>Desarrollador de software apasionado por crear soluciones innovadoras y eficientes. Bienvenido a mi portafolio de GitHub.</p>
                <div class="hero-btns">
                    <a href="#projects" class="btn">Ver Proyectos</a>
                    <a href="#contact" class="btn">Contáctame</a>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
        <div class="container">
            <h2 class="section-title">Sobre Mí</h2>
            <div class="about-content">
                <div class="about-text">
                    <h2>¡Hola! Soy [Tu Nombre]</h2>
                    <p>Soy un desarrollador [Frontend/Backend/Full Stack] con [X] años de experiencia en la creación de aplicaciones web y soluciones de software.</p>
                    <p>Me apasiona resolver problemas complejos mediante código limpio y eficiente. Siempre estoy aprendiendo nuevas tecnologías y mejorando mis habilidades.</p>
                    <p>En mi tiempo libre, disfruto contribuir a proyectos de código abierto y participar en comunidades de desarrolladores.</p>
                    <a href="#" class="btn">Descargar CV</a>
                </div>
                <div class="about-image">
                    <!-- Reemplaza con tu imagen -->
                    <div style="width: 100%; height: 400px; background-color: #ddd; border-radius: 10px; display: flex; align-items: center; justify-content: center; color: var(--text-light);">
                        Tu imagen aquí
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="skills">
        <div class="container">
            <h2 class="section-title">Mis Habilidades</h2>
            <div class="skills-container">
                <div class="skill-card">
                    <div class="skill-icon">💻</div>
                    <h3>Frontend</h3>
                    <p>HTML, CSS, JavaScript, React, Vue.js, Angular</p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">⚙️</div>
                    <h3>Backend</h3>
                    <p>Node.js, Python, PHP, Java, C#, Bases de datos</p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">📱</div>
                    <h3>Mobile</h3>
                    <p>React Native, Flutter, iOS, Android</p>
                </div>
                <div class="skill-card">
                    <div class="skill-icon">🔧</div>
                    <h3>Herramientas</h3>
                    <p>Git, Docker, AWS, CI/CD, Testing</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="projects">
        <div class="container">
            <h2 class="section-title">Proyectos Destacados</h2>
            <div class="projects-container">
                <div class="project-card">
                    <div class="project-img">
                        Imagen del proyecto
                    </div>
                    <div class="project-content">
                        <h3>Nombre del Proyecto 1</h3>
                        <p>Descripción breve del proyecto, qué hace y qué tecnologías utiliza.</p>
                        <div class="project-tech">
                            <span class="tech-tag">React</span>
                            <span class="tech-tag">Node.js</span>
                            <span class="tech-tag">MongoDB</span>
                        </div>
                        <a href="#" class="btn">Ver en GitHub</a>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-img">
                        Imagen del proyecto
                    </div>
                    <div class="project-content">
                        <h3>Nombre del Proyecto 2</h3>
                        <p>Descripción breve del proyecto, qué hace y qué tecnologías utiliza.</p>
                        <div class="project-tech">
                            <span class="tech-tag">Vue.js</span>
                            <span class="tech-tag">Express</span>
                            <span class="tech-tag">PostgreSQL</span>
                        </div>
                        <a href="#" class="btn">Ver en GitHub</a>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-img">
                        Imagen del proyecto
                    </div>
                    <div class="project-content">
                        <h3>Nombre del Proyecto 3</h3>
                        <p>Descripción breve del proyecto, qué hace y qué tecnologías utiliza.</p>
                        <div class="project-tech">
                            <span class="tech-tag">Python</span>
                            <span class="tech-tag">Django</span>
                            <span class="tech-tag">MySQL</span>
                        </div>
                        <a href="#" class="btn">Ver en GitHub</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
        <div class="container">
            <h2 class="section-title">Contáctame</h2>
            <p>¿Tienes un proyecto en mente o quieres colaborar? ¡No dudes en contactarme!</p>
            <a href="mailto:tuemail@ejemplo.com" class="btn">Enviar Email</a>
            <div class="social-links">
                <a href="#" class="social-link">GitHub</a>
                <a href="#" class="social-link">LinkedIn</a>
                <a href="#" class="social-link">Twitter</a>
                <a href="#" class="social-link">Instagram</a>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <p>&copy; 2023 Tu Nombre. Todos los derechos reservados.</p>
        </div>
    </footer>

    <script>
        // Smooth scrolling para los enlaces de navegación
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if(targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if(targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });
    </script>
</body>
</html>
