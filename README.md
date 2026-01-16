<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ACQUAH Digital Services</title>

    <style>
        /* --- 1. Global Reset & Base Styles --- */
        * {
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; /* Modern, clean font */
            margin: 0;
            padding: 0;
            background: #f4f4f4;
            line-height: 1.6;
            color: #333;
        }

        /* --- 2. Header & Navigation --- */
        header {
            background: #003366;
            color: white;
            padding: 30px 20px;
            text-align: center;
        }

        header h1 { margin: 0; font-size: 2.5rem; }
        header p { margin: 10px 0 0; opacity: 0.9; font-size: 1.1rem; }

        nav {
            background: #222;
            padding: 15px;
            text-align: center;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 5px rgba(0,0,0,0.2);
        }

        nav a {
            color: white;
            text-decoration: none;
            margin: 0 15px;
            font-weight: bold;
            font-size: 16px;
            transition: color 0.3s;
            display: inline-block;
        }

        nav a:hover {
            color: #00ccff;
        }

        /* --- 3. Section Layouts --- */
        section {
            padding: 40px;
            background: white;
            margin: 30px auto;
            max-width: 1000px;
            display: none; /* Hidden by default via JS */
            border-radius: 8px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
        }

        h2 {
            color: #003366;
            border-bottom: 2px solid #eee;
            padding-bottom: 10px;
            margin-top: 0;
            font-size: 24px;
        }

        p {
            margin-bottom: 15px;
        }

        /* --- 4. The Grid System (Used on Home, Services, About) --- */
        .grid-container {
            display: flex;
            flex-wrap: wrap;
            gap: 25px;
            margin-top: 25px;
        }

        .card {
            background: #fff;
            padding: 25px;
            border-radius: 8px;
            flex: 1;
            min-width: 280px; /* Prevents squishing on mobile */
            border: 1px solid #eee;
            border-left: 5px solid #003366; /* Brand accent color */
            box-shadow: 0 2px 5px rgba(0,0,0,0.05);
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .card:hover {
            transform: translateY(-5px); /* Moves card up slightly */
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }

        .card h3 { margin-top: 0; color: #003366; }

        /* --- 5. Hero Section (Home) --- */
        .hero {
            text-align: center;
            padding-bottom: 40px;
            border-bottom: 1px solid #eee;
            margin-bottom: 30px;
        }

        .hero h2 { border: none; font-size: 2rem; color: #222; }
        
        .cta-button {
            background: #00ccff;
            color: #003366;
            padding: 15px 30px;
            text-decoration: none;
            font-weight: bold;
            border-radius: 5px;
            display: inline-block;
            margin-top: 20px;
            transition: background 0.3s;
            border: none;
            cursor: pointer;
            font-size: 16px;
        }
        .cta-button:hover { background: #0099cc; color: white; }

        /* --- 6. About Page Specifics --- */
        .about-split {
            display: flex;
            gap: 20px;
            margin-top: 30px;
            flex-wrap: wrap;
        }
        
        .mission-box, .vision-box {
            flex: 1;
            padding: 20px;
            background: #f9fcff;
            border: 1px solid #e0efff;
            border-radius: 8px;
        }
        
        .mission-box h3, .vision-box h3 { color: #003366; margin-top: 0; }

        /* --- 7. Portfolio Specifics --- */
        .project-card {
            background: white;
            border: 1px solid #ddd;
            border-radius: 8px;
            overflow: hidden;
            margin-bottom: 0; /* Handled by grid gap */
        }

        .project-header {
            background: #003366;
            color: white;
            padding: 15px;
        }
        
        .project-header h3 { color: white; margin: 0; font-size: 18px; }

        .project-body {
            padding: 20px;
        }

        .tag {
            background: #eee;
            color: #555;
            padding: 4px 10px;
            border-radius: 12px;
            font-size: 12px;
            font-weight: bold;
            display: inline-block;
            margin-bottom: 10px;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        /* --- 8. Contact Form --- */
        label { font-weight: bold; display: block; margin-top: 15px; }
        input, textarea { width: 100%; padding: 12px; margin-top: 5px; border: 1px solid #ccc; border-radius: 4px; font-family: inherit; }
        textarea { height: 120px; resize: vertical; }
        input[type=submit] { background: #003366; color: white; border: none; cursor: pointer; margin-top: 20px; font-size: 16px; padding: 12px; transition: background 0.3s; }
        input[type=submit]:hover { background: #004d99; }
        
        .social-links {
            background: #f9f9f9;
            padding: 20px;
            border-radius: 5px;
            margin-top: 20px;
        }

        /* --- 9. Footer --- */
        footer { background: #003366; color: white; text-align: center; padding: 20px; margin-top: 40px; }

        /* Mobile Responsiveness */
        @media (max-width: 600px) {
            nav a { display: block; margin: 10px 0; border-bottom: 1px solid #444; padding-bottom: 5px; }
            section { padding: 20px; margin: 15px 10px; }
            header h1 { font-size: 1.8rem; }
            .about-split { flex-direction: column; }
        }
    </style>

    <script>
        function showPage(pageId){
            let pages = document.querySelectorAll("section");
            pages.forEach(page => page.style.display = "none");
            document.getElementById(pageId).style.display = "block";
            window.scrollTo(0,0); // Scrolls to top when switching tabs
        }
    </script>
</head>

<body onload="showPage('home')">

<header>
    <h1>ACQUAH Digital Services</h1>
    <p>Empowering Businesses Through Technology</p>
</header>

<nav>
    <a href="#" onclick="showPage('home')">Home</a>
    <a href="#" onclick="showPage('about')">About</a>
    <a href="#" onclick="showPage('services')">Services</a>
    <a href="#" onclick="showPage('portfolio')">Portfolio</a>
    <a href="#" onclick="showPage('contact')">Contact</a>
</nav>

<!-- ================= HOME SECTION ================= -->
<section id="home">
    <div class="hero">
        <h2>Innovative Digital Solutions</h2>
        <p>We bridge the gap between complex technology and business growth. From custom software development to corporate ICT training, we are your partner in digital transformation.</p>
        <button class="cta-button" onclick="showPage('contact')">Get a Free Quote</button>
    </div>

    <h3 style="text-align:center; color:#555; margin-top: 40px;">Why Partner With Us?</h3>
    <div class="grid-container">
        <div class="card">
            <h3>🚀 Custom Development</h3>
            <p>We don't rely on generic templates. We build tailored websites and software designed to solve your specific business challenges.</p>
        </div>
        <div class="card">
            <h3>🎓 Expert Training</h3>
            <p>Empowering your workforce with the digital skills needed to thrive in today's economy through hands-on ICT tuition.</p>
        </div>
        <div class="card">
            <h3>🛠️ Reliable Support</h3>
            <p>Our job doesn't end at launch. We provide ongoing hardware maintenance and technical support to ensure maximum uptime.</p>
        </div>
    </div>
</section>

<!-- ================= ABOUT SECTION (ENHANCED) ================= -->
<section id="about">
    <h2>About ACQUAH Digital Services</h2>
    <p>
        Founded in Ghana, ACQUAH Digital Services was born out of a desire to make high-quality technology accessible to local businesses and educational institutions. 
        We believe that technology is not just a tool, but a catalyst for economic growth.
    </p>
    <p>
        We specialize in understanding the unique challenges of the West African market, allowing us to deliver solutions that are not only technically sound but also culturally relevant and affordable.
    </p>

    <!-- Split Layout for Mission/Vision -->
    <div class="about-split">
        <div class="mission-box">
            <h3>Our Mission</h3>
            <p>To empower businesses and individuals with modern digital tools that drive efficiency, innovation, and sustainable growth.</p>
        </div>
        <div class="vision-box">
            <h3>Our Vision</h3>
            <p>To become the leading ICT solutions provider in West Africa, recognized for our integrity, innovation, and commitment to client success.</p>
        </div>
    </div>

    <h3 style="margin-top: 40px;">Our Core Values</h3>
    <div class="grid-container">
        <div class="card" style="border-left-color: #00ccff;">
            <h3>Integrity</h3>
            <p>We believe in transparent pricing and honest communication.</p>
        </div>
        <div class="card" style="border-left-color: #00ccff;">
            <h3>Innovation</h3>
            <p>We stay updated with global tech trends to bring you the best.</p>
        </div>
        <div class="card" style="border-left-color: #00ccff;">
            <h3>Excellence</h3>
            <p>We are committed to delivering high-quality work, on time, every time.</p>
        </div>
    </div>
</section>

<!-- ================= SERVICES SECTION (ENHANCED) ================= -->
<section id="services">
    <h2>Our Professional Services</h2>
    <p>We offer a comprehensive suite of digital services designed to handle every aspect of your business's technology needs.</p>

    <div class="grid-container">
        <div class="card">
            <h3>🌐 Website Development</h3>
            <p><strong>Corporate & E-commerce:</strong> We design responsive, SEO-friendly websites that look great on phones and computers. From simple landing pages to complex online stores.</p>
        </div>

        <div class="card">
            <h3>🎨 Graphic Design & Branding</h3>
            <p><strong>Visual Identity:</strong> Stand out from the crowd. We create logos, business cards, social media flyers, and complete brand identity packages that resonate with your audience.</p>
        </div>

        <div class="card">
            <h3>👨‍🏫 ICT Training</h3>
            <p><strong>Capacity Building:</strong> We offer corporate training sessions for staff and private tutoring for individuals. Topics include Microsoft Office, Web Basics, and Digital Marketing.</p>
        </div>

        <div class="card">
            <h3>🔧 Repairs & Maintenance</h3>
            <p><strong>Technical Support:</strong> Hardware diagnostics, software installation, virus removal, and routine maintenance to keep your business computers running smoothly.</p>
        </div>
    </div>
</section>

<!-- ================= PORTFOLIO SECTION (ENHANCED) ================= -->
<section id="portfolio">
    <h2>Our Portfolio</h2>
    <p>Take a look at some of the projects we have successfully delivered to our clients.</p>

    <div class="grid-container">
        <!-- Project 1 -->
        <div class="card project-card">
            <div class="project-header">
                <h3>StartUp Ghana Hub</h3>
            </div>
            <div class="project-body">
                <span class="tag">Web Development</span>
                <p><strong>The Challenge:</strong> A local incubator needed a platform to showcase startups to international investors.</p>
                <p><strong>The Solution:</strong> We built a dynamic portal allowing startups to create profiles, upload pitch decks, and connect with mentors.</p>
            </div>
        </div>

        <!-- Project 2 -->
        <div class="card project-card">
            <div class="project-header">
                <h3>Edu-Track System</h3>
            </div>
            <div class="project-body">
                <span class="tag">Software / App</span>
                <p><strong>The Challenge:</strong> A private school struggled with manual attendance and grade tracking.</p>
                <p><strong>The Solution:</strong> We developed a lightweight JavaScript-based management prototype for tracking student records efficiently.</p>
            </div>
        </div>

        <!-- Project 3 -->
        <div class="card project-card">
            <div class="project-header">
                <h3>Logistics Co. Rebrand</h3>
            </div>
            <div class="project-body">
                <span class="tag">Graphic Design</span>
                <p><strong>The Challenge:</strong> An established logistics company had an outdated image that didn't reflect their modern fleet.</p>
                <p><strong>The Solution:</strong> Designed a new logo, letterheads, and vehicle branding mockups to refresh their corporate identity.</p>
            </div>
        </div>
    </div>
</section>

<!-- ================= CONTACT SECTION ================= -->
<section id="contact">
    <h2>Contact Us</h2>
    <p>Ready to start your project? Send us a message below.</p>

    <form action="mailto:humphreyacquah4@gmail.com" method="post" enctype="text/plain">
        <label for="name">Your Name:</label>
        <input type="text" id="name" name="name" placeholder="Enter your full name" required>

        <label for="email">Your Email:</label>
        <input type="email" id="email" name="email" placeholder="Enter your email address" required>

        <label for="message">Message:</label>
        <textarea id="message" name="message" placeholder="Tell us about your project requirements..." required></textarea>

        <input type="submit" value="Send Message">
    </form>

    <hr style="margin: 30px 0; border: 0; border-top: 1px solid #ccc;">

    <h3>Founder’s Profile</h3>
    <p>ACQUAH Digital Services is founded and managed by <strong> Mr.Humphrey Herbert Acquah</strong>.</p>

    <div class="social-links">
        <p>📧 Email: <a href="mailto:humphreyacquah4@gmail.com">humphreyacquah4@gmail.com</a></p>
        <p>🔗 LinkedIn: <a href="https://www.linkedin.com/in/humphrey-acquah-59955b364" target="_blank">linkedin.com/in/humphrey-acquah</a></p>
        <p>💻 GitHub: <a href="https://github.com/humphreyacquah4-bit" target="_blank">github.com/humphreyacquah4-bit</a></p>
        <p>📱 Brand Handle: <strong>@koffie_blaq</strong></p>
    </div>
</section

<footer>
    <p>&copy; 2025 ACQUAH Digital Services. All Rights Reserved.</p>
</footer>

</body>
</html>
