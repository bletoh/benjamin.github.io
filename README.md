<html lang="nl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0" />
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

    body { font-family: 'DM Sans', sans-serif; background: var(--bg); color: var(--text); font-size: 16px; line-height: 1.7; }
    a { color: inherit; text-decoration: none; }

    /* Header — floating pill */
    header {
      position: fixed;
      top: 16px;
      left: 50%;
      transform: translateX(-50%);
      z-index: 100;
      background: transparent;
      border: none;
      pointer-events: none;
    }
    .header-inner {
      pointer-events: auto;
    }
    nav {
      display: flex;
      gap: 2px;
      background: rgba(255,255,255,0.92);
      backdrop-filter: blur(12px);
      -webkit-backdrop-filter: blur(12px);
      border: 1px solid var(--border);
      border-radius: 999px;
      padding: 4px;
      box-shadow: 0 4px 20px rgba(0,0,0,0.10);
    }
    nav a {
      font-size: 13px;
      font-weight: 500;
      color: var(--muted);
      padding: 6px 16px;
      border-radius: 999px;
      transition: background 0.15s, color 0.15s;
      white-space: nowrap;
    }
    nav a:hover, nav a.active {
      background: var(--text);
      color: #fff;
    }


    /* Layout */
    .container { max-width: 860px; margin: 0 auto; padding: 2rem 1rem; }
    .section-header { display: flex; align-items: center; gap: 12px; margin-bottom: 1.25rem; }
    .section-label { font-size: 11px; font-weight: 500; letter-spacing: 2px; text-transform: uppercase; color: var(--muted); white-space: nowrap; }
    .section-line { flex: 1; height: 1px; background: var(--border); }

    /* Featured */
    .featured {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: 16px;
      overflow: hidden;
      margin-bottom: 2rem;
      display: grid;
      grid-template-columns: 1fr 1fr;
      cursor: pointer;
      transition: box-shadow 0.2s;
    }
    .featured:hover { box-shadow: 0 8px 24px rgba(0,0,0,0.07); }
    .featured-visual {
      background: linear-gradient(135deg, #2D6A4F 0%, #1B4332 100%);
      min-height: 220px;
      display: flex;
      align-items: center;
      justify-content: center;
      position: relative;
      overflow: hidden;
    }
    .featured-visual::before {
      content: '';
      position: absolute;
      width: 200px; height: 200px;
      border: 40px solid rgba(255,255,255,0.06);
      border-radius: 50%;
      top: -40px; left: -40px;
    }
    .featured-visual::after {
      content: '';
      position: absolute;
      width: 160px; height: 160px;
      border: 30px solid rgba(255,255,255,0.04);
      border-radius: 50%;
      bottom: -30px; right: -30px;
    }
    .featured-icon { font-size: 56px; position: relative; z-index: 1; }
    .featured-body {
      padding: 1.5rem;
      display: flex;
      flex-direction: column;
      justify-content: center;
    }
    .featured-body h2 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(16px, 3vw, 22px);
      font-weight: 600;
      line-height: 1.3;
      margin-bottom: 8px;
      letter-spacing: -0.3px;
    }
    .featured-body p {
      font-size: 14px;
      color: var(--muted);
      font-weight: 300;
      margin-bottom: 1.25rem;
      line-height: 1.6;
    }

    /* Tags */
    .tag { display: inline-block; font-size: 11px; font-weight: 500; letter-spacing: 0.5px; padding: 4px 12px; border-radius: 20px; margin-bottom: 10px; }
    .tag-sport { background: var(--tag-sport-bg); color: var(--tag-sport-color); }
    .tag-boek  { background: var(--tag-boek-bg);  color: var(--tag-boek-color); }
    .post-meta { font-size: 12px; color: var(--muted); margin-bottom: 1rem; }
    .btn { display: inline-flex; align-items: center; gap: 6px; font-size: 14px; font-weight: 500; padding: 9px 18px; border-radius: 8px; border: 1px solid var(--border); background: var(--bg); color: var(--text); cursor: pointer; transition: background 0.15s; width: fit-content; }
    .btn:hover { background: var(--border); }

    /* Grid */
    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
      gap: 14px;
      margin-bottom: 2rem;
    }
    .card { background: var(--surface); border: 1px solid var(--border); border-radius: 14px; overflow: hidden; transition: transform 0.2s, box-shadow 0.2s; cursor: pointer; }
    .card:hover { transform: translateY(-3px); box-shadow: 0 8px 24px rgba(0,0,0,0.07); }
    .card-thumb { height: 100px; display: flex; align-items: center; justify-content: center; font-size: 38px; }
    .thumb-sport { background: linear-gradient(135deg, #d4f0e4, #a8dfc6); }
    .thumb-boek  { background: linear-gradient(135deg, #e4e0f8, #c8c0f0); }
    .card-body { padding: 1rem 1.1rem 1.1rem; }
    .card-body h3 { font-family: 'Playfair Display', serif; font-size: 15px; font-weight: 600; line-height: 1.35; margin-bottom: 5px; }
    .card-body p { font-size: 13px; color: var(--muted); font-weight: 300; line-height: 1.55; margin-bottom: 10px; }

    /* Post detail */
    .post-detail { display: none; background: var(--surface); border: 1px solid var(--border); border-radius: 16px; padding: 1.75rem; margin-bottom: 2rem; animation: fadeIn 0.25s ease; }
    @keyframes fadeIn { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: none; } }
    .post-detail.open { display: block; }
    .back-btn { font-size: 13px; color: var(--muted); cursor: pointer; margin-bottom: 1.5rem; display: inline-flex; align-items: center; gap: 6px; }
    .back-btn:hover { color: var(--text); }
    .post-detail h2 { font-family: 'Playfair Display', serif; font-size: clamp(20px, 5vw, 28px); font-weight: 600; line-height: 1.2; margin-bottom: 8px; letter-spacing: -0.4px; }
    .post-detail .body { margin-top: 1.25rem; }
    .post-detail .body h3 { font-size: 16px; font-weight: 500; margin: 1.5rem 0 0.5rem; }
    .post-detail .body p { font-size: 15px; line-height: 1.75; margin-bottom: 1rem; color: #3a3a36; }
    .post-detail .body ul { padding-left: 1.25rem; margin-bottom: 1rem; }
    .post-detail .body li { font-size: 15px; line-height: 1.7; color: #3a3a36; margin-bottom: 4px; }

    /* Table */
    .schedule-table { width: 100%; border-collapse: collapse; margin: 1rem 0 1.5rem; font-size: 14px; }
    .schedule-table th { background: var(--bg); text-align: left; padding: 8px 10px; font-weight: 500; border-bottom: 1px solid var(--border); }
    .schedule-table td { padding: 8px 10px; border-bottom: 1px solid var(--border); color: #3a3a36; }
    .schedule-table tr:last-child td { border-bottom: none; }

    /* About */
    .about-strip { background: var(--surface); border: 1px solid var(--border); border-radius: 14px; padding: 1.5rem; display: flex; align-items: center; gap: 1.25rem; margin-bottom: 1.5rem; }
    .avatar { width: 52px; height: 52px; border-radius: 50%; background: linear-gradient(135deg, #2D6A4F, #4A3580); display: flex; align-items: center; justify-content: center; font-size: 22px; flex-shrink: 0; }
    .about-strip p { font-size: 14px; color: var(--muted); font-weight: 300; line-height: 1.6; }
    .about-strip strong { color: var(--text); font-weight: 500; }

    /* Footer */
    footer { border-top: 1px solid var(--border); text-align: center; padding: 1.5rem; font-size: 13px; color: var(--muted); }

    /* ── Mobile ── */
    @media (max-width: 600px) {
      /* Featured: stack vertically on mobile */
      .featured {
        grid-template-columns: 1fr;
      }
      .featured-visual {
        min-height: 140px;
      }
      .featured-icon {
        font-size: 48px;
      }
      .featured-body {
        padding: 1.25rem;
      }
      .featured-body p {
        display: none; /* keep card compact on mobile */
      }

      /* Grid: single column on small screens */
      .grid {
        grid-template-columns: 1fr;
      }

      /* About strip: stack on very small */
      .about-strip {
        flex-direction: column;
        text-align: center;
        gap: 0.75rem;
      }

      /* Table scroll on mobile */
      .schedule-table-wrap {
        overflow-x: auto;
        -webkit-overflow-scrolling: touch;
      }

      .post-detail {
        padding: 1.25rem;
        border-radius: 12px;
      }
    }
  </style>
</head>
<body>

<header>
  <div class="header-inner">
    <nav>
      <a href="#" class="active" onclick="showAll(event)">Alles</a>
      <a href="#" onclick="filterPosts(event, 'sport')">Sport</a>
      <a href="#" onclick="filterPosts(event, 'boek')">Boekverslagen</a>
    </nav>
  </div>
</header>


<main class="container">

  <div class="post-detail" id="post-detail">
    <span class="back-btn" onclick="closePost()">← Terug naar overzicht</span>
    <div id="post-content"></div>
  </div>

  <div id="overview">

    <div class="section-header">
      <span class="section-label">Uitgelicht</span>
      <div class="section-line"></div>
    </div>

    <article class="featured" onclick="openPost('achilles')">
      <div class="featured-visual">
        <div class="featured-icon">🏃</div>
      </div>
      <div class="featured-body">
        <span class="tag tag-sport">Sport</span>
        <h2>Terugkomend van een achillesblessure</h2>
        <p>Het hele verhaal achter mijn blessure en hoe ik hiermee om ben gegaan.</p>
        <div class="post-meta">12 mei 2026 · 5 min lezen</div>
        <span class="btn">Lees verder →</span>
      </div>
    </article>

    <div class="section-header">
      <span class="section-label">Recente posts</span>
      <div class="section-line"></div>
    </div>

    <div class="grid" id="post-grid">

      <article class="card" data-type="sport" onclick="openPost('wfl')">
        <div class="card-thumb thumb-sport">💪</div>
        <div class="card-body">
          <span class="tag tag-sport">Sport</span>
          <h3>Wings For Life</h3>
          <p>Wedstrijdverslag van de WFL World Run</p>
          <div class="post-meta">10 mei 2026 · 4 min lezen</div>
        </div>
      </article>

      <article class="card" data-type="boek" onclick="openPost('camus')">
        <div class="card-thumb thumb-boek">📖</div>
        <div class="card-body">
          <span class="tag tag-boek">Boekverslag</span>
          <h3>The Stranger — Albert Camus</h3>
          <p>Mijn kijk op absurdisme</p>
          <div class="post-meta">3 mei 2026 · 6 min lezen</div>
        </div>
      </article>

    </div>

    <div class="about-strip">
      <div class="avatar">👤</div>
      <div>
        <p><strong>Hoi, ik ben Benjamin Hashi.</strong><br>
        Ik schrijf over mijn trainingen en de boeken die ik lees. Vragen? Mail me op
        <a href="mailto:baa.hashi@outlook.com" style="color: var(--accent);">baa.hashi@outlook.com</a></p>
      </div>
    </div>

  </div>

</main>

<footer>
  © 2026 Benjamin Hashi
</footer>

<script>
  const posts = {
    achilles: {
      type: 'sport',
      html: `
        <span class="tag tag-sport">Sport</span>
        <h2>Terugkomend van een achillesblessure</h2>
        <div class="post-meta">12 mei 2026 · 5 min lezen</div>
        <div class="body">
          <p>Na weken weg te zijn geweest van het hardlopen vanwege een blessure ben ik veel te weten gekomen over de fysieke en mentale uitdagingen die komen kijken bij een blessure.</p>
          <h3>1. Alternatieve training</h3>
          <p>Om je conditie te houden is het belangrijk om je cardiovasculaire systeem te blijven uitdagen — bijvoorbeeld via fietsen, de crosstrainer of sauna.</p>
          <div class="schedule-table-wrap">
          <table class="schedule-table">
            <thead><tr><th>Dag</th><th>Training</th><th>Duur</th></tr></thead>
            <tbody>
              <tr><td>Maandag</td><td>Crosstrainer</td><td>~60 min</td></tr>
              <tr><td>Woensdag</td><td>Fietsen</td><td>~50 min</td></tr>
              <tr><td>Zondag</td><td>Sauna</td><td>2x ~20 min</td></tr>
            </tbody>
          </table>
          </div>
          <h3>2. Het mentale aspect</h3>
          <p>Tijdens een blessure heb je altijd het gevoel dat je dagelijks conditie verliest, wat uiteindelijk niet het geval is wanneer je regelmatig bezig bent met alternatieve training. Het is ook altijd een leermoment om te reflecteren op wat je anders kunt doen wanneer je weer fit bent.</p>
          <h3>Mijn tips</h3>
          <ul>
            <li>Zorg voor veel actief herstel</li>
            <li>Slaap minstens 8 uur per nacht en zorg voor een vaste bedtijd</li>
            <li>Blijf je hart uitdagen</li>
          </ul>
          <p>Vragen? Mail me op <a href="mailto:baa.hashi@outlook.com" style="color: var(--accent);">baa.hashi@outlook.com</a></p>
        </div>
      `
    },
    wfl: {
      type: 'sport',
      html: `
        <span class="tag tag-sport">Sport</span>
        <h2>WFL World Run — wedstrijdverslag</h2>
        <div class="post-meta">10 mei 2026 · 4 min lezen</div>
        <div class="body">
          <h3>Wat waren mijn doelen voorafgaand aan de wedstrijd?</h3>
          <p>Mijn doel was om 40km te lopen op een tempo van 4:30 min/km. Dit leek mij haalbaar aangezien dit mijn zone 3 tempo is in de meeste trainingen, en omdat ik weer af en toe pijnvrij heb kunnen trainen na een redelijk lange blessure aan mijn achillespees.</p>
          <h3>Wedstrijdverslag</h3>
          <p>Ik ging met de kopgroep mee van ca. 6 man — hierdoor heb ik in het begin veel wind gevangen en voelde ik mij sterk. We maakten rondjes van ca. 5km. Bij km 15 merkte ik dat de vele heuvels ervoor zorgden dat mijn benen een beetje verzuurden. Ik bleef achterin de groep en zag steeds meer mensen afvallen. Uiteindelijk ben ik tot 25km aangehaakt en heb ik de laatste 5km zelf doorgejogd op ca. 5:00 min/km. De catcher car was op dat moment ca. 6km van mij vandaan.</p>
          <p>Niet bekend met het concept? Bekijk <a href="https://www.wingsforlifeworldrun.com/en" target="_blank" style="color: var(--accent);">wingsforlifeworldrun.com</a>.</p>
          <h3>Wat had anders gekund?</h3>
          <p>Doordat ik met de kopgroep meeging liep ik niet op het tempo dat ik wilde — rond 4:00/4:15 min/km in plaats van de beoogde 4:30. Ook merkte ik dat ik te weinig geoefend had met het verwerken van snelle koolhydraten: in totaal 160g (Maurten gels & drinkmixes). De volgende keer moet ik meer mijn eigen plan trekken en geen onbekende dingen doen op racedays!</p>
        </div>
      `
    },
    camus: {
      type: 'boek',
      html: `
        <span class="tag tag-boek">Boekverslag</span>
        <h2>Absurdisme — The Stranger & De mythe van Sisyphus</h2>
        <div class="post-meta">3 mei 2026 · 6 min lezen</div>
        <div class="body">
          <h3>The Stranger</h3>
          <p>Vanaf het begin wordt de hoofdpersoon geïntroduceerd als iemand met weinig emotie en empathie. Maar waarom is dat zo? Die vraag stellen meerdere personages zich ook, omdat er verschillende conflicten ontstaan tijdens zijn interacties met anderen. Waar andere personages emoties voelen bij bepaalde gebeurtenissen, lijkt de hoofdpersoon die nauwelijks te ervaren.</p>
          <p>Ik denk dat dit grotendeels komt doordat hij vindt dat veel menselijke handelingen uiteindelijk nutteloos zijn — iedereen heeft immers hetzelfde einde: de dood. Maar als het leven geen betekenis heeft, waarom blijven we dan leven?</p>
          <p>Wat ik interessant vond was de laatste interactie met de gelovige die hem vertelt over een leven na de dood. De hoofdpersoon bekritiseert dit idee omdat het volgens hem het leven juist minder betekenis geeft: je hoop ligt dan niet in het heden maar in een onzekere toekomst.</p>
          <p>De conclusie is dat de andere personages voor de hoofdpersoon net zo vreemd zijn als hij voor hen. Uiteindelijk accepteert hij dit samen met het idee dat de dood voor iedereen onvermijdelijk is. Camus laat het boek bewust eindigen in de gevangenis: hoewel de hoofdpersoon fysiek gevangen zit, is hij mentaal vrijer dan de mensen die hem als een vreemdeling beschouwen.</p>
          <h3>Welke visie heb ik op het absurdisme?</h3>
          <p>Ik kom bijna maandelijks terug op deze boeken om te reflecteren op hoe ze mijn visie hebben veranderd. Ik denk vooral dat hoop hebben in toekomstige dingen mensen gevangen houdt in hun eigen gedachten. Een goed voorbeeld — ook besproken in De mythe van Sisyphus — is dat hoop de taak van Sisyphus oneindig en uitzichtloos maakte. Door het gevoel van hoop te verplaatsen naar het heden ontstaat er een bepaalde vrijheid.</p>
          <p>Meer over Sisyphus: <a href="https://nl.wikipedia.org/wiki/Sisyphos" target="_blank" style="color: var(--accent);">wikipedia.org/wiki/Sisyphos</a></p>
          <h3>Wat heeft het absurdisme mij gebracht?</h3>
          <p>Bewustwording van een bepaalde ironie in het dagelijks leven. Een video die dit goed illustreert: <a href="https://www.youtube.com/watch?v=SaP7qmsQbSI" target="_blank" style="color: var(--accent);">youtube.com/watch?v=SaP7qmsQbSI</a></p>
        </div>
      `
    }
  };

  function openPost(id) {
    const post = posts[id];
    if (!post) return;
    document.getElementById('post-content').innerHTML = post.html;
    document.getElementById('post-detail').classList.add('open');
    document.getElementById('overview').style.display = 'none';
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }

  function closePost() {
    document.getElementById('post-detail').classList.remove('open');
    document.getElementById('overview').style.display = 'block';
  }

  function filterPosts(e, type) {
    e.preventDefault();
    document.querySelectorAll('nav a').forEach(a => a.classList.remove('active'));
    e.target.classList.add('active');
    document.querySelectorAll('#post-grid .card').forEach(card => {
      card.style.display = card.dataset.type === type ? 'block' : 'none';
    });
    document.querySelector('.featured').style.display = type === 'sport' ? 'grid' : 'none';
  }

  function showAll(e) {
    e.preventDefault();
    document.querySelectorAll('nav a').forEach(a => a.classList.remove('active'));
    e.target.classList.add('active');
    document.querySelectorAll('#post-grid .card').forEach(card => card.style.display = 'block');
    document.querySelector('.featured').style.display = 'grid';
  }
</script>

</body>
</html>
