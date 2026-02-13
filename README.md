<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Arnav - Affordable web developer offering modern, clean, and professional websites.">
    <title>Arnav | Web Developer</title>

    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
    <link href="https://unpkg.com/aos@2.3.4/dist/aos.css" rel="stylesheet">

    <style>
        html { scroll-behavior: smooth; }

        body {
            margin: 0;
            font-family: 'Inter', sans-serif;
            color: white;
            overflow-x: hidden;
            background: #0f172a;
            transition: background 0.3s ease; /* For dark mode toggle */
        }

        /* 🍎 Apple Style Animated Background */
        body::before {
            content: "";
            position: fixed;
            width: 200%;
            height: 200%;
            top: -50%;
            left: -50%;
            z-index: -1;
            background:
                radial-gradient(circle at 20% 30%, rgba(168,85,247,0.4), transparent 45%),
                radial-gradient(circle at 80% 40%, rgba(139,92,246,0.35), transparent 50%),
                radial-gradient(circle at 50% 75%, rgba(124,58,237,0.4), transparent 45%);
            filter: blur(50px); /* Reduced blur for better performance */
            animation: appleMove 120s ease-in-out infinite alternate; /* Slower and calmer */
        }

        @keyframes appleMove {
            0%   { transform: translate(0%, 0%) scale(1); }
            50%  { transform: translate(-1%, -1.5%) scale(1.01); } /* Gentler movement */
            100% { transform: translate(1%, 1.5%) scale(1.005); }
        }

        header {
            padding: 20px 10%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(11,18,32,0.7);
            backdrop-filter: blur(12px);
            position: sticky;
            top: 0;
        }

        header h1 { color: #c084fc; margin: 0; }

        header nav a {
            color: white;
            margin-left: 20px;
            text-decoration: none;
            font-weight: 600;
        }

        header nav a:hover, header nav a:focus { color: #c084fc; outline: 2px solid #c084fc; }

        .hero {
            padding: 120px 10%;
            text-align: center;
        }

        .hero h2 {
            font-size: 2.8rem;
            margin-bottom: 20px;
        }

        .hero p { color: #cbd5e1; margin-bottom: 30px; }

        .btn {
            background: linear-gradient(45deg,#a855f7,#7c3aed);
            padding: 12px 25px;
            border-radius: 8px;
            text-decoration: none;
            color: white;
            font-weight: bold;
            display: inline-block;
            transition: transform 0.2s;
            margin: 0 10px;
        }

        .btn:hover { transform: scale(1.05); }

        .btn i { margin-right: 8px; } /* For icon in button */

        .section { padding: 80px 10%; text-align: center; }

        .dark {
            background: rgba(30,41,59,0.5);
            backdrop-filter: blur(8px);
        }

        .service-boxes, .pricing-boxes {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
            margin-top: 40px;
        }

        .box {
            background: rgba(15,23,42,0.75);
            padding: 25px;
            border-radius: 14px;
            border: 1px solid rgba(168,85,247,0.2);
            transition: 0.4s;
            backdrop-filter: blur(10px);
        }

        .box:hover, .box:focus {
            transform: translateY(-8px);
            border-color: #a855f7;
            outline: 2px solid #a855f7;
        }

        .price {
            font-size: 1.8rem;
            color: #22c55e;
            font-weight: bold;
            margin: 15px 0;
        }

        /* Contact Form */
        .contact-form {
            max-width: 500px;
            margin: 30px auto;
        }

        .contact-form input,
        .contact-form textarea {
            width: 100%;
            padding: 12px;
            margin: 10px 0;
            border-radius: 6px;
            border: 1px solid #374151;
            background: #1e293b;
            color: white;
            font-family: inherit;
        }

        .contact-form input:focus,
        .contact-form textarea:focus {
            outline: 2px solid #a855f7;
            border-color: #a855f7;
        }

        .contact-form textarea {
            height: 120px;
            resize: vertical;
        }

        .contact-form button {
            width: 100%;
            padding: 12px;
            background: #a855f7;
            border: none;
            border-radius: 6px;
            font-weight: bold;
            color: white;
            cursor: pointer;
            transition: background 0.2s;
        }

        .contact-form button:hover { background: #7c3aed; }

        /* New: Contact Details */
        .contact-details {
            margin: 40px auto;
            max-width: 600px;
        }

        .contact-details h4 {
            margin-bottom: 20px;
            color: #c084fc;
        }

        .contact-info {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 10px;
            color: #cbd5e1;
        }

        .contact-item i {
            font-size: 1.5rem;
            color: #a855f7;
        }

        .contact-item a {
            color: #cbd5e1;
            text-decoration: none;
        }

        .contact-item a:hover {
            color: #c084fc;
            text-decoration: underline;
        }

        .social-links {
            margin-top: 20px;
        }

        .social-links a {
            margin: 0 10px;
            font-size: 1.8rem;
            color: #cbd5e1;
            transition: color 0.2s;
        }

        .social-links a:hover {
            color: #a855f7;
        }

        /* Payment Section */
        .qr-box img {
            width: 220px;
            border-radius: 12px;
            margin: 20px 0;
            loading: lazy; /* Lazy load for performance */
        }

        .pay-btn {
            display: inline-block;
            background: linear-gradient(45deg,#22c55e,#16a34a);
            padding: 12px 28px;
            border-radius: 8px;
            color: white;
            text-decoration: none;
            font-weight: bold;
            transition: transform 0.2s;
        }

        .pay-btn:hover { transform: scale(1.05); }

        /* Floating Buttons */
        .whatsapp-float, .email-float {
            position: fixed;
            bottom: 20px;
            right: 20px;
            color: white;
            font-size: 26px;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            transition: transform 0.2s;
        }

        .whatsapp-float { background: #25D366; }
        .email-float {
            background: #a855f7;
            bottom: 90px;
            width: 55px;
            height: 55px;
            font-size: 22px;
        }

        .whatsapp-float:hover, .email-float:hover { transform: scale(1.1); }

        /* Dark Mode Toggle */
        .dark-mode-toggle {
            position: fixed;
            top: 20px;
            right: 20px;
            background: #a855f7;
            color: white;
            border: none;
            padding: 10px;
            border-radius: 50%;
            cursor: pointer;
        }

        footer {
            text-align: center;
            padding: 20px;
            background: rgba(11,18,32,0.7);
            color: #c4b5fd;
        }

        /* Responsive Adjustments */
        @media (max-width: 768px) {
            .hero h2 { font-size: 2rem; }
            .service-boxes, .pricing-boxes { grid-template-columns: 1fr; }
            .qr-box img { width: 150px; }
            .contact-info { flex-direction: column; align-items: center; }
            .hero .btn { display: block; margin: 10px auto; width: fit-content; }
        }
    </style>
</head>

<body>
    <!-- Dark Mode Toggle -->
    <button class="dark-mode-toggle" id="darkModeToggle" aria-label="Toggle Dark Mode">
        <i class="fa-solid fa-moon"></i>
    </button>

    <header>
        <h1>Arnav</h1>
        <nav>
            <a href="#services">Services</a>
            <a href="#pricing">Pricing</a>
            <a href="#contact">Contact</a>
        </nav>
    </header>

    <section class="hero" data-aos="fade-up">
        <h2>I Build Modern Websites</h2>
        <p>Affordable. Clean. Professional.</p>
        <a href="#contact" class="btn">Get Started</a>
        <!-- New: Direct Message Button -->
        <a href="https://wa.me/918532016515?text=Hi%20Arnav,%20I%20want%20a%20website" class="btn" target="_blank" aria-label="Message me on WhatsApp">
            <i class="fa-brands fa-whatsapp"></i> Message Me
        </a>
    </section>

    <section id="services" class="section dark" data-aos="fade-up">
        <h3>Services</h3>
        <div class="service-boxes">
            <div class="box" tabindex="0">
                <h4>Website Design</h4>
                <p>Modern UI Design</p>
            </div>
            <div class="box" tabindex="0">
                <h4>Development</h4>
                <p>Fast & Responsive</p>
            </div>
            <div class="box" tabindex="0">
                <h4>SEO Setup</h4>
                <p>Basic Google Setup</p>
            </div>
        </div>
    </section>

    <section id="pricing" class="section" data-aos="fade-up">
        <h3>Pricing</h3>
        <div class="pricing-boxes">
            <div class="box" tabindex="0">
                <h4>Starter</h4>
                <div class="price">₹799</div>
                <p>1 Page Website</p>
            </div>
            <div class="box" tabindex="0">
                <h4>Professional</h4>
                <div class="price">₹999</div>
                <p>3 Pages + Contact</p>
            </div>
            <div class="box" tabindex="0">
                <h4>Business</h4>
                <div class="price">₹1500</div>
                <p>5 Pages + SEO</p>
            </div>
        </div>
    </section>

    <section id="contact" class="section dark" data-aos="zoom-in">
        <h3>Contact Me</h3>

        <!-- New: Contact Details -->
        <div class="contact-details">
            <h4>Get in Touch</h4>
            <div class="contact-info">
                <div class="contact-item">
                    <i class="fa-solid fa-phone"></i>
                    <a href="tel:+918532016515" aria-label="Call Arnav">+91 85320 16515</a>
                </div>
                <div class="contact-item">
                    <i class="fa-solid fa-envelope"></i>
                    <a href="mailto:arnav15042011@gmail.com" aria-label="Email Arnav">arnav15042011@gmail.com</a>
                </div>
            </div>
            <div class="social-links">
                <a href="https://linkedin.com/in/yourprofile" target="_blank" aria-label="LinkedIn"><i class="fa-brands fa-linkedin"></i></a>
                <a href="https://github.com/yourusername" target="_blank" aria-label="GitHub"><i class="fa-brands fa-github"></i></a>
                <a href="https://twitter.com/yourhandle" target="_blank" aria-label="Twitter"><i class="fa-brands fa-twitter"></i></a>
            </div>
        </div>

        <form action="https://formsubmit.co/arnav15042011@gmail.com" method="POST" class="contact-form" id="contactForm">
            <input type="text" name="name" placeholder="Your Name" required aria-label="Name">
            <input type="email" name="email" placeholder="Your Email" required aria-label="Email">
            <textarea name="message" placeholder="Your Message" required aria-label="Message"></textarea>
            <button type="submit">Send Message</button>
        </form>

        <h3>Pay & Confirm</h3>
        <div class="qr-box">
            <img src="qr.png" alt="UPI QR Code for payment to Arnav" loading="lazy">
        </div>
        <a href="upi://pay?pa=8532016515@fam&pn=Arnav&cu=INR" class="pay-btn" aria-label="Pay via UPI">Pay via UPI</a>
    </section>

    <footer>
        © 2024 Arnav. All rights reserved.
    </footer>

    <!-- WhatsApp -->
    <a href="https://wa.me/918532016515?text=Hi%20Arnav,%20I%20want%20a%20website" 
       class="whatsapp-float" target="_blank" aria-label="Contact via WhatsApp">
       <i class="fa-brands fa-whatsapp"></i>
    </a>

    <!-- Email -->
    <a href="mailto:arnav15042011@gmail.com?subject=Website%20Inquiry" 
       class="email-float" aria-label="Send Email">
       <i class="fa-solid fa-envelope"></i>
    </a>

    <script src="https://unpkg.com/aos@2.3.4/dist/aos.js"></script>
    <script>
        AOS.init({ duration: 1000, once: true });

        // Basic form validation
        document.getElementById('contactForm').addEventListener('submit', function(e) {
            const name = document.querySelector('input[name="name"]').value.trim();
            const email = document.querySelector('input[name="email"]').value.trim();
            const message = document.querySelector('textarea[name="message"]').value.trim();

            if (!name || !email || !message) {
                alert('Please fill in all fields.');
                e.preventDefault();
            } else if (!/\S+@\S+\.\S+/.test(email)) {
                alert('Please enter a valid email.');
                e.preventDefault();
            }
        });

        // Dark mode toggle (basic example)
        const toggle = document.getElementById('darkModeToggle');
        toggle.addEventListener('click', () => {
            document.body.classList.toggle('dark-mode'); // Add custom styles if needed
            toggle.innerHTML = document.body.classList.contains('dark-mode') ? '<i class="fa-solid fa-sun"></i>' : '<i class="fa-solid fa-moon"></i>';
        });
    </script>
</body>
</html>
