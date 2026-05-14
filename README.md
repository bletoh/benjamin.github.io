<html lang="nl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1" />
  <title>Benjamin Hashi — Sport & Boekverslagen</title>

  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet" />

  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

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

    html, body {
      width: 100%;
      overflow-x: hidden;
    }

    body {
      font-family: 'DM Sans', sans-serif;
      background: var(--bg);
      color: var(--text);
      font-size: 16px;
      line-height: 1.7;
    }

    a { color: inherit; text-decoration: none; }

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
      justify-content: space-between;
      height: 64px;
    }

    .logo {
      font-family: 'Playfair Display', serif;
      font-size: 22px;
      font-weight: 600;
    }

    .logo span { color: var(--accent); }

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
      padding: 4rem 2rem;
      text-align: center;
    }

    .hero h1 {
      font-family: 'Playfair Display', serif;
      font-size: 3rem;
      margin-bottom: 1rem;
    }

    .hero p {
      color: var(--muted);
      max-width: 520px;
      margin: 0 auto;
    }

    /* LAYOUT */
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
      display: grid;
      grid-template-columns: 1fr 1fr;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 16px;
      overflow: hidden;
      cursor: pointer;
      margin-bottom: 3rem;
    }

    .featured-visual {
      background: linear-gradient(135deg, #2D6A4F, #1B4332);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 60px;
    }

    .featured-body {
      padding: 2rem;
    }

    /* GRID */
    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
      gap: 16px;
    }

    .card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 14px;
      cursor: pointer;
      transition: 0.2s;
    }

    .card:hover {
      transform: translateY(-3px);
    }

    .card-thumb {
      height: 110px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 40px;
    }

    .thumb-sport { background: linear-gradient(135deg,#d4f0e4,#a8dfc6); }
    .thumb-boek { background: linear-gradient(135deg,#e4e0f8,#c8c0f0); }

    .card-body {
      padding: 1rem;
    }

    /* TAGS */
    .tag {
      font-size: 11px;
      padding: 4px 10px;
      border-radius: 20px;
      display: inline-block;
      margin-bottom: 10px;
    }

    .tag-sport { background: var(--tag-sport-bg); color: var(--tag-sport-color); }
    .tag-boek { background: var(--tag-boek-bg); color: var(--tag-boek-color); }

    /* MOBILE APP STYLE */
    @media (max-width: 640px) {

      .header-inner {
        padding: 0 1rem;
      }

      .hero {
        padding: 2.5rem 1rem;
      }

      .hero h1 {
        font-size: 28px;
      }

      .container {
        padding: 1.2rem 1rem;
      }

      .featured {
        grid-template-columns: 1fr;
        border-radius: 18px;
      }

      .grid {
        grid-template-columns: 1fr;
        gap: 12px;
      }

      nav a {
        padding: 8px 12px;
        border-radius: 999px;
        background: rgba(0,0,0,0.04);
      }

      nav a.active {
        background: var(--text);
        color: white;
      }
    }

  </style>
</head>

<body>

<header>
  <div class="header-inner">
    <div class="logo">BH</div>
    <nav>
      <a href="#" class="active" onclick="showAll(event)">Alles</a>
      <a href="#" onclick="filterPosts(event,'sport')">Sport</a>
      <a href="#" onclick="filterPosts(event,'boek')">Boek</a>
    </nav>
  </div>
</header>

<section class="hero">
  <h1>Sport & Boekverslagen</h1>
  <p>Mijn ervaringen met trainen en lezen</p>
</section>

<main class="container">

  <div class="section-header">
    <span class="section-label">Uitgelicht</span>
    <div class="section-line"></div>
  </div>

  <article class="featured" onclick="openPost('achilles')">
    <div class="featured-visual">🏃</div>
    <div class="featured-body">
      <span class="tag tag-sport">Sport</span>
      <h2>Achillesblessure verhaal</h2>
    </div>
  </article>

  <div class="section-header">
    <span class="section-label">Posts</span>
    <div class="section-line"></div>
  </div>

  <div class="grid" id="post-grid">

    <article class="card" data-type="sport" onclick="openPost('wfl')">
      <div class="card-thumb thumb-sport">💪</div>
      <div class="card-body">
        <span class="tag tag-sport">Sport</span>
        <h3>WFL Run</h3>
      </div>
    </article>

    <article class="card" data-type="boek" onclick="openPost('camus')">
      <div class="card-thumb thumb-boek">📖</div>
      <div class="card-body">
        <span class="tag tag-boek">Boek</span>
        <h3>The Stranger</h3>
      </div>
    </article>

  </div>

</main>

<script>
function openPost(id){ alert("Post: " + id); }
function filterPosts(e,type){
  e.preventDefault();
  document.querySelectorAll(".card").forEach(c=>{
    c.style.display = c.dataset.type===type ? "block":"none";
  });
}
function showAll(e){
  e.preventDefault();
  document.querySelectorAll(".card").forEach(c=>{
    c.style.display="block";
  });
}
</script>

</body>
</html>
