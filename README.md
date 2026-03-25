# barbaracrocha.github.io

<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Barbara Rocha — Portfolio</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Mono:wght@300;400;500&family=Syne:wght@400;600;800&display=swap" rel="stylesheet" />
  <style>
    :root {
      --bg: #0a0a0a;
      --surface: #111111;
      --border: #1e1e1e;
      --accent: #c8f563;
      --accent-dim: #8fad3a;
      --text: #e8e8e8;
      --muted: #666;
      --white: #f5f5f5;
    }

    *, *::before, *::after {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'DM Mono', monospace;
      font-size: 14px;
      line-height: 1.7;
      overflow-x: hidden;
    }

    /* NOISE OVERLAY */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
      pointer-events: none;
      z-index: 9999;
      opacity: 0.5;
    }

    /* LAYOUT */
    .container {
      max-width: 900px;
      margin: 0 auto;
      padding: 0 32px;
    }

    /* NAV */
    nav {
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      z-index: 100;
      padding: 20px 32px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      border-bottom: 1px solid var(--border);
      background: rgba(10, 10, 10, 0.85);
      backdrop-filter: blur(12px);
    }

    .nav-logo {
      font-family: 'Syne', sans-serif;
      font-weight: 800;
      font-size: 15px;
      color: var(--accent);
      letter-spacing: 0.08em;
      text-decoration: none;
    }

    .nav-links {
      display: flex;
      gap: 28px;
      list-style: none;
    }

    .nav-links a {
      color: var(--muted);
      text-decoration: none;
      font-size: 12px;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      transition: color 0.2s;
    }

    .nav-links a:hover {
      color: var(--accent);
    }

    /* HERO */
    .hero {
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
      padding: 0 32px 80px;
      max-width: 900px;
      margin: 0 auto;
      position: relative;
    }

    .hero-tag {
      font-size: 11px;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 24px;
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .hero-tag::before {
      content: '';
      display: block;
      width: 32px;
      height: 1px;
      background: var(--accent);
    }

    .hero-title {
      font-family: 'DM Serif Display', serif;
      font-size: clamp(52px, 8vw, 96px);
      line-height: 1.0;
      color: var(--white);
      margin-bottom: 32px;
      font-weight: 400;
    }

    .hero-title em {
      font-style: italic;
      color: var(--accent);
    }

    .hero-desc {
      max-width: 520px;
      color: var(--muted);
      font-size: 13px;
      line-height: 1.9;
      margin-bottom: 48px;
    }

    .hero-cta {
      display: flex;
      align-items: center;
      gap: 24px;
      flex-wrap: wrap;
    }

    .btn-primary {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      background: var(--accent);
      color: #0a0a0a;
      padding: 14px 28px;
      text-decoration: none;
      font-family: 'Syne', sans-serif;
      font-weight: 600;
      font-size: 12px;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      transition: background 0.2s, transform 0.15s;
    }

    .btn-primary:hover {
      background: var(--accent-dim);
      transform: translateY(-2px);
    }

    .btn-ghost {
      display: inline-flex;
      align-items: center;
      gap: 10px;
      color: var(--muted);
      text-decoration: none;
      font-size: 12px;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      border-bottom: 1px solid var(--border);
      padding-bottom: 4px;
      transition: color 0.2s, border-color 0.2s;
    }

    .btn-ghost:hover {
      color: var(--white);
      border-color: var(--white);
    }

    .hero-number {
      position: absolute;
      right: 32px;
      top: 50%;
      transform: translateY(-50%);
      font-family: 'DM Serif Display', serif;
      font-size: clamp(160px, 22vw, 260px);
      color: transparent;
      -webkit-text-stroke: 1px var(--border);
      line-height: 1;
      user-select: none;
      pointer-events: none;
    }

    /* SECTION */
    section {
      padding: 100px 0;
      border-top: 1px solid var(--border);
    }

    .section-label {
      font-size: 10px;
      letter-spacing: 0.25em;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 48px;
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .section-label::after {
      content: '';
      flex: 1;
      height: 1px;
      background: var(--border);
    }

    .section-title {
      font-family: 'DM Serif Display', serif;
      font-size: clamp(32px, 4vw, 52px);
      color: var(--white);
      font-weight: 400;
      line-height: 1.1;
      margin-bottom: 32px;
    }

    /* ABOUT */
    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 64px;
      align-items: start;
    }

    .about-text {
      color: var(--muted);
      font-size: 13px;
      line-height: 2;
    }

    .about-text p + p {
      margin-top: 20px;
    }

    .stack-list {
      display: flex;
      flex-direction: column;
      gap: 8px;
    }

    .stack-item {
      display: flex;
      align-items: center;
      gap: 12px;
      padding: 12px 16px;
      border: 1px solid var(--border);
      transition: border-color 0.2s;
    }

    .stack-item:hover {
      border-color: var(--accent);
    }

    .stack-dot {
      width: 6px;
      height: 6px;
      background: var(--accent);
      border-radius: 50%;
      flex-shrink: 0;
    }

    .stack-name {
      color: var(--text);
      font-size: 12px;
      letter-spacing: 0.05em;
    }

    .stack-level {
      margin-left: auto;
      font-size: 10px;
      color: var(--muted);
      letter-spacing: 0.1em;
      text-transform: uppercase;
    }

    /* PROJECTS */
    .projects-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1px;
      background: var(--border);
    }

    .project-card {
      background: var(--bg);
      padding: 40px 36px;
      text-decoration: none;
      display: block;
      transition: background 0.2s;
      position: relative;
      overflow: hidden;
    }

    .project-card::after {
      content: '';
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      height: 2px;
      background: var(--accent);
      transform: scaleX(0);
      transform-origin: left;
      transition: transform 0.3s ease;
    }

    .project-card:hover {
      background: var(--surface);
    }

    .project-card:hover::after {
      transform: scaleX(1);
    }

    .project-index {
      font-size: 10px;
      color: var(--accent);
      letter-spacing: 0.2em;
      margin-bottom: 20px;
      font-family: 'Syne', sans-serif;
    }

    .project-name {
      font-family: 'DM Serif Display', serif;
      font-size: 22px;
      color: var(--white);
      margin-bottom: 12px;
      font-weight: 400;
    }

    .project-desc {
      font-size: 12px;
      color: var(--muted);
      line-height: 1.8;
      margin-bottom: 24px;
    }

    .project-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
    }

    .tag {
      font-size: 10px;
      color: var(--accent);
      border: 1px solid var(--accent);
      padding: 3px 10px;
      letter-spacing: 0.1em;
      text-transform: uppercase;
    }

    /* CONTACT */
    .contact-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 1px;
      background: var(--border);
      margin-top: 48px;
    }

    .contact-item {
      background: var(--bg);
      padding: 28px 32px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      text-decoration: none;
      transition: background 0.2s;
    }

    .contact-item:hover {
      background: var(--surface);
    }

    .contact-label {
      font-size: 10px;
      text-transform: uppercase;
      letter-spacing: 0.15em;
      color: var(--muted);
      margin-bottom: 4px;
    }

    .contact-value {
      font-family: 'Syne', sans-serif;
      font-size: 14px;
      font-weight: 600;
      color: var(--white);
    }

    .contact-arrow {
      color: var(--accent);
      font-size: 18px;
      transition: transform 0.2s;
    }

    .contact-item:hover .contact-arrow {
      transform: translate(4px, -4px);
    }

    /* FOOTER */
    footer {
      border-top: 1px solid var(--border);
      padding: 32px 0;
    }

    .footer-inner {
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .footer-copy {
      font-size: 11px;
      color: var(--muted);
    }

    .footer-tag {
      font-size: 11px;
      color: var(--muted);
    }

    .footer-tag span {
      color: var(--accent);
    }

    /* ANIMATIONS */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(24px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    .hero-tag   { animation: fadeUp 0.6s ease both; animation-delay: 0.1s; }
    .hero-title { animation: fadeUp 0.6s ease both; animation-delay: 0.2s; }
    .hero-desc  { animation: fadeUp 0.6s ease both; animation-delay: 0.35s; }
    .hero-cta   { animation: fadeUp 0.6s ease both; animation-delay: 0.5s; }

    /* RESPONSIVE */
    @media (max-width: 640px) {
      nav { padding: 16px 20px; }
      .container, .hero { padding-left: 20px; padding-right: 20px; }

      .hero-number { display: none; }

      .about-grid,
      .projects-grid,
      .contact-grid {
        grid-template-columns: 1fr;
      }

      .nav-links { display: none; }
    }
  </style>
</head>
<body>

  <nav>
    <a class="nav-logo" href="#">BR</a>
    <ul class="nav-links">
      <li><a href="#sobre">Sobre</a></li>
      <li><a href="#projetos">Projetos</a></li>
      <li><a href="#contato">Contato</a></li>
    </ul>
  </nav>

  <!-- HERO -->
  <div class="hero">
    <div class="hero-number">01</div>
    <div class="hero-tag">Developer & Builder</div>
    <h1 class="hero-title">
      Barbara<br />
      <em>Rocha</em>
    </h1>
    <p class="hero-desc">
      Desenvolvedora em formacao, apaixonada por automacoes, integracao de APIs e construcao de produtos digitais.
      Porto Alegre — RS.
    </p>
    <div class="hero-cta">
      <a class="btn-primary" href="#projetos">Ver projetos &rarr;</a>
      <a class="btn-ghost" href="#contato">Entrar em contato</a>
    </div>
  </div>

  <!-- SOBRE -->
  <section id="sobre">
    <div class="container">
      <div class="section-label">Sobre</div>
      <div class="about-grid">
        <div>
          <h2 class="section-title">Tecnologia<br /><em style="font-style:italic; color: var(--accent)">como ferramenta</em></h2>
          <div class="about-text">
            <p>
              Passei por varias areas antes de entrar de vez no mundo da programacao. Hoje, foco em automacoes, integracoes de sistemas e desenvolvimento web.
            </p>
            <p>
              Trabalho com ferramentas como n8n, APIs REST, Node.js e estou sempre construindo coisas novas pelos meus projetos — Mapeiatech e Ads Nexus.
            </p>
            <p>
              Acredito em aprender fazendo, documentar bem e construir com intencao.
            </p>
          </div>
        </div>
        <div>
          <div class="stack-list">
            <div class="stack-item">
              <div class="stack-dot"></div>
              <span class="stack-name">JavaScript / Node.js</span>
              <span class="stack-level">Em uso</span>
            </div>
            <div class="stack-item">
              <div class="stack-dot"></div>
              <span class="stack-name">n8n Workflows</span>
              <span class="stack-level">Em uso</span>
            </div>
            <div class="stack-item">
              <div class="stack-dot"></div>
              <span class="stack-name">REST APIs & Auth</span>
              <span class="stack-level">Em uso</span>
            </div>
            <div class="stack-item">
              <div class="stack-dot"></div>
              <span class="stack-name">React / TypeScript</span>
              <span class="stack-level">Aprendendo</span>
            </div>
            <div class="stack-item">
              <div class="stack-dot"></div>
              <span class="stack-name">HTML / CSS</span>
              <span class="stack-level">Em uso</span>
            </div>
            <div class="stack-item">
              <div class="stack-dot"></div>
              <span class="stack-name">Tuya IoT / Smart Home</span>
              <span class="stack-level">Em uso</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- PROJETOS -->
  <section id="projetos">
    <div class="container">
      <div class="section-label">Projetos</div>
      <h2 class="section-title">O que estou<br /><em style="font-style:italic; color: var(--accent)">construindo</em></h2>
    </div>
    <div class="container" style="padding-top: 40px;">
      <div class="projects-grid">
        <a class="project-card" href="https://mapeiatech.co" target="_blank" rel="noopener">
          <div class="project-index">01</div>
          <div class="project-name">Mapeiatech</div>
          <p class="project-desc">
            Plataforma de tecnologia para negocios. Automacoes, integraces e solucoes digitais sob medida.
          </p>
          <div class="project-tags">
            <span class="tag">Web</span>
            <span class="tag">Automacao</span>
            <span class="tag">SaaS</span>
          </div>
        </a>
        <a class="project-card" href="https://adsnexus.com.br" target="_blank" rel="noopener">
          <div class="project-index">02</div>
          <div class="project-name">Ads Nexus</div>
          <p class="project-desc">
            Plataforma voltada para gestao e performance de anuncios digitais.
          </p>
          <div class="project-tags">
            <span class="tag">Marketing</span>
            <span class="tag">Ads</span>
            <span class="tag">Performance</span>
          </div>
        </a>
        <a class="project-card" href="https://github.com/barbs-rocha" target="_blank" rel="noopener">
          <div class="project-index">03</div>
          <div class="project-name">Tuya IoT Integration</div>
          <p class="project-desc">
            Integracao de fechaduras inteligentes via API Tuya com n8n — autenticacao OAuth, HMAC-SHA256 e geracao de senhas temporarias.
          </p>
          <div class="project-tags">
            <span class="tag">n8n</span>
            <span class="tag">IoT</span>
            <span class="tag">API</span>
          </div>
        </a>
        <a class="project-card" href="https://github.com/barbs-rocha" target="_blank" rel="noopener">
          <div class="project-index">04</div>
          <div class="project-name">Github — em construcao</div>
          <p class="project-desc">
            Mais projetos em desenvolvimento. Acompanhe o repositorio para novidades.
          </p>
          <div class="project-tags">
            <span class="tag">Em breve</span>
          </div>
        </a>
      </div>
    </div>
  </section>

  <!-- CONTATO -->
  <section id="contato">
    <div class="container">
      <div class="section-label">Contato</div>
      <h2 class="section-title">Vamos<br /><em style="font-style:italic; color: var(--accent)">conversar</em></h2>
      <p style="color: var(--muted); font-size: 13px; max-width: 420px; line-height: 1.9; margin-top: 8px;">
        Aberta a projetos, parcerias e trocas de conhecimento.
      </p>
      <div class="contact-grid">
        <a class="contact-item" href="https://wa.me/5548991201765" target="_blank" rel="noopener">
          <div>
            <div class="contact-label">WhatsApp</div>
            <div class="contact-value">+55 48 99120-1765</div>
          </div>
          <span class="contact-arrow">&nearr;</span>
        </a>
        <a class="contact-item" href="https://www.instagram.com/_barbarac.rocha/" target="_blank" rel="noopener">
          <div>
            <div class="contact-label">Instagram</div>
            <div class="contact-value">@_barbarac.rocha</div>
          </div>
          <span class="contact-arrow">&nearr;</span>
        </a>
        <a class="contact-item" href="https://mapeiatech.co" target="_blank" rel="noopener">
          <div>
            <div class="contact-label">Site</div>
            <div class="contact-value">mapeiatech.co</div>
          </div>
          <span class="contact-arrow">&nearr;</span>
        </a>
        <a class="contact-item" href="https://adsnexus.com.br" target="_blank" rel="noopener">
          <div>
            <div class="contact-label">Site</div>
            <div class="contact-value">adsnexus.com.br</div>
          </div>
          <span class="contact-arrow">&nearr;</span>
        </a>
        <a class="contact-item" href="https://github.com/barbs-rocha" target="_blank" rel="noopener" style="grid-column: 1 / -1;">
          <div>
            <div class="contact-label">GitHub</div>
            <div class="contact-value">github.com/barbs-rocha</div>
          </div>
          <span class="contact-arrow">&nearr;</span>
        </a>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    <div class="container">
      <div class="footer-inner">
        <span class="footer-copy">&copy; 2026 Barbara Rocha</span>
        <span class="footer-tag">Porto Alegre, RS — <span>BR</span></span>
      </div>
    </div>
  </footer>

</body>
</html>
