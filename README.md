<!DOCTYPE html><html lang="en">
<head>
<meta charset="UTF-8">
<title>For My Wifey ❤️</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
*{box-sizing:border-box}
body{
  margin:0; height:100vh; overflow:hidden;
  font-family:'Segoe UI',Arial,sans-serif;
  background:linear-gradient(180deg,#0b132b,#1c2541,#3a506b);
  color:white;
}
.section{position:absolute; inset:0; display:none; justify-content:center; align-items:center; text-align:center; padding:20px}
.active{display:flex}/* BOOK */ .book{ background:rgba(255,255,255,0.08); backdrop-filter:blur(6px); border-radius:26px; padding:32px; max-width:520px; width:90%; box-shadow:0 0 40px rgba(255,154,203,.45); } .page{font-size:1.6em; line-height:1.7; animation:fade .9s} .tap{margin-top:18px; opacity:.7; font-size:.9em} @keyframes fade{from{opacity:0}to{opacity:1}}

/* VIDEO */ .name{font-size:4em; text-shadow:0 0 40px #ff9acb} .msg{font-size:1.7em; margin-top:22px; opacity:0; transition:opacity 2s}

/* HEARTS */ .heart{position:absolute; font-size:22px; animation:float 9s linear infinite} @keyframes float{0%{transform:translateY(110vh);opacity:1}100%{transform:translateY(-10vh);opacity:0}}

/* PROPOSAL */ button{font-size:1.3em; padding:14px 34px; margin:14px; border:none; border-radius:40px; cursor:pointer} .yes{background:#ff7eb3; color:white; box-shadow:0 0 20px #ff7eb3} .no{background:#444; color:white; position:relative}

/* CELEBRATION */ .burst{position:absolute; font-size:26px; animation:pop 3.5s forwards} @keyframes pop{from{transform:scale(.6);opacity:1}to{transform:scale(3);opacity:0}}

.final{font-size:2em; animation:fade 2s} </style>

</head>
<body><!-- BOOK --><div class="section active" id="book">
  <div class="book">
    <div class="page" id="pageText"></div>
    <div class="tap">Tap anywhere to turn the page 📖</div>
  </div>
</div><!-- VIDEO --><div class="section" id="video">
  <div>
    <div class="name" id="name"></div>
    <div class="msg" id="vmsg">You are my peace, my excitement, my forever 🫶</div>
  </div>
</div><!-- PROPOSAL --><div class="section" id="proposal">
  <div>
    <h1 style="font-size:2.4em">Will you marry me? 💍❤️</h1>
    <button class="yes" id="yesBtn">YES 💖</button>
    <button class="no" id="noBtn">NO 🙈</button>
  </div>
</div><!-- FINAL --><div class="section" id="final">
  <div class="final">This is just the beginning of us… 💞<br>Forever with you, Wifey ❤️</div>
</div><audio id="music" loop>
  <source src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_2b3f9c44e4.mp3">
</audio><script>
const book=document.getElementById('book');
const video=document.getElementById('video');
const proposal=document.getElementById('proposal');
const final=document.getElementById('final');
const pageText=document.getElementById('pageText');
const nameEl=document.getElementById('name');
const vmsg=document.getElementById('vmsg');
const yesBtn=document.getElementById('yesBtn');
const noBtn=document.getElementById('noBtn');
const music=document.getElementById('music');

const pages=[
 "This is not just a story… it’s my heart speaking to you ❤️",
 "You changed my life without trying, just by being you ✨",
 "Every smile of yours feels like a promise of happiness 🫶",
 "No matter where life takes us, my place is beside you 💫",
 "So I made this… because you deserve something special"
];
let p=0; pageText.innerHTML=pages[p];
book.onclick=()=>{
  p++;
  if(p<pages.length){pageText.innerHTML=pages[p];}
  else{book.classList.remove('active');video.classList.add('active');startVideo();}
};

const nameText="Wifey ❤️"; let i=0;
function startVideo(){
  music.play();
  function type(){
    if(i<nameText.length){nameEl.innerHTML+=nameText.charAt(i++);setTimeout(type,180);} 
    else{
      setTimeout(()=>vmsg.style.opacity=1,900);
      setTimeout(()=>{video.classList.remove('active');proposal.classList.add('active');},6500);
    }
  }
  type();
}

setInterval(()=>{
  const h=document.createElement('div');h.className='heart';h.innerHTML='💖';
  h.style.left=Math.random()*100+'vw';document.body.appendChild(h);
  setTimeout(()=>h.remove(),9000);
},320);

noBtn.onclick=()=>{
  noBtn.style.transform=`translate(${Math.random()*140-70}px,${Math.random()*100-50}px)`;
};

yesBtn.onclick=()=>{
  proposal.classList.remove('active');final.classList.add('active');
  for(let k=0;k<60;k++){
    const b=document.createElement('div');b.className='burst';b.innerHTML='🎉💖✨';
    b.style.left=Math.random()*100+'vw';b.style.top=Math.random()*100+'vh';
    document.body.appendChild(b);setTimeout(()=>b.remove(),3500);
  }
};
</script></body>
</html>
