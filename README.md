<html lang="nl">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1" />
<title>Benjamin Hashi — Sport & Boekverslagen</title>

<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>

<style>
*{margin:0;padding:0;box-sizing:border-box}

:root{
  --bg:#F7F5F0;
  --surface:#fff;
  --text:#1A1A18;
  --muted:#7A7870;
  --border:#E2DED6;
  --accent:#2D6A4F;
}

body{
  font-family:'DM Sans',sans-serif;
  background:var(--bg);
  color:var(--text);
  font-size:16px;
  line-height:1.6;
  overflow-x:hidden;
  -webkit-text-size-adjust:100%;
}

/* HEADER */
header{
  position:sticky;
  top:0;
  background:var(--surface);
  border-bottom:1px solid var(--border);
  z-index:100;
}

.header-inner{
  max-width:900px;
  margin:auto;
  padding:14px 16px;
  display:flex;
  justify-content:space-between;
  align-items:center;
}

.logo{
  font-family:'Playfair Display',serif;
  font-size:20px;
}
.logo span{color:var(--accent)}

nav{
  display:flex;
  gap:8px;
  flex-wrap:wrap;
}

nav a{
  font-size:13px;
  padding:6px 10px;
  border-radius:20px;
  color:var(--muted);
  text-decoration:none;
}

nav a.active{
  background:var(--bg);
  color:var(--text);
}

/* HERO */
.hero{
  text-align:center;
  padding:40px 16px;
  background:var(--surface);
  border-bottom:1px solid var(--border);
}

.hero h1{
  font-family:'Playfair Display',serif;
  font-size:clamp(24px,6vw,40px);
}

.hero p{
  color:var(--muted);
  margin-top:8px;
}

/* CONTAINER */
.container{
  max-width:900px;
  margin:auto;
  padding:20px 16px;
}

/* FEATURED */
.featured{
  display:grid;
  grid-template-columns:1fr 1fr;
  background:var(--surface);
  border:1px solid var(--border);
  border-radius:14px;
  overflow:hidden;
  cursor:pointer;
}

.featured-visual{
  background:#2D6A4F;
  min-height:180px;
  display:flex;
  align-items:center;
  justify-content:center;
  color:white;
  font-size:40px;
}

.featured-body{
  padding:16px;
}

/* GRID */
.grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(160px,1fr));
  gap:12px;
  margin-top:16px;
}

.card{
  background:var(--surface);
  border:1px solid var(--border);
  border-radius:12px;
  overflow:hidden;
  cursor:pointer;
  padding:12px;
}

.card:hover{transform:translateY(-2px)}

.card h3{
  font-family:'Playfair Display',serif;
  font-size:15px;
}

/* DETAIL PAGE */
.post-detail{
  display:none;
  background:var(--surface);
  padding:20px;
  border-radius:14px;
  border:1px solid var(--border);
}

.post-detail.open{display:block}

.back-btn{
  font-size:13px;
  color:var(--muted);
  margin-bottom:10px;
  display:block;
}

/* MOBILE FIX */
@media(max-width:640px){

  .featured{
    grid-template-columns:1fr;
  }

  .header-inner{
    flex-direction:column;
    gap:10px;
    align-items:flex-start;
  }

  nav a{
    font-size:12px;
  }

  .container{
    padding:16px 12px;
  }
}
</style>
</head>

<body>

<header>
  <div class="header-inner">
    <div class="logo">Benjamin<span>Hashi</span></div>
    <nav>
      <a class="active" href="#" onclick="showAll(event)">Alles</a>
      <a href="#" onclick="filterPosts(event,'sport')">Sport</a>
      <a href="#" onclick="filterPosts(event,'boek')">Boek</a>
    </nav>
  </div>
</header>

<section class="hero">
  <h1>Sport & Boekverslagen</h1>
  <p>Mijn trainingen en boeken</p>
</section>

<main class="container">

<!-- DETAIL -->
<div id="post-detail" class="post-detail">
  <span class="back-btn" onclick="closePost()">← Terug</span>
  <div id="post-content"></div>
</div>

<!-- OVERVIEW -->
<div id="overview">

  <div class="featured" onclick="openPost('achilles')">
    <div class="featured-visual">🏃</div>
    <div class="featured-body">
      <h3>Achilles blessure</h3>
      <p>Mijn herstelproces</p>
    </div>
  </div>

  <div class="grid">

    <div class="card" data-type="sport" onclick="openPost('wfl')">
      <h3>Wings For Life</h3>
      <p>Wedstrijd verslag</p>
    </div>

    <div class="card" data-type="boek" onclick="openPost('camus')">
      <h3>The Stranger</h3>
      <p>Camus analyse</p>
    </div>

  </div>

</div>

</main>

<script>
const posts = {

achilles:{
html:`<h2>Achilles blessure</h2><p>Volledig herstel verhaal + training schema + mentale tips...</p>`
},

wfl:{
html:`<h2>WFL Run</h2><p>Wedstrijd strategie, pacing en fouten analyse...</p>`
},

camus:{
html:`<h2>The Stranger</h2><p>Analyse van absurdism en Camus filosofie...</p>`
}

}

function openPost(id){
document.getElementById("post-content").innerHTML = posts[id].html;
document.getElementById("post-detail").classList.add("open");
document.getElementById("overview").style.display="none";
window.scrollTo(0,0);
}

function closePost(){
document.getElementById("post-detail").classList.remove("open");
document.getElementById("overview").style.display="block";
}

function filterPosts(e,type){
e.preventDefault();
document.querySelectorAll(".card").forEach(c=>{
c.style.display = c.dataset.type===type?"block":"none";
});
}

function showAll(e){
e.preventDefault();
document.querySelectorAll(".card").forEach(c=>c.style.display="block");
}
</script>

</body>
</html>
