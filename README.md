# kevin
para mi vida
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Para Ti ❤️</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&family=Playfair+Display:wght@600&display=swap" rel="stylesheet">

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
}

body{
overflow:hidden;
font-family:'Poppins',sans-serif;
background:#000;
height:100vh;
}

.background{
position:fixed;
top:0;
left:0;
width:100%;
height:100%;
background-image:url('kevin_bell.jpeg');
background-position:center;
background-size:cover;
background-repeat:no-repeat;
z-index:0;
animation:zoom 20s ease-in-out infinite alternate;
}

.overlay{
position:absolute;
width:100%;
height:100%;
background:linear-gradient(rgba(0,0,0,.45), rgba(20,0,15,.7));
backdrop-filter: blur(2px);
z-index:1;
}

.content{
position:absolute;
top:50%;
left:50%;
transform:translate(-50%,-50%);
text-align:center;
width:90%;
max-width:900px;
color:white;
animation:fadeUp 2s ease;
z-index:2;
position:relative;
}

h1{
font-family:'Playfair Display',serif;
font-size:clamp(2rem,6vw,4.5rem);
line-height:1.3;
text-shadow:0 0 25px rgba(255,182,193,.7);
}

.subtitle{
margin-top:25px;
font-size:1.1rem;
color:#ffd9e6;
letter-spacing:2px;
}

.music-btn{
margin-top:35px;
padding:14px 25px;
border:none;
border-radius:50px;
background:rgba(255,192,203,.18);
color:white;
font-size:1rem;
cursor:pointer;
backdrop-filter:blur(10px);
transition:.4s;
}

.music-btn:hover{
transform:scale(1.05);
}

.sparkles span{
position:absolute;
display:block;
width:4px;
height:4px;
background:white;
border-radius:50%;
animation:sparkle 8s linear infinite;
opacity:.8;
}

@keyframes zoom{
from{
transform:scale(1);
}
to{
transform:scale(1.15);
}
}

@keyframes fadeUp{
from{
opacity:0;
transform:translate(-50%,-40%);
}
to{
opacity:1;
transform:translate(-50%,-50%);
}
}

@keyframes sparkle{
0%{
transform:translateY(100vh);
opacity:0;
}
20%{
opacity:1;
}
100%{
transform:translateY(-100px);
opacity:0;
}
}

</style>
</head>

<body>

<div class="background"></div>
<div class="overlay"></div>

<div class="sparkles">
<span style="left:10%;animation-delay:0s;"></span>
<span style="left:20%;animation-delay:2s;"></span>
<span style="left:35%;animation-delay:4s;"></span>
<span style="left:50%;animation-delay:1s;"></span>
<span style="left:70%;animation-delay:5s;"></span>
<span style="left:85%;animation-delay:3s;"></span>
</div>

<div class="content">

<h1>
TUS OJOS SON LA MAGIA CON LA QUE ENTRASTE EN MI CORAZÓN<br>
FELIZ CUMPLEAÑOS MI PEDACITO DE CIELO ❤️
</h1>

<div class="subtitle">
Siempre tú, siempre nosotros.
</div>

<button class="music-btn" id="musicButton" onclick="toggleMusic()">
🎵 Reproducir Música
</button>

</div>

<audio id="music" loop preload="auto">
  <source src="momento.mp3" type="audio/mpeg">
</audio>

<script>
const button = document.getElementById("musicButton");
const music = document.getElementById("music");
let isPlaying = false;

function updateButton() {
  button.textContent = isPlaying ? '⏸️ Pausar Música' : '🎵 Reproducir Música';
}

function toggleMusic() {
  if (!isPlaying) {
    music.play().then(() => {
      isPlaying = true;
      updateButton();
    }).catch(() => {
      button.textContent = '🔇 No se pudo reproducir';
    });
  } else {
    music.pause();
    isPlaying = false;
    updateButton();
  }
}

music.addEventListener('play', () => {
  isPlaying = true;
  updateButton();
});

music.addEventListener('pause', () => {
  isPlaying = false;
  updateButton();
});

updateButton();
</script>

</body>
</html>
