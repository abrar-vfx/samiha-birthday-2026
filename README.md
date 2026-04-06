# samiha-birthday-2026<!DOCTYPE html>
<html>
<head>
<title>Happy Birthday Samiha 🎂</title>

<style>
body {
  text-align: center;
  font-family: Arial;
  background: linear-gradient(to right, #ffccff, #ccffff);
  overflow: hidden;
}

button {
  padding: 10px 20px;
  font-size: 18px;
  margin: 10px;
  border-radius: 10px;
  border: none;
  background: #ff66b2;
  color: white;
}

h2, h3 {
  color: #ff3399;
}
</style>
</head>

<body>

<h2 id="question"></h2>

<div id="options">
  <button onclick="answer('yes')">Yes</button>
  <button onclick="answer('no')">No</button>
</div>

<div id="content"></div>

<!-- 🎵 Music -->
<audio autoplay loop>
  <source src="https://www2.cs.uic.edu/~i101/SoundFiles/HappyBirthday.mid">
</audio>

<!-- 🎊 Confetti -->
<canvas id="confetti"></canvas>

<script>

// ✨ Typing Effect
function typeText(elementId, text, speed = 50) {
  let i = 0;
  document.getElementById(elementId).innerHTML = "";
  
  function typing() {
    if (i < text.length) {
      document.getElementById(elementId).innerHTML += text.charAt(i);
      i++;
      setTimeout(typing, speed);
    }
  }
  typing();
}

// 🎬 Start typing on load
window.onload = function() {
  typeText("question", "Hey Samiha, do u know what's today? 🤔", 60);
};

// 🎯 Answer logic
function answer(choice){
  if(choice === 'no'){
    typeText("question", "Uff 🤦 Samiha, it's your birthday 🎂", 60);
    document.getElementById('options').innerHTML =
    '<button onclick="gift()">Want to get a gift? 🎁</button>';
  } else {
    final();
  }
}

// 🎁 Gift scene
function gift(){
  document.getElementById('content').innerHTML =
  '<h3>🎁 Opening gift box...</h3><img src="https://i.imgur.com/6X4Xx7U.gif"><br><br><button onclick="final()">Take it ❤️</button>';
}

// 🎉 Final scene
function final(){
  typeText("question", "🎉 A VERY VERY HAPPY BIRTHDAY SAMIHA 🎂🎈 🎉", 60);
  document.getElementById('options').innerHTML = "";
  document.getElementById('content').innerHTML =
  '<h2>🧸 Here is your teddy bear!</h2><img src="https://i.imgur.com/OYVpe2W.png">';
}

// 🎊 Confetti animation
const canvas = document.getElementById('confetti');
const ctx = canvas.getContext('2d');
canvas.width = window.innerWidth;
canvas.height = window.innerHeight;

let pieces = [];
for (let i = 0; i < 120; i++) {
  pieces.push({
    x: Math.random() * canvas.width,
    y: Math.random() * canvas.height,
    size: Math.random() * 10 + 5,
    speed: Math.random() * 3 + 2
  });
}

function update() {
  ctx.clearRect(0, 0, canvas.width, canvas.height);
  pieces.forEach(p => {
    ctx.fillStyle = "hsl(" + Math.random()*360 + ",100%,50%)";
    ctx.fillRect(p.x, p.y, p.size, p.size);
    p.y += p.speed;
    if (p.y > canvas.height) p.y = 0;
  });
  requestAnimationFrame(update);
}
update();

</script>

</body>
</html>
