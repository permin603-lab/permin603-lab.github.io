<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Ryle L. De Hitta — Portfolio</title>
  <meta name="description" content="Curious mind. Community builder. Code crafter. Ryle L. De Hitta — BSIT-CPT-1."/>

  <style>
    :root{
      --bg:#0f1724;
      --card:#0b1220;
      --muted:#94a3b8;
      --accent:#7c3aed;
      --accent-2:#ff7a18;
      --glass: rgba(255,255,255,0.04);
      --radius:14px;
      --container:1100px;
      --nav-height:72px;
    }
    *{box-sizing:border-box}
    html,body{height:100%;margin:0;font-family:Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;color:#e6eef8;background:linear-gradient(180deg,#071026 0%, #07182a 60%);}
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
    a{color:inherit;text-decoration:none}
    .site-wrap{max-width:var(--container);margin:0 auto;padding:24px}
    /* Sticky nav */
    .nav {
      position:sticky;top:0;z-index:40;height:var(--nav-height);display:flex;align-items:center;justify-content:space-between;padding:8px 16px;background:linear-gradient(180deg, rgba(11,18,32,0.6), rgba(11,18,32,0.35));backdrop-filter: blur(6px);border-radius:10px;
      margin-bottom:18px;
    }
    .brand{display:flex;align-items:center;gap:12px}
    .brand .logo{
      width:44px;height:44px;border-radius:10px;display:inline-grid;place-items:center;background:linear-gradient(135deg,var(--accent),#4f46e5);font-weight:800;color:#fff;font-size:14px;
      box-shadow:0 6px 18px rgba(28,27,44,0.6);
    }
    .brand .name{font-weight:800;color:#fff;font-size:16px;letter-spacing:-0.01em}
    .nav-links{display:flex;gap:14px;align-items:center}
    .nav-links a{padding:8px 12px;border-radius:10px;color:var(--muted);font-weight:600;transition:all .18s ease}
    .nav-links a:hover{color:#fff;background:rgba(255,255,255,0.03)}
    .nav-links a.active{background:linear-gradient(90deg, rgba(124,58,237,0.14), rgba(255,122,24,0.06));color:#fff;box-shadow:0 6px 20px rgba(124,58,237,0.06)}
    /* mobile toggle */
    .nav-toggle{display:none;background:transparent;border:1px solid rgba(255,255,255,0.04);padding:6px;border-radius:8px;color:var(--muted);cursor:pointer}
    /* Hero */
    .hero{
      display:grid;grid-template-columns:1fr 360px;gap:28px;align-items:center;padding:36px;border-radius:18px;background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));box-shadow:0 20px 60px rgba(2,6,23,0.7);
    }
    .hero-left{padding-right:6px}
    .eyebrow{display:inline-block;color:var(--accent);font-weight:700;background:rgba(124,58,237,0.08);padding:6px 10px;border-radius:999px;font-size:13px}
    h1{margin:14px 0 6px;font-size:clamp(28px,4.4vw,44px);line-height:1.02;font-weight:900;color:#fff}
    p.lead{margin:0;color:var(--muted);max-width:56ch}
    .hero-ctas{margin-top:18px;display:flex;gap:12px;flex-wrap:wrap}
    .btn{
      padding:10px 16px;border-radius:12px;font-weight:800;display:inline-flex;align-items:center;gap:10px;border:0;cursor:pointer;
    }
    .btn-primary{background:linear-gradient(90deg,var(--accent),#4f46e5);color:#fff;box-shadow:0 12px 30px rgba(124,58,237,0.12)}
    .btn-ghost{background:transparent;border:1px solid rgba(255,255,255,0.08);color:#fff}
    .btn-primary:hover{transform:translateY(-3px)}
    .btn-ghost:hover{background:rgba(255,255,255,0.02)}
    /* Photo card */
    .photo-card{background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));padding:16px;border-radius:16px;display:flex;flex-direction:column;align-items:center;gap:12px;box-shadow:0 8px 30px rgba(2,6,23,0.6)}
    .avatar{
      width:210px;height:210px;border-radius:999px;overflow:hidden;border:6px solid rgba(255,255,255,0.04);
      box-shadow:0 12px 36px rgba(2,6,23,0.6);
      display:inline-block;background:#fff;
    }
    .avatar img{width:100%;height:100%;object-fit:cover;display:block}
    .photo-meta{text-align:center;color:var(--muted);font-weight:700}
    /* small bio line */
    .bio-mini{margin-top:6px;color:var(--muted);font-size:14px}
    /* active section indicator (thin) */
    .section-indicator{height:6px;border-radius:999px;background:linear-gradient(90deg,var(--accent),var(--accent-2));width:80px;margin-top:10px;box-shadow:0 6px 18px rgba(124,58,237,0.08)}
    /* responsive */
    @media(max-width:980px){
      .hero{grid-template-columns:1fr;gap:18px;padding:24px}
      .nav-links{display:none}
      .nav-toggle{display:inline-flex}
    }
    /* small helpers */
    .muted{color:var(--muted)}
    .small{font-size:13px;color:var(--muted)}
    .sr-only{position:absolute;width:1px;height:1px;padding:0;margin:-1px;overflow:hidden;clip:rect(0,0,0,0);white-space:nowrap;border:0}
  </style>
</head>
<body>
  <div class="site-wrap">
    <header class="nav" role="banner" aria-label="Top navigation">
      <div class="brand">
        <div class="logo" aria-hidden="true">RL</div>
        <div class="name">Ryle L. De Hitta</div>
      </div>

      <nav aria-label="Primary" class="nav-links" id="primaryNav">
        <a href="#home" class="nav-link active">Home</a>
        <a href="#about" class="nav-link">About</a>
        <a href="#projects" class="nav-link">Projects</a>
        <a href="#skills" class="nav-link">Skills</a>
        <a href="#contact" class="nav-link">Contact</a>
      </nav>

      <button class="nav-toggle" id="navToggle" aria-expanded="false" aria-controls="primaryNav">☰</button>
    </header>

    <!-- Hero -->
    <main id="home" class="hero" role="main" aria-labelledby="hero-title">
      <div class="hero-left">
        <span class="eyebrow">BSIT-CPT-1 • Coding</span>
        <h1 id="hero-title">Curious mind. Community builder. Code crafter.</h1>
        <p class="lead">Hi, I’m <strong>Ryle L. De Hitta</strong>. I build AI-powered apps, electronics demos, and community tools inspired by Filipino culture. I learn by doing and I love sharing knowledge through real-world examples.</p>

        <div class="hero-ctas" role="group" aria-label="Primary actions">
          <a href="#projects" class="btn btn-primary">View projects</a>
          <a href="#contact" class="btn btn-ghost">Contact</a>
        </div>

        <div class="section-indicator" aria-hidden="true"></div>
      </div>

      <aside class="photo-card" aria-labelledby="photo-meta">
        <div class="avatar" role="img" aria-label="Profile photo of Ryle L De Hitta">
          <img src="1000089590.jpg" alt="Ryle L. De Hitta profile photo">
        </div>
        <div class="photo-meta">
          <div style="font-weight:900;color:#fff">Ryle L. De Hitta</div>
          <div class="bio-mini">BSIT-CPT-1 • Tagkawayan, Philippines</div>
        </div>
        <div class="small muted">Habits: coding • exploring new tech</div>
      </aside>
    </main>
  </div>

  <script>
    // Mobile nav toggle
    (function(){
      const btn = document.getElementById('navToggle');
      const nav = document.getElementById('primaryNav');
      btn.addEventListener('click', () => {
        const expanded = btn.getAttribute('aria-expanded') === 'true';
        btn.setAttribute('aria-expanded', String(!expanded));
        nav.style.display = expanded ? 'flex' : 'flex';
        // simple toggle for small screens
        if (window.innerWidth <= 980) {
          nav.style.flexDirection = expanded ? '' : 'column';
          nav.style.gap = expanded ? '' : '12px';
          nav.style.background = expanded ? '' : 'rgba(0,0,0,0.06)';
          nav.style.padding = expanded ? '' : '8px';
          nav.style.borderRadius = expanded ? '' : '10px';
        }
      });
      // Close nav when clicking outside on small screens
      document.addEventListener('click', (e) => {
        if (window.innerWidth > 980) return;
        if (!btn.contains(e.target) && !nav.contains(e.target)) {
          btn.setAttribute('aria-expanded','false');
          nav.style.display = 'none';
        }
      });
      // Ensure initial state
      if (window.innerWidth <= 980) nav.style.display = 'none';
      window.addEventListener('resize', ()=> { if (window.innerWidth > 980) nav.style.display = 'flex'; });
    })();

    // Smooth scroll and active link highlight
    (function(){
      const links = document.querySelectorAll('.nav-link');
      const sections = Array.from(document.querySelectorAll('main, #about, #projects, #skills, #contact')).filter(Boolean);

      // Smooth scroll for nav links
      document.querySelectorAll('a[href^="#"]').forEach(a => {
        a.addEventListener('click', function(e){
          const href = this.getAttribute('href') || '';
          if (!href.startsWith('#')) return;
          e.preventDefault();
          const id = href.slice(1);
          if (!id) { window.scrollTo({top:0,behavior:'smooth'}); return; }
          const el = document.getElementById(id);
          if (el) el.scrollIntoView({behavior:'smooth',block:'start'});
        });
      });

      // IntersectionObserver to set active link
      if ('IntersectionObserver' in window) {
        const obs = new IntersectionObserver((entries) => {
          entries.forEach(entry => {
            if (entry.isIntersecting) {
              const id = entry.target.id;
              links.forEach(l => l.classList.toggle('active', l.getAttribute('href') === '#' + id));
            }
          });
        }, { root: null, threshold: 0.4 });

        // Observe main hero and any sections that exist
        const toObserve = [];
        const hero = document.getElementById('home');
        if (hero) toObserve.push(hero);
        ['about','projects','skills','contact'].forEach(id => {
          const el = document.getElementById(id);
          if (el) toObserve.push(el);
        });
        toObserve.forEach(el => obs.observe(el));
      } else {
        // fallback: highlight Home
        document.querySelector('.nav-link').classList.add('active');
      }
    })();

    // Simple entrance animation for hero elements
    (function(){
      const hero = document.querySelector('.hero-left');
      const photo = document.querySelector('.avatar');
      if (hero) {
        hero.style.opacity = 0;
        hero.style.transform = 'translateY(12px)';
        setTimeout(()=>{ hero.style.transition = 'opacity .7s ease, transform .7s ease'; hero.style.opacity = 1; hero.style.transform = 'none'; }, 120);
      }
      if (photo) {
        photo.style.opacity = 0;
        photo.style.transform = 'scale(.98)';
        setTimeout(()=>{ photo.style.transition = 'opacity .7s ease, transform .7s ease'; photo.style.opacity = 1; photo.style.transform = 'none'; }, 260);
      }
    })();
    // Back to Top button logic
(function(){
  const btn = document.getElementById('backToTop');
  window.addEventListener('scroll', () => {
    if (window.scrollY > 300) {
      btn.classList.add('show');
    } else {
      btn.classList.remove('show');
    }
  });
  btn.addEventListener('click', () => {
    window.scrollTo({ top: 0, behavior: 'smooth' });
  });
})();
  </script>
  <!-- Back to Top Button -->
<button id="backToTop" aria-label="Back to top" title="Back to top">
  ↑
</button>
</body>
</html>
