[Uploading index.html…]()
<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Вайб-кодер — портфолио</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Sans:wght@400;500&family=JetBrains+Mono:wght@400&family=Oswald:wght@500;600&display=swap" rel="stylesheet">
<style>
:root{--bg:#e4e7ec;--ink:#11141b;--mut:#4b5263;--co:#2b4dff;--line:rgba(17,20,27,.22);color-scheme:light;box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
html{scroll-padding-top:calc(env(safe-area-inset-top,0px) + 70px);scroll-behavior:smooth}
*,*::before,*::after{box-sizing:inherit;margin:0;padding:0}
body{background:repeating-linear-gradient(90deg,rgba(255,255,255,.2) 0 1px,transparent 1px 3px),linear-gradient(180deg,#eceef2,#dde1e8);background-color:var(--bg);color:var(--ink);font-family:"IBM Plex Sans",system-ui,-apple-system,"Segoe UI",sans-serif;font-size:17px;line-height:1.6;overflow-x:hidden}
#ch{position:fixed;inset:0;width:100%;height:100%;z-index:1;pointer-events:none;display:block}
header{position:fixed;top:0;left:0;right:0;z-index:5;display:flex;justify-content:space-between;align-items:center;padding:calc(env(safe-area-inset-top,0px) + 14px) clamp(46px,9vw,130px) 14px;background:linear-gradient(rgba(236,238,242,.95),rgba(236,238,242,0))}
.mark{font:600 20px Oswald,Impact,sans-serif;letter-spacing:.04em;color:var(--ink);text-decoration:none}
nav{display:flex;gap:clamp(14px,3vw,34px)}
nav a{color:var(--mut);text-decoration:none;font-size:15px;transition:color .25s}
nav a:hover{color:var(--co)}
a:focus-visible{outline:2px solid var(--co);outline-offset:4px;border-radius:4px}
main{position:relative;z-index:2;max-width:1280px;margin:0 auto;padding:0 clamp(46px,9vw,130px)}
h1,h2,h3{font-family:Oswald,Impact,"Arial Narrow",sans-serif;font-weight:600;text-transform:uppercase;letter-spacing:.01em}
#top{min-height:100vh;min-height:100svh;display:flex;flex-direction:column;justify-content:center;padding:110px 0 50px}
h1{font-size:clamp(54px,11vw,160px);line-height:.92}
.lead{margin-top:26px;max-width:46ch;font-size:clamp(16px,1.6vw,20px);color:var(--mut)}
.prompt{margin-top:38px;max-width:620px;border-radius:14px;padding:18px 22px;background:var(--ink);color:#eef1f8;font:400 clamp(14px,1.5vw,16px)/1.6 "JetBrains Mono",ui-monospace,Consolas,monospace;min-height:62px;box-shadow:0 18px 40px -18px rgba(17,20,27,.6)}
.prompt b{color:#8ea0ff;font-weight:400;margin-right:10px}
.prompt i{display:inline-block;width:.55em;height:1.1em;background:#8ea0ff;vertical-align:-.18em;margin-left:2px;animation:bl 1s steps(1) infinite}
@keyframes bl{50%{opacity:0}}
.chain{--w:64px;height:34px;background-image:var(--tile);background-repeat:repeat-x;background-size:var(--w) auto;animation:march 9s linear infinite;-webkit-mask-image:linear-gradient(90deg,transparent,#000 9%,#000 91%,transparent);mask-image:linear-gradient(90deg,transparent,#000 9%,#000 91%,transparent)}
.chain.sm{--w:32px;height:17px;animation-duration:7s}
.chain.rev{animation-direction:reverse}
@keyframes march{to{background-position-x:var(--w)}}
section{padding:clamp(54px,9vh,100px) 0}
h2{font-size:clamp(38px,6vw,80px);line-height:1;margin-bottom:14px}
.sub{color:var(--mut);max-width:50ch;margin-bottom:34px}
.row{display:grid;grid-template-columns:minmax(150px,.8fr) 2fr auto;gap:8px 32px;align-items:baseline;padding:24px 14px;transition:background .3s}
.row:hover{background:linear-gradient(90deg,rgba(43,77,255,.12),rgba(43,77,255,0))}
.row h3{font-size:clamp(26px,3vw,38px);line-height:1.1;transition:transform .3s,color .3s}
.row:hover h3{transform:translateX(8px);color:var(--co)}
.row p{color:var(--mut)}
.tags{list-style:none;display:flex;gap:8px;flex-wrap:wrap;justify-content:flex-end}
.tags li{font-size:13px;border:1px solid var(--line);border-radius:999px;padding:3px 12px;background:rgba(255,255,255,.45)}
.steps{display:grid;grid-template-columns:repeat(3,1fr);gap:30px}
.step{padding-top:20px;border-top:4px solid var(--ink)}
.step h3{font-size:28px;margin-bottom:8px}
.step p{color:var(--mut)}
.chips{display:flex;flex-wrap:wrap;gap:10px;margin-top:44px}
.chips span{border:1px solid var(--line);border-radius:999px;padding:8px 18px;background:rgba(255,255,255,.5);font-size:15px}
#hello h2{font-size:clamp(42px,8vw,110px);max-width:12em}
.links{display:flex;flex-wrap:wrap;gap:14px;margin-top:30px}
.btn{display:inline-block;text-decoration:none;padding:15px 30px;border-radius:999px;border:2px solid var(--ink);color:var(--ink);font-weight:500;transition:background .25s,color .25s,border-color .25s}
.btn:hover{border-color:var(--co);color:var(--co)}
.btn.main{background:var(--ink);color:#fff}
.btn.main:hover{background:var(--co);border-color:var(--co);color:#fff}
footer{padding:50px 0 70px;color:var(--mut);font-size:14px}
@media (max-width:760px){.row{grid-template-columns:1fr}.tags{justify-content:flex-start}.steps{grid-template-columns:1fr}}
@media (prefers-reduced-motion:reduce){html{scroll-behavior:auto}.chain,.prompt i{animation:none}}
</style>
</head>
<body>
<canvas id="ch" aria-hidden="true"></canvas>
<header>
  <a class="mark" href="#top">Твоё имя</a>
  <nav aria-label="Разделы"><a href="#work">Проекты</a><a href="#flow">Процесс</a><a href="#hello">Связаться</a></nav>
</header>
<main>
  <section id="top">
    <h1>Говорю идею.<br>Получаю продукт.</h1>
    <p class="lead">Я вайб-кодер: собираю плагины, сайты и интерфейсы вместе с ИИ. Идея, вкус и проверка результата остаются за мной.</p>
    <div class="prompt" aria-label="Пример запроса"><b>&gt;</b><span id="typ"></span><i></i></div>
  </section>

  <div class="chain" role="presentation"></div>

  <section id="work">
    <h2>Проекты</h2>
    <p class="sub">Всё это собрано в диалоге с ИИ: от первой идеи до рабочей версии.</p>
    <div class="chain sm" role="presentation"></div>
    <article class="row"><h3>RMenu</h3><p>Меню сервера для Rust по моим скриншотам: оформление, разделы и кнопки как в референсе.</p><ul class="tags"><li>C#</li><li>Oxide</li><li>CUI</li></ul></article>
    <div class="chain sm rev" role="presentation"></div>
    <article class="row"><h3>RAdminMenu</h3><p>Админ-меню для Rust-сервера, собранное с нуля: быстрые действия без команд в консоли.</p><ul class="tags"><li>C#</li><li>Oxide</li><li>CUI</li></ul></article>
    <div class="chain sm" role="presentation"></div>
    <article class="row"><h3>WipeBlock</h3><p>Красивое GUI-меню /block, переделанное на основе готового плагина.</p><ul class="tags"><li>C#</li><li>GUI</li></ul></article>
    <div class="chain sm rev" role="presentation"></div>
    <article class="row"><h3>GameStores</h3><p>Сайт для продажи игровых ресурсов Rust: каталог, оформление и понятный путь к покупке.</p><ul class="tags"><li>HTML</li><li>CSS</li><li>JavaScript</li></ul></article>
    <div class="chain sm" role="presentation"></div>
  </section>

  <div class="chain rev" role="presentation"></div>

  <section id="flow">
    <h2>Как я работаю</h2>
    <p class="sub">Три шага, которые повторяются, пока результат не станет таким, каким я его вижу.</p>
    <div class="steps">
      <div class="step"><h3>Описываю</h3><p>Формулирую задачу простыми словами и показываю референс: скриншот, пример, набросок.</p></div>
      <div class="step"><h3>Итерирую</h3><p>ИИ пишет код, я смотрю на результат и прошу поправить, пока не совпадёт с задумкой.</p></div>
      <div class="step"><h3>Проверяю</h3><p>Собираю проект, тестирую на сервере и только после этого выкладываю.</p></div>
    </div>
    <div class="chips"><span>Claude Code</span><span>VS Code</span><span>C#</span><span>Rust</span><span>Oxide</span><span>HTML, CSS, JS</span></div>
  </section>

  <div class="chain" role="presentation"></div>

  <section id="hello">
    <h2>Есть идея? Соберём её вместе</h2>
    <p class="sub">Напиши, что нужно сделать, и пришли пример, если он есть. Отвечу и скажу, как быстро это получится.</p>
    <div class="links"><a class="btn main" href="mailto:you@example.com">you@example.com</a><a class="btn" href="https://t.me/yourname">Telegram</a></div>
  </section>
  <footer>Страница сделана вместе с Claude.</footer>
</main>
<script>
(()=>{
const reduce=matchMedia('(prefers-reduced-motion: reduce)').matches;
const mobile=innerWidth<700;

// Контур овального звена
function stad(c,len,w){const r=w/2,l=len/2-r;c.beginPath();c.moveTo(-l,-r);c.lineTo(l,-r);c.arc(l,0,r,-Math.PI/2,Math.PI/2);c.lineTo(-l,r);c.arc(-l,0,r,Math.PI/2,Math.PI*1.5);c.closePath();}
// Одно звено: face=true — звено анфас (кольцо), false — звено ребром (брусок)
function link(c,cx,cy,len,w,t,ang,face){
  c.save();c.translate(cx,cy);c.rotate(ang);
  const e=t*1.9,hh=face?w:e,g=c.createLinearGradient(0,-hh/2,0,hh/2);
  [[0,'#232833'],[.3,'#9aa3b5'],[.45,'#ffffff'],[.65,'#6c7488'],[1,'#12151c']].forEach(s=>g.addColorStop(s[0],s[1]));
  if(face){stad(c,len,w-t);c.lineWidth=t+2.4;c.strokeStyle='#0d1016';c.stroke();c.lineWidth=t;c.strokeStyle=g;c.stroke();}
  else{stad(c,len+2,e+2);c.fillStyle='#0d1016';c.fill();stad(c,len,e);c.fillStyle=g;c.fill();}
  c.restore();
}

// Плитка бегущей цепи для разделителей
(function(){
  const k=2,t=document.createElement('canvas');t.width=64*k;t.height=34*k;
  const g=t.getContext('2d');g.scale(k,k);
  link(g,56,17,40,22,4.6,0,false);link(g,-8,17,40,22,4.6,0,false);link(g,24,17,40,22,4.6,0,true);
  document.documentElement.style.setProperty('--tile','url('+t.toDataURL()+')');
})();

// Свисающие цепи по бокам (верле-физика)
const cv=document.getElementById('ch'),c=cv.getContext('2d');
const SEG=mobile?21:27,LEN=SEG*1.38,WID=SEG*.8,TH=SEG*.17;
let W,H,D,chains=[],mx=-999,my=-999,t=0,kick=0,lastY=scrollY;
function build(){
  D=Math.min(devicePixelRatio||1,2);W=innerWidth;H=innerHeight;
  cv.width=W*D;cv.height=H*D;c.setTransform(D,0,0,D,0,0);
  const gx=mobile?16:Math.min(56,Math.max(26,W*.035)),n=Math.floor(H*.9/SEG);
  chains=[[gx,1],[W-gx,-1]].map(([x,dir],k)=>{
    const pts=[];for(let i=0;i<=n;i++)pts.push({x:x,y:-30+i*SEG,px:x-dir*i*.06,py:-30+i*SEG});
    return {x:x,pts:pts,ph:k*2};
  });
  if(reduce){for(let i=0;i<260;i++)sim();draw();}
}
function sim(){
  t+=.016;kick*=.9;
  for(const ch of chains){
    const p=ch.pts,n=p.length;
    for(let i=1;i<n;i++){
      const q=p[i],vx=(q.x-q.px)*.993,vy=(q.y-q.py)*.993;
      q.px=q.x;q.py=q.y;
      q.x+=vx+(reduce?0:Math.sin(t*.7+i*.18+ch.ph)*.035+kick*(i/n));
      q.y+=vy+.55;
      const dx=q.x-mx,dy=q.y-my,d=Math.hypot(dx,dy);
      if(d<110&&d>.01){const f=(1-d/110)*2.2;q.x+=dx/d*f;q.y+=dy/d*f*.5;}
    }
    for(let it=0;it<16;it++){
      p[0].x=ch.x;p[0].y=-30;
      for(let i=0;i<n-1;i++){
        const a=p[i],b=p[i+1],dx=b.x-a.x,dy=b.y-a.y,d=Math.hypot(dx,dy)||.001,df=(d-SEG)/d;
        if(i===0){b.x-=dx*df;b.y-=dy*df;}
        else{a.x+=dx*df*.5;a.y+=dy*df*.5;b.x-=dx*df*.5;b.y-=dy*df*.5;}
      }
    }
  }
}
function draw(){
  c.clearRect(0,0,W,H);
  for(const ch of chains){
    const p=ch.pts,n=p.length;
    for(const face of [false,true])
      for(let i=0;i<n-1;i++){
        if((i%2===0)!==face)continue;
        const a=p[i],b=p[i+1];
        link(c,(a.x+b.x)/2,(a.y+b.y)/2,LEN,WID,TH,Math.atan2(b.y-a.y,b.x-a.x),face);
      }
    const e=p[n-1],gl=c.createRadialGradient(e.x,e.y,2,e.x,e.y,46);
    gl.addColorStop(0,'rgba(43,77,255,.55)');gl.addColorStop(1,'rgba(43,77,255,0)');
    c.fillStyle=gl;c.fillRect(e.x-46,e.y-46,92,92);
    link(c,e.x,e.y,SEG*1.25,SEG*1.25,TH*1.2,0,true);
  }
}
addEventListener('pointermove',e=>{mx=e.clientX;my=e.clientY;},{passive:true});
addEventListener('pointerleave',()=>{mx=my=-999;});
addEventListener('scroll',()=>{kick+=(scrollY-lastY)*.004;kick=Math.max(-1.2,Math.min(1.2,kick));lastY=scrollY;},{passive:true});
let rt;addEventListener('resize',()=>{clearTimeout(rt);rt=setTimeout(build,200);});
build();
if(!reduce){(function loop(){sim();draw();requestAnimationFrame(loop);})();}

// Печатающийся запрос
const T=['сделай админ-меню для Rust-сервера','добавь красивый GUI в плагин','нужен сайт магазина игровых ресурсов','исправь ошибку компиляции и объясни почему'];
const el=document.getElementById('typ');
if(reduce){el.textContent=T[0];}else{
  let i=0,j=0,del=false;
  (function tick(){
    const s=T[i];
    if(!del){j++;el.textContent=s.slice(0,j);if(j>=s.length){del=true;return setTimeout(tick,1900);}}
    else{j-=2;if(j<=0){j=0;del=false;i=(i+1)%T.length;el.textContent='';return setTimeout(tick,450);}el.textContent=s.slice(0,j);}
    setTimeout(tick,del?22:55);
  })();
}
})();
</script>
</body>
</html>
