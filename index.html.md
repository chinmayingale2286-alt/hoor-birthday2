<!DOCTYPE html>  
<html lang="en">  
<head>  
<meta charset="UTF-8">  
<title>Happy 18th Birthday Hoor 🎉</title>  
<meta name="viewport" content="width=device-width, initial-scale=1.0">  
  
<style>  
body {  
  margin: 0;  
  font-family: 'Poppins', sans-serif;  
  background: linear-gradient(135deg, #ff9a9e, #fad0c4);  
  color: #fff;  
  text-align: center;  
  overflow-x: hidden;  
}  
  
.container {  
  padding: 30px 20px;  
}  
  
h1 { font-size: 3em; }  
h2 { font-weight: 300; }  
  
.card {  
  background: rgba(255,255,255,0.2);  
  border-radius: 20px;  
  padding: 25px;  
  max-width: 650px;  
  margin: 20px auto;  
  backdrop-filter: blur(10px);  
}  
  
button {  
  padding: 15px 30px;  
  border: none;  
  border-radius: 30px;  
  background: #ff4d6d;  
  color: white;  
  font-size: 1em;  
  cursor: pointer;  
  margin-top: 20px;  
}  
  
button:hover { transform: scale(1.1); }  
  
.hidden { display: none; }  
  
/* Balloons */  
.balloon {  
  position: fixed;  
  bottom: -100px;  
  font-size: 40px;  
  animation: floatUp 8s linear infinite;  
}  
  
@keyframes floatUp {  
  from { transform: translateY(0); }  
  to { transform: translateY(-120vh); }  
}  
  
/* Cats dancing */  
.cats {  
  display: flex;  
  justify-content: center;  
  gap: 15px;  
  font-size: 60px;  
  animation: dance 1s infinite alternate;  
}  
  
@keyframes dance {  
  from { transform: translateY(0); }  
  to { transform: translateY(-15px); }  
}  
  
/* Confetti */  
.confetti {  
  position: fixed;  
  top: -10px;  
  width: 10px;  
  height: 10px;  
  background: red;  
  animation: fall 3s linear forwards;  
}  
  
@keyframes fall {  
  to { transform: translateY(110vh) rotate(720deg); }  
}  
</style>  
</head>  
  
<body>  
  
<!-- 🎵 Background Music -->  
<audio autoplay loop>  
  <source src="birthday.mp3" type="audio/mpeg">  
</audio>  
  
<div class="container">  
  <h1>🎉 Happy 18th Birthday Hoor 🎂</h1>  
  <h2>Now the party REALLY starts 😌💖</h2>  
  
  <div class="card">  
    <div class="cats">🐱🎉 🐱🎈 🐱🎂</div>  
    <p>Dancing cats + party hats = perfect birthday 😆</p>  
  </div>  
  
  <button onclick="partyTime()">Open my love letter 💌</button>  
  
  <div id="loveCard" class="card hidden">  
    <div id="letter"></div>  
  </div>  
</div>  
  
<script>  
/* Love letter text */  
const text =  
`My dearest Hoor 💖,  
  
Happy 18th Birthday 🎉✨  
You are cute, strong, kind, and truly special to me.  
  
Your smile lights up my world,  
and I feel lucky every day to have you 💕  
  
May your life be full of love,  
success, happiness, and dreams coming true 🌸  
  
I love you endlessly ❤️`;  
  
let index = 0;  
  
function partyTime() {  
  document.getElementById("loveCard").classList.remove("hidden");  
  document.getElementById("letter").innerHTML = "";  
  index = 0;  
  typeEffect();  
  confettiBlast(150);  
}  
  
function typeEffect() {  
  if (index < text.length) {  
    document.getElementById("letter").innerHTML += text.charAt(index);  
    index++;  
    setTimeout(typeEffect, 40);  
  }  
}  
  
/* Confetti blast */  
function confettiBlast(amount) {  
  for (let i = 0; i < amount; i++) {  
    const confetti = document.createElement("div");  
    confetti.className = "confetti";  
    confetti.style.left = Math.random() * 100 + "vw";  
    confetti.style.background =  
      ["#ff4d6d","#ffd166","#06d6a0","#4d96ff"][Math.floor(Math.random()*4)];  
    confetti.style.animationDuration = (2 + Math.random() * 2) + "s";  
    document.body.appendChild(confetti);  
    setTimeout(() => confetti.remove(), 4000);  
  }  
}  
  
/* Auto confetti on load */  
window.onload = () => confettiBlast(200);  
  
/* Balloons */  
setInterval(() => {  
  const b = document.createElement("div");  
  b.className = "balloon";  
  b.innerText = "🎈";  
  b.style.left = Math.random() * 100 + "vw";  
  document.body.appendChild(b);  
  setTimeout(() => b.remove(), 8000);  
}, 600); ,  
</script>  
  
</body>  
</html>  
