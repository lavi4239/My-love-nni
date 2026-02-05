# My-love-nni
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>For My NNI♥️ 🌹</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">

<style>
:root {
  --primary: #ff4d6d;
  --bg: #0a0a0a;
  --glass: rgba(255, 255, 255, 0.1);
}

body {
  margin: 0;
  font-family: 'Poppins', sans-serif;
  background: var(--bg);
  color: #fff;
  overflow-x: hidden;
  min-height: 100vh;
  transition: background 0.8s;
}

/* --- LOCK SCREEN --- */
#lock-screen {
  position: fixed;
  inset: 0;
  background: #000;
  z-index: 10000;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: 1.2s cubic-bezier(0.7, 0, 0.3, 1);
}

.lock-card {
  text-align: center;
  padding: 30px;
  background: var(--glass);
  backdrop-filter: blur(15px);
  border-radius: 20px;
  border: 1px solid rgba(255,255,255,0.1);
  width: 85%;
  max-width: 350px;
}

input {
  padding: 15px;
  border-radius: 50px;
  border: 1px solid rgba(255,255,255,0.3);
  width: 85%;
  text-align: center;
  outline: none;
  background: rgba(0,0,0,0.5);
  color: #fff;
  font-size: 1rem;
  margin: 20px 0;
}

/* --- BOY ANIMATION --- */
#animation-container {
  position: relative;
  height: 180px;
  width: 100%;
  display: none;
  margin-top: 20px;
}

.boy {
  position: absolute;
  left: -100px;
  font-size: 70px;
  bottom: 0;
  transition: 3.5s linear;
}

.boy-walk { left: calc(50% - 35px); }

.rose-gift {
  position: absolute;
  opacity: 0;
  font-size: 50px;
  bottom: 50px;
  left: calc(50% + 5px);
  transition: 0.8s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}

/* --- MAIN CONTENT --- */
.content-wrapper { display: none; padding: 20px; text-align: center; }

.main-title {
  font-family: 'Dancing Script', cursive;
  font-size: 3rem;
  opacity: 0;
  transition: 1.5s;
  margin: 15px 0;
}

.glass-box {
  background: var(--glass);
  backdrop-filter: blur(15px);
  padding: 25px;
  border-radius: 20px;
  border: 1px solid rgba(255,255,255,0.2);
  margin: 20px auto;
  max-width: 450px;
  display: none;
}

.btn-action {
  padding: 15px 30px;
  background: var(--primary);
  border: none;
  border-radius: 50px;
  color: white;
  font-weight: bold;
  cursor: pointer;
  box-shadow: 0 0 15px rgba(255, 77, 109, 0.5);
  margin: 10px;
  transition: 0.3s;
}

.btn-action:active { transform: scale(0.9); }

#final-buttons { display: none; margin-top: 20px; }

/* --- EFFECTS --- */
.blush-bg { background: radial-gradient(circle, #800f2f 0%, #0a0a0a 100%) !important; }

.petal {
  position: fixed;
  pointer-events: none;
  z-index: -1;
  animation: fly linear forwards;
}

@keyframes fly {
  0% { transform: translateY(110vh) rotate(0deg); opacity: 1; }
  100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
}
</style>
</head>
<body>

<div id="lock-screen">
  <div class="lock-card">
    <h1 style="font-family:'Dancing Script'; font-size: 2.5rem;">For NNI♥️</h1>
    <p>Enter the date of our 1st coffee... ☕</p>
    <input type="text" id="pass" placeholder="Type here...">
    <br>
    <button onclick="unlock()" class="btn-action">Unlock Surprise</button>
    <p id="err" style="font-size: 0.8rem; color: #ff758c; margin-top: 10px;"></p>
  </div>
</div>

<div class="content-wrapper" id="main-ui">
  
  <div id="animation-container">
    <div class="boy" id="boy-char">🚶‍♂️</div>
    <div class="rose-gift" id="rose-gift">🌹</div>
  </div>

  <h1 class="main-title" id="title">Happy Rose Day, NNI♥️</h1>

  <div id="reveal-zone">
    <button onclick="bringRose()" id="action-btn" class="btn-action">Look who's here... 👀</button>
  </div>

  <div class="glass-box" id="message-box">
    <div id="text-output" style="font-size:1.05rem; line-height:1.6; white-space:pre-line; text-align: left;"></div>
    
    <div id="final-buttons">
      <hr style="opacity:0.2; margin: 20px 0;">
      <p style="font-family:'Dancing Script'; font-size: 1.6rem;">I'm right here with you... ❤️</p>
      <button class="btn-action" onclick="virtualHug()">Get a Hug 🤗</button>
      <button class="btn-action" onclick="virtualKiss()">Get a Kiss 💋</button>
    </div>
  </div>
</div>

<script>
// Valid answers
const codes = ["1 december", "01 december", "december 1", "1st december"];

function unlock() {
  const val = document.getElementById('pass').value.toLowerCase().trim();
  if(codes.includes(val)) {
    document.getElementById('lock-screen').style.transform = 'translateY(-100%)';
    setTimeout(() => {
      document.getElementById('lock-screen').style.display = 'none';
      document.getElementById('main-ui').style.display = 'block';
    }, 800);
  } else {
    document.getElementById('err').innerText = "❌ Try again, my love...";
    document.getElementById('pass').value = "";
  }
}

function bringRose() {
  document.getElementById('action-btn').style.display = 'none';
  document.getElementById('animation-container').style.display = 'block';
  
  const boy = document.getElementById('boy-char');
  const rose = document.getElementById('rose-gift');
  const title = document.getElementById('title');

  setTimeout(() => boy.classList.add('boy-walk'), 100);

  setTimeout(() => {
    boy.innerHTML = "🙋‍♂️"; 
    rose.style.opacity = '1';
    rose.style.transform = 'scale(1.6) translateY(-10px)';
    title.style.opacity = '1';
    if(window.navigator.vibrate) window.navigator.vibrate([100, 50, 100]);
    setInterval(spawnPetal, 700);
  }, 3500);

  setTimeout(() => {
    document.getElementById('message-box').style.display = 'block';
    startTyping();
  }, 5000);
}

const letter = `My beautiful NNI♥️,

Even though miles separate us, nothing can stop me from bringing you a rose today. 

You are the most precious flower I have ever found, and I promise to keep you safe and happy, no matter where I am. 

Happy Rose Day, my life! 🌹`;

let char = 0;
function startTyping() {
  const output = document.getElementById('text-output');
  if(char < letter.length) {
    output.innerHTML += letter.charAt(char);
    char++;
    setTimeout(startTyping, 45);
  } else {
    document.getElementById('final-buttons').style.display = 'block';
  }
}

function virtualHug() {
  document.body.classList.add('blush-bg');
  for(let i=0; i<30; i++) spawnPetal('❤️');
  setTimeout(() => document.body.classList.remove('blush-bg'), 2000);
  if(window.navigator.vibrate) window.navigator.vibrate(300);
}

function virtualKiss() {
  for(let i=0; i<25; i++) spawnPetal('💋');
  if(window.navigator.vibrate) window.navigator.vibrate([200, 100, 200]);
}

function spawnPetal(sym) {
  const p = document.createElement('div');
  p.className = 'petal';
  p.innerHTML = sym || (Math.random() > 0.5 ? '🌹' : '🌸');
  p.style.left = Math.random() * 100 + 'vw';
  p.style.fontSize = Math.random() * 20 + 20 + 'px';
  p.style.animationDuration = Math.random() * 3 + 3 + 's';
  document.body.appendChild(p);
  setTimeout(() => p.remove(), 5000);
}
</script>

</body>
</html>
