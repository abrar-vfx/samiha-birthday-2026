<!DOCTYPE html>
<html>

<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Happy Birthday Samiha 🎂</title>

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Arial;
}

body{
height:100vh;
display:flex;
justify-content:center;
align-items:center;
background:linear-gradient(135deg,#f8c6ff,#c9f5ff);
overflow:hidden;
text-align:center;
}

.box{
background:white;
padding:35px;
width:90%;
max-width:420px;
border-radius:25px;
box-shadow:0 10px 30px rgba(0,0,0,.2);
}

h1{
color:#ff3f88;
margin-bottom:20px;
}

button{

padding:12px 22px;

border:none;

border-radius:25px;

margin:8px;

background:#ff4f98;

color:white;

font-size:18px;

cursor:pointer;

}

.hidden{
display:none;
}

#final{

display:none;

position:fixed;

inset:0;

flex-direction:column;

justify-content:center;

align-items:center;

color:white;

background:
linear-gradient(
180deg,
#ff75b5,
#ffd86b
);

}

.note{

font-size:28px;

padding:25px;

}

.cake{

font-size:120px;

animation:bounce 1.5s infinite;

}

.star{

position:absolute;

font-size:28px;

animation:up 5s linear infinite;

}

.confetti{

position:absolute;

width:10px;

height:10px;

animation:fall 4s linear infinite;

}

@keyframes bounce{

50%{
transform:
translateY(-18px);
}

}

@keyframes up{

0%{
transform:
translateY(100vh);
}

100%{
transform:
translateY(-100px);
}

}

@keyframes fall{

0%{
transform:
translateY(-20px);
}

100%{
transform:
translateY(100vh);
}

}

</style>

</head>

<body>

<div
class="box"
id="page1">

<h1>
Hey SAMIHA!<br>
Do u know what's today?
</h1>

<button
onclick="yesTap()">
Yes
</button>

<button
onclick="goNext()">
No
</button>

<p id="text1"></p>

</div>


<div
class="box hidden"
id="page2">

<h1>
It's ur birthday 🎇🎂
</h1>

<button
onclick="endTap()">
Want to end
</button>

<button
onclick="gift()">
Want the gift
</button>

<p id="text2"></p>

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

document
.getElementById(
"text1"
)
.innerHTML=
"Think again 😏";

}

function goNext(){

page1
.classList
.add(
"hidden"
);

page2
.classList
.remove(
"hidden"
);

}

function endTap(){

document
.getElementById(
"text2"
)
.innerHTML=
"Why! First take ur gift 🎁";

}

function gift(){

page2
.classList
.add(
"hidden"
);

final
.style
.display=
"flex";

for(
let i=0;
i<80;
i++
){

let c=
document
.createElement(
"div"
);

c.className=
"confetti";

c.style.left=
Math.random()*100
+"vw";

c.style.background=
`hsl(
${Math.random()*360},
100%,
60%
)`;

c.style.animationDuration=
(
Math.random()*3
+2
)
+"s";

document.body
.appendChild(c);

}

for(
let i=0;
i<30;
i++
){

let s=
document
.createElement(
"div"
);

s.className=
"star";

s.innerHTML=
"⭐";

s.style.left=
Math.random()*100
+"vw";

document.body
.appendChild(s);

}

}

</script>

</body>

</html>
