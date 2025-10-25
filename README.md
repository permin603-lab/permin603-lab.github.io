<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Ryle L. De Hitta — Portfolio</title>
  <meta name="description" content="Portfolio of Ryle L. De Hitta, BSIT-CPT-1 student and coding enthusiast." />

  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&family=Space+Grotesk:wght@500;700&display=swap" rel="stylesheet">
  <!-- Font Awesome -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.6.0/css/all.min.css" crossorigin="anonymous"/>
<!-- 3D + Motion Libraries -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>

  <style>
    :root {
      --bg-1:#050811;--bg-2:#0b1121;--card:#101626;--muted:#a1adc6;
      --accent-1:#8b5cf6;--accent-2:#6366f1;--glass:rgba(255,255,255,0.04);
      --radius:14px;--container:1100px;--shadow:0 10px 35px rgba(0,0,0,0.5);
    }
    [data-theme="light"]{
      --bg-1:#f5f6fa;--bg-2:#fff;--card:#fefefe;--muted:#444;
      --glass:rgba(0,0,0,0.04);--shadow:0 4px 15px rgba(0,0,0,0.1);
      color:#111;
    }
    *{box-sizing:border-box;margin:0;padding:0}
    body{
      font-family:'Inter',sans-serif;background:radial-gradient(circle at 20% 30%,var(--bg-2) 0%,var(--bg-1)100%);
      color:#e6eef8;line-height:1.6;overflow-x:hidden;position:relative;
    }
    body[data-theme="light"]{color:#111;}
    canvas#particles{position:fixed;top:0;left:0;width:100%;height:100%;z-index:-1;}
    a{text-decoration:none;color:inherit}

    @keyframes fadeInUp{0%{opacity:0;transform:translateY(12px)}100%{opacity:1;transform:translateY(0)}}

    nav{
      position:sticky;top:0;z-index:50;backdrop-filter:blur(14px);
      background:rgba(15,18,34,0.6);border-bottom:1px solid rgba(255,255,255,0.05);
      display:flex;justify-content:space-between;align-items:center;padding:12px 28px;
    }
    [data-theme="light"] nav{background:rgba(255,255,255,0.8);}
    .logo{font-family:'Space Grotesk',sans-serif;font-size:1.3rem;font-weight:700;
      background:linear-gradient(90deg,var(--accent-1),var(--accent-2));
      -webkit-background-clip:text;-webkit-text-fill-color:transparent}
    .nav-links{display:flex;gap:18px}
    .nav-links a{font-weight:600;font-size:.95rem;color:var(--muted);padding:8px 12px;border-radius:8px;transition:.25s}
    .nav-links a:hover{background:rgba(255,255,255,0.05);color:#fff;transform:translateY(-2px)}
    .nav-toggle{display:none;background:transparent;border:0;color:var(--muted);font-size:1.2rem}
    .theme-toggle{background:none;border:0;color:var(--muted);font-size:1.2rem;cursor:pointer}

    .hero{display:flex;align-items:center;justify-content:space-between;gap:40px;padding:80px 24px 100px;
      max-width:var(--container);margin:0 auto;animation:fadeInUp 1s ease}
    .hero-left h1{font-family:'Space Grotesk',sans-serif;font-size:2.6rem;margin-bottom:10px;color:#fff}
    [data-theme="light"] .hero-left h1{color:#111;}
    .hero-left p{color:var(--muted);max-width:540px;}
    .hero-cta{margin-top:26px;display:flex;gap:14px;flex-wrap:wrap}
    .btn{display:inline-flex;align-items:center;gap:10px;font-weight:700;font-size:.95rem;border-radius:10px;
      padding:12px 16px;cursor:pointer;transition:.25s;border:0}
    .btn-primary{background:linear-gradient(90deg,var(--accent-1),var(--accent-2));color:#fff;box-shadow:0 6px 20px rgba(99,102,241,0.25)}
    .btn-outline{background:transparent;color:var(--muted);border:1px solid rgba(255,255,255,0.08)}
    .btn:hover{transform:translateY(-3px);box-shadow:0 12px 30px rgba(99,102,241,0.25)}
    .hero-right{flex:0 0 240px;display:flex;justify-content:center}
    .profile{width:240px;height:240px;border-radius:50%;overflow:hidden;border:3px solid rgba(255,255,255,0.08);
      background:linear-gradient(180deg,rgba(255,255,255,0.05),rgba(255,255,255,0.02));box-shadow:var(--shadow);transition:.4s}
    .profile:hover{transform:scale(1.05)}
    .profile img{width:100%;height:100%;object-fit:cover}

    section{animation:fadeInUp 1s ease;}
    h2{font-family:'Space Grotesk',sans-serif;font-size:2rem;margin-bottom:40px;text-align:center;}

    /* Project & Skill styling as before */
    .proj-card{position:relative;overflow:hidden;border-radius:var(--radius);background:var(--card);
      transition:transform .3s,box-shadow .3s;box-shadow:var(--shadow)}
    .proj-card img{width:100%;height:200px;object-fit:cover;filter:brightness(.8);transition:.4s}
    .proj-info{padding:20px}
    .proj-card:hover img{transform:scale(1.08);filter:brightness(1)}
    .proj-card:hover{transform:translateY(-6px);box-shadow:0 12px 40px rgba(99,102,241,0.3)}
    .bar{background:rgba(255,255,255,0.05);border-radius:10px;height:10px;overflow:hidden}
    .fill{height:100%;background:linear-gradient(90deg,var(--accent-1),var(--accent-2));border-radius:10px;width:0;animation:fillAnim 2s ease forwards}
    @keyframes fillAnim{from{width:0}}

    footer{text-align:center;padding:40px 20px;color:var(--muted);font-size:.9rem;background:#060911}
    [data-theme="light"] footer{background:#f0f0f5;color:#666}
    @media(max-width:880px){
      .nav-links{display:none}
      .nav-toggle{display:block}
      .hero{flex-direction:column;text-align:center}
      .hero-right{order:-1;margin-bottom:24px}
    }
    /* === 3D Background Canvas === */
#bg-3d {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1;
  background: radial-gradient(ellipse at bottom, #0b0d16 0%, #000 100%);
}

/* === Logo Reveal Animation === */
.logo-reveal {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 2.5rem;
  font-weight: 800;
  color: #8a63ff;
  letter-spacing: 2px;
  text-shadow: 0 0 20px #8a63ff, 0 0 40px #8a63ff;
  opacity: 0;
  z-index: 99;
  pointer-events: none;
  user-select: none;
}

/* === Smooth UI Motion === */
button, .btn, .nav-link {
  transition: all 0.3s ease;
}

button:hover, .btn:hover, .nav-link:hover {
  transform: translateY(-3px) scale(1.03);
  box-shadow: 0 0 10px #8a63ff66;
}

/* Disable heavy animations on mobile */
@media (max-width: 768px) {
  #bg-3d {
    display: none;
  }
    }
                                
  </style>
</head>

<body data-theme="dark">
  <!-- 3D Background -->
<canvas id="bg-3d"></canvas>

<!-- Logo Reveal Animation -->
<div class="logo-reveal">Ryle L. De Hitta</div>

  <canvas id="particles"></canvas>

  <nav>
    <div class="logo">Ryle L. De Hitta</div>
    <div class="nav-links" id="navLinks">
      <a href="#home">Home</a><a href="#about">About</a><a href="#projects">Projects</a>
      <a href="#skills">Skills</a><a href="#contact">Contact</a>
    </div>
    <div style="display:flex;gap:10px;">
      <button class="theme-toggle" id="themeToggle"><i class="fa-solid fa-sun"></i></button>
      <button class="nav-toggle" id="navToggle"><i class="fa-solid fa-bars"></i></button>
    </div>
  </nav>

  <section class="hero" id="home">
    <div class="hero-left">
      <h1>Curious Mind. Code Crafter. Innovator.</h1>
      <p>Hey, I’m <strong>Ryle L. De Hitta</strong> — a BSIT-CPT-1 student and coding enthusiast passionate about building modern, AI-driven, and tech-inspired experiences.</p>
      <div class="hero-cta">
        <a class="btn btn-primary" href="#projects"><i class="fa-solid fa-rocket"></i> Explore Projects</a>
        <a class="btn btn-outline" href="#contact"><i class="fa-solid fa-paper-plane"></i> Contact</a>
      </div>
    </div>
    <div class="hero-right">
      <div class="profile">
        <img src="IMG_20250814_092221.jpg" alt="Ryle L. De Hitta"
             onerror="this.src='https://via.placeholder.com/400x400.png?text=Profile';"/>
      </div>
    </div>
  </section>

  <section id="about" style="max-width:var(--container);margin:0 auto;padding:100px 24px;">
    <h2>About Me</h2>
    <div style="display:flex;flex-wrap:wrap;gap:24px;justify-content:center;">
      <div style="background:var(--glass);border:1px solid rgba(255,255,255,0.05);
        border-radius:var(--radius);padding:28px;width:100%;max-width:500px;box-shadow:var(--shadow);">
        <h3 style="color:var(--accent-2);">Who I Am</h3>
        <p>I'm <strong>Ryle L. De Hitta</strong>, a BSIT-CPT-1 student passionate about coding, design, and technology.</p>
      </div>
      <div style="background:var(--glass);border:1px solid rgba(255,255,255,0.05);
        border-radius:var(--radius);padding:28px;width:100%;max-width:500px;box-shadow:var(--shadow);">
        <h3 style="color:var(--accent-2);">What Drives Me</h3>
        <p>I love challenges — whether it’s solving a tough bug or building something new. My goal: impactful, creative tech solutions.</p>
      </div>
    </div>
  </section>

  <section id="projects" style="padding:100px 24px;background:linear-gradient(180deg,#070b14 0%,#0a0f20 100%);">
    <h2>Projects</h2>
    <div style="display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
      gap:28px;max-width:var(--container);margin:0 auto;">
      <div class="proj-card"><img src="https://via.placeholder.com/500x300.png?text=Project+1" alt="">
        <div class="proj-info"><h3>Portfolio Website</h3><p>Personal showcase built with HTML & CSS.</p></div></div>
      <div class="proj-card"><img src="https://via.placeholder.com/500x300.png?text=Project+2" alt="">
        <div class="proj-info"><h3>Task Manager App</h3><p>Organize tasks using JavaScript & LocalStorage.</p></div></div>
      <div class="proj-card"><img src="https://via.placeholder.com/500x300.png?text=Project+3" alt="">
        <div class="proj-info"><h3>Weather Dashboard</h3><p>Real-time weather with clean UI & API integration.</p></div></div>
    </div>
  </section>

  <section id="skills" style="max-width:var(--container);margin:0 auto;padding:100px 24px;">
    <h2>Skills</h2>
    <div style="display:grid;gap:24px;max-width:600px;margin:0 auto;">
      <div class="skill"><span>HTML</span><div class="bar"><div class="fill" style="width:95%;"></div></div></div>
      <div class="skill"><span>CSS</span><div class="bar"><div class="fill" style="width:90%;"></div></div></div>
      <div class="skill"><span>JavaScript</span><div class="bar"><div class="fill" style="width:75%;"></div></div></div>
      <div class="skill"><span>Python</span><div class="bar"><div class="fill" style="width:70%;"></div></div></div>
      <div class="skill"><span>React</span><div class="bar"><div class="fill" style="width:60%;"></div></div></div>
    </div>
  </section>

  <section id="contact" style="padding:100px 24px;background:linear-gradient(180deg,#0a0f20 0%,#080c18 100%);">
    <h2>Contact Me</h2>
    <form action="#" method="post" style="max-width:600px;margin:0 auto;background:var(--glass);
      border:1px solid rgba(255,255,255,0.05);border-radius:var(--radius);
      padding:30px;box-shadow:var(--shadow);">
      <input type="text" placeholder="Your Name" required style="width:100%;padding:12px;margin-bottom:14px;
        background:rgba(255,255,255,0.04);border:1px solid rgba(255,255,255,0.08);
        border-radius:8px;color:#fff;">
      <input type="email" placeholder="Your Email" required style="width:100%;padding:12px;margin-bottom:14px;
        background:rgba(255,255,255,0.04);border:1px solid rgba(255,255,255,0.08);
        border-radius:8px;color:#fff;">
      <textarea placeholder="Your Message" rows="5" required style="width:100%;padding:12px;margin-bottom:16px;
        background:rgba(255,255,255,0.04);border:1px solid rgba(255,255,255,0.08);
        border-radius:8px;color:#fff;"></textarea>
      <button type="submit" class="btn btn-primary" style="width:100%;">Send Message</button>
    </form>
  </section>

  <footer>© 2025 Ryle L. De Hitta. Crafted with ❤️ and creativity.</footer>

  <script>
    // Mobile nav
    const navToggle=document.getElementById('navToggle');
    const navLinks=document.getElementById('navLinks');
    navToggle.addEventListener('click',()=>{navLinks.style.display=navLinks.style.display==='flex'?'none':'flex';});
    // Theme toggle
    const themeToggle=document.getElementById('themeToggle');
    const body=document.body;
    themeToggle.addEventListener('click',()=>{
      const current=body.getAttribute('data-theme');
      const next=current==='dark'?'light':'dark';
      body.setAttribute('data-theme',next);
      themeToggle.innerHTML=next==='dark'?'<i class="fa-solid fa-sun"></i>':'<i class="fa-solid fa-moon"></i>';
    });
    // Floating particles background
    const c=document.getElementById('particles');const ctx=c.getContext('2d');
    let particles=[];
    function resize(){c.width=innerWidth;c.height=innerHeight;}
    window.addEventListener('resize',resize);resize();
    for(let i=0;i<80;i++){
      particles.push({x:Math.random()*c.width,y:Math.random()*c.height,
        r:Math.random()*1.8+0.2,dx:(Math.random()-0.5)*0.4,dy:(Math.random()-0.5)*0.4});
    }
    function draw(){
      ctx.clearRect(0,0,c.width,c.height);
      ctx.fillStyle='rgba(255,255,255,0.6)';
      particles.forEach(p=>{
        ctx.beginPath();ctx.arc(p.x,p.y,p.r,0,Math.PI*2);ctx.fill();
        p.x+=p.dx;p.y+=p.dy;
        if(p.x<0||p.x>c.width)p.dx*=-1;
        if(p.y<0||p.y>c.height)p.dy*=-1;
      });
      requestAnimationFrame(draw);
    }
    draw();
  </script>
  <!-- 3D BACKGROUND -->
<script src="https://cdn.jsdelivr.net/npm/three@0.150.1/build/three.min.js"></script>
<script>
  // === Three.js Scene Setup ===
  const scene = new THREE.Scene();
  const camera = new THREE.PerspectiveCamera(75, window.innerWidth/window.innerHeight, 0.1, 1000);
  const renderer = new THREE.WebGLRenderer({alpha: true, antialias: true});
  renderer.setSize(window.innerWidth, window.innerHeight);
  renderer.domElement.style.position = 'fixed';
  renderer.domElement.style.top = 0;
  renderer.domElement.style.left = 0;
  renderer.domElement.style.zIndex = '-1';
  document.body.appendChild(renderer.domElement);

  // === Floating Light Sphere ===
  const geometry = new THREE.SphereGeometry(1.2, 64, 64);
  const material = new THREE.MeshStandardMaterial({
    color: 0x6366f1,
    emissive: 0x4338ca,
    emissiveIntensity: 1.5,
    metalness: 0.8,
    roughness: 0.2
  });
  const sphere = new THREE.Mesh(geometry, material);
  scene.add(sphere);

  // === Particles ===
  const particlesGeometry = new THREE.BufferGeometry();
  const particleCount = 800;
  const posArray = new Float32Array(particleCount * 3);
  for (let i = 0; i < particleCount * 3; i++) {
    posArray[i] = (Math.random() - 0.5) * 20;
  }
  particlesGeometry.setAttribute('position', new THREE.BufferAttribute(posArray, 3));
  const particlesMaterial = new THREE.PointsMaterial({
    size: 0.02,
    color: 0x818cf8,
    transparent: true,
    opacity: 0.8
  });
  const particlesMesh = new THREE.Points(particlesGeometry, particlesMaterial);
  scene.add(particlesMesh);

  // === Lighting ===
  const pointLight = new THREE.PointLight(0x6366f1, 1.5);
  pointLight.position.set(5, 5, 5);
  scene.add(pointLight);
  const ambientLight = new THREE.AmbientLight(0x1e1b4b, 0.6);
  scene.add(ambientLight);

  camera.position.z = 5;

  // === Animation ===
  function animate() {
    requestAnimationFrame(animate);
    sphere.rotation.x += 0.004;
    sphere.rotation.y += 0.005;
    particlesMesh.rotation.y += 0.0008;
    renderer.render(scene, camera);
  }
  animate();

  // === Responsive Resize ===
  window.addEventListener('resize', () => {
    camera.aspect = window.innerWidth / window.innerHeight;
    camera.updateProjectionMatrix();
    renderer.setSize(window.innerWidth, window.innerHeight);
  });
</script>

<!-- 3D UI Hover Effects -->
<script>
  // Apply 3D tilt to project cards & buttons
  const tiltElements = document.querySelectorAll('.proj-card, .btn');
  tiltElements.forEach(el => {
    el.addEventListener('mousemove', e => {
      const rect = el.getBoundingClientRect();
      const x = e.clientX - rect.left;
      const y = e.clientY - rect.top;
      const centerX = rect.width / 2;
      const centerY = rect.height / 2;
      const rotateX = ((y - centerY) / centerY) * 6;
      const rotateY = ((x - centerX) / centerX) * -6;
      el.style.transform = `rotateX(${rotateX}deg) rotateY(${rotateY}deg) scale(1.03)`;
    });
    el.addEventListener('mouseleave', () => {
      el.style.transform = 'rotateX(0deg) rotateY(0deg) scale(1)';
      el.style.transition = 'transform 0.3s ease';
    });
  });
</script>
<!-- PART 4: Cinematic 3D Intro Overlay -->
<style>
  /* Intro overlay styles (keep lightweight) */
  #introOverlay {
    position: fixed;
    inset: 0;
    z-index: 9999;
    display: grid;
    place-items: center;
    background: linear-gradient(180deg, rgba(2,6,23,0.92), rgba(2,6,23,0.75));
    backdrop-filter: blur(6px) saturate(1.05);
    -webkit-backdrop-filter: blur(6px) saturate(1.05);
    transition: opacity .6s ease, visibility .6s ease;
  }
  #introOverlay.hidden { opacity: 0; visibility: hidden; pointer-events: none; }

  .intro-card {
    text-align: center;
    transform-style: preserve-3d;
    perspective: 900px;
    will-change: transform;
  }

  .neon-title {
    font-family: 'Space Grotesk', sans-serif;
    font-size: clamp(2.4rem, 6vw, 5.2rem);
    color: #fff;
    letter-spacing: 0.6px;
    margin: 0 0 12px;
    transform: translateZ(40px) rotateY(0deg);
    transition: transform .35s ease;
    text-shadow:
      0 0 6px rgba(139,92,246,0.9),
      0 0 14px rgba(99,102,241,0.7),
      0 6px 30px rgba(8,6,30,0.6);
  }

  .neon-sub {
    font-size: clamp(0.95rem, 2.2vw, 1.15rem);
    color: rgba(230,238,248,0.9);
    margin-bottom: 22px;
    text-shadow: 0 2px 12px rgba(2,6,23,0.6);
    transform: translateZ(24px);
  }

  .intro-actions {
    display:flex;
    gap:12px;
    justify-content:center;
    transform: translateZ(12px);
  }

  .intro-btn {
    padding:10px 16px;
    border-radius:10px;
    font-weight:700;
    cursor:pointer;
    border:0;
    box-shadow: 0 10px 30px rgba(23,8,84,0.18);
    transition: transform .22s ease, box-shadow .22s ease, opacity .22s;
    background: linear-gradient(90deg, #8b5cf6, #6366f1);
    color: #fff;
  }
  .intro-btn.secondary {
    background: transparent;
    border:1px solid rgba(255,255,255,0.08);
    color: rgba(230,238,248,0.95);
  }
  .intro-btn:active { transform: translateY(1px) scale(.997); }

  /* subtle entry animation */
  @keyframes introPulse {
    0% { transform: translateY(6px) scale(.99); opacity: 0; }
    60% { transform: translateY(0) scale(1.02); opacity: 1; }
    100% { transform: translateY(0) scale(1); opacity: 1; }
  }
  .intro-card { animation: introPulse .9s cubic-bezier(.2,.9,.3,1); }

  /* small decorative 3D shards (very light, GPU-friendly) */
  .intro-shard {
    position: absolute;
    width: 140px;
    height: 10px;
    background: linear-gradient(90deg, rgba(139,92,246,0.18), rgba(99,102,241,0.12));
    filter: blur(10px);
    transform: translateZ(0);
    pointer-events: none;
  }
  .shard-1 { top:20%; left:10%; transform: rotate(12deg); opacity:.55; }
  .shard-2 { top:40%; right:12%; transform: rotate(-8deg); opacity:.45; width:200px; }
  .shard-3 { bottom:18%; left:20%; transform: rotate(6deg); opacity:.35; width:180px; }
</style>

<div id="introOverlay" aria-hidden="false" role="dialog" aria-label="Intro overlay - welcome">
  <div class="intro-shard shard-1"></div>
  <div class="intro-shard shard-2"></div>
  <div class="intro-shard shard-3"></div>

  <div class="intro-card" id="introCard">
    <h1 class="neon-title">Ryle L. De Hitta</h1>
    <p class="neon-sub">Curious mind • Community builder • Code crafter — BSIT-CPT-1</p>
    <div class="intro-actions">
      <button class="intro-btn" id="enterBtn">Enter Portfolio</button>
      <button class="intro-btn secondary" id="skipBtn">Skip Intro</button>
    </div>
  </div>
</div>

<script>
  (function(){
    // Elements
    const overlay = document.getElementById('introOverlay');
    const card = document.getElementById('introCard');
    const enter = document.getElementById('enterBtn');
    const skip = document.getElementById('skipBtn');

    // Prevent page scroll while intro is visible
    const lockScroll = () => { document.documentElement.style.overflow = 'hidden'; document.body.style.overflow = 'hidden'; };
    const unlockScroll = () => { document.documentElement.style.overflow = ''; document.body.style.overflow = ''; };

    lockScroll();

    // Parallax: small rotation based on mouse
    const handleMove = (e) => {
      const w = window.innerWidth, h = window.innerHeight;
      const nx = (e.clientX / w) - 0.5; // -0.5 .. 0.5
      const ny = (e.clientY / h) - 0.5;
      // rotateY (around vertical) and tilt slightly on X
      const rotateY = nx * 8; // degrees
      const rotateX = -ny * 6;
      // subtle translateZ effect via scale
      card.style.transform = `rotateX(${rotateX}deg) rotateY(${rotateY}deg) translateZ(0)`;
      // nudge neon-title for layered feel
      const title = card.querySelector('.neon-title');
      title.style.transform = `translateZ(40px) rotateY(${rotateY * 0.24}deg)`;
    };

    // Auto dismiss after 3000ms (3s)
    let dismissed = false;
    const autoDismissTimer = setTimeout(() => { dismissIntro(); }, 3000);

    function dismissIntro() {
      if (dismissed) return;
      dismissed = true;
      clearTimeout(autoDismissTimer);
      // fade out overlay
      overlay.classList.add('hidden');
      overlay.setAttribute('aria-hidden', 'true');
      // restore page scroll
      unlockScroll();
      // small cleanup: remove event listener
      window.removeEventListener('mousemove', handleMove);
      // re-enable Three.js subtle motion (if you paused it when intro shown)
      // (If you want, you can tie to a flag; here we just leave it running)
    }

    // click handlers
    enter.addEventListener('click', dismissIntro);
    skip.addEventListener('click', dismissIntro);
    // mouse parallax while visible
    window.addEventListener('mousemove', handleMove);

    // allow keyboard dismiss (Enter/Escape)
    window.addEventListener('keydown', (e) => {
      if (!overlay.classList.contains('hidden')) {
        if (e.key === 'Enter' || e.key === 'Escape') dismissIntro();
      }
    });

    // Accessibility: hide after focus moves away (optional)
    // If user tabs to page content, dismiss to avoid trap
    document.addEventListener('focusin', (e) => {
      if (!overlay.classList.contains('hidden')) {
        // if focus is inside overlay, ignore; else dismiss
        if (!overlay.contains(e.target)) dismissIntro();
      }
    });

    // Safety: if user's device is low-power / small screen, shorten or skip
    const prefersReducedMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches;
    if (prefersReducedMotion || window.innerWidth < 520) {
      // show for just 600ms then dismiss
      clearTimeout(autoDismissTimer);
      setTimeout(dismissIntro, 600);
    }
  })();
</script>
<script>
/* === 3D BACKGROUND SETUP === */
const scene = new THREE.Scene();
const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
const renderer = new THREE.WebGLRenderer({ canvas: document.getElementById("bg-3d"), alpha: true });
renderer.setSize(window.innerWidth, window.innerHeight);
camera.position.z = 5;

// Lighting
const light = new THREE.PointLight(0x8a63ff, 2, 50);
light.position.set(5, 5, 5);
scene.add(light);

// Geometric shapes
const geometry = new THREE.BoxGeometry();
const material = new THREE.MeshStandardMaterial({ color: 0x8a63ff, emissive: 0x1a0033, metalness: 0.7, roughness: 0.3 });
const cubes = [];

for (let i = 0; i < 25; i++) {
  const cube = new THREE.Mesh(geometry, material);
  cube.position.set((Math.random() - 0.5) * 10, (Math.random() - 0.5) * 10, (Math.random() - 0.5) * 10);
  cube.rotation.x = Math.random() * Math.PI;
  cube.rotation.y = Math.random() * Math.PI;
  cube.scale.setScalar(Math.random() * 0.5 + 0.3);
  scene.add(cube);
  cubes.push(cube);
}

function animate() {
  requestAnimationFrame(animate);
  cubes.forEach(cube => {
    cube.rotation.x += 0.002;
    cube.rotation.y += 0.003;
  });
  renderer.render(scene, camera);
}
animate();

// Resize responsive
window.addEventListener('resize', () => {
  camera.aspect = window.innerWidth / window.innerHeight;
  camera.updateProjectionMatrix();
  renderer.setSize(window.innerWidth, window.innerHeight);
});

/* === LOGO REVEAL ANIMATION === */
const logo = document.querySelector('.logo-reveal');
gsap.to(logo, { opacity: 1, scale: 1.2, duration: 1.2, ease: "power2.out" });
gsap.to(logo, { opacity: 0, y: -100, delay: 2.2, duration: 1.2, ease: "power2.inOut" });

/* === UI ENTRANCE MOTION === */
window.addEventListener('load', () => {
  gsap.from('h1, h2, p, .btn, .nav-link', {
    opacity: 0,
    y: 30,
    duration: 0.8,
    stagger: 0.1,
    ease: "power2.out"
  });
});
</script>

</body>
</html>
