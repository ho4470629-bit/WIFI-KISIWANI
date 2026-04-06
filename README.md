<!DOCTYPE html>
<html lang="sw">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>NEXT LEVEL STUDIO</title>

<style>
:root {
    --gold: #d4af37;
    --dark-gold: #996515;
    --black: #0a0a0a;
    --gray: #1a1a1a;
}

/* BODY */
body {
    background: var(--black);
    color: white;
    font-family: 'Segoe UI', sans-serif;
    margin: 0;
}

/* 3D TEXT */
.logo, h1, h2, h3 {
    text-shadow: 0 0 5px #000, 0 0 10px var(--gold), 0 0 20px var(--gold);
}

/* INTRO */
#introModal {
    position: fixed;
    width: 100%;
    height: 100%;
    background: black;
    z-index: 9999;
    display: flex;
    justify-content: center;
    align-items: center;
}

.intro-box {
    background: #111;
    border: 2px solid var(--gold);
    padding: 30px;
    border-radius: 15px;
    text-align: center;
}

/* HEADER */
header {
    display: flex;
    justify-content: space-between;
    padding: 15px 5%;
    background: var(--gray);
}

.logo {
    font-size: 26px;
    color: var(--gold);
    font-weight: bold;
}

/* CONTACT */
.wa-contact {
    display: flex;
    align-items: center;
    gap: 10px;
    color: var(--gold);
    font-weight: bold;
}

.wa-contact img {
    width: 28px;
}

/* DJ MENU */
#dj-menu {
    display: none;
    position: fixed;
    width: 100%;
    height: 100%;
    background: black;
    z-index: 2000;
    padding: 20px;
    text-align: center;
}

.dj-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(120px,1fr));
    gap: 10px;
}

.dj-item {
    padding: 10px;
    border: 1px solid var(--gold);
    color: var(--gold);
}

/* MAIN */
.main-container {
    display: flex;
}

.sidebar {
    width: 20%;
    padding: 20px;
    background: #0f0f0f;
}

.sidebar ul {
    list-style: none;
    padding: 0;
}

.sidebar li {
    padding: 10px;
    cursor: pointer;
    text-transform: uppercase;
}

.sidebar li:hover {
    color: var(--gold);
}

/* CONTENT */
.content-area {
    width: 80%;
    padding: 20px;
}

.search-bar {
    width: 80%;
    padding: 12px;
    border-radius: 30px;
    border: 1px solid var(--gold);
    background: #111;
    color: white;
}

/* MOVIE */
.movie-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit,minmax(250px,1fr));
    gap: 20px;
}

.movie-card {
    background: #111;
    border: 1px solid #333;
    border-radius: 10px;
}

.video-container {
    position: relative;
    padding-bottom: 56%;
}

.video-container iframe {
    position: absolute;
    width: 100%;
    height: 100%;
}

.movie-info {
    padding: 10px;
}

/* BUTTON */
.ep-btn {
    background: #222;
    color: white;
    border: 1px solid #444;
    padding: 5px;
}

/* MODAL */
.modal {
    display: none;
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
    background: #111;
    padding: 20px;
    border: 2px solid var(--gold);
}

</style>
</head>

<body>

<!-- INTRO -->
<div id="introModal">
<div class="intro-box">
<h2>NEXT LEVEL STUDIO</h2>
<p>KARIBU KWENYE MFUMO WA KISASA WA MOVIE</p>
<button onclick="closeIntro()">INGIA</button>
</div>
</div>

<!-- HEADER -->
<header>
<div class="logo">NEXT LEVEL STUDIO</div>

<div class="wa-contact">
<img src="https://img.freepik.com/premium-vector/whatsapp-logo-icon-set-vector-illustration-design_744955-2933.jpg">
<span>0768129449</span>
</div>

<button onclick="toggleDJ()">MOVIE ZA WEEK</button>
</header>

<!-- DJ MENU -->
<div id="dj-menu">
<h1>MA DJ & MOVIE ZA WEEK</h1>

<div class="dj-grid">
<div class="dj-item">DJ MSATI</div>
<div class="dj-item">DJ MURPH</div>
<div class="dj-item">DJ MAPP</div>
<div class="dj-item">DJ MJUKUU</div>
<div class="dj-item">DJ ALLY D</div>
<div class="dj-item">DJ SPENSA</div>
<div class="dj-item">DJ SKILLS</div>
<div class="dj-item">DJ WARETE</div>
<div class="dj-item">DJ KHALID</div>
<div class="dj-item">DJ BONGO</div>
<div class="dj-item">DJ FIRE</div>
<div class="dj-item">DJ KING</div>
</div>

<button onclick="toggleDJ()">FUNGA</button>
</div>

<!-- MAIN -->
<div class="main-container">

<!-- SIDEBAR -->
<div class="sidebar">
<h3>KATEGORIA</h3>
<ul>
<li>KATUNI</li>
<li>COMEDY</li>
<li>ACTION</li>
<li>ROMANCE</li>
<li>HORROR</li>
<li>SCI-FI</li>
<li>ADVENTURE</li>
<li>DRAMA</li>
<li>ANIME</li>
<li>SERIES</li>
<li>DOCUMENTARY</li>
<li>TRENDING</li>
<li>NEW RELEASE</li>
<li>NETFLIX</li>
<li>HOLLYWOOD</li>
<li>BONGO MOVIES</li>
</ul>
</div>

<!-- CONTENT -->
<div class="content-area">

<input type="text" id="myInput" onkeyup="searchMovie()" class="search-bar" placeholder="TAFUTA MOVIE...">

<div class="movie-grid" id="movieGrid">

<div class="movie-card">
<div class="video-container">
<iframe src="https://ok.ru/videoembed/13087197629111"></iframe>
</div>
<div class="movie-info">
<h3 class="title">GAME PLANE</h3>
<button class="ep-btn">EP 1</button>
<button class="ep-btn" onclick="showPay()">EP 2</button>
</div>
</div>

<div class="movie-card">
<div class="video-container">
<iframe src="https://ok.ru/videoembed/13087108106935"></iframe>
</div>
<div class="movie-info">
<h3 class="title">EMERGENCY LOVE</h3>
<button class="ep-btn">EP 1</button>
<button class="ep-btn" onclick="showPay()">EP 2</button>
</div>
</div>

</div>
</div>
</div>

<!-- PAY -->
<div id="payModal" class="modal">
<h2>LIPA</h2>
<p>0768129449</p>
<button onclick="closePay()">FUNGA</button>
</div>

<script>
function closeIntro(){
document.getElementById('introModal').style.display='none';
}

function toggleDJ(){
let m=document.getElementById('dj-menu');
m.style.display = (m.style.display==='block')?'none':'block';
}

function searchMovie(){
let input=document.getElementById('myInput').value.toUpperCase();
let cards=document.getElementsByClassName('movie-card');

for(let i=0;i<cards.length;i++){
let title=cards[i].querySelector(".title").innerText;
cards[i].style.display = title.toUpperCase().includes(input) ? "" : "none";
}
}

function showPay(){
document.getElementById('payModal').style.display='block';
}

function closePay(){
document.getElementById('payModal').style.display='none';
}
</script>

</body>
</html>
