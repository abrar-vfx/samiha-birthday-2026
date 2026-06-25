<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Samiha 🎂</title>

<style>
*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Arial;
}

body{
background:linear-gradient(135deg,#ffb6c1,#ffd6e8);
height:100vh;
display:flex;
justify-content:center;
align-items:center;
overflow:hidden;
text-align:center;
}

.box{
background:white;
padding:35px;
border-radius:25px;
width:90%;
max-width:420px;
box-shadow:0 10px 30px rgba(0,0,0,.2);
}

h1{
color:#ff4081;
margin-bottom:25px;
}

button{
padding:12px 20px;
margin:8px;
border:none;
border-radius:30px;
font-size:18px;
cursor:pointer;
background:#ff5fa2;
color:white;
}

button:hover{
transform:scale(1.05);
}

.hidden{
display:none;
}

#final{
position:fixed;
inset:0;
display:none;
flex-direction:column;
justify-content:center;
align-items:center;
background:
linear-gradient(
180deg,
#ff7eb3,
#ffd86f
);
color:white;
animation:fade 1s;
}

.cake{
font-size:110px;
animation:bounce 1.4s infinite;
}

.note{
font-size:28px;
margin-top:20px;
padding:20px;
}

.star{
position:absolute;
font-size:28px;
animation:float 5s linear infinite;
}

.confetti{
position:absolute;
width:10px;
height:10px;
animation:fall 4s linear infinite;
}

@keyframes bounce{
50%{
transform:translateY(-20px);
}
}

@keyframes float{
0%{
transform:translateY(100vh);
}
100%{
transform:translateY(-100px);
}
}

@keyframes fall{
0%{
transform:translateY(-20px);
}
100%{
transform:translateY(100vh);
}
}

@keyframes fade{
from{
opacity:0;
}
to{
opacity:1;
}
}
</style>
</head>

<body>

<div class="box" id="screen1">

<h1>
Hey SAMIHA!<br>
Do u know what's today?
</h1>

<button onclick="yesTap()">Yes</button>

<button onclick="next1()">
No
</button>

<p id="msg"></p>

</div>

<div class="box hidden" id="screen2">

<h1>
It's ur birthday 🎇🎂
</h1>

<button onclick="endTap()">
Want to end
</button>

<button onclick="gift()">
Want the gift
</button>

<p id="msg2"></p>

</div>

<div id="final">

<div class="cake">
🎁🎂✨
</div>

<div class="note">
Happy birthday to u and many many returns of the day 💖
</div>

</div>

<script>

function yesTap(){
document.getElementById("msg").innerHTML=
"Think again 😏";
}

function next1(){
screen1.classList.add("hidden");
screen2.classList.remove("hidden");
}

function endTap(){
document.getElementById("msg2").innerHTML=
"Why! First take ur gift 🎁";
}

function gift(){

document.getElementById("screen2")
.classList.add("hidden");

document.getElementById("final")
.style.display="flex";

for(let i=0;i<80;i++){

let c=document.createElement("div");

c.className="confetti";

c.style.left=
Math.random()*100+"vw";

c.style.background=
`hsl(${Math.random()*360},100%,60%)`;

c.style.animationDuration=
(Math.random()*3+2)+"s";

document.body.appendChild(c);

}

for(let i=0;i<25;i++){

let s=document.createElement("div");

s.className="star";

s.innerHTML="⭐";

s.style.left=
Math.random()*100+"vw";

s.style.animationDuration=
(Math.random()*6+2)+"s";

document.body.appendChild(s);

}

}

</script>

</body>
</html>
