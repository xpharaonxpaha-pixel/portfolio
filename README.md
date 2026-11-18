[index.html](https://github.com/user-attachments/files/35024428/index.html)
<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>vibe.code — портфолио вайб-кодера</title>
<meta name="description" content="Портфолио вайб-кодера: промты сайтов, работы и плагины. Неоновая аурора, терминал и живой фон." />

<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&family=JetBrains+Mono:wght@400;500;600&family=Unbounded:wght@500;700;900&display=swap" rel="stylesheet" />

<style>
  :root {
    --bg: #08080f;
    --bg2: #0e0e1a;
    --text: #f1f1fa;
    --muted: #9a9ab8;
    --faint: #6b6b8a;
    --line: rgba(255, 255, 255, 0.09);
    --card: rgba(20, 20, 34, 0.5);
    --violet: #a78bfa;
    --pink:   #f472b6;
    --cyan:   #67e8f9;
    --tint-violet: rgba(167, 139, 250, 0.16);
    --tint-pink:   rgba(244, 114, 182, 0.16);
    --tint-cyan:   rgba(103, 232, 249, 0.16);
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }
  html { scroll-behavior: smooth; }

  body {
    font-family: 'Inter', system-ui, sans-serif;
    color: var(--text);
    background: var(--bg);
    overflow-x: hidden;
    min-height: 100vh;
    -webkit-font-smoothing: antialiased;
  }

  /* ---------- Аурора (vibe-фон) ---------- */
  .aurora { position: fixed; inset: 0; z-index: 0; overflow: hidden; }
  .blob { position: absolute; border-radius: 50%; filter: blur(100px); mix-blend-mode: screen; }
  .blob-1 { width: 560px; height: 560px; background: #7c3aed; opacity: 0.34; top: -120px; left: -80px; animation: drift1 22s ease-in-out infinite; }
  .blob-2 { width: 520px; height: 520px; background: #db2777; opacity: 0.30; top: -60px; right: -100px; animation: drift2 26s ease-in-out infinite; }
  .blob-3 { width: 480px; height: 480px; background: #0891b2; opacity: 0.28; bottom: -140px; left: 30%; animation: drift3 24s ease-in-out infinite; }
  @keyframes drift1 { 50% { transform: translate(140px, 90px) scale(1.15); } }
  @keyframes drift2 { 50% { transform: translate(-120px, 120px) scale(1.1); } }
  @keyframes drift3 { 50% { transform: translate(-100px, -80px) scale(1.2); } }

  canvas#scene { position: fixed; inset: 0; width: 100%; height: 100%; z-index: 0; display: block; }

  .vignette {
    position: fixed; inset: 0; z-index: 1; pointer-events: none;
    background: radial-gradient(120% 100% at 50% 40%, transparent 55%, rgba(4,4,9,0.6) 100%);
  }
  .grain {
    position: fixed; inset: -50%; z-index: 1; pointer-events: none; opacity: 0.05;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='140' height='140'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='2'/%3E%3C/filter%3E%3Crect width='140' height='140' filter='url(%23n)'/%3E%3C/svg%3E");
  }

  #loader {
    position: fixed; inset: 0; z-index: 50;
    display: flex; align-items: center; justify-content: center; background: var(--bg);
    transition: opacity 0.7s ease, visibility 0.7s ease;
  }
  #loader.hidden { opacity: 0; visibility: hidden; pointer-events: none; }
  .loader-ring {
    width: 46px; height: 46px; border-radius: 50%;
    border: 2px solid rgba(255,255,255,0.1); border-top-color: var(--cyan);
    animation: spin 0.9s linear infinite;
  }
  @keyframes spin { to { transform: rotate(360deg); } }

  /* ---------- Обёртка ---------- */
  .overlay { position: relative; z-index: 2; }
  .wrap { max-width: 1080px; margin: 0 auto; padding: 0 28px; }

  /* ---------- Шапка ---------- */
  header {
    position: fixed; top: 0; left: 0; right: 0; z-index: 10;
    backdrop-filter: blur(16px);
    background: linear-gradient(180deg, rgba(8,8,15,0.7), rgba(8,8,15,0.2));
    border-bottom: 1px solid transparent;
  }
  .nav { display: flex; align-items: center; justify-content: space-between; height: 66px; }
  .logo {
    font-family: 'JetBrains Mono', monospace; font-weight: 600; font-size: 1.02rem;
    color: var(--text); letter-spacing: -0.01em;
  }
  .logo .brace { color: var(--pink); }
  .logo .dot { color: var(--cyan); }
  .nav-links { display: flex; gap: 26px; list-style: none; }
  .nav-links a { color: var(--muted); text-decoration: none; font-size: 0.9rem; transition: color 0.2s ease; }
  .nav-links a:hover { color: var(--text); }
  .nav-btn {
    font-family: 'Inter', sans-serif; font-size: 0.9rem; font-weight: 500;
    padding: 9px 18px; border-radius: 10px; cursor: pointer; color: var(--text);
    border: 1px solid var(--line); background: rgba(255,255,255,0.04);
    transition: background 0.2s ease, border-color 0.2s ease, transform 0.2s ease;
  }
  .nav-btn:hover { background: rgba(255,255,255,0.08); border-color: rgba(167,139,250,0.4); }

  /* ---------- Hero ---------- */
  .hero { min-height: 100vh; display: flex; align-items: center; padding: 130px 0 90px; position: relative; }
  .hero-grid { display: grid; grid-template-columns: 1.15fr 0.85fr; gap: 48px; align-items: center; }
  .badge {
    display: inline-flex; align-items: center; gap: 9px;
    font-family: 'JetBrains Mono', monospace; font-size: 0.78rem; letter-spacing: 0.05em;
    color: var(--cyan); padding: 8px 16px; border-radius: 999px;
    border: 1px solid rgba(103,232,249,0.3); background: rgba(103,232,249,0.07);
    margin-bottom: 26px;
  }
  .badge .dot { width: 8px; height: 8px; border-radius: 50%; background: var(--cyan); box-shadow: 0 0 12px var(--cyan); animation: pulse 2s ease-in-out infinite; }
  @keyframes pulse { 50% { opacity: 0.4; } }

  h1 {
    font-family: 'Unbounded', sans-serif; font-weight: 700;
    font-size: clamp(2rem, 5.2vw, 3.8rem);
    line-height: 1.08; letter-spacing: -0.01em; margin-bottom: 22px;
  }
  h1 .grad {
    background: linear-gradient(92deg, var(--violet), var(--pink) 55%, var(--cyan));
    -webkit-background-clip: text; background-clip: text; color: transparent;
  }

  .typing-row {
    font-family: 'JetBrains Mono', monospace; font-size: clamp(0.95rem, 1.8vw, 1.1rem);
    color: var(--muted); min-height: 1.8em; margin-bottom: 34px;
  }
  .typing-row .caret {
    display: inline-block; width: 9px; height: 1.1em; margin-left: 3px;
    background: var(--pink); vertical-align: text-bottom; animation: blink 1s step-end infinite;
  }
  @keyframes blink { 50% { opacity: 0; } }

  .cta-row { display: flex; gap: 14px; flex-wrap: wrap; }
  .btn {
    font-family: 'Inter', sans-serif; font-size: 0.95rem; font-weight: 500;
    padding: 13px 24px; border-radius: 12px; cursor: pointer; text-decoration: none;
    border: 1px solid var(--line); transition: transform 0.2s ease, background 0.2s ease, border-color 0.2s ease, box-shadow 0.2s ease;
  }
  .btn-primary {
    color: #0a0a12;
    background: linear-gradient(120deg, var(--violet), var(--pink));
    border-color: transparent; box-shadow: 0 12px 40px rgba(167,139,250,0.35);
  }
  .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 18px 50px rgba(244,114,182,0.45); }
  .btn-ghost { color: var(--text); background: rgba(255,255,255,0.03); }
  .btn-ghost:hover { transform: translateY(-2px); background: rgba(255,255,255,0.07); border-color: rgba(255,255,255,0.2); }

  /* терминал */
  .terminal {
    background: rgba(14,14,26,0.72); border: 1px solid var(--line); border-radius: 16px;
    backdrop-filter: blur(18px); box-shadow: 0 30px 80px rgba(0,0,0,0.45);
    overflow: hidden; font-family: 'JetBrains Mono', monospace;
  }
  .terminal-bar { display: flex; align-items: center; gap: 8px; padding: 13px 16px; border-bottom: 1px solid var(--line); }
  .t-dot { width: 12px; height: 12px; border-radius: 50%; }
  .t-red { background: #ff5f57; } .t-yellow { background: #febc2e; } .t-green { background: #28c840; }
  .terminal-title { margin-left: 10px; color: var(--faint); font-size: 0.78rem; }
  .terminal-body { padding: 20px; font-size: 0.86rem; line-height: 1.8; min-height: 190px; }
  .terminal-body .line { white-space: pre-wrap; }
  .terminal-body .cursor {
    display: inline-block; width: 8px; height: 1em; margin-left: 2px;
    background: var(--cyan); vertical-align: text-bottom; animation: blink 1s step-end infinite;
  }
  .c-prompt  { color: #e2e8f0; }
  .c-prompt::before { content: ''; }
  .c-ok      { color: #6ee7b7; }
  .c-kw      { color: #c4b5fd; }
  .c-fn      { color: #f0abfc; }
  .c-comment { color: #64748b; }

  /* плавающие чипы */
  .chip {
    position: absolute; z-index: 1; font-family: 'JetBrains Mono', monospace; font-size: 0.78rem;
    color: var(--muted); padding: 8px 14px; border-radius: 999px;
    background: rgba(20,20,34,0.6); border: 1px solid var(--line); backdrop-filter: blur(10px);
    animation: floaty 7s ease-in-out infinite; pointer-events: none; white-space: nowrap;
  }
  .chip b { color: var(--cyan); font-weight: 500; }
  .chip.pink b { color: var(--pink); }
  .chip.violet b { color: var(--violet); }
  .chip-1 { top: 22%; left: 44%; animation-delay: 0s; }
  .chip-2 { top: 16%; right: 6%; animation-delay: 1.2s; }
  .chip-3 { bottom: 24%; left: 4%; animation-delay: 2s; }
  .chip-4 { bottom: 12%; right: 34%; animation-delay: 0.6s; }
  .chip-5 { top: 46%; left: 2%; animation-delay: 1.6s; }
  @keyframes floaty { 50% { transform: translateY(-14px); } }

  .scroll-hint {
    position: absolute; bottom: 30px; left: 50%; transform: translateX(-50%);
    color: var(--faint); font-size: 0.72rem; letter-spacing: 0.22em; text-transform: uppercase;
  }
  .scroll-hint .line { width: 1px; height: 38px; margin: 10px auto 0; background: linear-gradient(var(--pink), transparent); animation: drop 1.8s ease-in-out infinite; }
  @keyframes drop {
    0% { transform: scaleY(0); transform-origin: top; } 50% { transform: scaleY(1); transform-origin: top; }
    51% { transform-origin: bottom; } 100% { transform: scaleY(0); transform-origin: bottom; }
  }

  /* ---------- Секции ---------- */
  section { padding: 100px 0; }
  .section-head { display: flex; align-items: baseline; gap: 14px; margin-bottom: 10px; flex-wrap: wrap; }
  .section-head .kicker {
    font-family: 'JetBrains Mono', monospace; font-size: 0.78rem; color: var(--cyan); letter-spacing: 0.05em;
    display: flex; align-items: center; gap: 8px;
  }
  .section-head h2 { font-family: 'Unbounded', sans-serif; font-weight: 600; font-size: clamp(1.5rem, 3.4vw, 2.1rem); letter-spacing: -0.01em; }
  .count { font-size: 0.78rem; color: var(--faint); padding: 3px 10px; border: 1px solid var(--line); border-radius: 999px; }
  .section-note { color: var(--muted); font-size: 0.95rem; line-height: 1.7; max-width: 560px; margin-bottom: 34px; }

  .grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(300px, 1fr)); gap: 16px; }
  .card {
    position: relative; padding: 24px; border-radius: 16px;
    background: var(--card); border: 1px solid var(--line);
    backdrop-filter: blur(12px);
    transition: transform 0.25s ease, border-color 0.25s ease, background 0.25s ease;
  }
  .card:hover { transform: translateY(-4px); border-color: rgba(167,139,250,0.4); background: rgba(24,24,40,0.6); }
  .card-top { display: flex; align-items: center; justify-content: space-between; margin-bottom: 14px; }
  .tag {
    font-family: 'JetBrains Mono', monospace; font-size: 0.7rem; letter-spacing: 0.08em; text-transform: uppercase;
    padding: 4px 11px; border-radius: 999px;
  }
  .tag.prompts { color: var(--cyan); background: var(--tint-cyan); }
  .tag.works   { color: var(--violet); background: var(--tint-violet); }
  .tag.plugins { color: var(--pink); background: var(--tint-pink); }
  .card-del {
    background: none; border: none; cursor: pointer; color: var(--faint); font-size: 1.1rem;
    line-height: 1; padding: 2px 6px; border-radius: 6px; opacity: 0; transition: opacity 0.2s ease, color 0.2s ease;
  }
  .card:hover .card-del { opacity: 1; }
  .card-del:hover { color: #f87171; }
  .card h3 { font-family: 'Inter', sans-serif; font-weight: 600; font-size: 1.05rem; margin-bottom: 10px; }
  .card p { color: var(--muted); font-size: 0.92rem; line-height: 1.6; }
  .card a.link { display: inline-block; margin-top: 16px; font-size: 0.88rem; color: var(--cyan); text-decoration: none; }
  .card a.link:hover { text-decoration: underline; }

  .empty { grid-column: 1 / -1; padding: 40px; border: 1px dashed var(--line); border-radius: 16px; color: var(--faint); text-align: center; font-size: 0.92rem; }

  footer { border-top: 1px solid var(--line); padding: 40px 0 48px; }
  .foot { display: flex; align-items: center; justify-content: space-between; flex-wrap: wrap; gap: 14px; color: var(--faint); font-size: 0.85rem; }
  .foot .mono { font-family: 'JetBrains Mono', monospace; }

  .fab {
    position: fixed; right: 26px; bottom: 26px; z-index: 20;
    width: 54px; height: 54px; border-radius: 50%; border: 1px solid var(--line);
    background: rgba(22,22,36,0.85); color: var(--pink); font-size: 1.6rem; cursor: pointer;
    backdrop-filter: blur(12px); box-shadow: 0 8px 30px rgba(0,0,0,0.4);
    transition: transform 0.2s ease, background 0.2s ease;
  }
  .fab:hover { transform: translateY(-3px); background: rgba(34,34,52,0.9); }

  /* ---------- Модалка ---------- */
  .modal {
    position: fixed; inset: 0; z-index: 40;
    display: flex; align-items: center; justify-content: center; padding: 20px;
    background: rgba(6,6,12,0.7); backdrop-filter: blur(6px);
    opacity: 0; visibility: hidden; transition: opacity 0.25s ease, visibility 0.25s ease;
  }
  .modal.open { opacity: 1; visibility: visible; }
  .modal-card {
    width: 100%; max-width: 460px; padding: 28px; border-radius: 18px;
    background: var(--bg2); border: 1px solid var(--line);
    transform: translateY(12px); transition: transform 0.25s ease; box-shadow: 0 30px 80px rgba(0,0,0,0.5);
  }
  .modal.open .modal-card { transform: translateY(0); }
  .modal-head { display: flex; align-items: center; justify-content: space-between; margin-bottom: 20px; }
  .modal-head h3 { font-family: 'Unbounded', sans-serif; font-weight: 600; font-size: 1.1rem; }
  .modal-close { background: none; border: none; color: var(--muted); font-size: 1.6rem; cursor: pointer; line-height: 1; }
  .modal-close:hover { color: var(--text); }
  form label { display: block; font-size: 0.85rem; color: var(--muted); margin-bottom: 16px; }
  form input, form select, form textarea {
    width: 100%; margin-top: 7px; padding: 12px 14px; border-radius: 10px;
    border: 1px solid var(--line); background: rgba(255,255,255,0.04);
    color: var(--text); font-family: 'Inter', sans-serif; font-size: 0.95rem; outline: none; transition: border-color 0.2s ease;
  }
  form input:focus, form select:focus, form textarea:focus { border-color: var(--violet); }
  form textarea { resize: vertical; }
  form select option { background: var(--bg2); }
  .modal-actions { display: flex; gap: 12px; justify-content: flex-end; margin-top: 8px; }

  @media (max-width: 860px) {
    .hero-grid { grid-template-columns: 1fr; }
    .terminal { max-width: 460px; }
    .chip { display: none; }
  }
  @media (max-width: 640px) {
    .nav-links { display: none; }
    .grid { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>
  <div class="aurora">
    <div class="blob blob-1"></div>
    <div class="blob blob-2"></div>
    <div class="blob blob-3"></div>
  </div>
  <canvas id="scene"></canvas>
  <div class="vignette"></div>
  <div class="grain"></div>
  <div id="loader"><div class="loader-ring"></div></div>

  <div class="overlay">
    <header>
      <div class="wrap nav">
        <div class="logo"><span class="brace">vibe</span>.code<span class="dot">_</span></div>
        <ul class="nav-links">
          <li><a href="#prompts">Промты</a></li>
          <li><a href="#works">Работы</a></li>
          <li><a href="#plugins">Плагины</a></li>
        </ul>
        <button class="nav-btn" id="nav-add">+ Добавить</button>
      </div>
    </header>

    <main>
      <section class="hero">
        <span class="chip chip-1">&lt;/&gt;</span>
        <span class="chip chip-2 pink"><b>npm i vibe</b></span>
        <span class="chip chip-3 violet"><b>ship()</b> 🚀</span>
        <span class="chip chip-4">{ <b>code by feel</b> }</span>
        <span class="chip chip-5"><b>git push</b> →</span>

        <div class="wrap">
          <div class="hero-grid">
            <div>
              <div class="badge"><span class="dot"></span> vibe coding mode</div>
              <h1>Привет. Я кодирую <span class="grad">по вайбу</span>.</h1>
              <div class="typing-row"><span id="typed"></span><span class="caret"></span></div>
              <div class="cta-row">
                <a class="btn btn-primary" href="#works">Смотреть работы</a>
                <button class="btn btn-ghost" id="hero-add">Добавить элемент</button>
              </div>
            </div>
            <div class="terminal">
              <div class="terminal-bar">
                <span class="t-dot t-red"></span><span class="t-dot t-yellow"></span><span class="t-dot t-green"></span>
                <span class="terminal-title">vibe@coder: ~/portfolio</span>
              </div>
              <div class="terminal-body" id="terminal"></div>
            </div>
          </div>
        </div>
        <div class="scroll-hint"><span>Листайте</span><div class="line"></div></div>
      </section>

      <section id="prompts">
        <div class="wrap">
          <div class="section-head"><span class="kicker">~/prompts</span><h2>Промты сайтов</h2><span class="count" id="count-prompts">0</span></div>
          <p class="section-note">Готовые промты, по которым можно собрать сайт.</p>
          <div class="grid" id="grid-prompts"></div>
        </div>
      </section>

      <section id="works">
        <div class="wrap">
          <div class="section-head"><span class="kicker">~/works</span><h2>Работы</h2><span class="count" id="count-works">0</span></div>
          <p class="section-note">Готовые проекты, сайты и эксперименты.</p>
          <div class="grid" id="grid-works"></div>
        </div>
      </section>

      <section id="plugins">
        <div class="wrap">
          <div class="section-head"><span class="kicker">~/plugins</span><h2>Плагины</h2><span class="count" id="count-plugins">0</span></div>
          <p class="section-note">Расширения, плагины и инструменты.</p>
          <div class="grid" id="grid-plugins"></div>
        </div>
      </section>
    </main>

    <footer>
      <div class="wrap foot">
        <span class="mono">vibe.code © 2026</span>
        <span class="mono">built with three.js · webgl · glsl</span>
      </div>
    </footer>
  </div>

  <button class="fab" id="fab" aria-label="Добавить элемент">+</button>

  <div class="modal" id="modal">
    <div class="modal-card">
      <div class="modal-head">
        <h3>Новый элемент</h3>
        <button class="modal-close" id="modal-close" aria-label="Закрыть">×</button>
      </div>
      <form id="add-form">
        <label>Категория
          <select name="category">
            <option value="prompts">Промт сайта</option>
            <option value="works">Работа</option>
            <option value="plugins">Плагин</option>
          </select>
        </label>
        <label>Название
          <input name="title" required placeholder="Например: NEBULA — 3D вселенная" />
        </label>
        <label>Описание
          <textarea name="desc" rows="3" placeholder="Короткое описание"></textarea>
        </label>
        <label>Ссылка
          <input name="link" placeholder="https://…" />
        </label>
        <div class="modal-actions">
          <button type="button" class="btn btn-ghost" id="modal-cancel">Отмена</button>
          <button type="submit" class="btn btn-primary">Добавить</button>
        </div>
      </form>
    </div>
  </div>

  <script type="importmap">
    {
      "imports": {
        "three": "https://cdn.jsdelivr.net/npm/three@0.160.0/build/three.module.js",
        "three/addons/": "https://cdn.jsdelivr.net/npm/three@0.160.0/examples/jsm/"
      }
    }
  </script>

  <script type="module">
    import * as THREE from 'three';

    /* =========================================================
       ПОРТФОЛИО — localStorage
       ========================================================= */
    const STORAGE_KEY = 'vibecode_items_v1';
    const CATS = {
      prompts: { label: 'Промт' },
      works:   { label: 'Работа' },
      plugins: { label: 'Плагин' },
    };

    function seed() {
      return [
        { id: 'p1', category: 'prompts', title: 'NEBULA — 3D вселенная', desc: 'Промт для интерактивного лендинга с тор-узлом, частицами и bloom-свечением.', link: '' },
        { id: 'w1', category: 'works',   title: 'vibe.code', desc: 'Это самое портфолио: аурора, терминал с печатающимся кодом и живой фон.', link: '' },
        { id: 'pl1', category: 'plugins', title: 'Плагин для DSH', desc: 'Инструмент, который подключает новую команду в DeepSeek Harness.', link: '' },
      ];
    }

    let items = [];
    try { const raw = localStorage.getItem(STORAGE_KEY); items = raw ? JSON.parse(raw) : seed(); }
    catch (e) { items = seed(); }
    function save() { try { localStorage.setItem(STORAGE_KEY, JSON.stringify(items)); } catch (e) {} }

    const esc = s => String(s ?? '').replace(/[&<>"']/g, c => ({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));

    function cardHTML(item) {
      const link = item.link && item.link.trim()
        ? `<a class="link" href="${esc(item.link)}" target="_blank" rel="noopener">открыть →</a>` : '';
      return `
        <div class="card" data-id="${esc(item.id)}">
          <div class="card-top">
            <span class="tag ${item.category}">${CATS[item.category].label}</span>
            <button class="card-del" title="Удалить">×</button>
          </div>
          <h3>${esc(item.title)}</h3>
          <p>${esc(item.desc)}</p>
          ${link}
        </div>`;
    }

    function render() {
      for (const key of Object.keys(CATS)) {
        const grid = document.getElementById('grid-' + key);
        const list = items.filter(i => i.category === key);
        document.getElementById('count-' + key).textContent = list.length;
        grid.innerHTML = list.length ? list.map(cardHTML).join('') : `<div class="empty">Пока пусто — добавьте первый элемент.</div>`;
      }
    }

    document.addEventListener('click', (e) => {
      const del = e.target.closest('.card-del');
      if (!del) return;
      const id = del.closest('.card').dataset.id;
      items = items.filter(i => i.id !== id);
      save(); render();
    });

    /* модалка */
    const modal = document.getElementById('modal');
    const addForm = document.getElementById('add-form');
    const openModal = () => { modal.classList.add('open'); addForm.elements.title.focus(); };
    const closeModal = () => { modal.classList.remove('open'); addForm.reset(); };
    document.getElementById('nav-add').addEventListener('click', openModal);
    document.getElementById('hero-add').addEventListener('click', openModal);
    document.getElementById('fab').addEventListener('click', openModal);
    document.getElementById('modal-close').addEventListener('click', closeModal);
    document.getElementById('modal-cancel').addEventListener('click', closeModal);
    modal.addEventListener('click', (e) => { if (e.target === modal) closeModal(); });
    document.addEventListener('keydown', (e) => { if (e.key === 'Escape') closeModal(); });

    addForm.addEventListener('submit', (e) => {
      e.preventDefault();
      const f = addForm.elements;
      let link = f.link.value.trim();
      if (link && !/^https?:\/\//i.test(link)) link = 'https://' + link;
      items.push({ id: 'i' + Date.now(), category: f.category.value, title: f.title.value.trim(), desc: f.desc.value.trim(), link });
      save(); render(); closeModal();
    });

    render();

    /* =========================================================
       ТЕРМИНАЛ — печатающийся код
       ========================================================= */
    const terminalEl = document.getElementById('terminal');
    const terminalLines = [
      { text: '$ npm run dev', cls: 'c-prompt' },
      { text: '✓ ready in 412ms', cls: 'c-ok' },
      { text: ' ' , cls: '' },
      { text: 'const vibe = true;', cls: 'c-kw' },
      { text: 'while (vibe) { ship(); }', cls: 'c-fn' },
      { text: '// deploy 🚀', cls: 'c-comment' },
    ];

    function sleep(ms) { return new Promise(r => setTimeout(r, ms)); }

    async function runTerminal() {
      while (true) {
        terminalEl.innerHTML = '';
        for (const line of terminalLines) {
          const div = document.createElement('div');
          div.className = 'line ' + line.cls;
          terminalEl.appendChild(div);
          for (const ch of line.text) {
            div.textContent += ch;
            await sleep(28 + Math.random() * 40);
          }
          await sleep(180);
        }
        const cursor = document.createElement('span');
        cursor.className = 'cursor';
        terminalEl.appendChild(cursor);
        await sleep(6000);
        terminalEl.innerHTML = '';
      }
    }
    runTerminal();

    /* =========================================================
       ТАЙПРАЙТЕР в hero
       ========================================================= */
    const typedEl = document.getElementById('typed');
    const phrases = [
      'пишу код по ощущениям…',
      'шиплю быстро, потом разбираюсь…',
      'AI + я = 🚀…',
      'от идеи до деплоя за вечер…',
      'вайб превыше всего…',
    ];
    let pi = 0, ci = 0, deleting = false;

    async function typewriter() {
      while (true) {
        const phrase = phrases[pi];
        if (!deleting) {
          typedEl.textContent = phrase.slice(0, ++ci);
          if (ci === phrase.length) { deleting = true; await sleep(1800); }
          else await sleep(55);
        } else {
          typedEl.textContent = phrase.slice(0, --ci);
          if (ci === 0) { deleting = false; pi = (pi + 1) % phrases.length; await sleep(300); }
          else await sleep(28);
        }
      }
    }
    typewriter();

    /* =========================================================
       3D-СЦЕНА — частицы, дрейфующие вверх (vibe)
       ========================================================= */
    const canvas = document.getElementById('scene');
    const loader = document.getElementById('loader');

    let renderer;
    try { renderer = new THREE.WebGLRenderer({ canvas, antialias: true, alpha: true }); }
    catch (e) { loader.classList.add('hidden'); throw e; }

    renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
    renderer.setSize(window.innerWidth, window.innerHeight);
    renderer.toneMapping = THREE.ACESFilmicToneMapping;
    renderer.toneMappingExposure = 1.0;

    const scene = new THREE.Scene();
    const camera = new THREE.PerspectiveCamera(55, window.innerWidth / window.innerHeight, 0.1, 200);
    camera.position.set(0, 0, 11);

    // тонкий вращающийся каркас
    const ico = new THREE.Mesh(
      new THREE.IcosahedronGeometry(5.2, 1),
      new THREE.MeshBasicMaterial({ color: 0x7c3aed, wireframe: true, transparent: true, opacity: 0.05 })
    );
    ico.position.set(3.5, 0.5, -2);
    scene.add(ico);

    // дрейфующие частицы
    const N = 420;
    const pGeo = new THREE.BufferGeometry();
    const pPos = new Float32Array(N * 3);
    const pCol = new Float32Array(N * 3);
    const pSpeed = new Float32Array(N);
    const palette = [new THREE.Color('#a78bfa'), new THREE.Color('#f472b6'), new THREE.Color('#67e8f9'), new THREE.Color('#ffffff')];
    for (let i = 0; i < N; i++) {
      pPos[i * 3] = (Math.random() - 0.5) * 34;
      pPos[i * 3 + 1] = (Math.random() - 0.5) * 46;
      pPos[i * 3 + 2] = (Math.random() - 0.5) * 18;
      pSpeed[i] = 0.02 + Math.random() * 0.07;
      const c = palette[Math.floor(Math.random() * palette.length)];
      pCol[i * 3] = c.r; pCol[i * 3 + 1] = c.g; pCol[i * 3 + 2] = c.b;
    }
    pGeo.setAttribute('position', new THREE.BufferAttribute(pPos, 3));
    pGeo.setAttribute('color', new THREE.BufferAttribute(pCol, 3));
    const points = new THREE.Points(pGeo, new THREE.PointsMaterial({
      size: 0.07, vertexColors: true, transparent: true, opacity: 0.55,
      blending: THREE.AdditiveBlending, depthWrite: false, sizeAttenuation: true,
    }));
    scene.add(points);

    let mouseX = 0, mouseY = 0;
    window.addEventListener('pointermove', (e) => {
      mouseX = (e.clientX / window.innerWidth) * 2 - 1;
      mouseY = -(e.clientY / window.innerHeight) * 2 + 1;
    });
    window.addEventListener('resize', () => {
      camera.aspect = window.innerWidth / window.innerHeight;
      camera.updateProjectionMatrix();
      renderer.setSize(window.innerWidth, window.innerHeight);
    });

    const clock = new THREE.Clock();
    const lerp = (a, b, t) => a + (b - a) * t;
    let firstFrame = true;

    function animate() {
      requestAnimationFrame(animate);
      const t = clock.getElapsedTime();
      const dt = Math.min(clock.getDelta(), 0.1);

      // дрейф частиц вверх
      const arr = pGeo.attributes.position.array;
      for (let i = 0; i < N; i++) {
        let y = arr[i * 3 + 1] + pSpeed[i] * dt * 6;
        if (y > 23) y = -23;
        arr[i * 3 + 1] = y;
      }
      pGeo.attributes.position.needsUpdate = true;

      ico.rotation.y = t * 0.06;
      ico.rotation.x = Math.sin(t * 0.1) * 0.3;

      camera.position.x = lerp(camera.position.x, mouseX * 0.6, 0.04);
      camera.position.y = lerp(camera.position.y, -mouseY * 0.4, 0.04);
      camera.lookAt(0, 0, 0);

      renderer.render(scene, camera);

      if (firstFrame) { firstFrame = false; loader.classList.add('hidden'); }
    }
    animate();
  </script>
</body>
</html>
