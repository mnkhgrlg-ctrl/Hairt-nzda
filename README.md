# Hairt-nzda
<!naiz ci bol nz html>
<html lang="mn">
<head>
<meta charset="UTF-8">
<title>😎 Найздаа зориулав</title>

<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:'Segoe UI',sans-serif}

body{
  height:100vh;
  background:
    linear-gradient(rgba(0,0,0,.6),rgba(0,0,0,.6)),
    url("https://images.unsplash.com/photo-1519681393784-d120267933ba");
  background-size:cover;
  background-position:center;
  overflow:hidden;
  color:white;
}

/* CENTER */
.center{
  position:absolute;
  top:50%;
  left:50%;
  transform:translate(-50%,-50%);
  text-align:center;
}

/* INPUT */
input{
  padding:12px 18px;
  border-radius:10px;
  border:none;
  font-size:18px;
}

/* BUTTON */
button{
  padding:12px 22px;
  border:none;
  border-radius:10px;
  background:#00ffaa;
  color:black;
  font-size:18px;
  cursor:pointer;
}

/* GIFT */
#gift{
  font-size:150px;
  cursor:pointer;
  display:none;
  transition:.5s;
}
#gift.open{
  transform:scale(1.2) rotate(10deg);
}

/* TEXT */
#text{
  font-size:45px;
  margin-top:25px;
  display:none;
  animation:fade 2s forwards;
}
@keyframes fade{
  from{opacity:0;transform:translateY(40px)}
  to{opacity:1;transform:translateY(0)}
}

/* FLOAT TEXT */
.float{
  position:absolute;
  bottom:-40px;
  font-size:22px;
  animation:fly 8s linear forwards;
}
@keyframes fly{
  to{
    transform:translateY(-120vh);
    opacity:0;
  }
}

/* FIREWORK */
.fire{
  position:absolute;
  width:6px;
  height:6px;
  background:white;
  border-radius:50%;
  animation:boom 2s forwards;
}
@keyframes boom{
  to{transform:scale(40);opacity:0}
}
</style>
</head>

<body>

<div class="center">

<div id="codeBox">
  <p>🔐 Найзын код оруул</p><br>
  <input id="code" placeholder="Code..."><br><br>
  <button onclick="check()">bro</button>
  <p style="font-size:14px;opacity:.7;margin-top:10px">
    Hint: <b>psdamn</b> 😎
  </p>
</div>

<div id="gift" onclick="openGift()">🎁</div>
<div id="text">🔥 chi bol jinken teneg al😂 🔥</div>

</div>

<script>
let opened = false;

// "psdamn" base64 encrypt (nuuts bolgoson)
const _x = ["cHNkYW1u"];
const secret = atob(_x[0]);

function check(){
  let code = document.getElementById("code").value.trim();

  if(code === secret){
    document.getElementById("codeBox").style.display="none";
    document.getElementById("gift").style.display="block";
  }else{
    alert("❌ Буруу код байна 😂");
  }
}

function openGift(){
  if(opened) return;
  opened = true;

  document.getElementById("gift").classList.add("open");
  fireworks();

  setTimeout(()=>{
    document.getElementById("text").style.display="block";
    startFloat();
  },1500);
}

/* FIREWORK */
function fireworks(){
  for(let i=0;i<12;i++){
    const f=document.createElement("div");
    f.className="fire";
    f.style.left=Math.random()*100+"%";
    f.style.top=Math.random()*70+"%";
    document.body.appendChild(f);
    setTimeout(()=>f.remove(),2000);
  }
}

/* FRIEND FLOAT WORDS */
const words=[
"😂 АЛНА ШҮҮ",
"huhai zambal al",
"ci bur uhchiisen suga bsda",
"haltar naraashde ci",
"bulshan deerchin bujiglene",
"arhichn gicii",
"chiheldej uhsen jinger",
"mal har pussy",
"erhuu gicii",
"zail almn",
];

function startFloat(){
  words.forEach((w,i)=>{
    setTimeout(()=>{
      const d=document.createElement("div");
      d.className="float";
      d.innerText=w;
      d.style.left=Math.random()*85+"%";
      document.body.appendChild(d);
      setTimeout(()=>d.remove(),8000);
    },i*400);
  });
}
</script>

</body>
</html>
