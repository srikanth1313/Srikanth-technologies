<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Srikanth Technologies - Hyderabad</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <header>
    <div class="container">
      <h1>Srikanth Technologies</h1>
      <p>Empowering IT Skills Since 2005 | Based in Hyderabad</p>
    </div>
  </header>

  <nav>
    <ul class="container">
      <li><a href="#services">Services</a></li>
      <li><a href="#about">About Us</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

  <section class="hero">
    <div class="container">
      <h2>Learn. Build. Grow.</h2>
      <p>Your IT training partner in Hyderabad. Courses for every developer, student, and professional.</p>
      <button id="learnMoreBtn">Learn More</button>
    </div>
  </section>

  <section id="services" class="container">
    <h2>Our Courses</h2>
    <div class="grid">
      <div class="card">
        <h3>Web Development</h3>
        <p>Master frontend and backend development: HTML, CSS, JavaScript, React, Angular, Node.js</p>
      </div>
      <div class="card">
        <h3>Programming</h3>
        <p>Get skilled in Python, Java, C/C++, and core data structures & algorithms.</p>
      </div>
      <div class="card">
        <h3>Data Science</h3>
        <p>Explore AI, Machine Learning, data visualization, and statistical analysis tools.</p>
      </div>
      <div class="card">
        <h3>Cloud Computing</h3>
        <p>Hands-on with AWS, Microsoft Azure, Google Cloud Platform, and DevOps essentials.</p>
      </div>
      <div class="card">
        <h3>Database</h3>
        <p>Learn SQL, NoSQL, database design, and performance optimization.</p>
      </div>
      <div class="card">
        <h3>Mobile Development</h3>
        <p>Build apps using Flutter, Android Studio, Kotlin, and cross-platform frameworks.</p>
      </div>
    </div>
  </section>

  <section id="about" class="container">
    <h2>About Srikanth Technologies</h2>
    <p>
      Since 2005, Srikanth Technologies has been the leading IT training institute in Hyderabad. We are committed to
      delivering practical and project-based learning, helping thousands achieve their career goals in software development
      and IT domains.
    </p>
    <p>
      Our certified trainers come from top industry backgrounds, offering personal mentorship and updated course material.
    </p>
  </section>

  <section id="contact" class="container">
    <h2>Contact Us</h2>
    <p>📍 Hyderabad, Telangana, India</p>
    <p>📞 +91 8463931010</p>
    <p>📧 contact@srikanthtech.in</p>

    <form id="contactForm" novalidate>
      <h3>Send us a message</h3>
      <label for="name">Full Name:</label>
      <input type="text" id="name" name="name" required placeholder="Your full name" />
      
      <label for="email">Email:</label>
      <input type="email" id="email" name="email" required placeholder="Your email" />
      
      <label for="message">Message:</label>
      <textarea id="message" name="message" required placeholder="Your message" rows="4"></textarea>
      
      <button type="submit">Submit</button>
      <p id="formMessage" class="hidden"></p>
    </form>
  </section>

  <footer>
    <div class="container">
      <p>&copy; 2025 Srikanth Technologies. All rights reserved.</p>
    </div>
  </footer>

  <script src="script.js"></script>
</body>
</html>
// Wait for DOM load
document.addEventListener('DOMContentLoaded', () => {
  const form = document.getElementById('contactForm');
  const formMessage = document.getElementById('formMessage');
  const learnMoreBtn = document.getElementById('learnMoreBtn');

  // Form validation and submission simulation
  form.addEventListener('submit', function(e) {
    e.preventDefault();

    // Clear previous message
    formMessage.textContent = '';
    formMessage.classList.add('hidden');
    formMessage.style.color = 'red';

    // Simple validation
    const name = form.name.value.trim();
    const email = form.email.value.trim();
    const message = form.message.value.trim();

    if(name.length < 3) {
      formMessage.textContent = 'Please enter a valid name (at least 3 characters).';
      formMessage.classList.remove('hidden');
      return;
    }

    if(!validateEmail(email)) {
      formMessage.textContent = 'Please enter a valid email address.';
      formMessage.classList.remove('hidden');
      return;
    }

    if(message.length < 10) {
      formMessage.textContent = 'Please enter a message of at least 10 characters.';
      formMessage.classList.remove('hidden');
      return;
    }

    // Simulate form submission success
    formMessage.textContent = 'Thank you for contacting us! We will get back to you soon.';
    formMessage.style.color = 'green';
    formMessage.classList.remove('hidden');

    form.reset();
  });

  // Learn More button scroll to about section
  learnMoreBtn.addEventListener('click', () => {
    document.getElementById('about').scrollIntoView({behavior: 'smooth'});
  });

  // Email validation helper function
  function validateEmail(email) {
    // Basic email regex pattern
    const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    return re.test(email.toLowerCase());
  }
});
