<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BloomScrolling</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

body {
    font-family: 'Poppins', sans-serif;
    background: #f9f9f9;
    color: #333;
    overflow-x: hidden;
}

header {
    position: fixed;
    width: 100%;
    top: 0;
    z-index: 1000;
    background: rgba(0, 0, 0, 0.8);
    padding: 15px 30px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    color: #fff;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

header .logo {
    font-size: 1.5rem;
    font-weight: 600;
}

header nav a {
    color: #fff;
    text-decoration: none;
    margin: 0 15px;
    font-weight: 500;
}

header nav a:hover {
    text-decoration: underline;
}

.hero {
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: linear-gradient(to bottom, #6a11cb, #2575fc);
    text-align: center;
    color: #fff;
    position: relative;
    overflow: hidden;
}

.hero::after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: url('https://source.unsplash.com/1600x900/?nature,abstract') no-repeat center/cover;
    opacity: 0.4;
    z-index: -1;
}

.hero h1 {
    font-size: 3.5rem;
    margin-bottom: 1rem;
            animation: fadeInDown 2s;
        }

.hero p {
    font-size: 1.5rem;
    animation: fadeInUp 2s;
}

/* Adding flower blooming animation */
.flower {
    position: absolute;
    width: 30px;
    height: 30px;
    border-radius: 50%;
    animation: bloom 2s infinite ease-in-out; /* Faster bloom */
    opacity: 0;
    z-index: 0;
}

.flower:nth-child(odd) {
    animation-duration: 3s;
    animation-delay: 1s;
}

.flower:nth-child(even) {
    animation-duration: 2.5s;
    animation-delay: 0.5s;
}

        /* Flower Colors */
.flower:nth-child(1) { background: radial-gradient(circle, #ff8a00, #ff0080); }
.flower:nth-child(2) { background: radial-gradient(circle, #ff8a00, #ff7b00); }
.flower:nth-child(3) { background: radial-gradient(circle, #ff00b3, #ff00d4); }
.flower:nth-child(4) { background: radial-gradient(circle, #ff7b00, #ff4800); }
.flower:nth-child(5) { background: radial-gradient(circle, #00b300, #80e400); }
.flower:nth-child(6) { background: radial-gradient(circle, #1e90ff, #00c6ff); }
.flower:nth-child(7) { background: radial-gradient(circle, #ff69b4, #ff1493); }
.flower:nth-child(8) { background: radial-gradient(circle, #adff2f, #32cd32); }
.flower:nth-child(9) { background: radial-gradient(circle, #ff6347, #ff4500); }
.flower:nth-child(10) { background: radial-gradient(circle, #8a2be2, #9370db); }
.flower:nth-child(11) { background: radial-gradient(circle, #ff00ff, #ff1493); }
.flower:nth-child(12) { background: radial-gradient(circle, #00fa9a, #ff6347); }
.flower:nth-child(13) { background: radial-gradient(circle, #d2691e, #f4a261); }
.flower:nth-child(14) { background: radial-gradient(circle, #ff6347, #ff8c00); }
.flower:nth-child(15) { background: radial-gradient(circle, #4682b4, #5f9ea0); }
.flower:nth-child(16) { background: radial-gradient(circle, #3cb371, #32cd32); }
.flower:nth-child(17) { background: radial-gradient(circle, #f4a261, #ff4500); }
.flower:nth-child(18) { background: radial-gradient(circle, #9400d3, #8a2be2); }
.flower:nth-child(19) { background: radial-gradient(circle, #ff1493, #ff6347); }
.flower:nth-child(20) { background: radial-gradient(circle, #ffb6c1, #f4c2c2); }

@keyframes bloom {
    0% {
        transform: scale(0);
        opacity: 1;
    }
    50% {
        transform: scale(1.5);
        opacity: 0.8;
    }
    100% {
        transform: scale(0);
        opacity: 0;
    }
}

/* Positioning flowers randomly */
.flower:nth-child(1) { top: 30%; left: 10%; }
.flower:nth-child(2) { top: 20%; left: 60%; }
.flower:nth-child(3) { top: 50%; left: 80%; }
.flower:nth-child(4) { top: 70%; left: 30%; }
.flower:nth-child(5) { top: 10%; left: 50%; }
.flower:nth-child(6) { top: 40%; left: 20%; }
.flower:nth-child(7) { top: 60%; left: 75%; }
.flower:nth-child(8) { top: 80%; left: 35%; }
.flower:nth-child(9) { top: 5%; left: 80%; }
.flower:nth-child(10) { top: 45%; left: 10%; }
.flower:nth-child(11) { top: 20%; left: 80%; }
.flower:nth-child(12) { top: 30%; left: 50%; }
.flower:nth-child(13) { top: 70%; left: 40%; }
.flower:nth-child(14) { top: 40%; left: 70%; }
.flower:nth-child(15) { top: 15%; left: 60%; }
.flower:nth-child(16) { top: 75%; left: 25%; }
.flower:nth-child(17) { top: 55%; left: 80%; }
.flower:nth-child(18) { top: 65%; left: 10%; }
.flower:nth-child(19) { top: 25%; left: 20%; }
.flower:nth-child(20) { top: 80%; left: 70%; }

/* Vision Background Eye Animation */
.vision {
    position: relative;
    padding: 100px 20px;
    background: radial-gradient(circle, #00b3b3, #000000);
    color: white;
    text-align: center;
    z-index: 1;
    display: flex;
    justify-content: flex-start; /* Aligns content to the left */
    align-items: center;
}

.vision .content {
    flex: 0 0 45%;
    animation: slideInLeft 2s ease-out;
}

.vision img {
    width: 100%;
    height: auto;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    animation: fadeInUp 2s ease-out;
    order: 2; /* Ensures image is on the right side */
}

.vision .text-content h2 {
    font-size: 2rem;
    margin-bottom: 1rem;
    animation: fadeInDown 2s ease-out;
}

.vision .text-content p {
    font-size: 1.2rem;
    line-height: 1.8;
    max-width: 800px;
    margin: 0 auto;
}

/* Mission Background Trophy Animation */
.mission {
    position: relative;
    padding: 100px 20px;
    background: linear-gradient(135deg, #ff5500, #ff8a00); /* Changed background color */
    color: white;
    text-align: center;
    z-index: 1;
    display: flex;
    justify-content: flex-start; /* Aligns content to the left */
    align-items: center;
}

.mission .content {
    flex: 0 0 45%;
    animation: slideInRight 2s ease-out;
}

.mission img {
    width: 100%;
    height: auto;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    animation: fadeInUp 2s ease-out;
    order: 2; /* Ensures image is on the right side */
}

.mission .text-content h2 {
    font-size: 2rem;
    margin-bottom: 1rem;
    animation: fadeInDown 2s ease-out;
}

.mission .text-content p {
    font-size: 1.2rem;
    line-height: 1.8;
    max-width: 800px;
    margin: 0 auto;
}

/* Features Section Styling */
#features {
    background: #f9f9f9;
    padding: 50px 20px;
    text-align: center;
}

#features h2 {
    font-size: 2.5rem;
    margin-bottom: 2rem;
}

.features-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
}

.feature-box {
    width: 30%;
    padding: 20px;
    margin: 15px;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

footer {
    background: #333;
    color: #fff;
    padding: 20px;
    text-align: center;
}

</style>
</head>
<body>
<header>
<div class="logo">BloomScrolling</div>
<nav>
    <a href="#vision">Vision</a>
    <a href="#mission">Mission</a>
    <a href="#features">Features</a>
    <a href="#contact">Contact</a>
</nav>
</header>

<div class="hero">
<h1>Welcome to BloomScrolling</h1>
<p>Discover how we bring creativity and innovation to life through blooming digital designs.</p>
</div>

<section id="vision" class="vision">
<div class="content">
    <div class="text-content">
        <h2>Our Vision</h2>
        <p>We envision a world where creativity and technology merge to provide the most immersive user experiences possible. With a commitment to excellence and innovation, we aim to create digital solutions that inspire, engage, and bring joy to people all over the globe.</p>
        <p>Our vision is driven by the belief that digital design can transform the way we interact with the world. By harnessing cutting-edge technology, we aspire to build a future where everyone can access the tools and platforms they need to express their creativity and achieve their goals.</p>
        <p>Through collaboration, experimentation, and relentless dedication, we aim to push the boundaries of what's possible and deliver results that exceed expectations.</p>
    </div>
</div>
<img src="https://picsum.photos/800/400" alt="Vision Image">
</section>

<section id="mission" class="mission">
<div class="content">
    <div class="text-content">
        <h2>Our Mission</h2>
        <p>Our mission is to innovate and create dynamic digital experiences that not only look beautiful but also work seamlessly. With a focus on user-centered design and technological advancements, we strive to provide solutions that stand the test of time.</p>
        <p>Our mission is rooted in the values of collaboration, creativity, and continuous improvement. We believe in the power of teamwork and always strive to deliver high-quality solutions that solve real-world problems.</p>
        <p>Through every project, we are committed to making a positive impact on the communities we serve. We envision our work as a tool for change, growth, and innovation, delivering experiences that truly matter.</p>
    </div>
</div>
<img src="https://picsum.photos/800/400" alt="Mission Image">
</section>

<section id="features" style="background-color: #f4a261; padding: 50px 20px;">
<h2>Our Features</h2>
<div class="features-container">
    <div class="feature-box" style="background-color: rgba(255, 204, 0, 0.7);">
        <h3>Creative User Interfaces</h3>
        <p>We design intuitive and visually appealing user interfaces that enhance user interaction and experience.</p>
    </div>
    <div class="feature-box" style="background-color: rgba(0, 204, 255, 0.7);">
        <h3>Responsive Design</h3>
        <p>Our designs are fully responsive, ensuring seamless performance across all devices and screen sizes.</p>
    </div>
    <div class="feature-box" style="background-color: rgba(255, 0, 204, 0.7);">
        <h3>Cutting-Edge Technology</h3>
        <p>We leverage the latest in technology to create innovative solutions that push the boundaries of what is possible.</p>
    </div>
    <div class="feature-box" style="background-color: rgba(0, 255, 0, 0.7);">
        <h3>Seamless Integration</h3>
        <p>Our digital solutions integrate smoothly with existing platforms, ensuring a hassle-free experience for users and businesses.</p>
    </div>
    <div class="feature-box" style="background-color: rgba(255, 128, 0, 0.7);">
        <h3>User-Centered Approach</h3>
        <p>Every design decision is made with the user in mind, ensuring we meet their needs and deliver outstanding results.</p>
    </div>
    <div class="feature-box" style="background-color: rgba(255, 85, 85, 0.7);">
        <h3>Continuous Improvement</h3>
        <p>We constantly iterate and improve on our designs, using feedback and data to optimize and enhance user experiences.</p>
    </div>
</div>
</section>

<!-- Contact Form Section -->
<section id="contact" style="background-color: #ffecb3; padding: 50px 20px;">
<h2 style="text-align: center; color: #333; font-size: 2.5rem; margin-bottom: 30px;">Contact Us</h2>
<form action="submit_form.php" method="POST" style="max-width: 600px; margin: 0 auto; background-color: #fff; padding: 30px; border-radius: 8px; box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);">
    <label for="name" style="display: block; font-size: 1.1rem; margin-bottom: 8px;">Name</label>
    <input type="text" id="name" name="name" placeholder="Your Name" required style="width: 100%; padding: 12px; margin-bottom: 20px; border: 1px solid #ddd; border-radius: 8px; font-size: 1rem;">
    
    <label for="email" style="display: block; font-size: 1.1rem; margin-bottom: 8px;">Email</label>
    <input type="email" id="email" name="email" placeholder="Your Email" required style="width: 100%; padding: 12px; margin-bottom: 20px; border: 1px solid #ddd; border-radius: 8px; font-size: 1rem;">
    
    <label for="message" style="display: block; font-size: 1.1rem; margin-bottom: 8px;">Message</label>
    <textarea id="message" name="message" rows="4" placeholder="Your Message" required style="width: 100%; padding: 12px; margin-bottom: 20px; border: 1px solid #ddd; border-radius: 8px; font-size: 1rem;"></textarea>
    
    <button type="submit" style="background-color: #00b3b3; color: white; padding: 12px 20px; border: none; border-radius: 8px; font-size: 1.1rem; cursor: pointer; width: 100%;">Send Message</button>
</form>
</section>

<footer>
<p>&copy; 2025 Creative Website. All Rights Reserved.</p>
    </footer>
    
<style>
/* Features Section Styling */
#features {
    background-color: #f0f8ff; /* Light blue background for features */
    padding: 50px 20px;
    text-align: center;
}

#features h2 {
    font-size: 2.5rem;
    margin-bottom: 2rem;
    color: #333;
}

.features-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr); /* 3 columns in a row */
    gap: 20px;
    justify-items: center;
}

.feature-box {
    padding: 20px;
    margin: 15px;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease;
    width: 100%;
}

.feature-box h3 {
    font-size: 1.8rem;
    margin-bottom: 1rem;
    color: #333;
}

.feature-box p {
    font-size: 1rem;
    line-height: 1.6;
    color: #555;
}

.feature-box:hover {
    transform: scale(1.05);
}

/* Responsive adjustments */
@media (max-width: 1024px) {
    .features-container {
        grid-template-columns: repeat(2, 1fr); /* 2 columns on medium screens */
    }
}

@media (max-width: 600px) {
    .features-container {
        grid-template-columns: 1fr; /* 1 column on small screens */
    }
        }
    
/* Contact Form Styling */
#contact form input,
#contact form textarea,
#contact form button {
    font-family: 'Poppins', sans-serif;
}

#contact form label {
    font-weight: 600;
}

#contact form input[type="text"],
#contact form input[type="email"],
#contact form textarea {
    border: 1px solid #ddd;
    border-radius: 8px;
    padding: 12px;
    width: 100%;
    margin-bottom: 15px;
    font-size: 1rem;
}

#contact form button {
    background-color: #00b3b3;
    color: white;
    padding: 12px 20px;
    border: none;
    border-radius: 8px;
    font-size: 1.1rem;
    cursor: pointer;
    width: 100%;
}

#contact form button:hover {
    background-color: #008f8f;
}
</style>

<!-- Flower Blooming Animation -->
<div class="flower"></div>
<div class="flower"></div>
<div class="flower"></div>
<div class="flower"></div>
<div class="flower"></div>
<div class="flower"></div>
<div class="flower"></div>
<div class="flower"></div>
<div class="flower"></div>
<div class="flower"></div>
<div class="flower"></div>
<div class="flower"></div>
<div class="flower"></div>
<div class="flower"></div>
<div class="flower"></div>
<div class="flower"></div>
<div class="flower"></div>
<div class="flower"></div>
<div class="flower"></div>
<div class="flower"></div>
</body>
<script>
// Smooth Scroll for Navigation Links
const navLinks = document.querySelectorAll('header nav a');

navLinks.forEach(link => {
link.addEventListener('click', function(e) {
    e.preventDefault();
    const targetId = this.getAttribute('href').substring(1);
    const targetElement = document.getElementById(targetId);
    window.scrollTo({
        top: targetElement.offsetTop - 60, // Account for fixed header height
        behavior: 'smooth'
    });
});
    });

// Adjust Flower Blooming Animation on Scroll
const flowers = document.querySelectorAll('.flower');

window.addEventListener('scroll', () => {
const scrollPosition = window.scrollY;
flowers.forEach((flower, index) => {
    const flowerAnimationDuration = 2 + (index % 5); // Vary the bloom timing based on index
    const bloomDelay = (scrollPosition / 1000) + (index * 0.5); // Adjust delay based on scroll position
    flower.style.animationDuration = `${flowerAnimationDuration}s`;
    flower.style.animationDelay = `${bloomDelay}s`;
});
});

// Simple Contact Form Validation (Client-Side)
const contactForm = document.querySelector('#contact form');
contactForm.addEventListener('submit', function(e) {
const name = document.getElementById('name').value;
const email = document.getElementById('email').value;
const message = document.getElementById('message').value;

if (!name || !email || !message) {
    e.preventDefault();
    alert('Please fill out all fields before submitting the form!');
}
});
</script>

</html>
