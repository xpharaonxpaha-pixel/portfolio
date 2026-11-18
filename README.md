[Uploading Портфолио вайб-кодера.html…]()
<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Вайб-кодер — портфолио</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400&family=Onest:wght@400;500&family=Unbounded:wght@300;500&display=swap" rel="stylesheet">
<style>
:root{--bg:#0b0716;--fg:#f4efff;--mut:#a79fc4;--vi:#8b5cff;--mi:#28e0c8;--pe:#ff9e7a;--line:rgba(244,239,255,.14);color-scheme:dark;box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
html{scroll-padding-top:calc(env(safe-area-inset-top,0px) + 70px);scroll-behavior:smooth}
*,*::before,*::after{box-sizing:inherit;margin:0;padding:0}
body{background:var(--bg);color:var(--fg);font-family:Onest,system-ui,-apple-system,"Segoe UI",sans-serif;font-size:17px;line-height:1.6;overflow-x:hidden;-webkit-font-smoothing:antialiased}
#bg{position:fixed;inset:0;width:100%;height:100%;z-index:0;display:block}
.code{position:fixed;inset:0;z-index:1;display:flex;justify-content:space-around;overflow:hidden;opacity:.1;pointer-events:none;font:400 13px/2 "JetBrains Mono",ui-monospace,Consolas,monospace;color:var(--mut);white-space:nowrap}
.code div{animation:up 80s linear infinite}
.code div:nth-child(2){animation-duration:110s}.code div:nth-child(3){animation-duration:95s}.code div:nth-child(4){animation-duration:130s}
@keyframes up{to{transform:translateY(-50%)}}
.shade{position:fixed;inset:0;z-index:1;pointer-events:none;background:radial-gradient(ellipse at 30% 40%,rgba(11,7,22,.55),rgba(11,7,22,.2) 60%,rgba(11,7,22,.55))}
header{position:fixed;top:0;left:0;right:0;z-index:5;display:flex;justify-content:space-between;align-items:center;padding:calc(env(safe-area-inset-top,0px) + 16px) clamp(20px,5vw,64px) 16px;background:linear-gradient(rgba(11,7,22,.85),rgba(11,7,22,0))}
.mark{font:500 15px Unbounded,system-ui,sans-serif;color:var(--fg);text-decoration:none}
nav{display:flex;gap:clamp(14px,3vw,34px)}
nav a{color:var(--mut);text-decoration:none;font-size:15px;transition:color .25s}
nav a:hover{color:var(--fg)}
a:focus-visible{outline:2px solid var(--mi);outline-offset:4px;border-radius:4px}
main{position:relative;z-index:2;max-width:1180px;margin:0 auto;padding:0 clamp(20px,5vw,64px)}
#top{min-height:100vh;min-height:100svh;display:flex;flex-direction:column;justify-content:center;padding:110px 0 60px}
h1,h2,h3{font-family:Unbounded,system-ui,sans-serif;font-weight:300;letter-spacing:-.02em}
h1{font-size:clamp(34px,6.2vw,88px);line-height:1.05;max-width:15em}
.lead{margin-top:28px;max-width:46ch;font-size:clamp(16px,1.6vw,20px);color:var(--mut)}
.prompt{margin-top:44px;max-width:640px;border:1px solid var(--line);border-radius:18px;padding:20px 22px;background:rgba(20,12,40,.55);-webkit-backdrop-filter:blur(14px);backdrop-filter:blur(14px);font:400 clamp(14px,1.5vw,16px)/1.6 "JetBrains Mono",ui-monospace,Consolas,monospace;min-height:66px}
.prompt b{color:var(--mi);font-weight:400;margin-right:10px}
.prompt i{display:inline-block;width:.55em;height:1.1em;background:var(--mi);vertical-align:-.18em;margin-left:2px;animation:bl 1s steps(1) infinite}
@keyframes bl{50%{opacity:0}}
section{padding:clamp(70px,12vh,130px) 0}
h2{font-size:clamp(26px,3.8vw,46px);line-height:1.1;margin-bottom:14px}
.sub{color:var(--mut);max-width:50ch;margin-bottom:38px}
.row{display:grid;grid-template-columns:minmax(140px,.8fr) 2fr auto;gap:10px 32px;align-items:baseline;padding:30px 12px;border-top:1px solid var(--line);transition:background .35s}
.row:last-of-type{border-bottom:1px solid var(--line)}
.row:hover{background:linear-gradient(90deg,rgba(139,92,255,.18),rgba(139,92,255,0))}
.row h3{font-size:clamp(20px,2.4vw,28px);font-weight:500;transition:transform .35s,color .35s}
.row:hover h3{transform:translateX(8px);color:var(--mi)}
.row p{color:var(--mut)}
.tags{list-style:none;display:flex;gap:8px;flex-wrap:wrap;justify-content:flex-end}
.tags li{font-size:13px;border:1px solid var(--line);border-radius:999px;padding:3px 12px;color:var(--fg)}
.steps{display:grid;grid-template-columns:repeat(3,1fr);gap:28px}
.step{padding-top:22px;border-top:3px solid var(--c)}
.step h3{font-size:20px;font-weight:500;margin-bottom:10px}
.step p{color:var(--mut)}
.chips{display:flex;flex-wrap:wrap;gap:10px;margin-top:8px}
.chips span{border:1px solid var(--line);border-radius:999px;padding:8px 18px;background:rgba(20,12,40,.45);font-size:15px}
#hello{padding-bottom:70px}
#hello h2{font-size:clamp(30px,5.4vw,72px);max-width:14em}
.links{display:flex;flex-wrap:wrap;gap:14px;margin-top:34px}
.btn{display:inline-block;text-decoration:none;color:var(--fg);padding:15px 30px;border-radius:999px;border:1px solid var(--line);background:rgba(20,12,40,.5);-webkit-backdrop-filter:blur(10px);backdrop-filter:blur(10px);font-weight:500;transition:background .3s,border-color .3s}
.btn:hover{border-color:var(--mi);background:rgba(40,224,200,.12)}
.btn.main{background:linear-gradient(120deg,var(--vi),#c04bd8 60%,var(--pe));border-color:transparent;color:#fff}
.btn.main:hover{filter:brightness(1.12)}
footer{margin-top:90px;color:var(--mut);font-size:14px}
@media (max-width:760px){.row{grid-template-columns:1fr}.tags{justify-content:flex-start}.steps{grid-template-columns:1fr}.code div:nth-child(n+3){display:none}}
@media (prefers-reduced-motion:reduce){html{scroll-behavior:auto}.code div,.prompt i{animation:none}}
</style>
</head>
<body>
<canvas id="bg" aria-hidden="true"></canvas>
<div class="code" id="code" aria-hidden="true"></div>
<div class="shade"></div>
<header>
  <a class="mark" href="#top">Твоё имя</a>
  <nav aria-label="Разделы"><a href="#work">Проекты</a><a href="#flow">Процесс</a><a href="#hello">Связаться</a></nav>
</header>
<main>
  <section id="top">
    <h1>Говорю идею словами и получаю работающий продукт</h1>
    <p class="lead">Я вайб-кодер: собираю плагины, сайты и интерфейсы вместе с ИИ. Идея, вкус и проверка результата остаются за мной.</p>
    <div class="prompt" aria-label="Пример запроса"><b>&gt;</b><span id="typ"></span><i></i></div>
  </section>

  <section id="work">
    <h2>Проекты</h2>
    <p class="sub">Всё это собрано в диалоге с ИИ: от первой идеи до рабочей версии.</p>
    <article class="row"><h3>RMenu</h3><p>Меню сервера для Rust по моим скриншотам: оформление, разделы и кнопки как в референсе.</p><ul class="tags"><li>C#</li><li>Oxide</li><li>CUI</li></ul></article>
    <article class="row"><h3>RAdminMenu</h3><p>Админ-меню для Rust-сервера, собранное с нуля: быстрые действия без команд в консоли.</p><ul class="tags"><li>C#</li><li>Oxide</li><li>CUI</li></ul></article>
    <article class="row"><h3>WipeBlock</h3><p>Красивое GUI-меню /block, переделанное на основе готового плагина.</p><ul class="tags"><li>C#</li><li>GUI</li></ul></article>
    <article class="row"><h3>GameStores</h3><p>Сайт для продажи игровых ресурсов Rust: каталог, оформление и понятный путь к покупке.</p><ul class="tags"><li>HTML</li><li>CSS</li><li>JavaScript</li></ul></article>
  </section>

  <section id="flow">
    <h2>Как я работаю</h2>
    <p class="sub">Три шага, которые повторяются, пока результат не станет таким, каким я его вижу.</p>
    <div class="steps">
      <div class="step" style="--c:var(--vi)"><h3>Описываю</h3><p>Формулирую задачу простыми словами и показываю референс: скриншот, пример, набросок.</p></div>
      <div class="step" style="--c:var(--mi)"><h3>Итерирую</h3><p>ИИ пишет код, я смотрю на результат и прошу поправить, пока не совпадёт с задумкой.</p></div>
      <div class="step" style="--c:var(--pe)"><h3>Проверяю</h3><p>Собираю проект, тестирую на сервере и только после этого выкладываю.</p></div>
    </div>
    <div class="chips" style="margin-top:46px"><span>Claude Code</span><span>VS Code</span><span>C#</span><span>Rust</span><span>Oxide</span><span>HTML, CSS, JS</span></div>
  </section>

  <section id="hello">
    <h2>Есть идея? Давай соберём её вместе</h2>
    <p class="sub">Напиши, что нужно сделать, и пришли пример, если он есть. Отвечу и скажу, как быстро это получится.</p>
    <div class="links"><a class="btn main" href="mailto:you@example.com">you@example.com</a><a class="btn" href="https://t.me/yourname">Telegram</a></div>
    <footer>Страница сделана вместе с Claude.</footer>
  </section>
</main>
<script>
(()=>{
const reduce=matchMedia('(prefers-reduced-motion: reduce)').matches;

// Колонки кода на фоне
const S=['using Oxide.Core;','public class RMenu : RustPlugin','// сделай красиво','void OnPlayerConnected(BasePlayer p)','> добавь кнопку /block','CuiHelper.AddUi(player, json);','cargo build --release','fn main() -> Result<(), Error> {','dotnet build -c Release','let menu = Menu::new();','private void CmdBlock(BasePlayer p)','> поправь отступы и цвета','Interface.Oxide.LogInfo("ok");','impl Plugin for Menu {','> теперь сделай адаптив'];
const box=document.getElementById('code');
for(let c=0;c<4;c++){
  const a=S.slice(c*2).concat(S.slice(0,c*2)).join('\n');
  const d=document.createElement('div');d.textContent=a+'\n'+a;d.style.whiteSpace='pre';box.appendChild(d);
}

// Фон: потоки света
const cv=document.getElementById('bg'),x=cv.getContext('2d');
const cols=['139,92,255','40,224,200','255,158,122'];
let W,H,D,ps=[],t=0;
function init(){
  D=Math.min(devicePixelRatio||1,1.5);W=cv.width=innerWidth*D;H=cv.height=innerHeight*D;
  x.globalCompositeOperation='source-over';x.fillStyle='#0b0716';x.fillRect(0,0,W,H);
  const n=Math.min(170,Math.round(innerWidth*innerHeight/8000));
  ps=Array.from({length:n},()=>({x:Math.random()*W,y:Math.random()*H,c:cols[(Math.random()*3)|0]}));
  for(let i=0;i<220;i++)step();
}
function step(){
  x.globalCompositeOperation='source-over';x.fillStyle='rgba(11,7,22,.045)';x.fillRect(0,0,W,H);
  x.globalCompositeOperation='lighter';x.lineWidth=1.1*D;
  for(const p of ps){
    const a=Math.sin(p.x*.0016/D+t*.25)*Math.cos(p.y*.002/D-t*.18)*Math.PI*2.4;
    const nx=p.x+Math.cos(a)*1.8*D,ny=p.y+Math.sin(a)*1.8*D;
    x.strokeStyle='rgba('+p.c+',.5)';x.beginPath();x.moveTo(p.x,p.y);x.lineTo(nx,ny);x.stroke();
    p.x=nx;p.y=ny;
    if(p.x<0||p.x>W||p.y<0||p.y>H||Math.random()<.002){p.x=Math.random()*W;p.y=Math.random()*H;}
  }
  t+=.004;
}
let rt;addEventListener('resize',()=>{clearTimeout(rt);rt=setTimeout(init,200);});
init();
if(!reduce){(function loop(){step();requestAnimationFrame(loop);})();}

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
