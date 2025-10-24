<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Ryle L. De Hitta — Portfolio</title>
  <meta name="description" content="Curious mind. Community builder. Code crafter. Portfolio of Ryle L. De Hitta, BSIT-CPT-1 student and coding enthusiast." />

  <!-- Font Awesome for icons -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.6.0/css/all.min.css" integrity="sha512-..." crossorigin="anonymous" referrerpolicy="no-referrer" />

  <style>
    /* =========================
       Base / Layout / Theme
       ========================= */
    :root{
      --bg-1: #07182a;
      --bg-2: #0f1724;
      --card: #0f172f;
      --muted: #94a3b8;
      --accent-1: #7c3aed;
      --accent-2: #4f46e5;
      --glass: rgba(255,255,255,0.04);
      --glass-strong: rgba(255,255,255,0.06);
      --radius: 12px;
      --container: 1100px;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family: "Segoe UI", Roboto, system-ui, -apple-system, "Helvetica Neue", Arial;
      background: linear-gradient(180deg,var(--bg-2),var(--bg-1));
      color:#e6eef8;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      line-height:1.5;
    }
    .container{max-width:var(--container);margin:0 auto;padding:24px;}

    a{color:inherit;text-decoration:none}
    img{display:block;max-width:100%;height:auto}

    /* =========================
       Navigation
       ========================= */
    nav{
      position:sticky;
      top:0;
      z-index:120;
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:16px;
      padding:12px 24px;
      background:linear-gradient(180deg, rgba(6,10,16,0.65), rgba(6,10,16,0.25));
      backdrop-filter: blur(8px);
      border-bottom:1px solid rgba(255,255,255,0.02);
    }
    .logo{font-weight:700;color:#fff}
    .nav-links{display:flex;gap:8px;align-items:center}
    .nav-links a{
      padding:8px 10px;border-radius:10px;font-weight:600;color:var(--muted);
      transition:all .18s ease;
    }
    .nav-links a:hover{background:var(--glass);color:#fff;transform:translateY(-2px)}
    .nav-toggle{display:none}

    /* =========================
       Hero
       ========================= */
    .hero{
      margin-top:18px;
      display:flex;
      gap:24px;
      align-items:center;
      padding:36px;
      border-radius:18px;
      background: linear-gradient(90deg, rgba(20,25,35,0.6), rgba(26,28,40,0.65));
      box-shadow: 0 10px 30px rgba(2,6,23,0.6);
    }
    .hero-left{flex:1;min-width:260px}
    .hero h1{font-size:32px;margin:0 0 10px;color:#fff}
    .hero p{color:var(--muted);margin:0;font-size:15px}
    .hero-cta{margin-top:18px;display:flex;gap:12px;flex-wrap:wrap}
    .btn{
      display:inline-flex;align-items:center;gap:10px;padding:10px 14px;border-radius:10px;
      font-weight:700;cursor:pointer;border:0;transition:transform .16s ease, box-shadow .16s ease;
    }
    .btn:active{transform:translateY(1px)}
    .btn-primary{background: linear-gradient(90deg, var(--accent-1), var(--accent-2)); color:#fff;box-shadow:0 8px 22px rgba(79,70,229,0.12)}
    .btn-outline{background:transparent;border:1px solid rgba(255,255,255,0.06);color:var(--muted)}

    .hero-right{width:220px;min-width:160px;display:flex;align-items:center;justify-content:center}
    .profile {
      width:220px;height:220px;border-radius:999px;overflow:hidden;border:4px solid rgba(255,255,255,0.06);
      background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      box-shadow: 0 12px 30px rgba(3,6,23,0.6);
    }
    .profile img{width:100%;height:100%;object-fit:cover}

    /* =========================
       Sections
       ========================= */
    section{margin-top:48px}
    h2{font-size:20px;margin:0 0 12px;color:#fff}
    .lead{color:var(--muted)}

    /* About */
    .about-grid{display:grid;grid-template-columns:1fr 320px;gap:20px;align-items:start}
    .about-card{background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.02)); padding:18px;border-radius:14px;border:1px solid rgba(255,255,255,0.02)}

    /* Projects */
    .projects-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:18px}
    .project{
      background:var(--card);padding:14px;border-radius:12px;border:1px solid rgba(255,255,255,0.03);
      transition:transform .16s ease, box-shadow .16s ease;
    }
    .project:hover{transform:translateY(-6px);box-shadow:0 12px 30px rgba(3,6,23,0.6)}
    .project .meta{color:var(--muted);font-size:13px;margin-top:8px}

    /* Skills */
    .skill{margin-bottom:14px}
    .skill .bar{background:rgba(255,255,255,0.04);height:10px;border-radius:999px;overflow:hidden}
    .skill .bar > i{display:block;height:100%;border-radius:999px;background:linear-gradient(90deg,var(--accent-1),var(--accent-2))}

    /* Contact */
    form{background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.02));padding:18px;border-radius:12px;border:1px solid rgba(255,255,255,0.02)}
    input,textarea{
      width:100%;padding:10px;border-radius:8px;border:0;background:#061224;color:#e6eef8;margin-top:6px;margin-bottom:6px;
    }
    button[type="submit"]{background:linear-gradient(90deg,var(--accent-1),var(--accent-2));color:#fff;padding:10px 14px;border-radius:10px;border:0;font-weight:700;cursor:pointer}

    /* =========================
       Back to top & Floating footer
       ========================= */
    #backToTop{
      position:fixed;right:20px;bottom:86px;width:44px;height:44px;border-radius:999px;border:0;
      background:linear-gradient(135deg,var(--accent-1),var(--accent-2));color:#fff;z-index:140;
      display:flex;align-items:center;justify-content:center;font-weight:700;box-shadow:0 10px 28px rgba(79,70,229,0.12);
      opacity:0;pointer-events:none;transform:translateY(6px);transition:all .22s ease;
    }
    #backToTop.show{opacity:1;pointer-events:auto;transform:translateY(0)}

    /* Floating / sticky bottom bar */
    .bottom-bar{
      position:fixed;left:50%;transform:translateX(-50%);bottom:16px;padding:10px 14px;border-radius:999px;
      display:flex;gap:12px;align-items:center;background:linear-gradient(180deg, rgba(6,8,16,0.86), rgba(8,12,22,0.9));
      box-shadow:0 12px 40px rgba(2,6,18,0.6);z-index:150;border:1px solid rgba(255,255,255,0.03);
    }
    .bottom-bar a{display:inline-flex;align-items:center;gap:8px;color:var(--muted);padding:6px 8px;border-radius:8px}
    .bottom-bar a:hover{background:var(--glass-strong);color:#fff;transform:translateY(-2px)}

    /* =========================
       Footer (non-floating fallback)
       ========================= */
    footer.main-footer{margin-top:42px;padding:28px 14px;text-align:center;color:var(--muted);font-size:14px;border-top:1px solid rgba(255,255,255,0.02)}
    footer.main-footer a{color:var(--accent-1);margin:0 8px}

    /* =========================
       Responsive
       ========================= */
    @media (max-width:880px){
      .hero{flex-direction:column;align-items:flex-start}
      .about-grid{grid-template-columns:1fr}
      .nav-links{display:none}
      .nav-toggle{display:block}
      .hero-right{align-self:center}
    }
  </style>
</head>
<body>
  <!-- Navigation -->
  <nav class="container" role="navigation" aria-label="Main navigation">
    <div class="logo">Ryle L. De Hitta</div>

    <div class="nav-links" id="navLinks">
      <a href="#home">Home</a>
      <a href="#about">About</a>
      <a href="#projects">Projects</a>
      <a href="#skills">Skills</a>
      <a href="#contact">Contact</a>
    </div>

    <button class="nav-toggle" id="navToggle" aria-expanded="false" aria-controls="navLinks" title="Toggle menu">
      <i class="fa-solid fa-bars" style="color:var(--muted)"></i>
    </button>
  </nav>

  <!-- HERO -->
  <main class="container" id="home" role="main">
    <section class="hero" aria-labelledby="heroTitle">
      <div class="hero-left">
        <h1 id="heroTitle">Curious mind. Community builder. Code crafter.</h1>
        <p class="lead">Hi, I’m <strong>Ryle L. De Hitta</strong>. I build AI-powered apps, electronics demos, and community tools inspired by Filipino culture. I learn by doing and love sharing knowledge through real-world examples.</p>

        <div class="hero-cta">
          <a class="btn btn-primary" href="#projects"><i class="fa-solid fa-rocket"></i> View Projects</a>
          <a class="btn btn-outline" href="#contact"><i class="fa-solid fa-paper-plane"></i> Contact</a>
        </div>
      </div>

      <div class="hero-right">
        <div class="profile" role="img" aria-label="Profile image of Ryle L. De Hitta">
          <!-- Replace below src with your profile image path -->
          <img src="IMG_20250814_092221.jpg" alt="Ryle L. De Hitta profile photo" onerror="this.onerror=null;this.src='https://via.placeholder.com/420x420.png?text=Profile+Image';" />
        </div>
      </div>
    </section>

    <!-- ABOUT -->
    <section id="about" aria-labelledby="aboutTitle">
      <h2 id="aboutTitle">About Me</h2>
      <div class="about-grid" style="margin-top:12px;">
        <div class="about-card">
          <p class="lead">
            Hello! I’m <strong>Ryle L. De Hitta</strong>, a passionate tech explorer currently studying <strong>BSIT-CPT-1</strong>.
            My favorite habit? <strong>Coding</strong> — whether it’s building apps, experimenting with electronics, or crafting community tools that make life easier.
            I believe in learning through real-world examples, and I’m deeply inspired by Filipino culture, collaborative development, and empowering new tech.
          </p>

          <ul style="margin-top:16px;color:var(--muted);padding-left:18px;line-height:1.8">
            <li>📚 <strong>Course:</strong> BSIT-CPT-1</li>
            <li>💻 <strong>Habit:</strong> Coding and exploring new tech</li>
            <li>📍 <strong>Location:</strong>Brgy. Mapulot,Tagkawayan,Quezon</li>
            <li>💡 <strong>Interests:</strong> AI-powered tools, electronics, Filipino literature, and community impact</li>
          </ul>
        </div>

        <aside style="display:flex;flex-direction:column;gap:12px;align-items:center;">
          <div style="width:100%;background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.02));padding:12px;border-radius:12px;border:1px solid rgba(255,255,255,0.02);text-align:center">
            <h3 style="margin:0;color:#fff">Course</h3>
            <p style="margin:6px 0 0;color:var(--muted)">BSIT-CPT-1</p>
          </div>

          <div style="width:100%;background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,255,255,0.02));padding:12px;border-radius:12px;border:1px solid rgba(255,255,255,0.02);text-align:center">
            <h3 style="margin:0;color:#fff">Location</h3>
            <p style="margin:6px 0 0;color:var(--muted)">Brgy. Mapulot,Tagkawayan,Quezon</p>
          </div>
        </aside>
      </div>
    </section>

    <!-- PROJECTS -->
    <section id="projects" aria-labelledby="projectsTitle">
      <h2 id="projectsTitle">Projects</h2>
      <div class="projects-grid" style="margin-top:12px">
        <!-- Project 1 -->
        <article class="project" aria-labelledby="p1">
          <img src="IMG_20251016_170758.png" alt="AnimeInfo project screenshot" style="border-radius:8px;max-height:160px;width:100%;object-fit:cover" onerror="this.onerror=null;this.src='https://via.placeholder.com/800x450.png?text=Project+1';" />
          <h3 id="p1" style="margin:12px 0 6px">AnimeInfo</h3>
          <p class="meta">AI-powered anime search and community curation — React, Node.js, AI</p>
        </article>

        <!-- Project 2 -->
        <article class="project" aria-labelledby="p2">
          <img src="IMG_20251022_080816.jpg" alt="Barangay Assistant project screenshot" style="border-radius:8px;max-height:160px;width:100%;object-fit:cover" onerror="this.onerror=null;this.src='https://via.placeholder.com/800x450.png?text=Project+2';" />
          <h3 id="p2" style="margin:12px 0 6px">Logic and Switching Theory</h3>
          <p class="meta">logic and switching theory-OR gates Activity</p>
        </article>

        <!-- Project 3 -->
        <article class="project" aria-labelledby="p3">
          <img src="Screenshot_20251022_194013_22e4250240c136c826b8a3b1264b092d.jpg" alt="Electronics Experiments project screenshot" style="border-radius:8px;max-height:160px;width:100%;object-fit:cover" onerror="this.onerror=null;this.src='https://via.placeholder.com/800x450.png?text=Project+3';" />
          <h3 id="p3" style="margin:12px 0 6px">MLBB Highlights </h3>
          <p class="meta">Mobile legend bang bang Highlights-Honored Tigril</p>
        </article>
      </div>
    </section>

    <!-- SKILLS -->
    <section id="skills" aria-labelledby="skillsTitle">
      <h2 id="skillsTitle">Skills</h2>
      <div style="max-width:640px;margin-top:12px">
        <div class="skill">
          <label style="display:flex;justify-content:space-between;color:var(--muted)">JavaScript <span style="color:var(--muted)">Advanced</span></label>
          <div class="bar" style="margin-top:6px"><i style="width:85%;"></i></div>
        </div>

        <div class="skill">
          <label style="display:flex;justify-content:space-between;color:var(--muted)">Python <span style="color:var(--muted)">Intermediate</span></label>
          <div class="bar" style="margin-top:6px"><i style="width:70%;"></i></div>
        </div>

        <div class="skill">
          <label style="display:flex;justify-content:space-between;color:var(--muted)">Switching Theory <span style="color:var(--muted)">Practical</span></label>
          <div class="bar" style="margin-top:6px"><i style="width:65%;"></i></div>
        </div>
      </div>
    </section>

    <!-- CONTACT -->
    <section id="contact" aria-labelledby="contactTitle">
      <h2 id="contactTitle">Contact</h2>
      <p class="lead" style="margin-top:6px">Let’s build something electrifying ⚡ — send me a message below or reach out on GitHub / LinkedIn.</p>

      <form id="contactForm" style="margin-top:12px;max-width:720px" novalidate>
        <label>
          <span style="color:var(--muted)">Name</span><br />
          <input type="text" name="name" required placeholder="Your name" />
        </label>

        <label>
          <span style="color:var(--muted)">Email</span><br />
          <input type="email" name="email" required placeholder="your@email.example" />
        </label>

        <label>
          <span style="color:var(--muted)">Message</span><br />
          <textarea name="message" rows="5" required placeholder="Hi Ryle, ..."></textarea>
        </label>

        <div style="margin-top:10px;display:flex;gap:12px;align-items:center">
          <button type="submit">Send message</button>
          <div id="formStatus" style="color:var(--muted);font-size:14px"></div>
        </div>
      </form>
    </section>

    <!-- Footer (page) -->
    <footer class="main-footer" role="contentinfo">
      <div style="margin-bottom:10px">
        Connect with me:
        <!-- Update these links -->
        <a href="https://github.com/yourusername" target="_blank" rel="noopener"><i class="fa-brands fa-github"></i> GitHub</a>
        <a href="https://linkedin.com/in/yourusername" target="_blank" rel="noopener"><i class="fa-brands fa-linkedin"></i> LinkedIn</a>
        <a href="mailto:youremail@example.com"><i class="fa-solid fa-envelope"></i> Email</a>
      </div>
      <div>© <span id="year"></span> Ryle L. De Hitta — Built with curiosity and code ⚡</div>
    </footer>
  </main>

  <!-- Back to top -->
  <button id="backToTop" aria-label="Back to top">↑</button>

  <!-- Floating sticky bottom bar with icons -->
  <div class="bottom-bar" role="toolbar" aria-label="Quick contact">
    <a href="https://github.com/yourusername" target="_blank" rel="noopener"><i class="fa-brands fa-github"></i> GitHub</a>
    <a href="https://linkedin.com/in/yourusername" target="_blank" rel="noopener"><i class="fa-brands fa-linkedin"></i> LinkedIn</a>
    <a href="mailto:youremail@example.com"><i class="fa-solid fa-envelope"></i> Email</a>
    <a href="#contact" title="Open contact form"><i class="fa-solid fa-comment-dots"></i> Message</a>
  </div>

  <script>
    // ====== Small UI helpers ======
    // Nav toggle (mobile)
    const navToggle = document.getElementById('navToggle');
    const navLinks = document.getElementById('navLinks');
    navToggle && navToggle.addEventListener('click', () => {
      const expanded = navToggle.getAttribute('aria-expanded') === 'true';
      navToggle.setAttribute('aria-expanded', String(!expanded));
      if (navLinks.style.display === 'flex') navLinks.style.display = '';
      else navLinks.style.display = 'flex';
    });

    // Back to top visibility
    const backToTop = document.getElementById('backToTop');
    window.addEventListener('scroll', () => {
      if (window.scrollY > 320) backToTop.classList.add('show');
      else backToTop.classList.remove('show');
    });
    backToTop.addEventListener('click', () => window.scrollTo({top:0,behavior:'smooth'}));

    // Smooth scroll for internal links
    document.querySelectorAll('a[href^="#"]').forEach(a=>{
      a.addEventListener('click', function(e){
        const target = document.querySelector(this.getAttribute('href'));
        if(target){
          e.preventDefault();
          target.scrollIntoView({behavior:'smooth',block:'start'});
        }
      });
    });

    // Contact form: mailto fallback
    const form = document.getElementById('contactForm');
    const status = document.getElementById('formStatus');
    form && form.addEventListener('submit', function(e){
      e.preventDefault();
      const fd = new FormData(form);
      const name = fd.get('name') || '';
      const email = fd.get('email') || '';
      const message = fd.get('message') || '';
      const subject = encodeURIComponent('Portfolio contact from ' + name);
      const body = encodeURIComponent(`Email: ${email}\n\n${message}`);
      // Replace this recipient with your real email address
      const recipient = 'youremail@example.com';
      const mailto = `mailto:${recipient}?subject=${subject}&body=${body}`;
      // Try opening mail client
      window.location.href = mailto;
      status.textContent = 'Opening your mail client...';
      setTimeout(()=>{ status.textContent = 'If your mail client did not open, copy this message and email directly.' }, 2500);
    });

    // Set copyright year
    document.getElementById('year').textContent = new Date().getFullYear();

    // Accessibility: allow keyboard access to bottom-bar links with Enter/Space
    document.querySelectorAll('.bottom-bar a').forEach(a => {
      a.addEventListener('keydown', e => {
        if (e.key === 'Enter' || e.key === ' ') { a.click(); }
      });
    });
  </script>
</body>
</html>
