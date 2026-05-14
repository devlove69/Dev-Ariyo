<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Dev × Ariyo</title>

<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@500;700;900&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
}

html{
scroll-behavior:smooth;
}

body{
font-family:'Inter',sans-serif;
background:#06010f;
overflow-x:hidden;
color:white;
}

/* VIDEO BACKGROUND */

.video-bg{
position:fixed;
top:0;
left:0;
width:100%;
height:100%;
z-index:-3;
overflow:hidden;
}

.video-bg video{
width:100%;
height:100%;
object-fit:cover;
}

/* OVERLAY */

.overlay{
position:fixed;
top:0;
left:0;
width:100%;
height:100%;
background:
linear-gradient(to right,#05010d 20%,rgba(5,1,13,0.65)),
linear-gradient(to top,rgba(0,0,0,0.7),transparent);
z-index:-2;
}

/* GLOW */

.glow{
position:fixed;
width:700px;
height:700px;
background:radial-gradient(circle,#b64cff55,transparent 70%);
top:-200px;
right:-150px;
filter:blur(60px);
z-index:-1;
animation:floatGlow 8s ease-in-out infinite alternate;
}

@keyframes floatGlow{
0%{
transform:translateY(0px);
}
100%{
transform:translateY(60px);
}
}

/* NAVBAR */

nav{
width:100%;
padding:22px 7%;
display:flex;
justify-content:space-between;
align-items:center;
position:fixed;
top:0;
left:0;
z-index:1000;
backdrop-filter:blur(14px);
background:rgba(10,5,20,0.25);
border-bottom:1px solid rgba(255,255,255,0.08);
}

.logo{
font-size:28px;
font-family:'Orbitron',sans-serif;
font-weight:900;
background:linear-gradient(to right,#ffffff,#b56dff);
-webkit-background-clip:text;
-webkit-text-fill-color:transparent;
}

nav ul{
display:flex;
gap:28px;
list-style:none;
}

nav ul li a{
text-decoration:none;
color:#eee;
font-size:15px;
transition:0.4s;
}

nav ul li a:hover{
color:#c66eff;
text-shadow:0 0 12px #c66eff;
}

/* HERO */

.hero{
min-height:100vh;
display:flex;
align-items:center;
justify-content:space-between;
padding:140px 7% 80px;
gap:40px;
flex-wrap:wrap;
}

/* LEFT */

.left{
flex:1;
min-width:320px;
animation:fadeLeft 1.3s ease;
}

@keyframes fadeLeft{
from{
opacity:0;
transform:translateX(-60px);
}
to{
opacity:1;
transform:translateX(0);
}
}

.title{
font-size:95px;
font-family:'Orbitron',sans-serif;
font-weight:900;
line-height:1;
margin-bottom:28px;
background:linear-gradient(to right,#ffffff,#f3c7ff,#b76cff);
-webkit-background-clip:text;
-webkit-text-fill-color:transparent;
text-shadow:
0 0 25px rgba(182,76,255,0.45),
0 0 70px rgba(182,76,255,0.25);
}

.role-box{
display:inline-block;
padding:18px 28px;
border-radius:22px;
border:1px solid rgba(199,109,255,0.35);
background:rgba(255,255,255,0.05);
backdrop-filter:blur(14px);
font-size:20px;
font-weight:600;
margin-bottom:32px;
box-shadow:0 0 35px rgba(182,76,255,0.18);
}

.role-box span{
background:linear-gradient(to right,#ffb8ff,#8ea2ff);
-webkit-background-clip:text;
-webkit-text-fill-color:transparent;
}

.desc{
font-size:28px;
line-height:1.6;
color:#dddddd;
max-width:760px;
margin-bottom:45px;
border-left:4px solid #b84dff;
padding-left:22px;
}

/* CARDS */

.cards{
display:flex;
gap:22px;
flex-wrap:wrap;
}

.card{
width:220px;
padding:28px;
border-radius:26px;
background:rgba(255,255,255,0.05);
border:1px solid rgba(255,255,255,0.08);
backdrop-filter:blur(18px);
transition:0.45s;
position:relative;
overflow:hidden;
}

.card::before{
content:'';
position:absolute;
width:180%;
height:180%;
background:linear-gradient(45deg,transparent,#b54dff22,transparent);
top:-50%;
left:-50%;
transform:rotate(25deg);
animation:shine 6s linear infinite;
}

@keyframes shine{
0%{
transform:translateX(-100%) rotate(25deg);
}
100%{
transform:translateX(100%) rotate(25deg);
}
}

.card:hover{
transform:translateY(-10px) scale(1.03);
box-shadow:0 0 45px rgba(181,77,255,0.35);
border-color:#c56eff;
}

.card h2{
font-size:33px;
margin-bottom:12px;
color:#d38cff;
}

.card h3{
font-size:28px;
margin-bottom:10px;
}

.card p{
font-size:15px;
color:#cfcfcf;
}

/* RIGHT */

.right{
flex:1;
min-width:320px;
display:flex;
justify-content:center;
position:relative;
animation:fadeRight 1.3s ease;
}

@keyframes fadeRight{
from{
opacity:0;
transform:translateX(60px);
}
to{
opacity:1;
transform:translateX(0);
}
}

/* MAIN IMAGE */

.character{
width:100%;
max-width:620px;
position:relative;
z-index:3;
animation:float 5s ease-in-out infinite alternate;
filter:drop-shadow(0 0 40px rgba(190,100,255,0.45));
}

@keyframes float{
0%{
transform:translateY(0px);
}
100%{
transform:translateY(-18px);
}
}

/* PROFILE PIC */

.profile-pic{
position:absolute;
top:40px;
left:20px;
width:120px;
height:120px;
border-radius:50%;
object-fit:cover;
border:4px solid #cb7dff;
z-index:5;
box-shadow:
0 0 25px #c46dff,
0 0 60px rgba(196,109,255,0.45);
animation:profilePulse 3s infinite;
}

@keyframes profilePulse{
0%{
transform:scale(1);
}
50%{
transform:scale(1.07);
}
100%{
transform:scale(1);
}
}

/* FLOAT BOXES */

.floating{
position:absolute;
padding:22px;
border-radius:22px;
background:rgba(255,255,255,0.05);
border:1px solid rgba(255,255,255,0.1);
backdrop-filter:blur(16px);
box-shadow:0 0 35px rgba(180,90,255,0.15);
animation:floatBox 4s ease-in-out infinite alternate;
}

@keyframes floatBox{
0%{
transform:translateY(0);
}
100%{
transform:translateY(-12px);
}
}

.box1{
top:20px;
right:0;
width:190px;
}

.box2{
top:180px;
left:0;
width:220px;
}

.box3{
bottom:70px;
right:10px;
width:180px;
}

.floating p{
color:#e5d3ff;
line-height:1.8;
}

/* SECTION */

.section{
padding:120px 7%;
}

.section-title{
font-size:58px;
font-family:'Orbitron',sans-serif;
margin-bottom:70px;
text-align:center;
background:linear-gradient(to right,#fff,#c56dff);
-webkit-background-clip:text;
-webkit-text-fill-color:transparent;
}

/* PROJECT GRID */

.project-grid{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(320px,1fr));
gap:30px;
}

.project{
padding:35px;
border-radius:28px;
background:rgba(255,255,255,0.05);
border:1px solid rgba(255,255,255,0.08);
backdrop-filter:blur(18px);
transition:0.45s;
}

.project:hover{
transform:translateY(-12px);
box-shadow:0 0 45px rgba(188,90,255,0.35);
}

.project h3{
font-size:32px;
margin-bottom:18px;
color:#d58eff;
}

.project p{
line-height:1.8;
color:#ddd;
}

/* FOOTER */

footer{
padding:45px;
text-align:center;
background:rgba(0,0,0,0.4);
border-top:1px solid rgba(255,255,255,0.08);
font-size:15px;
color:#ccc;
}

/* MOBILE */

@media(max-width:1100px){

.hero{
flex-direction:column;
text-align:center;
}

.title{
font-size:70px;
}

.desc{
font-size:22px;
border:none;
padding-left:0;
}

.cards{
justify-content:center;
}

.profile-pic{
width:95px;
height:95px;
top:10px;
left:10px;
}

}

@media(max-width:700px){

nav{
padding:18px 5%;
}

nav ul{
display:none;
}

.hero{
padding:120px 5% 70px;
}

.title{
font-size:52px;
}

.role-box{
font-size:15px;
padding:14px 20px;
}

.desc{
font-size:18px;
}

.card{
width:100%;
}

.character{
max-width:100%;
}

.floating{
transform:scale(.8);
}

.section-title{
font-size:38px;
}

}

</style>
</head>
<body>

<!-- VIDEO -->

<div class="video-bg">
<video autoplay muted loop playsinline>
<source src="https://files.catbox.moe/4kfdqi.mp4" type="video/mp4">
</video>
</div>

<div class="overlay"></div>
<div class="glow"></div>

<!-- NAV -->

<nav>

<div class="logo">Dev × Ariyo</div>

<ul>
<li><a href="#">Home</a></li>
<li><a href="#">Projects</a></li>
<li><a href="#">Skills</a></li>
<li><a href="#">Contact</a></li>
</ul>

</nav>

<!-- HERO -->

<section class="hero">

<!-- LEFT -->

<div class="left">

<h1 class="title">
Dev × Ariyo
</h1>

<div class="role-box">
SOFTWARE ENGINEER, 
<span>CONTENT CREATOR</span> 
& COMMUNITY ORGANIZER
</div>

<div class="desc">
Building scalable solutions, creating engaging content, and empowering communities with futuristic premium experiences.
</div>

<div class="cards">

<div class="card">
<h2>&lt;/&gt;</h2>
<h3>Engineer</h3>
<p>Code. Build. Solve.</p>
</div>

<div class="card">
<h2>✎</h2>
<h3>Creator</h3>
<p>Create. Inspire. Share.</p>
</div>

<div class="card">
<h2>👥</h2>
<h3>Organizer</h3>
<p>Connect. Collaborate. Grow.</p>
</div>

</div>

</div>

<!-- RIGHT -->

<div class="right">

<img class="profile-pic" src="https://i.ibb.co.com/3yrBSCXf/file-00000000d9d47208a3d6d6d164643102.png">

<img class="character" src="https://i.ibb.co.com/3yrBSCXf/file-00000000d9d47208a3d6d6d164643102.png">

<div class="floating box1">
<p>
// creating impact <br>
// one line at a time
</p>
</div>

<div class="floating box2">
<p>
Python <br>
JavaScript <br>
TypeScript <br>
React <br>
Node.js
</p>
</div>

<div class="floating box3">
<p>
Projects 25+ <br><br>
Communities 10K+ <br><br>
Content 100+
</p>
</div>

</div>

</section>

<!-- PROJECTS -->

<section class="section">

<h2 class="section-title">
Featured Projects
</h2>

<div class="project-grid">

<div class="project">
<h3>Cyberpunk Portfolio</h3>
<p>
Futuristic animated portfolio with premium glassmorphism effects, neon lighting and interactive dashboard UI.
</p>
</div>

<div class="project">
<h3>AI Dashboard</h3>
<p>
Advanced AI control system with realtime analytics, automation tools and modern futuristic interface.
</p>
</div>

<div class="project">
<h3>Community Platform</h3>
<p>
Large scale creator ecosystem platform designed for collaboration, content and engagement systems.
</p>
</div>

</div>

</section>

<footer>
© 2026 Dev × Ariyo — Futuristic Developer Portfolio
</footer>

</body>
</html>