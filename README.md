<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Divya B MTP Portfolio</title>
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;700;800&display=swap" rel="stylesheet" />
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" />
    <style>
        :root {
            --bg-0: #070b14;
            --bg-1: #0f172a;
            --bg-2: #111827;
            --text-1: #e5e7eb;
            --text-2: #9ca3af;
            --stroke: rgba(255, 255, 255, 0.12);
            --card: rgba(15, 23, 42, 0.72);
            --accent-a: #ebf0f1;
            --accent-b: #140205;
            --accent-c: #010e14;
            --shadow: 0 20px 45px rgba(0, 0, 0, 0.45);
        }

        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            font-family: "Plus Jakarta Sans", sans-serif;
            color: var(--text-1);
            line-height: 1.65;
            background:
                radial-gradient(circle at 8% 10%, rgba(34, 211, 238, 0.2), transparent 32%),
                radial-gradient(circle at 85% 18%, rgba(251, 113, 133, 0.2), transparent 30%),
                radial-gradient(circle at 70% 80%, rgba(245, 158, 11, 0.16), transparent 34%),
                linear-gradient(150deg, var(--bg-0), var(--bg-1) 45%, #0b1220 100%);
            min-height: 100vh;
            overflow-x: hidden;
        }

        .container {
            width: min(1080px, 92%);
            margin: 0 auto;
            padding: 52px 0 70px;
            position: relative;
            z-index: 1;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            background: rgba(7, 11, 20, 0.8);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid var(--stroke);
            z-index: 1000;
            padding: 16px 0;
            transition: all 0.3s ease;
        }

        nav.scrolled {
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        .nav-container {
            width: min(1080px, 92%);
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .nav-logo {
            font-weight: 800;
            font-size: 1.2rem;
            background: linear-gradient(90deg, var(--accent-a), var(--accent-b));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .nav-links {
            display: flex;
            gap: 30px;
            list-style: none;
            padding: 0;
            margin: 0;
        }

        .nav-links a {
            color: var(--text-2);
            text-decoration: none;
            font-size: 0.95rem;
            transition: color 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: var(--accent-a);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--accent-a);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        header {
            display: grid;
            place-items: center;
            text-align: center;
            gap: 14px;
            margin: 100px 0 34px;
            animation: fadeUp 700ms ease both;
        }

        .tag {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 6px 12px;
            border: 1px solid var(--stroke);
            border-radius: 999px;
            color: #bae6fd;
            background: rgba(14, 22, 39, 0.62);
            font-size: 0.82rem;
            letter-spacing: 0.06em;
            text-transform: uppercase;
        }

        h1 {
            margin: 0;
            font-size: clamp(2rem, 4.7vw, 3.7rem);
            line-height: 1.1;
            letter-spacing: -0.02em;
            text-wrap: balance;
            background: linear-gradient(90deg, #0788a2 0%, #dbeafe 35%, #99f6e4 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .subtitle {
            margin: 0;
            color: var(--text-2);
            font-size: clamp(0.98rem, 1.65vw, 1.08rem);
            max-width: 760px;
        }

        .social-links {
            display: flex;
            gap: 16px;
            justify-content: center;
            margin-top: 20px;
        }

        .social-links a {
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            border: 1px solid var(--stroke);
            border-radius: 50%;
            color: var(--accent-a);
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .social-links a:hover {
            background: rgba(34, 211, 238, 0.1);
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(34, 211, 238, 0.2);
        }

        .photo {
            display: grid;
            place-items: center;
            margin: 20px 0 30px;
            animation: fadeUp 860ms ease both;
        }

        .photo img {
            width: clamp(170px, 26vw, 220px);
            height: clamp(170px, 26vw, 220px);
            border-radius: 50%;
            object-fit: cover;
            border: 3px solid rgba(255, 255, 255, 0.85);
            box-shadow:
                0 0 0 8px rgba(34, 211, 238, 0.18),
                0 24px 50px rgba(0, 0, 0, 0.5);
            transition: transform 0.3s ease;
        }

        .photo img:hover {
            transform: scale(1.05);
        }

        .section {
            background: var(--card);
            backdrop-filter: blur(12px);
            border: 1px solid var(--stroke);
            border-radius: 18px;
            padding: 28px;
            margin: 18px 0;
            box-shadow: var(--shadow);
            animation: fadeUp 980ms ease both;
            transition: all 0.3s ease;
        }

        .section:hover {
            border-color: rgba(12, 79, 89, 0.5);
            box-shadow: 0 20px 50px rgba(34, 211, 238, 0.15);
        }

        .section h2 {
            margin: 0 0 12px;
            font-size: 1.4rem;
            color: #e2e8f0;
            letter-spacing: 0.01em;
        }

        .section p {
            margin: 0;
            color: #cbd5e1;
        }

        .skills {
            display: grid;
            grid-template-columns: repeat(3, minmax(220px, 1fr));
            gap: 16px;
        }

        .skill-category {
            background: rgba(15, 23, 42, 0.65);
            border: 1px solid rgba(148, 163, 184, 0.25);
            border-radius: 14px;
            padding: 16px;
            transition: all 0.3s ease;
        }

        .skill-category:hover {
            transform: translateY(-5px);
            border-color: var(--accent-a);
            box-shadow: 0 15px 30px rgba(34, 211, 238, 0.1);
        }

        .skill-category h3 {
            margin: 0 0 10px;
            color: #93c5fd;
            font-size: 1rem;
        }

        .skill-category ul {
            list-style: none;
            padding: 0;
            margin: 0;
            display: grid;
            gap: 8px;
        }

        .skill-category li {
            border: 1px solid rgba(100, 116, 139, 0.4);
            border-radius: 10px;
            padding: 8px 10px;
            color: #dbeafe;
            background: rgba(2, 6, 23, 0.45);
            font-size: 0.94rem;
            transition: all 0.3s ease;
        }

        .skill-category li:hover {
            background: rgba(34, 211, 238, 0.1);
            border-color: var(--accent-a);
            color: var(--accent-a);
        }

        .cta-buttons {
            display: flex;
            gap: 16px;
            justify-content: center;
            margin-top: 28px;
            flex-wrap: wrap;
            animation: fadeUp 1120ms ease both;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            padding: 12px 22px;
            border-radius: 12px;
            text-decoration: none;
            font-weight: 700;
            letter-spacing: 0.01em;
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            font-family: "Plus Jakarta Sans", sans-serif;
            font-size: 0.95rem;
        }

        .btn-primary {
            color: #081224;
            background: linear-gradient(95deg, var(--accent-a), var(--accent-b));
            box-shadow: 0 10px 30px rgba(34, 211, 238, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 15px 40px rgba(34, 211, 238, 0.4);
        }

        .btn-secondary {
            color: var(--accent-a);
            background: transparent;
            border: 1px solid var(--accent-a);
        }

        .btn-secondary:hover {
            background: rgba(34, 211, 238, 0.1);
            transform: translateY(-2px);
        }

        @keyframes fadeUp {
            from {
                opacity: 0;
                transform: translateY(16px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .reveal {
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.6s ease;
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        @media (max-width: 900px) {
            .skills {
                grid-template-columns: 1fr;
            }
            .section {
                padding: 20px;
            }
            .cta-buttons {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav id="navbar">
        <div class="nav-container">
            <div class="nav-logo">FB</div>
            <ul class="nav-links">
                <li><a href="#about">About</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </div>
    </nav>
    <!-- Google Font -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
            padding: 20px;
        }

        .card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(15px);
            border-radius: 20px;
            padding: 30px;
            width: 100%;
            max-width: 700px;
            color: white;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
            animation: fadeIn 1s ease-in-out;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .profile {
            text-align: center;
            margin-bottom: 25px;
        }

        .profile img {
            width: 140px;
            height: 140px;
            border-radius: 50%;
            border: 4px solid white;
            object-fit: cover;
            margin-bottom: 15px;
            box-shadow: 0 0 20px rgba(255, 255, 255, 0.4);
        }

        .profile h1 {
            font-weight: 600;
            margin-bottom: 5px;
        }

        .profile p {
            font-size: 14px;
            opacity: 0.9;
        }

        section {
            margin-top: 25px;
        }

        section h2 {
            margin-bottom: 10px;
            font-size: 18px;
            border-bottom: 2px solid rgba(255, 255, 255, 0.3);
            display: inline-block;
            padding-bottom: 5px;
        }

        .about p {
            margin-top: 10px;
            font-size: 14px;
            line-height: 1.6;
        }

        .skills {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-top: 15px;
        }

        .skill {
            background: rgba(255, 255, 255, 0.2);
            padding: 8px 15px;
            border-radius: 20px;
            font-size: 13px;
            transition: 0.3s ease;
            cursor: pointer;
        }

        .skill:hover {
            background: white;
            color: #203a43;
            transform: scale(1.05);
        }

        .github {
            text-align: center;
            margin-top: 25px;
        }

        .btn {
            display: inline-block;
            padding: 10px 20px;
            border-radius: 25px;
            background: white;
            color: #203a43;
            text-decoration: none;
            font-weight: 600;
            transition: 0.3s ease;
        }

        .btn:hover {
            background: #063644;
            color: white;
            transform: scale(1.05);
        }

        @media (max-width: 600px) {
            .card {
                padding: 20px;
            }
        }
    </style>
</head>

<body>

    <div class="card">

        <div class="profile">
            <img src="images/profile.png" alt="Divya B">
            <h1>Divya B</h1>
            <p>B.Tech CSE (AI & Data Science) Student</p>
        </div>

        <section class="about">
            <h2>About Me</h2>
            <p>
                I'm Divya B, a first-year B.Tech student in Computer Science and Engineering
                (AI & Data Science) at Lal Bahadhur Shastri College of Engineering, Kasaragod.
                I am passionate about coding, problem solving, and learning new technologies. I like working on projects that challenge me and help me grow as a developer. I am eager to explore the world of AI and data science and contribute to innovative solutions in the future. 
            </p>
        </section>
        
        <h2>Education</h2>
        <ul>

            <li>B.Tech in CSE(ai and data science)-2025-2029</li>
            <li>Higher Secodary Education-Science Stream</li>
        </ul>
        <h2>Technical Skills</h2>

        <p>C Programming</p>
        <div class="skill-bar">
            <div class="c"></div>
        </div>

        <p>Python</p>
        <div class="skill-bar">
            <div class="python"></div>
        </div>

        <p>Problem Solving</p>
        <div class="skill-bar">
            <div class="problem"></div>
        </div>

        <section>
            <h2>Skills</h2>
            <div class="skills">
                <div class="skill">C Programming (Basics)</div>
                <div class="skill">Python (Basics)</div>
                <div class="skill">Problem Solving</div>
                <div class="skill">HTML</div>
                <div class="skill">CSS</div>
            </div>
        </section>

        <h2>contact</h2>
        <section id="contact">
            <h2>9495784492</h2>
            <p>Email:divyaabhatb@gmail.com</p>
        <p>

        <div class="github">
            <a href="https://github.com/divyabhatb" target="_blank" class="btn">
                Visit My GitHub
            </a>
        </div>

    </div>
    
    <section class="section reveal" id="skills">
            <h2>Skills</h2>
            <div class="skills">
                <div class="skill-category">
                    <h3>Technical</h3>
                    <ul>
                        <li>Python (Basics to Intermediate)</li>
                        <li>Web Development (HTML, CSS, JavaScript)</li>
                    </ul>
                </div>
                <div class="skill-category">
                    <h3>Leadership & Communication</h3>
                    <ul>
                        <li>Leadership & Communication</li>
                        <li>Community Building</li>
                        <li>Event & Webinar Coordination</li>
                        <li>Public Speaking & Presentation</li>
                    </ul>
                </div>
            </div>
        </section>

        <section class="section reveal" id="contact">
            <h2>Let's Connect</h2>
            <p style="margin-bottom: 20px;">I'm always interested in hearing about new projects and opportunities. Feel free to reach out!</p>
            <div class="cta-buttons">
                <a href="https://github.com/divyabhatb" target="_blank" rel="noopener noreferrer" class="btn btn-primary">
                    <i class="fab fa-github"></i> View My GitHub
                </a>
                <a href="mailto:divyaabhatb@gmail.com" class="btn btn-secondary">
                    <i class="fas fa-envelope"></i> Send Email
                </a>
            </div>
        </section>
    </div>

    <script>
        // Navbar scroll effect
        const navbar = document.getElementById('navbar');
        window.addEventListener('scroll', () => {
            if (window.scrollY > 50) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });

        // Smooth scroll for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth' });
                }
            });
        });

        // Reveal elements on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('active');
                    observer.unobserve(entry.target);
                }
            });
        }, observerOptions);

        document.querySelectorAll('.reveal').forEach(element => {
            observer.observe(element);
        });
    </script>

</body>

</html