<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lina Lupita Arts</title>
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
        }

        .dark-theme {
            --background-color: var(--background-dark);
            --text-color: var(--text-dark);
            --accent-color: var(--highlight-dark);
            --dot-color: var(--dot-dark);
            --dot-active-color: var(--dot-dark-active);
        }

        body {
            font-family: 'Roboto Slab', serif;
            background-color: var(--background-color);
            color: var(--text-color);
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: flex-start;
            min-height: 100vh;
            transition: background-color 0.3s, color 0.3s;
        }

        /* Container styling */
        .container {
            max-width: 800px;
            width: 100%;
            text-align: center;
            border-radius: 12px;
            box-shadow: 0 8px 15px rgba(0, 0, 0, 0.15);
        }

        /* Header and toggles */
        .header {
            position: relative;
            margin-bottom: 1.5rem;
        }
        .header h1 {
            font-size: 2.5rem;
            font-family: 'Futura', sans-serif;
            color: var(--accent-color);
            margin-bottom: 0.5rem;
            text-transform: uppercase;
        }
        .toggle-buttons {
            position: absolute;
            top: -30px;
            right: 0;
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
            overflow-x: auto;
            scroll-snap-type: x mandatory;
            scroll-behavior: smooth;
            width: 100%;
            -ms-overflow-style: none;
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
    </style>
</head>
<body class="light-theme">
    <div class="container">
        <div class="header">
            <div class="toggle-buttons">
                <button id="theme-toggle">🌙</button>
                <button id="language-toggle">Español</button>
            </div>
            <h1 id="site-title" onclick="scrollToSlide(0)">Lina Lupita Arts</h1>
        </div>

        <div class="header-links">
            <a onclick="scrollToSlide(1)">Project Management & Coordination</a>
            <a onclick="scrollToSlide(2)">Exhibition Curation & Installation</a>
            <a onclick="scrollToSlide(3)">Arts Consulting Services</a>
            <a onclick="scrollToSlide(4)">Artwork Commissions</a>
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
                <h2>Portfolio</h2>
                <button class="button" onclick="window.open('https://dribbble.com/linaxlupita')">Dribbble</button>
                <button class="button" onclick="window.open('https://behance.net/linaxlupita')">Behance</button>
            </div>
            <div class="section">
                <h2>Contact</h2>
                <button class="button" onclick="location.href='mailto:linaxlupita@example.com'">Email Me</button>
            </div>
        </div>
    </div>

    <script>
        // Toggle theme functionality
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
                ? "Fomentar las artes y la programación relacionada en la comunidad del sureste de Los Ángeles y más allá..."
                : "To foster arts and arts-related programming in the Southeast Los Angeles Community and beyond...";
            document.getElementById("slide1-title").textContent = isEnglish ? "Gestión de Proyectos de Arte sin Complicaciones" : "Seamless Art Project Management";
            document.getElementById("slide1-content").textContent = isEnglish
                ? "Nuestro equipo ofrece servicios completos de gestión de proyectos artísticos, asegurando que se ejecuten dentro de los plazos y presupuestos planificados."
                : "Our team offers complete project management services for arts projects, ensuring they are executed within planned timeframes and budgets.";
        });

        // Dots and slides navigation functionality
        const dots = document.querySelectorAll(".dot");
        let currentSlide = 0;

        function scrollToSlide(slideIndex) {
            const slideWidth = document.getElementById("slides").clientWidth;
            document.getElementById("slides").scrollTo({
                left: slideWidth * slideIndex,
                behavior: "smooth"
            });
            currentSlide = slideIndex;
            updateDots();
        }

        function updateDots() {
            dots.forEach((dot, index) => dot.classList.toggle("active", index === currentSlide));
        }

        updateDots();
    </script>
</body>
</html>
