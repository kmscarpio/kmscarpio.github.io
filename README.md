

<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="theme-color" content="#101114">

  <title>Matthew | Developer Portfolio</title>
  <meta name="description" content="Matthew's personal portfolio, programming projects, skills, and journey into software development and cybersecurity.">

  <style>
    /* =========================
       1. VARIABLES & RESET
    ========================= */

    :root {
      --bg: #101114;
      --surface: #17191e;
      --surface-hover: #1e2128;
      --text: #f2f3f5;
      --muted: #999da8;
      --accent: #a6f77b;
      --accent-dark: #152414;
      --border: #292c33;
      --nav-bg: rgba(16, 17, 20, 0.85);
      --radius: 18px;
      --max-width: 1080px;
    }

    body.light {
      --bg: #f7f8f5;
      --surface: #ffffff;
      --surface-hover: #eef0ea;
      --text: #20231e;
      --muted: #656b61;
      --accent: #467d29;
      --accent-dark: #e6f3df;
      --border: #e0e3da;
      --nav-bg: rgba(247, 248, 245, 0.88);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
      scroll-padding-top: 100px;
    }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: Inter, ui-sans-serif, system-ui, -apple-system,
        BlinkMacSystemFont, "Segoe UI", sans-serif;
      line-height: 1.7;
      transition: background 0.25s, color 0.25s;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    button {
      font: inherit;
    }

    button, a {
      -webkit-tap-highlight-color: transparent;
    }

    button:focus-visible,
    a:focus-visible {
      outline: 2px solid var(--accent);
      outline-offset: 4px;
    }

    ::selection {
      background: var(--accent);
      color: #101114;
    }

    .container {
      width: min(var(--max-width), calc(100% - 40px));
      margin-inline: auto;
    }

    .accent {
      color: var(--accent);
    }

    .muted {
      color: var(--muted);
    }

    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      color: var(--accent);
      font-size: 0.76rem;
      font-weight: 750;
      letter-spacing: 0.15em;
      text-transform: uppercase;
    }

    .eyebrow::before {
      content: "";
      width: 22px;
      height: 2px;
      background: var(--accent);
    }

    .section {
      padding-block: 100px;
    }

    .section-heading {
      max-width: 600px;
      margin-bottom: 40px;
    }

    .section-heading h2 {
      margin-top: 12px;
      font-size: clamp(2rem, 5vw, 3rem);
      line-height: 1.15;
      letter-spacing: -0.055em;
    }

    .section-heading p {
      margin-top: 14px;
      color: var(--muted);
    }

    /* =========================
       2. NAVIGATION
    ========================= */

    .navbar {
      position: sticky;
      top: 0;
      z-index: 100;
      background: var(--nav-bg);
      backdrop-filter: blur(16px);
      border-bottom: 1px solid var(--border);
    }

    .nav-inner {
      min-height: 76px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 20px;
    }

    .brand {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      font-size: 1rem;
      font-weight: 850;
      letter-spacing: -0.04em;
    }

    .brand-icon {
      display: grid;
      place-items: center;
      width: 35px;
      height: 35px;
      color: #101114;
      background: var(--accent);
      border-radius: 11px;
      font-size: 1.05rem;
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 27px;
      list-style: none;
    }

    .nav-links a {
      color: var(--muted);
      font-size: 0.88rem;
      transition: color 0.2s;
    }

    .nav-links a:hover {
      color: var(--accent);
    }

    .nav-actions {
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .icon-button,
    .menu-button {
      display: grid;
      place-items: center;
      width: 40px;
      height: 40px;
      background: var(--surface);
      color: var(--text);
      border: 1px solid var(--border);
      border-radius: 12px;
      cursor: pointer;
    }

    .menu-button {
      display: none;
    }

    /* =========================
       3. BUTTONS
    ========================= */

    .button {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 9px;
      min-height: 46px;
      padding: 11px 18px;
      border: 1px solid transparent;
      border-radius: 12px;
      font-size: 0.88rem;
      font-weight: 750;
      cursor: pointer;
      transition: transform 0.2s, background 0.2s;
    }

    .button:hover {
      transform: translateY(-2px);
    }

    .button-primary {
      color: #101114;
      background: var(--accent);
    }

    .button-primary:hover {
      filter: brightness(0.94);
    }

    .button-secondary {
      background: var(--surface);
      border-color: var(--border);
      color: var(--text);
    }

    /* =========================
       4. HERO
    ========================= */

    .hero {
      position: relative;
      overflow: hidden;
      padding-block: 110px 75px;
    }

    .hero::before {
      content: "";
      position: absolute;
      top: -180px;
      right: -150px;
      width: 480px;
      height: 480px;
      border-radius: 50%;
      background: var(--accent);
      opacity: 0.055;
      filter: blur(100px);
      pointer-events: none;
    }

    .hero-grid {
      position: relative;
      display: grid;
      grid-template-columns: 1.15fr 0.85fr;
      align-items: center;
      gap: 60px;
    }

    .hero h1 {
      max-width: 700px;
      margin-top: 24px;
      font-size: clamp(3rem, 6.5vw, 5.4rem);
      font-weight: 850;
      line-height: 1.04;
      letter-spacing: -0.075em;
    }

    .hero-description {
      max-width: 510px;
      margin-top: 25px;
      color: var(--muted);
      font-size: 1.03rem;
    }

    .hero-buttons {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      margin-top: 30px;
    }

    .availability {
      display: inline-flex;
      align-items: center;
      gap: 9px;
      margin-top: 35px;
      color: var(--muted);
      font-size: 0.82rem;
    }

    .status-dot {
      width: 9px;
      height: 9px;
      background: var(--accent);
      border-radius: 50%;
      box-shadow: 0 0 12px var(--accent);
    }

    /* Decorative terminal card */

    .terminal {
      overflow: hidden;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 20px;
      box-shadow: 0 30px 80px rgba(0, 0, 0, 0.15);
      transform: rotate(1.5deg);
    }

    .terminal-top {
      display: flex;
      align-items: center;
      gap: 7px;
      padding: 15px 17px;
      border-bottom: 1px solid var(--border);
    }

    .terminal-dot {
      width: 9px;
      height: 9px;
      border-radius: 50%;
      background: #777;
    }

    .terminal-dot:nth-child(1) { background: #ff6b68; }
    .terminal-dot:nth-child(2) { background: #f4c45e; }
    .terminal-dot:nth-child(3) { background: #7bd88f; }

    .terminal-title {
      margin-left: auto;
      color: var(--muted);
      font-size: 0.72rem;
    }

    .terminal-body {
      padding: 25px 22px 28px;
      font-family: "SFMono-Regular", Consolas, monospace;
      font-size: clamp(0.72rem, 1.3vw, 0.87rem);
      line-height: 2.1;
      overflow-wrap: anywhere;
    }

    .code-muted { color: #858b98; }
    .code-purple { color: #c6a0f6; }
    .code-green { color: #a6f77b; }
    .code-blue { color: #83c7f8; }
    .code-orange { color: #f4bd80; }

    .terminal-footer {
      display: flex;
      justify-content: space-between;
      gap: 12px;
      padding: 13px 20px;
      color: var(--muted);
      background: var(--surface-hover);
      font-size: 0.7rem;
    }

    /* =========================
       5. QUICK FACTS
    ========================= */

    .facts {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      border-block: 1px solid var(--border);
    }

    .fact {
      padding: 25px 20px;
      text-align: center;
    }

    .fact + .fact {
      border-left: 1px solid var(--border);
    }

    .fact strong {
      display: block;
      font-size: 1rem;
    }

    .fact span {
      color: var(--muted);
      font-size: 0.8rem;
    }

    /* =========================
       6. ABOUT
    ========================= */

    .about-grid {
      display: grid;
      grid-template-columns: 0.85fr 1.15fr;
      gap: 70px;
      align-items: start;
    }

    .about-card {
      padding: 28px;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: var(--radius);
    }

    .about-symbol {
      display: grid;
      place-items: center;
      width: 55px;
      height: 55px;
      margin-bottom: 20px;
      background: var(--accent-dark);
      border-radius: 16px;
      font-size: 1.7rem;
    }

    .about-card h3 {
      margin-bottom: 9px;
      font-size: 1.15rem;
    }

    .about-card p,
    .about-copy p {
      color: var(--muted);
    }

    .about-copy p + p {
      margin-top: 17px;
    }

    .about-copy h3 {
      margin: 27px 0 12px;
    }

    .interest-list {
      display: flex;
      flex-wrap: wrap;
      gap: 9px;
      margin-top: 14px;
    }

    .tag {
      display: inline-flex;
      align-items: center;
      padding: 5px 11px;
      color: var(--muted);
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 8px;
      font-size: 0.76rem;
    }

    /* =========================
       7. SKILLS
    ========================= */

    .skills-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 18px;
    }

    .skill-card {
      padding: 25px;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      transition: border-color 0.2s, transform 0.2s;
    }

    .skill-card:hover {
      transform: translateY(-4px);
      border-color: var(--accent);
    }

    .skill-icon {
      display: grid;
      place-items: center;
      width: 44px;
      height: 44px;
      margin-bottom: 18px;
      background: var(--accent-dark);
      border-radius: 13px;
      font-size: 1.3rem;
    }

    .skill-card h3 {
      margin-bottom: 8px;
      font-size: 1rem;
    }

    .skill-card p {
      min-height: 48px;
      color: var(--muted);
      font-size: 0.86rem;
    }

    .skill-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 7px;
      margin-top: 18px;
    }

    .skill-tags span {
      padding: 4px 8px;
      background: var(--bg);
      border-radius: 6px;
      color: var(--muted);
      font-size: 0.72rem;
    }

    /* =========================
       8. PROJECTS
    ========================= */

    .project-toolbar {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-bottom: 25px;
    }

    .filter-button {
      padding: 8px 14px;
      color: var(--muted);
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 9px;
      cursor: pointer;
      font-size: 0.82rem;
    }

    .filter-button.active,
    .filter-button:hover {
      color: var(--text);
      border-color: var(--accent);
    }

    .projects-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 20px;
    }

    .project-card {
      overflow: hidden;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      transition: transform 0.2s, border-color 0.2s;
    }

    .project-card:hover {
      transform: translateY(-4px);
      border-color: var(--accent);
    }

    .project-cover {
      position: relative;
      display: grid;
      place-items: center;
      min-height: 180px;
      overflow: hidden;
      background:
        radial-gradient(ellipse at 20% 20%, #a6f77b22, transparent 60%),
        var(--surface-hover);
      border-bottom: 1px solid var(--border);
    }

    .project-cover::before,
    .project-cover::after {
      content: "";
      position: absolute;
      width: 200px;
      height: 200px;
      border: 1px solid var(--border);
      border-radius: 50%;
    }

    .project-cover::after {
      width: 140px;
      height: 140px;
    }

    .project-emoji {
      z-index: 1;
      display: grid;
      place-items: center;
      width: 75px;
      height: 75px;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 22px;
      font-size: 2rem;
      box-shadow: 0 10px 40px #00000020;
    }

    .project-number {
      position: absolute;
      top: 15px;
      left: 17px;
      color: var(--muted);
      font-family: monospace;
      font-size: 0.75rem;
    }

    .project-category {
      position: absolute;
      right: 15px;
      bottom: 15px;
      color: var(--muted);
      font-size: 0.72rem;
    }

    .project-content {
      padding: 23px;
    }

    .project-content h3 {
      font-size: 1.15rem;
    }

    .project-content p {
      min-height: 52px;
      margin-top: 9px;
      color: var(--muted);
      font-size: 0.87rem;
    }

    .project-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 7px;
      margin-top: 17px;
    }

    .project-links {
      display: flex;
      gap: 18px;
      margin-top: 22px;
    }

    .text-link {
      color: var(--text);
      font-size: 0.82rem;
      font-weight: 700;
    }

    .text-link:hover {
      color: var(--accent);
    }

    .empty-state {
      display: none;
      grid-column: 1 / -1;
      padding: 30px;
      color: var(--muted);
      text-align: center;
    }

    /* =========================
       9. LEARNING JOURNEY
    ========================= */

    .journey {
      display: grid;
      gap: 0;
      max-width: 760px;
    }

    .journey-item {
      position: relative;
      display: grid;
      grid-template-columns: 25px 1fr;
      gap: 18px;
      padding-bottom: 30px;
    }

    .journey-item:not(:last-child)::before {
      content: "";
      position: absolute;
      top: 24px;
      bottom: 0;
      left: 10px;
      width: 1px;
      background: var(--border);
    }

    .journey-dot {
      z-index: 1;
      width: 21px;
      height: 21px;
      background: var(--surface);
      border: 2px solid var(--accent);
      border-radius: 50%;
    }

    .journey-item h3 {
      font-size: 1rem;
    }

    .journey-item p {
      margin-top: 5px;
      color: var(--muted);
      font-size: 0.88rem;
    }

    .journey-status {
      display: inline-block;
      margin-top: 9px;
      color: var(--accent);
      font-size: 0.75rem;
      font-weight: 700;
    }

    /* =========================
       10. CONTACT
    ========================= */

    .contact-box {
      position: relative;
      overflow: hidden;
      padding: clamp(28px, 6vw, 60px);
      background:
        radial-gradient(ellipse at 100% 0%, #a6f77b17, transparent 55%),
        var(--surface);
      border: 1px solid var(--border);
      border-radius: 24px;
    }

    .contact-box h2 {
      max-width: 650px;
      margin-top: 14px;
      font-size: clamp(2rem, 5vw, 3.5rem);
      line-height: 1.1;
      letter-spacing: -0.06em;
    }

    .contact-box p {
      max-width: 520px;
      margin-top: 18px;
      color: var(--muted);
    }

    .contact-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      margin-top: 27px;
    }

    /* =========================
       11. FOOTER
    ========================= */

    .footer {
      margin-top: 80px;
      border-top: 1px solid var(--border);
    }

    .footer-inner {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: space-between;
      gap: 15px;
      padding-block: 25px;
      color: var(--muted);
      font-size: 0.8rem;
    }

    .footer-links {
      display: flex;
      flex-wrap: wrap;
      gap: 18px;
    }

    .footer-links a:hover {
      color: var(--accent);
    }

    /* =========================
       12. SCROLL ANIMATIONS
    ========================= */

    .reveal {
      opacity: 0;
      transform: translateY(18px);
      transition: opacity 0.65s ease, transform 0.65s ease;
    }

    .reveal.visible {
      opacity: 1;
      transform: translateY(0);
    }

    @media (prefers-reduced-motion: reduce) {
      *,
      *::before,
      *::after {
        scroll-behavior: auto !important;
        animation: none !important;
        transition-duration: 0.01ms !important;
      }

      .reveal {
        opacity: 1;
        transform: none;
      }
    }

    /* =========================
       13. RESPONSIVE DESIGN
    ========================= */

    @media (max-width: 850px) {
      .nav-links {
        gap: 16px;
      }

      .nav-links a {
        font-size: 0.8rem;
      }

      .hero-grid {
        grid-template-columns: 1fr;
        gap: 45px;
      }

      .hero {
        padding-top: 80px;
      }

      .terminal {
        max-width: 560px;
        transform: none;
      }

      .about-grid {
        grid-template-columns: 1fr;
        gap: 30px;
      }

      .skills-grid {
        grid-template-columns: repeat(2, 1fr);
      }
    }

    @media (max-width: 620px) {
      .container {
        width: min(100% - 30px, var(--max-width));
      }

      .nav-inner {
        min-height: 66px;
      }

      .menu-button {
        display: grid;
      }

      .nav-links {
        position: absolute;
        top: calc(100% + 1px);
        left: 0;
        right: 0;
        display: none;
        align-items: stretch;
        gap: 0;
        padding: 10px 20px 18px;
        background: var(--bg);
        border-bottom: 1px solid var(--border);
      }

      .nav-links.open {
        display: flex;
        flex-direction: column;
      }

      .nav-links a {
        display: block;
        padding: 11px 0;
        font-size: 0.95rem;
      }

      .hero {
        padding-block: 70px 55px;
      }

      .hero h1 {
        font-size: clamp(2.8rem, 13vw, 4rem);
      }

      .hero-description {
        font-size: 0.94rem;
      }

      .section {
        padding-block: 70px;
      }

      .facts {
        grid-template-columns: 1fr;
      }

      .fact {
        padding: 18px;
      }

      .fact + .fact {
        border-left: none;
        border-top: 1px solid var(--border);
      }

      .skills-grid,
      .projects-grid {
        grid-template-columns: 1fr;
      }

      .skill-card p,
      .project-content p {
        min-height: auto;
      }

      .project-cover {
        min-height: 155px;
      }

      .footer-inner {
        flex-direction: column;
        align-items: flex-start;
      }
    }
  </style>

  <link rel="icon" href="/kmsLogo.jpg?v=2" type="image/jpeg">
  
</head>

<body>
  <!-- NAVIGATION -->
  <header class="navbar">
    <nav class="container nav-inner" aria-label="Main navigation">
      <a href="#home" class="brand" aria-label="Matthew home">
        <span class="brand-icon">M.</span>
        MATTHEW<span class="accent">.</span>
      </a>

      <ul class="nav-links" id="navLinks">
        <li><a href="#about">About</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#journey">Journey</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>

      <div class="nav-actions">
        <button
          class="icon-button"
          id="themeToggle"
          type="button"
          aria-label="Switch color theme"
          title="Toggle theme"
        >☼</button>

        <button
          class="menu-button"
          id="menuToggle"
          type="button"
          aria-label="Open navigation menu"
          aria-expanded="false"
          aria-controls="navLinks"
        >☰</button>
      </div>
    </nav>
  </header>

  <main>
    <!-- HERO -->
    <section class="hero" id="home">
      <div class="container hero-grid">
        <div class="reveal">
          <span class="eyebrow">BSIT Student · Developer in Progress</span>

          <h1>
            Building things for the web,
            <span class="accent">one line at a time.</span>
          </h1>

          <p class="hero-description">
            I'm Matthew, an IT student learning to turn ideas into
            useful software. Currently exploring web development,
            programming, and cybersecurity.
          </p>

          <div class="hero-buttons">
            <a href="#projects" class="button button-primary">
              Explore my work <span aria-hidden="true">↘</span>
            </a>

            <!-- Replace YOUR-USERNAME with your GitHub username -->
            <a
              href="https://github.com/YOUR-USERNAME"
              class="button button-secondary"
              target="_blank"
              rel="noopener noreferrer"
            >
              GitHub <span aria-hidden="true">↗</span>
            </a>
          </div>

          <div class="availability">
            <span class="status-dot"></span>
            Learning, building, and improving every day
          </div>
        </div>

        <!-- Decorative code card -->
        <div class="terminal reveal" aria-label="Example code preview">
          <div class="terminal-top">
            <span class="terminal-dot"></span>
            <span class="terminal-dot"></span>
            <span class="terminal-dot"></span>
            <span class="terminal-title">about-me.js</span>
          </div>

          <div class="terminal-body">
            <div><span class="code-purple">const</span> <span class="code-blue">developer</span> = {</div>
            <div>&nbsp;&nbsp;name: <span class="code-green">"Matthew"</span>,</div>
            <div>&nbsp;&nbsp;role: <span class="code-green">"IT Student"</span>,</div>
            <div>&nbsp;&nbsp;interests: [</div>
            <div>&nbsp;&nbsp;&nbsp;&nbsp;<span class="code-orange">"Web Development"</span>,</div>
            <div>&nbsp;&nbsp;&nbsp;&nbsp;<span class="code-orange">"Cybersecurity"</span>,</div>
            <div>&nbsp;&nbsp;&nbsp;&nbsp;<span class="code-orange">"Problem Solving"</span></div>
            <div>&nbsp;&nbsp;],</div>
            <div>&nbsp;&nbsp;learning: <span class="code-purple">true</span>,</div>
            <div>&nbsp;&nbsp;giveUp: <span class="code-purple">false</span></div>
            <div>};</div>
            <br>
            <div><span class="code-muted">// Progress over perfection.</span></div>
          </div>

          <div class="terminal-footer">
            <span>● Ready to learn</span>
            <span>UTF-8 · JavaScript</span>
          </div>
        </div>
      </div>
    </section>

    <!-- QUICK FACTS -->
    <div class="container">
      <div class="facts reveal">
        <div class="fact">
          <strong>Student</strong>
          <span>Always learning</span>
        </div>
        <div class="fact">
          <strong>HTML · CSS · JS</strong>
          <span>Web fundamentals</span>
        </div>
        <div class="fact">
          <strong>Build → Test → Improve</strong>
          <span>My learning approach</span>
        </div>
      </div>
    </div>

    <!-- ABOUT -->
    <section class="section" id="about">
      <div class="container about-grid">
        <div class="about-card reveal">
          <div class="about-symbol" aria-hidden="true">⌘</div>
          <h3>A little about me</h3>
          <p>
            I'm building my skills one project at a time.
            This website is my small corner of the internet where
            I can document what I learn and share what I build.
          </p>
          <div class="interest-list">
            <span class="tag">Programming</span>
            <span class="tag">Technology</span>
            <span class="tag">Cybersecurity</span>
            <span class="tag">Problem solving</span>
          </div>
        </div>

        <div class="about-copy reveal">
          <span class="eyebrow">About me</span>
          <h2 style="font-size: 2rem; margin-top: 12px; letter-spacing: -0.05em;">
            Curious by nature.<br>
            <span class="accent">Technical by choice.</span>
          </h2>

          <p style="margin-top: 20px;">
            I'm an IT student interested in understanding how software
            works, how websites are built, and how systems can be made
            more secure.
          </p>

          <p>
            I believe the best way to learn programming is to write
            code, make mistakes, figure out why things break, and
            keep improving.
          </p>

          <h3>What I'm working toward</h3>
          <p>
            Developing a strong foundation in software development,
            building practical projects, and learning more about
            computer systems and security.
          </p>
        </div>
      </div>
    </section>

    <!-- SKILLS -->
    <section class="section" id="skills" style="background: var(--surface);">
      <div class="container">
        <div class="section-heading reveal">
          <span class="eyebrow">My toolkit</span>
          <h2>Skills I'm <span class="accent">developing.</span></h2>
          <p>
            A growing collection of technologies I'm learning
            through practice and personal projects.
          </p>
        </div>

        <div class="skills-grid">
          <article class="skill-card reveal">
            <div class="skill-icon" aria-hidden="true">⌨</div>
            <h3>Web Development</h3>
            <p>Building web pages with structure, styling, and interactivity.</p>
            <div class="skill-tags">
              <span>HTML5</span>
              <span>CSS3</span>
              <span>JavaScript</span>
            </div>
          </article>

          <article class="skill-card reveal">
            <div class="skill-icon" aria-hidden="true">{"{}"}</div>
            <h3>Programming</h3>
            <p>Learning programming concepts and building small applications.</p>
            <div class="skill-tags">
              <span>C#</span>
              <span>Python</span>
              <span>OOP</span>
            </div>
          </article>

          <article class="skill-card reveal">
            <div class="skill-icon" aria-hidden="true">⌘</div>
            <h3>Tools & Workflow</h3>
            <p>Managing code, tracking changes, and working with development tools.</p>
            <div class="skill-tags">
              <span>Git</span>
              <span>GitHub</span>
              <span>VS Code</span>
            </div>
          </article>

          <article class="skill-card reveal">
            <div class="skill-icon" aria-hidden="true">▤</div>
            <h3>Databases</h3>
            <p>Learning how applications store, organize, and retrieve information.</p>
            <div class="skill-tags">
              <span>SQL</span>
              <span>MySQL</span>
            </div>
          </article>

          <article class="skill-card reveal">
            <div class="skill-icon" aria-hidden="true">⌁</div>
            <h3>Cybersecurity</h3>
            <p>Exploring networking, Linux, and security testing in authorized labs.</p>
            <div class="skill-tags">
              <span>Linux</span>
              <span>Networking</span>
              <span>Security labs</span>
            </div>
          </article>

          <article class="skill-card reveal">
            <div class="skill-icon" aria-hidden="true">↗</div>
            <h3>Problem Solving</h3>
            <p>Breaking problems into smaller steps and debugging my own code.</p>
            <div class="skill-tags">
              <span>Debugging</span>
              <span>Logic</span>
              <span>Practice</span>
            </div>
          </article>
        </div>
      </div>
    </section>

    <!-- PROJECTS -->
    <section class="section" id="projects">
      <div class="container">
        <div class="section-heading reveal">
          <span class="eyebrow">Things I've built</span>
          <h2>Selected <span class="accent">projects.</span></h2>
          <p>
            A place for experiments, school projects, and applications
            that demonstrate what I can do.
          </p>
        </div>

        <div class="project-toolbar reveal" aria-label="Filter projects">
          <button class="filter-button active" data-filter="all" aria-pressed="true">
            All projects
          </button>
          <button class="filter-button" data-filter="web" aria-pressed="false">
            Web
          </button>
          <button class="filter-button" data-filter="software" aria-pressed="false">
            Software
          </button>
          <button class="filter-button" data-filter="security" aria-pressed="false">
            Security
          </button>
        </div>

        <div class="projects-grid" id="projectsGrid">
          <article class="project-card reveal" data-category="web">
            <div class="project-cover">
              <span class="project-number">PROJECT / 001</span>
              <div class="project-emoji" aria-hidden="true">🌐</div>
              <span class="project-category">WEB DEVELOPMENT</span>
            </div>
            <div class="project-content">
              <h3>Personal Portfolio</h3>
              <p>
                A responsive personal website showcasing my background,
                skills, projects, and learning progress.
              </p>
              <div class="project-tags">
                <span class="tag">HTML</span>
                <span class="tag">CSS</span>
                <span class="tag">JavaScript</span>
              </div>
              <div class="project-links">
                <!-- Replace # with your actual repository URL -->
                <a class="text-link" href="https://github.com/YOUR-USERNAME/YOUR-REPOSITORY" target="_blank" rel="noopener noreferrer">
                  Source code ↗
                </a>
              </div>
            </div>
          </article>

          <article class="project-card reveal" data-category="software">
            <div class="project-cover">
              <span class="project-number">PROJECT / 002</span>
              <div class="project-emoji" aria-hidden="true">⏱</div>
              <span class="project-category">DESKTOP SOFTWARE</span>
            </div>
            <div class="project-content">
              <h3>EyeCare Reminder</h3>
              <p>
                A desktop utility concept that reminds users to take
                regular screen breaks using a timed reminder system.
              </p>
              <div class="project-tags">
                <span class="tag">C#</span>
                <span class="tag">.NET</span>
                <span class="tag">Windows</span>
              </div>
              <div class="project-links">
                <a class="text-link" href="https://github.com/YOUR-USERNAME/YOUR-REPOSITORY" target="_blank" rel="noopener noreferrer">
                  Source code ↗
                </a>
              </div>
            </div>
          </article>

          <article class="project-card reveal" data-category="security">
            <div class="project-cover">
              <span class="project-number">PROJECT / 003</span>
              <div class="project-emoji" aria-hidden="true">⌘</div>
              <span class="project-category">CYBERSECURITY</span>
            </div>
            <div class="project-content">
              <h3>Security Lab Notes</h3>
              <p>
                A learning journal documenting networking concepts,
                Linux commands, lab exercises, and security findings.
              </p>
              <div class="project-tags">
                <span class="tag">Linux</span>
                <span class="tag">Networking</span>
                <span class="tag">Documentation</span>
              </div>
              <div class="project-links">
                <a class="text-link" href="https://github.com/YOUR-USERNAME/YOUR-REPOSITORY" target="_blank" rel="noopener noreferrer">
                  Source code ↗
                </a>
              </div>
            </div>
          </article>

          <div class="empty-state" id="emptyState">
            No projects in this category yet.
          </div>
        </div>
      </div>
    </section>

    <!-- LEARNING JOURNEY -->
    <section class="section" id="journey" style="background: var(--surface);">
      <div class="container">
        <div class="section-heading reveal">
          <span class="eyebrow">The process</span>
          <h2>My learning <span class="accent">journey.</span></h2>
          <p>
            The milestones I'm working through to become a better developer.
          </p>
        </div>

        <div class="journey">
          <article class="journey-item reveal">
            <div class="journey-dot"></div>
            <div>
              <h3>Learn the fundamentals</h3>
              <p>
                Practice programming logic, data types, conditionals,
                loops, functions, and object-oriented programming.
              </p>
              <span class="journey-status">01 / FOUNDATIONS</span>
            </div>
          </article>

          <article class="journey-item reveal">
            <div class="journey-dot"></div>
            <div>
              <h3>Build practical applications</h3>
              <p>
                Create small projects, solve real problems, and learn
                to debug and maintain code.
              </p>
              <span class="journey-status">02 / BUILDING</span>
            </div>
          </article>

          <article class="journey-item reveal">
            <div class="journey-dot"></div>
            <div>
              <h3>Explore web development</h3>
              <p>
                Develop responsive interfaces and learn how browsers,
                websites, and web servers work together.
              </p>
              <span class="journey-status">03 / THE WEB</span>
            </div>
          </article>

          <article class="journey-item reveal">
            <div class="journey-dot"></div>
            <div>
              <h3>Grow in cybersecurity</h3>
              <p>
                Study networking and system security, then practice
                safely in authorized training environments.
              </p>
              <span class="journey-status">04 / SECURITY</span>
            </div>
          </article>
        </div>
      </div>
    </section>

    <!-- CONTACT -->
    <section class="section" id="contact">
      <div class="container">
        <div class="contact-box reveal">
          <span class="eyebrow">Get in touch</span>
          <h2>Let's connect and <span class="accent">build something.</span></h2>
          <p>
            Interested in my projects or want to connect about technology?
            Find me through GitHub or send me an email.
          </p>

          <div class="contact-actions">
            <a
              class="button button-primary"
              href="mailto:YOUR-EMAIL@example.com"
            >
              Send an email ↗
            </a>
            <a
              class="button button-secondary"
              href="https://github.com/YOUR-USERNAME"
              target="_blank"
              rel="noopener noreferrer"
            >
              Visit GitHub ↗
            </a>
          </div>
        </div>
      </div>
    </section>
  </main>

  <!-- FOOTER -->
  <footer class="footer">
    <div class="container footer-inner">
      <span>© <span id="year"></span> Matthew. Built with HTML, CSS & JS.</span>

      <div class="footer-links">
        <a href="#home">Back to top ↑</a>
        <a href="https://github.com/YOUR-USERNAME" target="_blank" rel="noopener noreferrer">
          GitHub ↗
        </a>
      </div>
    </div>
  </footer>

  <script>
    // =========================
    // 1. AUTOMATIC FOOTER YEAR
    // =========================

    document.getElementById("year").textContent =
      new Date().getFullYear();


    // =========================
    // 2. MOBILE NAVIGATION
    // =========================

    const menuToggle = document.getElementById("menuToggle");
    const navLinks = document.getElementById("navLinks");

    menuToggle.addEventListener("click", () => {
      const isOpen = navLinks.classList.toggle("open");

      menuToggle.setAttribute("aria-expanded", String(isOpen));
      menuToggle.setAttribute(
        "aria-label",
        isOpen ? "Close navigation menu" : "Open navigation menu"
      );

      menuToggle.textContent = isOpen ? "✕" : "☰";
    });

    // Close the mobile menu after selecting a link.
    navLinks.querySelectorAll("a").forEach((link) => {
      link.addEventListener("click", () => {
        navLinks.classList.remove("open");
        menuToggle.setAttribute("aria-expanded", "false");
        menuToggle.setAttribute("aria-label", "Open navigation menu");
        menuToggle.textContent = "☰";
      });
    });


    // =========================
    // 3. LIGHT / DARK THEME
    // =========================

    const themeToggle = document.getElementById("themeToggle");

    function updateThemeButton() {
      const isLight = document.body.classList.contains("light");

      themeToggle.textContent = isLight ? "☾" : "☼";
      themeToggle.setAttribute(
        "aria-label",
        isLight ? "Switch to dark theme" : "Switch to light theme"
      );
    }

    // Restore a previously selected theme if one exists.
    try {
      if (localStorage.getItem("portfolio-theme") === "light") {
        document.body.classList.add("light");
      }
    } catch (error) {
      // The theme toggle still works if storage is unavailable.
    }

    updateThemeButton();

    themeToggle.addEventListener("click", () => {
      document.body.classList.toggle("light");

      try {
        localStorage.setItem(
          "portfolio-theme",
          document.body.classList.contains("light") ? "light" : "dark"
        );
      } catch (error) {
        // Theme switching remains functional without saved preferences.
      }

      updateThemeButton();
    });


    // =========================
    // 4. PROJECT FILTERS
    // =========================

    const filterButtons = document.querySelectorAll(".filter-button");
    const projectCards = document.querySelectorAll(".project-card");
    const emptyState = document.getElementById("emptyState");

    filterButtons.forEach((button) => {
      button.addEventListener("click", () => {
        const selectedFilter = button.dataset.filter;
        let visibleCount = 0;

        // Update the selected filter button.
        filterButtons.forEach((item) => {
          const isActive = item === button;

          item.classList.toggle("active", isActive);
          item.setAttribute("aria-pressed", String(isActive));
        });

        // Show only projects matching the selected category.
        projectCards.forEach((card) => {
          const matches =
            selectedFilter === "all" ||
            card.dataset.category === selectedFilter;

          card.hidden = !matches;

          if (matches) {
            visibleCount++;
          }
        });

        emptyState.style.display =
          visibleCount === 0 ? "block" : "none";
      });
    });


    // =========================
    // 5. SCROLL REVEAL EFFECT
    // =========================

    const revealElements = document.querySelectorAll(".reveal");

    // Provide a fallback for browsers without IntersectionObserver.
    if ("IntersectionObserver" in window) {
      const observer = new IntersectionObserver(
        (entries, currentObserver) => {
          entries.forEach((entry) => {
            if (entry.isIntersecting) {
              entry.target.classList.add("visible");
              currentObserver.unobserve(entry.target);
            }
          });
        },
        {
          threshold: 0.12
        }
      );

      revealElements.forEach((element) => {
        observer.observe(element);
      });
    } else {
      revealElements.forEach((element) => {
        element.classList.add("visible");
      });
    }
  </script>
</body>
</html>
