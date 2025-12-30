<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, viewport-fit=cover" />
<title>Happy New Year 2026</title>

<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;800&family=Pacifico&display=swap" rel="stylesheet">

<style>
:root{
  --vh:100vh;
}
html,body{
  margin:0;
  padding:0;
  height:100%;
  background:#050812;
  font-family:Montserrat,system-ui,Arial;
  overflow:hidden;
  color:#fff;
}

/* ===== START SCREEN ===== */
.name-overlay{
  position:fixed;
  inset:0;
  background:
    linear-gradient(rgba(0,0,0,.35),rgba(0,0,0,.55)),
    url("https://static.vecteezy.com/system/resources/previews/030/201/671/large_2x/beautiful-winter-snowman-for-new-year-and-christmas-free-photo.jpg");
  background-size:cover;
  background-position:center;
  display:flex;
  flex-direction:column;
  justify-content:center;
  align-items:center;
  gap:18px;
  z-index:100;
  padding:20px;
  text-align:center;
}

#nameInput{
  width:85%;
  max-width:280px;
  padding:12px;
  font-size:16px;
  border-radius:10px;
  border:none;
  text-align:center;
}

#submitName{
  padding:12px 26px;
  font-size:16px;
  border:none;
  border-radius:14px;
  background:#ff66b2;
  color:#fff;
  font-weight:700;
}

/* ===== MAIN VIEW ===== */
.reel-root{
  width:100%;
  height:calc(var(--vh) * 100);
  display:none;
  justify-content:center;
  align-items:center;
}

/* ===== CARD ===== */
.card{
  width:94%;
  height:94%;
  background:rgba(255,255,255,.06);
  border-radius:24px;
  padding:20px;
  backdrop-filter:blur(10px);
  display:flex;
  flex-direction:column;
  justify-content:space-between;
  align-items:center;
  z-index:10;
}

.to{
  font-family:Pacifico;
  font-size:30px;
  text-align:center;
}
.subtitle{
  font-size:13px;
  opacity:.8;
  text-align:center;
}

.messages{
  height:22%;
  display:flex;
  justify-content:center;
  align-items:center;
}

.typewriter{
  font-size:16px;
  text-align:center;
  padding:0 10px;
}
.cursor{
  display:inline-block;
  width:6px;
  height:18px;
  background:#fff;
  margin-left:4px;
  animation:blink 1s infinite;
}
@keyframes blink{50%{opacity:0}}

.progress{
  width:85%;
  height:5px;
  background:rgba(255,255,255,.2);
  border-radius:99px;
  overflow:hidden;
}
.progress i{
  display:block;
  height:100%;
  width:0%;
  background:linear-gradient(90deg,#ff66b2,#ffd166);
}

.credits{
  font-size:10px;
  opacity:.6;
}

/* ===== SNOWMEN ===== */
.emoji-snowman{
  position:fixed;
  bottom:70px;
  font-size:130px;
  z-index:6;
  display:none;
  pointer-events:none;
}
.emoji-snowman.left{left:-40px}
.emoji-snowman.right{right:-40px}

/* ===== SNOW ===== */
.snow,.snow-emoji{
  position:absolute;
  animation:fall linear infinite;
}
.snow{
  background:radial-gradient(circle,#fff,#e6f2ff);
  border-radius:50%;
}
.snow-emoji{
  font-size:16px;
}
@keyframes fall{to{transform:translateY(120vh)}}

/* ===== BALLOONS ===== */
.balloon{
  position:absolute;
  width:34px;
  height:50px;
  border-radius:50%;
  animation:floatUp linear infinite;
  z-index:7;
}
.balloon::after{
  content:"";
  position:absolute;
  top:38px;
  left:50%;
  width:1px;
  height:35px;
  background:rgba(255,255,255,.6);
}
@keyframes floatUp{
  from{transform:translateY(70vh)}
  to{transform:translateY(-120vh) translateX(var(--drift))}
}

/* ===== FIREWORKS ===== */
.firework{
  position:absolute;
  width:4px;
  height:4px;
  animation:shoot 2.5s linear forwards;
}
@keyframes shoot{to{transform:translateY(-80vh)}}
.burst{
  position:absolute;
  width:10px;
  height:10px;
  border-radius:50%;
  animation:explode 1s ease-out forwards;
}
@keyframes explode{
  to{transform:translate(var(--x),var(--y)) scale(0);opacity:0}
}
</style>
</head>

<body>

<div class="name-overlay" id="nameOverlay">
  <div style="font-size:18px">Enter Your Name</div>
  <input id="nameInput" placeholder="Your name">
  <button id="submitName">Start</button>
</div>

<div class="emoji-snowman left">⛄</div>
<div class="emoji-snowman right">⛄</div>

<div class="reel-root" id="reel">
  <div class="card">
    <div>
      <div class="to" id="toText">Happy New Year 2026 🎆</div>
      <div class="subtitle">A fresh beginning ❄️</div>
    </div>
        <div class="messages">
      <div class="typewriter">
        <span id="messageText"></span><span class="cursor"></span>
      </div>
    </div>

  <div style="width:100%;display:flex;flex-direction:column;align-items:center;gap:8px">
      <div class="progress"><i id="progressFill"></i></div>
      <div class="credits">Made with ❤️ by Shivmangal Singh</div>
    </div>
</div>
</div>

<script>
function fixVH(){
  document.documentElement.style.setProperty("--vh", window.innerHeight*0.01 + "px");
}
fixVH();
window.addEventListener("resize",fixVH);

const submitBtn=document.getElementById("submitName");
const nameInput=document.getElementById("nameInput");
const overlay=document.getElementById("nameOverlay");
const reel=document.getElementById("reel");
const toText=document.getElementById("toText");
const msg=document.getElementById("messageText");
const bar=document.getElementById("progressFill");
const snowmen=document.querySelectorAll(".emoji-snowman");

const messages=[
"As 2026 begins, may peace fill your heart ❤️",
"Keep believing in yourself ✨",
"Grow stronger every day 💪",
"Respect your parents 🙏",
"Work hard and stay humble 🌱",
"2026 is your fresh beginning 🌅"
];

submitBtn.onclick=()=>{
  if(!nameInput.value.trim())return;
  toText.textContent=`Happy New Year 2026, ${nameInput.value} 🎆`;
  overlay.style.display="none";
  reel.style.display="flex";
  snowmen.forEach(s=>s.style.display="block");
  startSnow();
  startEmojiSnow();
  startBalloons();
  startFireworks();
  runMessages();
};

async function runMessages(){
  for(let t of messages){
    msg.textContent="";
    bar.style.width="0%";
    for(let i=0;i<t.length;i++){
      msg.textContent+=t[i];
      bar.style.width=((i+1)/t.length*100)+"%";
      await new Promise(r=>setTimeout(r,35));
    }
    await new Promise(r=>setTimeout(r,1200));
  }
}

function startSnow(){
  for(let i=0;i<120;i++){
    const s=document.createElement("div");
    s.className="snow";
    const size=Math.random()*3+2;
    s.style.width=s.style.height=size+"px";
    s.style.left=Math.random()*100+"vw";
    s.style.top="-10vh";
    s.style.animationDuration=(18+Math.random()*12)+"s";
    document.body.appendChild(s);
  }
}
function startEmojiSnow(){
  for(let i=0;i<30;i++){
    const e=document.createElement("div");
    e.className="snow-emoji";
    e.textContent="❄️";
    e.style.left=Math.random()*100+"vw";
    e.style.top="-10vh";
    e.style.animationDuration=(22+Math.random()*12)+"s";
    document.body.appendChild(e);
  }
}
function startBalloons(){
  createBalloon();
  setInterval(createBalloon,900);
}
function createBalloon(){
  const b=document.createElement("div");
  b.className="balloon";
  b.style.left=Math.random()*100+"vw";
  b.style.setProperty("--drift",(Math.random()*30-15)+"px");
  b.style.animationDuration=(18+Math.random()*4)+"s";
  b.style.animationDelay="-6s";
  b.style.background=`radial-gradient(circle,#fff,hsl(${Math.random()*360},90%,60%))`;
  document.body.appendChild(b);
  setTimeout(()=>b.remove(),30000);
}
function startFireworks(){
  setInterval(()=>{
    const f=document.createElement("div");
    f.className="firework";
    f.style.left=Math.random()*100+"vw";
    f.style.bottom="0";
    document.body.appendChild(f);
    setTimeout(()=>{
      for(let i=0;i<50;i++){
        const b=document.createElement("div");
        b.className="burst";
        b.style.left=f.style.left;
        b.style.top=Math.random()*60+"vh";
        b.style.background=`hsl(${Math.random()*360},100%,65%)`;
        b.style.setProperty("--x",(Math.random()*300-150)+"px");
        b.style.setProperty("--y",(Math.random()*300-150)+"px");
        document.body.appendChild(b);
        setTimeout(()=>b.remove(),1000);
      }
      f.remove();
    },2000);
  },1600);
}
</script>

</body>
</html>
