<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Hack Screen</title>

<style>
body{
  margin:0;
  background:black;
  overflow:hidden;
  font-family:monospace;
}

/* ตัวเลขวิ่ง */
canvas{
  position:absolute;
  top:0;
  left:0;
}

/* SLUR */
.title{
  position:absolute;
  width:100%;
  text-align:center;
  top:25%;
  font-size:120px;
  font-weight:bold;
  color:#000;
  text-shadow:
    0 0 10px red,
    0 0 40px red,
    0 0 80px red;
  z-index:2;
}

/* โหลดบาร์ */
.barBox{
  position:absolute;
  bottom:80px;
  width:100%;
  text-align:center;
  z-index:2;
}

.bar{
  width:60%;
  height:35px;
  margin:auto;
  border:2px solid #ff0000;
  box-shadow:0 0 15px #ff0000;
  position:relative;
}

.fill{
  height:100%;
  width:0%;
  background:#00ff00;
  box-shadow:0 0 20px #ff0000;
}

.text{
  position:absolute;
  width:100%;
  top:6px;
  color:#00ff00;
  font-weight:bold;
}
</style>
</head>
<body>

<canvas id="matrix"></canvas>

<div class="title">SLUR</div>

<div class="barBox">
  <div class="bar">
    <div class="fill" id="load"></div>
    <div class="text">ACCESSING SYSTEM...</div>
  </div>
</div>

<script>
/* MATRIX EFFECT */
let c = document.getElementById("matrix");
let ctx = c.getContext("2d");

c.height = window.innerHeight;
c.width = window.innerWidth;

let letters = "01";
letters = letters.split("");

let fontSize = 14;
let columns = c.width/fontSize;

let drops = [];
for(let x=0;x<columns;x++)
  drops[x]=1;

function draw(){
  ctx.fillStyle="rgba(0,0,0,0.05)";
  ctx.fillRect(0,0,c.width,c.height);

  ctx.fillStyle="rgb(255, 0, 0)";
  ctx.font=fontSize+"px monospace";

  for(let i=0;i<drops.length;i++){
    let text = letters[Math.floor(Math.random()*letters.length)];
    ctx.fillText(text,i*fontSize,drops[i]*fontSize);

    if(drops[i]*fontSize>c.height && Math.random()>0.975)
      drops[i]=0;

    drops[i]++;
  }
}
setInterval(draw,33);


/* LOAD BAR */
let bar=document.getElementById("load");
let w=0;
let loading=setInterval(()=>{
  if(w>=100) clearInterval(loading);
  else{
    w++;
    bar.style.width=w+"%";
  }
},60);
</script>

</body>
</html>
