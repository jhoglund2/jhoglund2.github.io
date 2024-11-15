<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lina Lupita Arts</title>

    <script>
    if (/Mobi|Android/i.test(navigator.userAgent)) {
        window.location.href = "https://linalupita.com/mobile.html";
    }
</script>
    <style>
        /* Base styling and themes */
        :root {
            --background-light: #f5f0e6;
            --text-light: #3b3b3b;
            --accent-color: #b16a58;
            --secondary-accent: #476a6f;
            --dot-light: #619b8a;
            --background-dark: #2d2a26;
            --text-dark: #e6dcc8;
            --highlight-dark: #d4a276;
            --dot-dark-active: #d4a276;
            --dot-dark: #e6dcc8;
        }

        /* Light and dark themes */
        .light-theme {
            --background-color: var(--background-light);
            --text-color: var(--text-light);
            --accent-color: var(--accent-color);
            --dot-color: var(--dot-light);
            --dot-active-color: var(--text-light);
            --icon-color: var(--text-light);
            --hover-icon-color: var(--secondary-accent);
        }

        .dark-theme {
            --background-color: var(--background-dark);
            --text-color: var(--text-dark);
            --accent-color: var(--highlight-dark);
            --dot-color: var(--dot-dark);
            --dot-active-color: var(--dot-dark-active);
            --icon-color: var(--text-dark);
            --hover-icon-color: var(--highlight-dark);
        }

        body {
            font-family: 'Roboto Slab', serif;
            background-color: var(--background-color);
            color: var(--text-color);
            margin: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
            overflow-y: auto;
            transition: background-color 0.3s, color 0.3s;
        }

        /* Container styling */
        .container {
            max-width: 800px;
            width: 100%;
            text-align: center;
            border-radius: 12px;
            box-shadow: 0 8px 15px rgba(0, 0, 0, 0.15);
            padding-top: 2rem;
            margin-top: 3rem;
        }

        /* Header */
        .header h1 {
            font-size: 2.5rem;
            font-family: 'Futura', sans-serif;
            color: var(--accent-color);
            margin-bottom: 0.5rem;
            text-transform: uppercase;
        }

        /* Toggle buttons positioned just above the container */
        .toggle-buttons {
            position: absolute;
            top: 1rem;
            right: calc(50% - 400px);
            display: flex;
            gap: 0.5rem;
        }
        .toggle-buttons button {
            background: none;
            border: none;
            cursor: pointer;
            font-size: 1.2rem;
            color: inherit;
        }

        /* Navigation Links */
        .header-links {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-bottom: 1rem;
        }
        .header-links a {
            text-decoration: none;
            color: inherit;
            cursor: pointer;
            padding: 0.3rem 0.8rem;
            font-family: 'Futura', sans-serif;
            text-transform: uppercase;
            font-size: 0.8rem;
            letter-spacing: 0.5px;
            transition: transform 0.3s;
        }
        .header-links a:hover {
            transform: scale(1.1);
        }

        /* Slides container styling */
        .slides {
            display: flex;
            scroll-snap-type: x mandatory;
            overflow-x: auto;
            overflow-y: hidden;
            width: 100%;
            scrollbar-width: none;
        }
        .slides::-webkit-scrollbar {
            display: none;
        }

        /* Individual slide styling */
        .slide {
            flex: 0 0 100%;
            min-width: 100%;
            min-height: 70vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 1rem;
            box-sizing: border-box;
        }
        .slide h2 {
            font-size: 1.8rem;
            font-family: 'Futura', sans-serif;
            color: var(--accent-color);
            margin: 0.5rem 0;
        }
        .slide p {
            line-height: 1.6;
            max-width: 600px;
            font-family: 'Roboto Slab', serif;
        }
        .slide img {
            width: 100%;
            max-width: 600px;
            border-radius: 8px;
            box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.2);
        }

        /* Navigation dots */
        .dots {
            display: flex;
            justify-content: center;
            gap: 10px;
            padding: 1rem 0;
        }
        .dot {
            width: 12px;
            height: 12px;
            background: var(--dot-color);
            border-radius: 50%;
            cursor: pointer;
            transition: background 0.3s;
        }
        .dot.active {
            background: var(--dot-active-color);
        }

        /* Portfolio and Contact Sections */
        .bottom-sections {
            display: flex;
            justify-content: space-around;
            gap: 1rem;
            padding: 1rem;
        }
        .section {
            flex: 1;
            padding: 1rem;
            border-radius: 8px;
            text-align: center;
            box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
        }
        .button {
            padding: 0.5rem 1.5rem;
            font-family: 'Futura', sans-serif;
            border: 1px solid var(--text-color);
            border-radius: 8px;
            text-transform: uppercase;
            cursor: pointer;
            transition: background-color 0.3s, color 0.3s;
            background: none;
            color: var(--text-color);
        }
        .button:hover {
            background-color: var(--secondary-accent);
            color: #fff;
        }

        /* Icon styling */
        .icon-button {
            background: none;
            border: none;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            vertical-align: middle;
            margin-left: 0.5rem;
            transition: transform 0.3s;
        }
        .icon-button:hover {
            transform: scale(1.1);
        }
        .icon {
            width: 30px;
            height: 30px;
            transition: fill 0.3s;
            fill: var(--text-color);
        }
        .icon-button:hover .icon {
            fill: var(--hover-icon-color);
        }
         /* Dark theme SVG icon inversion */
    .dark-theme .icon {
        filter: invert(1);
    }

        /* Footer centered below container */
        footer {
            font-size: 0.8rem;
            padding: 1rem;
            color: var(--text-color);
            text-align: center;
            width: 100%;
            margin-top: 2rem;
        }
    </style>
</head>
<body class="light-theme">
    <!-- Toggle Buttons -->
    <div class="toggle-buttons">
        <button id="theme-toggle">🌙</button>
        <button id="language-toggle">Español</button>
    </div>

    <div class="container">
        <div class="header">
            <h1 id="site-title" onclick="scrollToSlide(0)">Lina Lupita Arts</h1>
        </div>

        <div class="header-links">
            <a onclick="scrollToSlide(1)" id="link-art-contractor">Project Management & Coordination</a>
            <a onclick="scrollToSlide(2)" id="link-community-organizer">Exhibition Curation & Installation</a>
            <a onclick="scrollToSlide(3)" id="link-event-planner">Arts Consulting Services</a>
            <a onclick="scrollToSlide(4)" id="link-artist">Artwork Commissions</a>
        </div>

        <!-- Slides container with mission statement as the first slide -->
        <div class="slides" id="slides">
            <section class="slide">
                <h2 id="mission-title">Mission Statement</h2>
                <p id="mission">To foster arts and arts-related programming in the Southeast Los Angeles Community and beyond...</p>
                <img src="https://i.ibb.co/1M0sT3m/mission.png" alt="Mission Statement Image">
            </section>
            <section class="slide">
                <h2 id="slide1-title">Seamless Art Project Management</h2>
                <p id="slide1-content">Our team offers complete project management services for arts projects, ensuring they are executed within planned timeframes and budgets.</p>
                <img src="https://i.ibb.co/9Z6d1BD/manage.png" alt="Project Management Image">
            </section>
            <section class="slide">
                <h2 id="slide2-title">Curating Experiences That Connect</h2>
                <p id="slide2-content">Our curated exhibitions reflect the voices of local communities, working with artists to bring diverse voices to the forefront.</p>
                <img src="https://i.ibb.co/jGk9Zkr/curate.png" alt="Curating Experiences Image">
            </section>
            <section class="slide">
                <h2 id="slide3-title">Empowering Your Vision Through Art</h2>
                <p id="slide3-content">We provide consulting services to organizations looking to make a meaningful impact through the arts.</p>
                <img src="https://i.ibb.co/V3n3zQ7/consult.png" alt="Consulting Image">
            </section>
            <section class="slide">
                <h2 id="slide4-title">Custom Art Creations for Every Community</h2>
                <p id="slide4-content">Led by Edlin G. Lopez, our commissions span various artistic forms, focusing on accessibility and community representation.</p>
                <img src="https://i.ibb.co/LP5jBgq/art.png" alt="Art Creations Image">
            </section>
        </div>

        <!-- Dot Indicators -->
        <div class="dots">
            <span class="dot" onclick="scrollToSlide(0)"></span>
            <span class="dot" onclick="scrollToSlide(1)"></span>
            <span class="dot" onclick="scrollToSlide(2)"></span>
            <span class="dot" onclick="scrollToSlide(3)"></span>
            <span class="dot" onclick="scrollToSlide(4)"></span>
        </div>

        <!-- Portfolio and Contact Buttons -->
        <div class="bottom-sections">
            <div class="section">
                <h2 id="portfolio-title">Portfolio</h2>
                <button class="button" onclick="window.open('https://dribbble.com/linaxlupita')">Dribbble</button>
                <button class="button" onclick="window.open('https://behance.net/linaxlupita')">Behance</button>
            </div>
            <div class="section">
                <h2 id="contact-title">Contact</h2>
                <button class="button" onclick="location.href='mailto:eglop23@gmail.com'">Email Me</button>
                <button class="icon-button" onclick="window.open('https://www.linkedin.com/in/edlin-hoglund-lopez-094736198/')">
                    <img class="icon" src="https://www.svgrepo.com/show/365515/linkedin-logo-thin.svg" alt="LinkedIn Icon">
                </button>
                <button class="icon-button" onclick="window.open('https://www.instagram.com/lina_lupita/')">
                    <img class="icon" src="https://www.svgrepo.com/show/365495/instagram-logo-thin.svg" alt="Instagram Icon">
                </button>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer>&copy; 2024 Lina Lupita Arts, LLC</footer>

    <script>
        const dots = document.querySelectorAll(".dot");
        const slidesContainer = document.getElementById("slides");

        function scrollToSlide(slideIndex) {
            const slideWidth = slidesContainer.clientWidth;
            slidesContainer.scrollTo({
                left: slideWidth * slideIndex,
                behavior: "smooth"
            });
            updateActiveDot(slideIndex);
        }

        function updateActiveDot(currentIndex) {
            dots.forEach((dot, index) => {
                dot.classList.toggle("active", index === currentIndex);
            });
        }

        slidesContainer.addEventListener("scroll", () => {
            const slideWidth = slidesContainer.clientWidth;
            const currentIndex = Math.round(slidesContainer.scrollLeft / slideWidth);
            updateActiveDot(currentIndex);
        });

        // Theme toggle functionality
        const themeToggleButton = document.getElementById("theme-toggle");
        themeToggleButton.addEventListener("click", () => {
            document.body.classList.toggle("light-theme");
            document.body.classList.toggle("dark-theme");
            themeToggleButton.textContent = document.body.classList.contains("dark-theme") ? "☀️" : "🌙";
        });

        // Language toggle functionality
        const languageToggleButton = document.getElementById("language-toggle");
        languageToggleButton.addEventListener("click", () => {
            const isEnglish = languageToggleButton.textContent === "Español";
            languageToggleButton.textContent = isEnglish ? "English" : "Español";
            document.getElementById("site-title").textContent = isEnglish ? "Artes de Lina Lupita" : "Lina Lupita Arts";
            document.getElementById("mission-title").textContent = isEnglish ? "Declaración de Misión" : "Mission Statement";
            document.getElementById("mission").textContent = isEnglish
                ? "Fomentar las artes y la programación en la comunidad del sureste de Los Ángeles y más allá..."
                : "To foster arts and arts-related programming in the Southeast Los Angeles Community and beyond...";
            
            document.getElementById("link-art-contractor").textContent = isEnglish ? "Gestión de Proyectos y Coordinación" : "Project Management & Coordination";
            document.getElementById("link-community-organizer").textContent = isEnglish ? "Curaduría e Instalación de Exposiciones" : "Exhibition Curation & Installation";
            document.getElementById("link-event-planner").textContent = isEnglish ? "Servicios de Consultoría Artística" : "Arts Consulting Services";
            document.getElementById("link-artist").textContent = isEnglish ? "Comisiones de Obras de Arte" : "Artwork Commissions";

            document.getElementById("slide1-title").textContent = isEnglish ? "Gestión de Proyectos de Arte sin Complicaciones" : "Seamless Art Project Management";
            document.getElementById("slide1-content").textContent = isEnglish ? "Nuestro equipo ofrece servicios completos de gestión de proyectos artísticos, asegurando que se ejecuten dentro de los plazos y presupuestos planificados." : "Our team offers complete project management services for arts projects, ensuring they are executed within planned timeframes and budgets.";
            document.getElementById("slide2-title").textContent = isEnglish ? "Curación de Experiencias que Conectan" : "Curating Experiences That Connect";
            document.getElementById("slide2-content").textContent = isEnglish ? "Nuestras exposiciones curadas reflejan las voces de las comunidades locales. Trabajamos con artistas para destacar voces diversas." : "Our curated exhibitions reflect the voices of local communities, working with artists to bring diverse voices to the forefront.";
            document.getElementById("slide3-title").textContent = isEnglish ? "Empoderando su Visión a Través del Arte" : "Empowering Your Vision Through Art";
            document.getElementById("slide3-content").textContent = isEnglish ? "Proveemos servicios de consultoría a organizaciones que buscan un impacto significativo a través del arte." : "We provide consulting services to organizations looking to make a meaningful impact through the arts.";
            document.getElementById("slide4-title").textContent = isEnglish ? "Creaciones de Arte Personalizadas para Cada Comunidad" : "Custom Art Creations for Every Community";
            document.getElementById("slide4-content").textContent = isEnglish ? "Liderado por Edlin G. Lopez, nuestras comisiones abarcan diversas formas artísticas, enfocándose en la accesibilidad y representación comunitaria." : "Led by Edlin G. Lopez, our commissions span various artistic forms, focusing on accessibility and community representation.";
            document.getElementById("portfolio-title").textContent = isEnglish ? "Portafolio" : "Portfolio";
            document.getElementById("contact-title").textContent = isEnglish ? "Contacto" : "Contact";
        });
    </script> <script>
    function isMobileDevice() {
        return /Mobi|Android/i.test(navigator.userAgent);
    }

    if (isMobileDevice()) {
        document.body.innerHTML = `
            <!-- Mobile HTML Code -->
            <div class="toggle-buttons">
                <button id="theme-toggle">🌙</button>
                <h1 id="site-title">Lina Lupita Arts</h1>
                <button id="language-toggle">Español</button>
            </div>

            <div class="container">
                <div class="header-links">
                    <a onclick="scrollToSlide(1)" id="link-project-management">Project Management</a>
                    <a onclick="scrollToSlide(2)" id="link-curation">Curation</a>
                    <a onclick="scrollToSlide(3)" id="link-consulting">Consulting</a>
                    <a onclick="scrollToSlide(4)" id="link-commissions">Commissions</a>
                </div>

                <!-- Slides container -->
                <div class="slides" id="slides">
                    <section class="slide">
                        <h2 id="mission-title">Mission Statement</h2>
                        <p id="mission">To foster arts and arts-related programming in the Southeast Los Angeles Community and beyond...</p>
                        <img src="https://i.ibb.co/1M0sT3m/mission.png" alt="Mission Statement Image" style="max-width:50%; margin:0 auto;">
                    </section>
                    <section class="slide" onclick="openGallery('https://i.ibb.co/9Z6d1BD/manage.png')">
                        <h2 id="slide1-title">Seamless Art Project Management</h2>
                        <p id="slide1-content">Our team offers complete project management services for arts projects, ensuring they are executed within planned timeframes and budgets.</p>
                        <img src="https://i.ibb.co/9Z6d1BD/manage.png" alt="Project Management Image" style="max-width:50%; margin:0 auto;">
                    </section>
                    <!-- Add additional slides as necessary -->
                </div>

                <!-- Learn More Section -->
                <div class="learn-more-section">
                    <h2 id="learn-more-title">Learn More</h2>
                    <button class="button" onclick="window.open('https://dribbble.com/linaxlupita')" id="learn-more-dribbble">Dribbble</button>
                    <button class="button" onclick="window.open('https://behance.net/linaxlupita')" id="learn-more-behance">Behance</button>
                    <button class="button" onclick="location.href='mailto:eglop23@gmail.com'" id="learn-more-email">Email Me</button>
                    <button class="button" onclick="window.open('https://www.linkedin.com/in/edlin-hoglund-lopez-094736198/')" id="learn-more-linkedin">LinkedIn</button>
                    <button class="button" onclick="window.open('https://www.instagram.com/lina_lupita/')" id="learn-more-instagram">Instagram</button>
                </div>
            </div>

            <footer>&copy; 2024 Lina Lupita Arts, LLC</footer>
            
            <!-- Insert JavaScript code for mobile version functions -->
        `;

        // Additional JavaScript to handle theme and language toggle
        const themeToggleButton = document.getElementById("theme-toggle");
        themeToggleButton.addEventListener("click", () => {
            document.body.classList.toggle("light-theme");
            document.body.classList.toggle("dark-theme");
            themeToggleButton.textContent = document.body.classList.contains("dark-theme") ? "☀️" : "🌙";
        });

        const languageToggleButton = document.getElementById("language-toggle");
        languageToggleButton.addEventListener("click", () => {
            const isEnglish = languageToggleButton.textContent === "Español";
            languageToggleButton.textContent = isEnglish ? "English" : "Español";
            document.getElementById("site-title").textContent = isEnglish ? "Artes de Lina Lupita" : "Lina Lupita Arts";
            document.getElementById("learn-more-title").textContent = isEnglish ? "Más Información" : "Learn More";
        });
    }
</script>
<script type="text/javascript">

if (screen.width <= 699) {
document.location = "linalupita.com/mobile";
}

</script>
</body>
</html>
