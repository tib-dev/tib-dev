<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Tibeb — Profile Header & README (Animated + Theme)</title>
  <style>
    :root{
      --bg: #0f1724;
      --card: #0b1220;
      --text: #e6eef8;
      --muted: #94a3b8;
      --accent1: #06b6d4;
      --accent2: #7c3aed;
      --glass: rgba(255,255,255,0.04);
    }
    .light{
      --bg: #f7fafc;
      --card: #ffffff;
      --text: #0f1724;
      --muted: #475569;
      --accent1: #0ea5a4;
      --accent2: #7c3aed;
      --glass: rgba(2,6,23,0.04);
    }
    html,body{height:100%;margin:0;font-family:Inter,ui-sans-serif,system-ui,-apple-system,'Segoe UI',Roboto,'Helvetica Neue',Arial; background:var(--bg); color:var(--text);}
    .container{max-width:980px;margin:36px auto;padding:28px;border-radius:16px;background:linear-gradient(180deg,rgba(255,255,255,0.02),transparent);box-shadow:0 6px 30px rgba(2,6,23,0.6);}

    /* Header */
    .header{display:flex;align-items:center;gap:18px}
    .logo-wrap{width:140px;height:140px;flex:0 0 140px;border-radius:14px;background:var(--glass);display:flex;align-items:center;justify-content:center;position:relative;overflow:hidden}
    .logo-svg{width:120px;height:120px}

    /* Animated SVG text */
    .title-block{flex:1}
    .main-title{font-size:28px;margin:0 0 6px 0;letter-spacing:-0.5px}
    .subtitle{margin:0;color:var(--muted)}

    /* Animated background shapes */
    .shape{position:absolute;filter:blur(30px);opacity:0.45;mix-blend-mode:screen}
    .shape.s1{width:220px;height:220px;right:-60px;top:-40px;background:linear-gradient(45deg,var(--accent1),var(--accent2));border-radius:50%}
    .shape.s2{width:140px;height:140px;left:-40px;bottom:-40px;background:linear-gradient(120deg,var(--accent2),var(--accent1));border-radius:40%}

    /* Controls */
    .controls{display:flex;gap:8px;align-items:center;margin-top:12px}
    .btn{background:transparent;border:1px solid rgba(255,255,255,0.06);padding:8px 12px;border-radius:10px;color:var(--text);cursor:pointer}
    .btn.secondary{border-color:rgba(255,255,255,0.04);opacity:0.9}

    /* README content */
    .content{margin-top:22px;padding:18px;border-radius:12px;background:linear-gradient(180deg,rgba(255,255,255,0.01),transparent)}
    h2{color:var(--text)}
    a{color:var(--accent1)}

    /* Responsive */
    @media (max-width:640px){.header{flex-direction:column;align-items:flex-start}.logo-wrap{width:96px;height:96px}.main-title{font-size:20px}}

    /* small animation for SVG gradient */
    @keyframes slide{from{transform:translateX(-10%)}to{transform:translateX(10%)}}
    .grad-anim{animation:slide 5s ease-in-out infinite alternate}
  </style>
</head>
<body>
  <div class="container" id="page">
    <div style="position:relative;overflow:visible">
      <div class="shape s1" aria-hidden="true"></div>
      <div class="shape s2" aria-hidden="true"></div>
    </div>

    <header class="header">
      <!-- Animated SVG logo / header. Save this block as `header.svg` if you want to reuse it separately. -->
      <div class="logo-wrap" aria-hidden="true">
        <svg class="logo-svg" viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Tibeb logo">
          <defs>
            <linearGradient id="g1" x1="0" x2="1">
              <stop offset="0%" stop-color="#06b6d4" />
              <stop offset="50%" stop-color="#7c3aed" />
              <stop offset="100%" stop-color="#f97316" />
            </linearGradient>
            <filter id="f1" x="-20%" y="-20%" width="140%" height="140%">
              <feGaussianBlur stdDeviation="6" result="b" />
              <feComposite in="SourceGraphic" in2="b" operator="over"/>
            </filter>
            <mask id="m1">
              <rect width="100%" height="100%" fill="white" />
              <circle cx="60" cy="60" r="40" fill="black" />
            </mask>
          </defs>

          <!-- animated ring -->
          <g transform="translate(100,100)">
            <circle r="54" fill="none" stroke="url(#g1)" stroke-width="8" stroke-linecap="round" stroke-dasharray="10 6" stroke-dashoffset="0">
              <animate attributeName="stroke-dashoffset" values="0;40;0" dur="6s" repeatCount="indefinite" />
            </circle>

            <!-- stylized initials: T -->
            <g transform="translate(-24,-32) scale(1.2)" fill="url(#g1)">
              <rect x="8" y="4" width="10" height="44" rx="2">
                <animate attributeName="y" values="6;2;6" dur="3s" repeatCount="indefinite" />
              </rect>
              <rect x="8" y="4" width="34" height="10" rx="3"/>
            </g>

            <!-- small pulsing dot -->
            <circle cx="54" cy="-54" r="6" fill="#fff">
              <animate attributeName="r" values="6;10;6" dur="2.5s" repeatCount="indefinite"/>
              <animate attributeName="opacity" values="0.85;0.25;0.85" dur="2.5s" repeatCount="indefinite"/>
            </circle>
          </g>
        </svg>
      </div>

      <div class="title-block">
        <h1 class="main-title">Hi, I’m <strong>Tibeb</strong> — Full‑Stack Developer & AI/ML Enthusiast</h1>
        <p class="subtitle">Building secure, scalable systems. Cloud, backend architecture, and applied ML.</p>

        <div class="controls">
          <button class="btn" id="toggleTheme" title="Toggle dark / light">Toggle theme</button>
          <a class="btn secondary" href="#readme" role="button">View README</a>
        </div>
      </div>
    </header>

    <!-- README content translated into HTML for the demo. Keep original README.md in your repo; to embed the header in README.md: add an image link to `header.svg` in the repository (raw URL). -->
    <main class="content" id="readme">
      <h2>About</h2>
      <p>I’m a software engineer who enjoys building reliable, secure, and scalable systems. I work across the stack—from frontend to backend, cloud, and AI—and I like solving real problems with clean and thoughtful engineering.</p>

      <h3>Highlights</h3>
      <ul>
        <li>Certified in Networking, Cybersecurity, and Data Communication</li>
        <li>Strong interest in backend architecture, security, and distributed systems</li>
        <li>Active in hackathons, OSS contributions, and collaborative side projects</li>
      </ul>

      <h3>Featured Projects</h3>
      <ol>
        <li><strong>Amazon Clone</strong> — React · Node.js · Express · Stripe — <a href="https://github.com/tib-dev/amazon-clone">github.com/tib-dev/amazon-clone</a></li>
        <li><strong>Education Management System</strong> — <a href="https://ems-qsofti.netlify.app">ems-qsofti.netlify.app</a></li>
        <li><strong>LinkedIn Automation Tool</strong> — <a href="https://github.com/tib-dev/linkedin-automation">github.com/tib-dev/linkedin-automation</a></li>
      </ol>

      <h3>Tech Stack</h3>
      <p>Cloud & DevOps: AWS · Docker<br/>Frontend: React · Next.js · Tailwind · MUI<br/>Backend: Node.js · Express · Prisma<br/>Databases: PostgreSQL · MySQL · MongoDB</p>

      <h3>Contact</h3>
      <p>Website: <a href="https://tibebukaleb.netlify.app">tibebukaleb.netlify.app</a><br/>Email: <a href="mailto:wise.tibec@gmail.com">wise.tibec@gmail.com</a></p>

      <hr/>
      <p style="color:var(--muted);font-size:13px">Tip: To embed the animated header in your GitHub README, add the file <code>header.svg</code> to your repo and reference it like this in <code>README.md</code>:</p>
      <pre style="background:rgba(255,255,255,0.02);padding:12px;border-radius:8px;overflow:auto;color:var(--muted)"><code>&lt;img src="./header.svg" alt="Tibeb — Full-Stack Developer"&gt;</code></pre>

      <p style="color:var(--muted);font-size:13px">If you use GitHub Pages or a personal site, the header will render the SVG animation and the dark/light toggle will work when included in an HTML page. GitHub README.md files do not run JavaScript, so the toggle is only available in pages that accept HTML/JS (GitHub Pages, your personal website, or a dedicated demo file).</p>
    </main>

  </div>

  <script>
    // theme toggle (persist in localStorage)
    const page = document.getElementById('page');
    const toggle = document.getElementById('toggleTheme');
    function applyTheme(isLight){
      if(isLight) document.documentElement.classList.add('light');
      else document.documentElement.classList.remove('light');
      localStorage.setItem('tib_theme_light', isLight? '1':'0');
    }
    toggle.addEventListener('click', ()=>{
      const now = document.documentElement.classList.toggle('light');
      applyTheme(now);
    });
    // initialize
    const saved = localStorage.getItem('tib_theme_light');
    applyTheme(saved === '1');
  </script>
</body>
</html>
