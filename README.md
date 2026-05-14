<html lang="nl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <title>Benjamin Hashi — Sport & Boekverslagen</title>

  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet" />

  <style>
    *, *::before, *::after {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    :root {
      --bg: #F7F5F0;
      --surface: #FFFFFF;
      --text: #1A1A18;
      --muted: #7A7870;
      --border: #E2DED6;
      --accent: #2D6A4F;

      --tag-sport-bg: #E1F5EE;
      --tag-sport-color: #0F6E56;

      --tag-boek-bg: #EEEDFE;
      --tag-boek-color: #3C3489;
    }

    body {
      font-family: 'DM Sans', sans-serif;
      background: var(--bg);
      color: var(--text);
      font-size: 16px;
      line-height: 1.7;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    /* HEADER */

    header {
      background: var(--surface);
      border-bottom: 1px solid var(--border);
      position: sticky;
      top: 0;
      z-index: 100;
    }

    .header-inner {
      max-width: 860px;
      margin: 0 auto;
      padding: 0 2rem;

      display: flex;
      align-items: center;
      justify-content: flex-start;
      gap: 2rem;

      height: 64px;
    }

    .logo {
      font-family: 'Playfair Display', serif;
      font-size: 22px;
      font-weight: 600;
      letter-spacing: -0.3px;
    }

    .logo span {
      color: var(--accent);
    }

    nav {
      display: flex;
      gap: 8px;
    }

    nav a {
      font-size: 14px;
      color: var(--muted);
      padding: 6px 14px;
      border-radius: 20px;
      transition: 0.15s;
    }

    nav a:hover,
    nav a.active {
      background: var(--bg);
      color: var(--text);
    }

    /* HERO */

    .hero {
      background: var(--surface);
      border-bottom: 1px solid var(--border);
    }

    .hero-inner {
      max-width: 860px;
      margin: 0 auto;
      padding: 4rem 2rem 3.5rem;
      text-align: center;
    }

    .hero-eyebrow {
      font-size: 12px;
      font-weight: 500;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: var(--accent);
      margin-bottom: 1rem;
    }

    .hero h1 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2rem, 5vw, 3.2rem);
      line-height: 1.2;
      margin-bottom: 1rem;
      letter-spacing: -0.5px;
    }

    .hero p {
      font-size: 17px;
      color: var(--muted);
      max-width: 520px;
      margin: 0 auto;
      font-weight: 300;
    }

    /* MAIN LAYOUT */

    .container {
      max-width: 860px;
      margin: 0 auto;
      padding: 3rem 2rem;
    }

    .section-header {
      display: flex;
      align-items: center;
      gap: 12px;
      margin-bottom: 1.5rem;
    }

    .section-label {
      font-size: 11px;
      font-weight: 500;
      letter-spacing: 2px;
      text-transform: uppercase;
      color: var(--muted);
    }

    .section-line {
      flex: 1;
      height: 1px;
      background: var(--border);
    }

    /* FEATURED */

    .featured {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 16px;
      overflow: hidden;
      margin-bottom: 3rem;

      display: grid;
      grid-template-columns: 1fr 1fr;

      cursor: pointer;
      transition: 0.2s;
    }

    .featured:hover {
      box-shadow: 0 8px 24px rgba(0,0,0,0.07);
    }

    .featured-visual {
      background: linear-gradient(135deg, #2D6A4F 0%, #1B4332 100%);
      min-height: 280px;

      display: flex;
      align-items: center;
      justify-content: center;

      position: relative;
      overflow: hidden;
    }

    .featured-visual::before {
      content: '';
      position: absolute;
      width: 200px;
      height: 200px;
      border: 40px solid rgba(255,255,255,0.06);
      border-radius: 50%;
      top: -40px;
      left: -40px;
    }

    .featured-visual::after {
      content: '';
      position: absolute;
      width: 160px;
      height: 160px;
      border: 30px solid rgba(255,255,255,0.04);
      border-radius: 50%;
      bottom: -30px;
      right: -30px;
    }

    .featured-icon {
      font-size: 64px;
      position: relative;
      z-index: 1;
    }

    .featured-body {
      padding: 2rem;

      display: flex;
      flex-direction: column;
      justify-content: center;
    }

    .featured-body h2 {
      font-family: 'Playfair Display', serif;
      font-size: 24px;
      line-height: 1.3;
      margin-bottom: 10px;
    }

    .featured-body p {
      font-size: 15px;
      color: var(--muted);
      margin-bottom: 1.5rem;
      font-weight: 300;
    }

    /* TAGS */

    .tag {
      display: inline-block;
      font-size: 11px;
      padding: 4px 12px;
      border-radius: 20px;
      margin-bottom: 12px;
    }

    .tag-sport {
      background: var(--tag-sport-bg);
      color: var(--tag-sport-color);
    }

    .tag-boek {
      background: var(--tag-boek-bg);
      color: var(--tag-boek-color);
    }

    .post-meta {
      font-size: 12px;
      color: var(--muted);
      margin-bottom: 1.25rem;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      gap: 6px;

      width: fit-content;

      padding: 10px 20px;

      border-radius: 8px;
      border: 1px solid var(--border);

      background: var(--bg);
    }

    /* GRID */

    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
      gap: 16px;
      margin-bottom: 3rem;
    }

    .card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 14px;
      overflow: hidden;
    }

    .card-thumb {
      height: 110px;

      display: flex;
      align-items: center;
      justify-content: center;

      font-size: 40px;
    }

    .thumb-sport {
      background: linear-gradient(135deg, #d4f0e4, #a8dfc6);
    }

    .thumb-boek {
      background: linear-gradient(135deg, #e4e0f8, #c8c0f0);
    }

    .card-body {
      padding: 1.1rem 1.25rem 1.25rem;
    }

    .card-body h3 {
      font-family: 'Playfair Display', serif;
      font-size: 16px;
      margin-bottom: 6px;
    }

    .card-body p {
      font-size: 13px;
      color: var(--muted);
      margin-bottom: 12px;
    }

    /* FOOTER */

    footer {
      border-top: 1px solid var(--border);
      text-align: center;
      padding: 2rem;
      font-size: 13px;
      color: var(--muted);
    }

    /* MOBILE */

    @media (max-width: 640px) {

      .header-inner {
        padding: 0 1rem;
        gap: 1rem;
      }

      .container {
        padding: 2rem 1rem;
      }

      .hero-inner {
        padding: 3rem 1rem;
      }

      .featured {
        grid-template-columns: 1fr;
      }

      .featured-visual {
        min-height: 180px;
      }

      nav a {
        padding: 6px 10px;
      }
    }
  </style>
</head>

<body>

  <header>
    <div class="header-inner">

      <div class="logo">
        Benjamin<span>Hashi</span>
      </div>

      <nav>
        <a href="#" class="active">Alles</a>
        <a href="#">Sport</a>
        <a href="#">Boekverslagen</a>
      </nav>

    </div>
  </header>

  <section class="hero">

    <div class="hero-inner">

      <div class="hero-eyebrow">
        Persoonlijke blog
      </div>

      <h1>
        Sport & Boekverslagen
      </h1>

      <p>
        Mijn ervaringen met trainen en lezen
      </p>

    </div>

  </section>

  <main class="container">

    <div class="section-header">
      <span class="section-label">Uitgelicht</span>
      <div class="section-line"></div>
    </div>

    <article class="featured">

      <div class="featured-visual">
        <div class="featured-icon">🏃</div>
      </div>

      <div class="featured-body">

        <span class="tag tag-sport">Sport</span>

        <h2>
          Terugkomend van een achillesblessure
        </h2>

        <p>
          Het hele verhaal achter mijn blessure en hoe ik hiermee om ben gegaan.
        </p>

        <div class="post-meta">
          12 mei 2026 · 5 min lezen
        </div>

        <span class="btn">
          Lees verder →
        </span>

      </div>

    </article>

    <div class="section-header">
      <span class="section-label">Recente posts</span>
      <div class="section-line"></div>
    </div>

    <div class="grid">

      <article class="card">

        <div class="card-thumb thumb-sport">
          💪
        </div>

        <div class="card-body">

          <span class="tag tag-sport">
            Sport
          </span>

          <h3>
            Wings For Life
          </h3>

          <p>
            Wedstrijdverslag van de WFL World Run
          </p>

          <div class="post-meta">
            10 mei 2026 · 4 min lezen
          </div>

        </div>

      </article>

      <article class="card">

        <div class="card-thumb thumb-boek">
          📖
        </div>

        <div class="card-body">

          <span class="tag tag-boek">
            Boekverslag
          </span>

          <h3>
            The Stranger — Albert Camus
          </h3>

          <p>
            Mijn kijk op absurdisme
          </p>

          <div class="post-meta">
            3 mei 2026 · 6 min lezen
          </div>

        </div>

      </article>

    </div>

  </main>

  <footer>
    © 2026 Benjamin Hashi
  </footer>

</body>
</html>
