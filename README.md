<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Ryle L. De Hitta — Portfolio</title>
  <meta name="description" content="Curious mind. Community builder. Code crafter. Portfolio of Ryle L. De Hitta, BSIT-CPT-1 student and coding enthusiast." />
  <style>
    /* Base styles */
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(to bottom, #0f1724, #07182a);
      color: #e2eaf5;
    }
    a { text-decoration: none; color: inherit; }
    .container { max-width: 1100px; margin: auto; padding: 24px; }

    /* Navigation */
    nav {
      position: sticky;
      top: 0;
      background: rgba(15, 23, 36, 0.9);
      backdrop-filter: blur(6px);
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 12px 24px;
      z-index: 100;
    }
    nav .logo { font-weight: bold; font-size: 18px; color: #fff; }
    nav .links a {
      margin-left: 16px;
      font-weight: 600;
      color: #94a3b8;
      padding: 6px 10px;
      border-radius: 8px;
    }
    nav .links a:hover {
      background: rgba(255,255,255,0.05);
      color: #fff;
    }

    /* Hero */
    .hero {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: space-between;
      padding: 48px 24px;
      background: linear-gradient(to right, #1e1e2f, #2a2a3d);
      border-radius: 16px;
      margin-top: 24px;
    }
    .hero-text {
      max-width: 600px;
    }
    .hero-text h1 {
      font-size: 36px;
      margin-bottom: 12px;
      color: #fff;
    }
    .hero-text p {
      font-size: 16px;
      color: #94a3b8;
    }
    .hero-buttons {
      margin-top: 20px;
      display: flex;
      gap: 12px;
    }
    .btn {
      padding: 10px 16px;
      border-radius: 10px;
      font-weight: bold;
      cursor: pointer;
      border: none;
    }
    .btn-primary {
      background: linear-gradient(to right, #7c3aed, #4f46e5);
      color: #fff;
    }
    .btn-outline {
      background: transparent;
      border: 1px solid #94a3b8;
      color: #94a3b8;
    }

    /* Profile image */
    .hero-img {
      width: 220px;
      height: 220px;
      border-radius: 50%;
      overflow: hidden;
      border: 4px solid rgba(255,255,255,0.1);
      box-shadow: 0 8px 24px rgba(0,0,0,0.4);
    }
    .hero-img img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    /* Back to top */
    #backToTop {
      position: fixed;
      bottom: 24px;
      right: 24px;
      background: linear-gradient(135deg, #7c3aed, #4f46e5);
      color: white;
      border: none;
      border-radius: 999px;
      width: 44px;
      height: 44px;
      font-size: 20px;
      font-weight: bold;
      cursor: pointer;
      box-shadow: 0 6px 18px rgba(124,58,237,0.3);
      transition: opacity 0.3s ease, transform 0.3s ease;
      opacity: 0;
      pointer-events: none;
      z-index: 50;
    }
    #backToTop:hover {
      transform: scale(1.1);
      box-shadow: 0 8px 24px rgba(124,58,237,0.5);
    }
    #backToTop.show {
      opacity: 1;
      pointer-events: auto;
    }
  </style>
</head>
<body>
  <nav>
    <div class="logo">Ryle L. De Hitta</div>
    <div class="links">
      <a href="#home">Home</a>
      <a href="#about">About</a>
      <a href="#projects">Projects</a>
      <a href="#skills">Skills</a>
      <a href="#contact">Contact</a>
    </div>
  </nav>

  <section class="hero container" id="home">
    <div class="hero-text">
      <h1>Curious mind. Community builder. Code crafter.</h1>
      <p>Hi, I’m <strong>Ryle L. De Hitta</strong>. I build AI-powered apps, electronics demos, and community tools inspired by Filipino culture. I learn by doing and love sharing knowledge through real-world examples.</p>
      <div class="hero-buttons">
        <a href="#projects" class="btn btn-primary">View Projects</a>
        <a href="#contact" class="btn btn-outline">Contact</a>
      </div>
    </div>
    <div class="hero-img">
      <img src="1000089590.jpg" alt="Ryle L. De Hitta profile photo" />
    </div>
  </section>

  <button id="backToTop" title="Back to top">↑</button>

  <script>
    // Back to top button
    const backToTop = document.getElementById('backToTop');
    window.addEventListener('scroll', () => {
      if (window.scrollY > 300) {
        backToTop.classList.add('show');
      } else {
        backToTop.classList.remove('show');
      }
    });
    backToTop.addEventListener('click', () => {
      window.scrollTo({ top: 0, behavior: 'smooth' });
    });
  </script>
  <!-- About Me -->
<section id="about" class="container" style="margin-top:48px;">
  <h2 style="font-size:24px;margin-bottom:12px;">About Me</h2>
  <p style="font-size:16px;line-height:1.6;color:#94a3b8;">
    Hello! I’m <strong>Ryle L. De Hitta</strong>, a passionate tech explorer currently studying <strong>BSIT-CPT-1</strong>.  
    My favorite habit? <strong>Coding</strong> — whether it’s building apps, experimenting with electronics, or crafting community tools that make life easier.  
    I believe in learning through real-world examples, and I’m deeply inspired by Filipino culture, collaborative development, and empowering new tech.
  </p>
  <ul style="margin-top:16px;padding-left:20px;color:#94a3b8;">
    <li>📚 <strong>Course:</strong> BSIT-CPT-1</li>
    <li>💻 <strong>Habit:</strong> Coding and exploring new tech</li>
    <li>📍 <strong>Location:</strong> Tagkawayan, Philippines</li>
    <li>💡 <strong>Interests:</strong> AI-powered tools, electronics, Filipino literature, and community impact</li>
  </ul>
</section>

<!-- Projects -->
<section id="projects" class="container" style="margin-top:48px;">
  <h2 style="font-size:24px;margin-bottom:12px;">Projects</h2>
  <div style="display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:24px;">
    <div style="background:#1e293b;padding:16px;border-radius:12px;">
      <h3 style="color:#fff;">AnimeInfo</h3>
      <p style="color:#94a3b8;">AI-powered anime search and community curation.</p>
      <p style="font-size:13px;color:#64748b;">Tech: React, Node.js, AI</p>
    </div>
    <div style="background:#1e293b;padding:16px;border-radius:12px;">
      <h3 style="color:#fff;">Barangay Assistant</h3>
      <p style="color:#94a3b8;">Community tools for local governance and support.</p>
      <p style="font-size:13px;color:#64748b;">Tech: Vue, Firebase</p>
    </div>
    <div style="background:#1e293b;padding:16px;border-radius:12px;">
      <h3 style="color:#fff;">Electronics Experiments</h3>
      <p style="color:#94a3b8;">Capacitor demos, Boolean logic simulations, and hands-on notes.</p>
      <p style="font-size:13px;color:#64748b;">Tech: Arduino, Python</p>
    </div>
  </div>
</section>

<!-- Skills -->
<section id="skills" class="container" style="margin-top:48px;">
  <h2 style="font-size:24px;margin-bottom:12px;">Skills</h2>
  <div style="max-width:600px;">
    <div style="margin-bottom:16px;">
      <label style="display:flex;justify-content:space-between;color:#94a3b8;">JavaScript <span>Advanced</span></label>
      <div style="background:#334155;height:8px;border-radius:999px;"><div style="width:85%;height:8px;background:#7c3aed;border-radius:999px;"></div></div>
    </div>
    <div style="margin-bottom:16px;">
      <label style="display:flex;justify-content:space-between;color:#94a3b8;">Python <span>Intermediate</span></label>
      <div style="background:#334155;height:8px;border-radius:999px;"><div style="width:70%;height:8px;background:#7c3aed;border-radius:999px;"></div></div>
    </div>
    <div style="margin-bottom:16px;">
      <label style="display:flex;justify-content:space-between;color:#94a3b8;">Switching Theory <span>Practical</span></label>
      <div style="background:#334155;height:8px;border-radius:999px;"><div style="width:65%;height:8px;background:#7c3aed;border-radius:999px;"></div></div>
    </div>
  </div>
</section>

<!-- Contact -->
<section id="contact" class="container" style="margin-top:48px;margin-bottom:64px;">
  <h2 style="font-size:24px;margin-bottom:12px;">Contact</h2>
  <p style="color:#94a3b8;">Let’s build something electrifying ⚡</p>
  <form id="contactForm" style="margin-top:16px;max-width:600px;">
    <label style="display:block;margin-bottom:12px;">
      <span style="color:#94a3b8;">Name</span><br />
      <input type="text" name="name" required style="width:100%;padding:10px;border-radius:8px;border:none;background:#1e293b;color:#fff;" />
    </label>
    <label style="display:block;margin-bottom:12px;">
      <span style="color:#94a3b8;">Email</span><br />
      <input type="email" name="email" required style="width:100%;padding:10px;border-radius:8px;border:none;background:#1e293b;color:#fff;" />
    </label>
    <label style="display:block;margin-bottom:12px;">
      <span style="color:#94a3b8;">Message</span><br />
      <textarea name="message" rows="4" required style="width:100%;padding:10px;border-radius:8px;border:none;background:#1e293b;color:#fff;"></textarea>
    </label>
    <button type="submit" style="padding:10px 16px;border-radius:10px;background:#7c3aed;color:#fff;border:none;font-weight:bold;">Send</button>
    <p id="formStatus" style="margin-top:12px;font-size:14px;color:#94a3b8;"></p>
  </form>
</section>

<script>
  // Contact form mailto fallback
  const form = document.getElementById('contactForm');
  const status = document.getElementById('formStatus');
  form.addEventListener('submit', function(e){
    e.preventDefault();
    const fd = new FormData(form);
    const name = fd.get('name');
    const email = fd.get('email');
    const message = fd.get('message');
    const subject = encodeURIComponent('Portfolio contact from ' + name);
    const body = encodeURIComponent(`Email: ${email}\n\n${message}`);
    window.location.href = `mailto:your@email.address?subject=${subject}&body=${body}`;
    status.textContent = 'Opening your mail client...';
  });
document.getElementById('year').textContent = new Date().getFullYear();
</script>
<footer style="background:#0f1724;padding:32px 24px;text-align:center;color:#94a3b8;font-size:14px;">
  <div style="margin-bottom:12px;">
    Connect with me:
    <a href="https://github.com/yourusername" target="_blank" style="margin:0 8px;color:#7c3aed;text-decoration:none;">GitHub</a>
    <a href="https://linkedin.com/in/yourusername" target="_blank" style="margin:0 8px;color:#7c3aed;text-decoration:none;">LinkedIn</a>
    <a href="mailto:your@email.address" style="margin:0 8px;color:#7c3aed;text-decoration:none;">Email</a>
  </div>
  <div>© <span id="year"></span> Ryle L. De Hitta — Built with curiosity and code ⚡</div>
</footer>
