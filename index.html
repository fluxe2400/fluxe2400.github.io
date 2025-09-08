<!doctype html>
<html lang="ru" class="no-native-scrollbar" data-theme="emerald">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover">
<title>fluxe — игры и программы</title>
<meta name="theme-color" content="#07140e">
<meta name="referrer" content="no-referrer">

<!-- CSP -->
<meta http-equiv="Content-Security-Policy" content="
  default-src 'self';
  script-src 'self' 'nonce-LEAVES';
  style-src 'self' 'unsafe-inline';
  img-src 'self' https: data: blob:;
  font-src 'self' https: data:;
  connect-src 'none';
  object-src 'none';
  base-uri 'self';
  form-action 'self';
  frame-ancestors 'none';
  upgrade-insecure-requests;
  block-all-mixed-content
">

<style>
  :root{
    --bg:#07140e;
    --green:#00ff88;
    --text:#eaf9f1;
    --muted:#b6e3c8;
    --accent:#7afdd0;

    --ring: rgba(122,253,208,.5);
    --panel: rgba(5,18,12,.86);
    --glass-1: linear-gradient(180deg, rgba(7,20,14,.7), rgba(7,20,14,.3) 60%, transparent);
    --glass-2: linear-gradient(180deg, rgba(5,18,12,.8), rgba(5,18,12,.6));
    --shadow-1: 0 8px 24px rgba(0,0,0,.35);
    --shadow-2: 0 16px 40px rgba(0,0,0,.5);
    --card-border: rgba(0,255,136,.18);
    --card-border-hover: rgba(0,255,136,.35);
  }

  html, body{ height:100%; }
  body{
    margin:0; color:var(--text);
    font-family:Inter, system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;

    /* единый фон */
    background: var(--bg);

    -webkit-tap-highlight-color: transparent;

    /* убираем нативный скроллбар (второй ползунок) */
    scrollbar-width: none !important;
    -ms-overflow-style: none !important;
    scroll-behavior: smooth;

    /* запрет копирования/выделения текста */
    user-select: none; -webkit-user-select: none; -ms-user-select: none;
    text-rendering: optimizeLegibility;
  }
  ::-webkit-scrollbar{ width:0; height:0; display:none; }
  html.no-native-scrollbar, body.no-native-scrollbar{
    scrollbar-width: none !important;
    -ms-overflow-style: none !important;
  }
  html.no-native-scrollbar::-webkit-scrollbar,
  body.no-native-scrollbar::-webkit-scrollbar{ width:0 !important; height:0 !important; display:none !important; background: transparent !important; }

  /* Фон (canvas поверх единого фона) */
  #bg-space{
    position:fixed; inset:0; width:100vw; height:100vh; z-index:0; pointer-events:none; display:block;
  }

  /* Кастомный курсор (только pointer:fine) */
  @media (pointer: fine){
    html, body{ cursor:none; }
    #cursor{
      position:fixed; left:0; top:0; width:18px; height:18px; border-radius:50%;
      background:rgba(255,255,255,.6); box-shadow:0 0 12px rgba(255,255,255,.35);
      transform: translate(-50%,-50%); pointer-events:none; z-index:5;
      transition: width .12s ease, height .12s ease, background .12s ease, box-shadow .12s ease;
      mix-blend-mode:screen; will-change:transform;
    }
    a, button, .btn, .icon-btn{ cursor:none; }
  }

  /* Лэйаут */
  .fluxe-site{ position:relative; min-height:100vh; overflow:hidden; z-index:1; }
  .header{ position:sticky; top:0; z-index:3; padding:22px;

    /* единый фон */
    background: var(--bg);

    backdrop-filter:blur(10px);
    border-bottom:1px solid rgba(0,255,136,.15);
  }
  .header .container{
    max-width:1200px; margin:0 auto; display:flex; align-items:center; justify-content:space-between; gap:12px; padding:0 6px;
  }

  .logo{
    font-weight:900; font-size:26px; letter-spacing:.6px; line-height:1;
    background: linear-gradient(90deg, #eafff7 0%, #6bffb5 30%, #00ff88 50%, #9fffd8 70%, #eafff7 100%);
    background-size:200% auto; -webkit-background-clip:text; background-clip:text; color:transparent;
    filter: drop-shadow(0 0 10px rgba(0,255,136,.35));
    animation: logoGlow 8s ease-in-out infinite;
  }
  @keyframes logoGlow{ 0%,100%{ background-position:0% 50%; } 50%{ background-position:100% 50%; } }

  .actions{ display:flex; align-items:center; gap:10px; }
  .icon-btn{
    width:44px; height:44px; border-radius:50%;
    background: rgba(0,255,136,.12); border:1px solid rgba(0,255,136,.25);
    box-shadow: 0 0 12px rgba(0,255,136,.35), 0 0 24px rgba(0,255,136,.15);
    display:inline-flex; align-items:center; justify-content:center; color:var(--green);
    transition: transform .18s ease, box-shadow .2s ease, filter .2s ease; text-decoration:none; touch-action: manipulation;
  }
  .icon-btn:hover{ transform: scale(1.08); box-shadow:0 0 16px rgba(0,255,136,.8), 0 0 40px rgba(0,255,136,.35); }
  .icon-btn:focus-visible{ outline:none; box-shadow: 0 0 0 3px var(--ring), 0 0 18px rgba(122,253,208,.4); }

  .hero{ position:relative; z-index:1; max-width:1200px; margin:40px auto 10px; padding:32px 22px 0; text-align:left; }

  /* Заголовок в одну строку */
  .title{
    font-size: clamp(18px, 5.2vw, 56px); font-weight:900; line-height:1.08; margin:0;
    white-space: nowrap;
    background: radial-gradient(120% 120% at 0% 50%, #eafff7 0%, #aaffdd 35%, #7afdd0 55%, #eafff7 100%);
    -webkit-background-clip:text; background-clip:text; color:transparent;
    text-shadow: 0 0 18px rgba(122,253,208,.25);
    letter-spacing:.3px; position:relative; padding-bottom:12px;
  }
  .title::after{
    content:""; position:absolute; left:0; bottom:0; width:180px; height:3px;
    background: linear-gradient(90deg, var(--accent), rgba(122,253,208,0));
    border-radius:3px; filter: drop-shadow(0 0 8px rgba(122,253,208,.5));
  }

  .section{ position:relative; z-index:1; max-width:1200px; margin:28px auto 8px; padding:0 22px; }
  .section-title{
    display:inline-flex; align-items:center; gap:10px; margin:22px 0 10px;
    font-size:20px; font-weight:800; letter-spacing:.45px; color:#dffdf0;
    padding:8px 14px; border-radius:999px; border:1px solid rgba(122,253,208,.35);
    background: linear-gradient(180deg, rgba(122,253,208,.15), rgba(122,253,208,.06));
    box-shadow: inset 0 0 0 1px rgba(122,253,208,.12);
  }
  .section-title svg{ width:18px; height:18px; color:var(--accent); filter: drop-shadow(0 0 8px rgba(122,253,208,.4)); }

  .catalog{ position:relative; z-index:1; max-width:1200px; margin:12px auto 46px; padding:0 22px;
    display:grid; grid-template-columns: repeat(12, 1fr); gap:18px;
  }
  .card{ grid-column: span 4; display:flex; flex-direction:column;
    background: var(--glass-2);
    border:1px solid var(--card-border); border-radius:16px; overflow:hidden;
    box-shadow:var(--shadow-1), 0 0 0 1px rgba(0,255,136,.08) inset;
    transition: transform .25s ease, box-shadow .25s ease, border-color .25s ease;
    content-visibility: auto;
    contain-intrinsic-size: 260px 200px;
  }
  .card:hover{ transform: translateY(-4px); box-shadow:var(--shadow-2), 0 0 30px rgba(0,255,136,.15); border-color: var(--card-border-hover); }

  .thumb{ position:relative; padding-top:58%; background-size:cover; background-position:center; filter:saturate(110%); }
  .thumb::after{ content:""; position:absolute; inset:0; background: radial-gradient(60% 80% at 70% 10%, rgba(0,255,136,.18), transparent 60%); mix-blend-mode: screen; }
  .thumb.placeholder{
    display:flex; align-items:center; justify-content:center;
    background: linear-gradient(135deg, rgba(0,255,136,.15), rgba(0,255,136,.05));
  }
  .thumb.placeholder::after{ display:none; }

  .card-body{ padding:16px; display:grid; gap:12px; }
  .card-title{ font-size:20px; font-weight:800; margin:0; }
  .meta{ display:flex; align-items:center; gap:8px; }
  .badge{ display:inline-flex; align-items:center; gap:8px; padding:6px 10px; border-radius:999px; font-size:13px; font-weight:700; letter-spacing:.2px; background: rgba(0,255,136,.08); color:#bfffe1; border:1px solid rgba(0,255,136,.25); text-transform:uppercase; }

  .btn{
    position:relative; overflow:hidden;
    display:inline-flex; justify-content:center; align-items:center; gap:10px; height:48px; padding:0 20px; border-radius:12px;
    color:#042d16; font-weight:900; letter-spacing:.3px; text-decoration:none; touch-action: manipulation;
    border:1px solid rgba(255,255,255,.18);
    background: linear-gradient(180deg, rgba(170,255,221,.95), rgba(122,253,208,.9));
    box-shadow: 0 0 0 2px rgba(122,253,208,.35) inset, 0 0 16px rgba(122,253,208,.6), 0 0 44px rgba(122,253,208,.25);
    transition: transform .18s ease, box-shadow .2s ease, filter .2s ease;
  }
  .btn::before{
    content:""; position:absolute; inset:-200% -20%; background: linear-gradient(90deg, rgba(255,255,255,.0) 10%, rgba(255,255,255,.35) 50%, rgba(255,255,255,0) 90%);
    transform: translateX(-60%); transition: transform .8s ease;
  }
  .btn:hover{ transform: translateY(-1px) scale(1.03); filter: brightness(1.02); }
  .btn:hover::before{ transform: translateX(60%); }
  .btn:active{ transform: translateY(0) scale(0.995); }
  .btn:focus{ outline:none; box-shadow: 0 0 0 3px rgba(122,253,208,.35), 0 0 0 6px rgba(122,253,208,.2), 0 0 22px rgba(122,253,208,.7); }

  .btn-ghost{
    color:#c7ffe9; background:rgba(0,255,136,.08);
    border:1px solid rgba(122,253,208,.35);
    box-shadow: inset 0 0 0 1px rgba(122,253,208,.12);
  }

  /* единый фон и в футере */
  .footer{ position:relative; z-index:1; color:var(--muted); text-align:center; padding:24px; border-top:1px solid rgba(0,255,136,.12); background: var(--bg); }

  .reveal{ opacity:0; transform: translateY(14px); transition: opacity .6s cubic-bezier(.2,.7,.2,1), transform .6s cubic-bezier(.2,.7,.2,1); will-change:opacity,transform; }
  .reveal.in{ opacity:1; transform:translateY(0); }

  /* 18+ */
  .guarded{ position:relative; }
  .guard-overlay{
    position:absolute; inset:0; display:flex; align-items:center; justify-content:center;
    background: linear-gradient(180deg, rgba(7,20,14,.88), rgba(7,20,14,.82));
    border-radius:16px; border:1px solid rgba(0,255,136,.15);
    z-index:2;
  }
  .guard-box{
    max-width:720px; padding:24px; border-radius:14px; text-align:center;
    background: linear-gradient(180deg, rgba(5,18,12,.9), rgba(5,18,12,.7));
    box-shadow: 0 12px 40px rgba(0,0,0,.5), 0 0 0 1px rgba(122,253,208,.18) inset;
  }
  .guard-actions{ margin-top:14px; display:flex; gap:10px; justify-content:center; flex-wrap:wrap; }
  .hidden{ display:none !important; }

  /* Оверлей внешних ссылок */
  .link-guard{
    position:fixed; inset:0; background:rgba(0,0,0,.55); backdrop-filter:blur(4px);
    z-index:10; display:flex; align-items:center; justify-content:center;
  }
  .link-guard .box{
    width:min(92vw,520px); padding:20px; border-radius:14px; text-align:center;
    background: linear-gradient(180deg, rgba(5,18,12,.95), rgba(5,18,12,.85));
    border:1px solid rgba(122,253,208,.28);
    box-shadow: 0 18px 60px rgba(0,0,0,.6), 0 0 0 1px rgba(122,253,208,.15) inset;
  }
  .link-guard .actions{ margin-top:14px; display:flex; gap:10px; justify-content:center; flex-wrap:wrap; }
  .link-guard strong{ color:#9fffd8 }

  /* Кастомный скроллбар */
  .scrollbar{
    position:fixed; right:14px; top:10px; bottom:10px; width:10px; z-index:6;
    pointer-events:none;
  }
  .scrollbar .track{
    position:absolute; inset:0;
    background: linear-gradient(180deg, rgba(122,253,208,.15), rgba(122,253,208,.06));
    border:1px solid rgba(122,253,208,.28);
    border-radius:999px;
    box-shadow: inset 0 0 0 1px rgba(122,253,208,.08);
  }
  .scrollbar .handle{
    position:absolute; left:-4px; width:18px; height:48px; top:0;
    border-radius:999px; pointer-events:auto; touch-action:none;
    background: linear-gradient(180deg, rgba(170,255,221,.95), rgba(122,253,208,.9));
    border:1px solid rgba(255,255,255,.18);
    box-shadow: 0 0 0 2px rgba(122,253,208,.35) inset, 0 6px 18px rgba(122,253,208,.4), 0 0 44px rgba(122,253,208,.25);
    transition: transform .12s ease;
  }
  @media (pointer: fine){
    .scrollbar .handle{ cursor: grab; }
    .scrollbar .handle:active{ cursor: grabbing; }
  }

  .back-top{
    position:fixed; right:48px; bottom:18px; z-index:7;
    opacity:0; transform: translateY(10px) scale(.98);
    transition: opacity .25s ease, transform .25s ease;
  }
  .back-top.show{ opacity:1; transform: translateY(0) scale(1); }

  /* Панель настроек (урезана) */
  .settings{
    position:fixed; right:18px; top:78px; z-index:7; width:min(92vw, 420px);
    padding:16px; border-radius:14px; border:1px solid rgba(122,253,208,.28);
    background: linear-gradient(180deg, rgba(5,18,12,.92), rgba(5,18,12,.8));
    box-shadow: 0 18px 60px rgba(0,0,0,.6), 0 0 0 1px rgba(122,253,208,.15) inset;
  }
  .settings h3{ margin:0 0 10px; font-weight:900; font-size:18px; }
  .settings .row{ display:flex; align-items:center; justify-content:space-between; gap:12px; padding:10px 0; border-bottom:1px dashed rgba(122,253,208,.2); }
  .settings .row:last-child{ border-bottom:none; }
  .settings .row label{ color:var(--muted); }
  .switch{
    --w:48px; --h:28px;
    position:relative; inline-size:var(--w); block-size:var(--h); border-radius:999px; background: rgba(0,255,136,.15);
    border:1px solid rgba(122,253,208,.35); box-shadow: inset 0 0 0 1px rgba(122,253,208,.12);
  }
  .switch input{ position:absolute; inset:0; opacity:0; }
  .switch i{
    position:absolute; top:2px; left:2px; inline-size:calc(var(--h) - 4px); block-size:calc(var(--h) - 4px); border-radius:999px;
    background: linear-gradient(180deg, rgba(170,255,221,.95), rgba(122,253,208,.9));
    box-shadow: 0 0 0 2px rgba(122,253,208,.35) inset, 0 6px 18px rgba(122,253,208,.4);
    transition: transform .18s ease;
  }
  .switch input:checked + i{ transform: translateX(calc(var(--w) - var(--h))); }

  /* Адаптив */
  @media (max-width:768px){
    .header{padding:18px}
    .header .container{padding:0 10px}
    .catalog{gap:16px}
    .card{grid-column: span 12}
    .btn{width:100%}
    .scrollbar{ right:10px; }
  }
  @media (max-width:640px){
    .hero{padding:24px 16px 0}
    .section{padding:0 16px}
    .catalog{padding:0 16px; gap:14px}
    .icon-btn{width:44px; height:44px}
    .back-top{ right:44px; }
  }
  @media (prefers-reduced-motion: reduce){ *{animation:none!important; transition:none!important} }
</style>
</head>
<body>
<canvas id="bg-space" aria-hidden="true"></canvas>
<div id="cursor" aria-hidden="true"></div>

<!-- Кастомный ползунок -->
<div class="scrollbar" id="scrollbar" aria-hidden="false">
  <div class="track" id="scrollbarTrack"></div>
  <div class="handle" id="scrollbarHandle" tabindex="0" role="slider" aria-orientation="vertical" aria-valuemin="0" aria-valuemax="100" aria-valuenow="0" aria-label="Прокрутка"></div>
</div>

<!-- Кнопка «Вверх» -->
<button id="backTop" class="back-top icon-btn" type="button" aria-label="Наверх" title="Наверх">
  <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
    <path d="M12 19V5"/><path d="M5 12l7-7 7 7"/>
  </svg>
</button>

<!-- Панель настроек (без тем/доверенных/скрытия нативного скролла/«Открыть 18+») -->
<div id="settings" class="settings hidden" role="dialog" aria-modal="true" aria-labelledby="settings-title">
  <h3 id="settings-title">Настройки</h3>
  <div class="row">
    <label for="sw-reduce-motion">Меньше анимаций</label>
    <span class="switch"><input id="sw-reduce-motion" type="checkbox"><i></i></span>
  </div>
  <div class="row">
    <label for="sw-tilt">3D-наклон карточек</label>
    <span class="switch"><input id="sw-tilt" type="checkbox" checked><i></i></span>
  </div>
  <div class="row">
    <label>Раздел 18+</label>
    <div class="flex g-8">
      <button class="btn btn-ghost" type="button" id="btn-adult-lock">Заблокировать</button>
      <!-- !открыть! удалено -->
    </div>
  </div>
</div>

<div class="fluxe-site" id="fluxe">
  <header class="header reveal">
    <div class="container">
      <div class="logo">fluxe</div>
      <div class="actions">
        <a class="icon-btn" href="https://fluxe240.github.io/game" target="_blank" rel="noopener noreferrer" aria-label="Предложить игру или программу">
          <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
            <path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h9"/>
            <path d="M16 3в6"/><path d="M13 6h6"/>
          </svg>
        </a>
        <button class="icon-btn" id="btn-settings" type="button" aria-haspopup="dialog" aria-controls="settings" aria-label="Открыть настройки" title="Настройки">
          <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
            <circle cx="12" cy="12" r="3"/><path d="M19.4 15a1.65 1.65 0 0 0 .33 1.82l.06.06a2 2 0 1 1-2.83 2.83l-.06-.06a1.65 1.65 0 0 0-1.82-.33 1.65 1.65 0 0 0-1 1.51V22a2 2 0 1 1-4 0v-.09a1.65 1.65 0 0 0-1-1.51 1.65 1.65 0 0 0-1.82.33l-.06.06a2 2 0 1 1-2.83-2.83l.06-.06a1.65 1.65 0 0 0 .33-1.82 1.65 1.65 0 0 0-1.51-1H2a2 2 0 1 1 0-4h.09a1.65 1.65 0 0 0 1.51-1 1.65 1.65 0 0 0-.33-1.82l-.06-.06a2 2 0 1 1 2.83-2.83l.06.06a1.65 1.65 0 0 0 1.82.33H8a1.65 1.65 0 0 0 1-1.51V2a2 2 0 1 1 4 0v.09a1.65 1.65 0 0 0 1 1.51 1.65 1.65 0 0 0 1.82-.33l.06-.06a2 2 0 1 1 2.83 2.83l-.06.06a1.65 1.65 0 0 0-.33 1.82V8c0 .66.26 1.3.73 1.77.47.47 1.11.73 1.77.73H22a2 2 0 1 1 0 4h-.09a1.65 1.65 0 0 0-1.51 1z"/>
          </svg>
        </button>
      </div>
    </div>
  </header>

  <section class="hero">
    <h1 class="title reveal">Скачивайте игры и программы в один клик</h1>
  </section>

  <!-- Игры -->
  <div class="section">
    <h2 class="section-title reveal">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2l2.64 5.35L20.7 8l-4.35 4.24L17.2 19 12 15.9 6.8 19l.85-6.76L3.3 8l6.06-.65L12 2z"/></svg>
      Игры
    </h2>
  </div>
  <section class="catalog" aria-label="Список игр">
    <article class="card reveal">
      <div class="thumb" style="background-image:url('https://buckshotroulette.com//data/image/game/buckshot-roulette-feature-image.jpg');"></div>
      <div class="card-body">
        <h3 class="card-title">Buckshot Roulette</h3>
        <div class="meta"><span class="badge">Онлайн: нет</span></div>
        <a class="btn" href="https://mega.nz/file/Xt5nAZwD#Ce9Q4PMAJ9ZwHImhzcW6sbP6ljY66CSdE6SBq_9z7U0" target="_blank" rel="noopener noreferrer nofollow">Скачать</a>
      </div>
    </article>

    <article class="card reveal">
      <div class="thumb" style="background-image:url('https://f4.bcbits.com/img/a0084845941_16.jpg');"></div>
      <div class="card-body">
        <h3 class="card-title">ULTRAKILL</h3>
        <div class="meta"><span class="badge">Онлайн: нет</span></div>
        <a class="btn" href="https://mega.nz/file/XwBXQBzZ#T0mLOXEwsD-jkMeAmrOseM6uSABdOE8fDh8pTYhzLzQ" target="_blank" rel="noopener noreferrer nofollow">Скачать</a>
      </div>
    </article>

    <article class="card reveal">
      <div class="thumb" style="background-image:url('https://itorrents-igruha.org/uploads/posts/2023-01/1672795576_cover.jpg');"></div>
      <div class="card-body">
        <h3 class="card-title">Hotline Miami</h3>
        <div class="meta"><span class="badge">Онлайн: нет</span></div>
        <a class="btn" href="https://mega.nz/file/LkQ0VDoD#2Af6pxZq4K6ADTrw_YhDHDhpl_Dvv44dfTCyvuLcGiM" target="_blank" rel="noopener noreferrer nofollow">Скачать</a>
      </div>
    </article>

    <article class="card reveal">
      <div class="thumb" style="background-image:url('https://i.playground.ru/e/HB-5Xo_DO35lX0_FVIlIHQ.jpeg?600-600');"></div>
      <div class="card-body">
        <h3 class="card-title">ленивая принцесса-монстр не хочет работать</h3>
        <div class="meta"><span class="badge">Онлайн: нет</span></div>
        <a class="btn" href="https://mega.nz/file/e5hhgYzB#JaLJwF_EwO0xg6qljqPCKINXbwFgqIOA-GZDLmef07U" target="_blank" rel="noopener noreferrer nofollow">Скачать</a>
      </div>
    </article>

    <article class="card reveal">
      <div class="thumb" style="background-image:url('https://i.redd.it/zozlzva328291.jpg');"></div>
      <div class="card-body">
        <h3 class="card-title">Five nights at Floppa</h3>
        <div class="meta"><span class="badge">Онлайн: нет</span></div>
        <a class="btn" href="https://mega.nz/file/ywATmbTB#qHoCjHIJwPwbLF5n_AQsELVG8YHk9_LfW49mH2a17Xs" target="_blank" rel="noopener noreferrer nofollow">Скачать</a>
      </div>
    </article>
  </section>

  <!-- Порно игры -->
  <div class="section">
    <h2 class="section-title reveal">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
        <path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 1 0-7.78 7.78L12 21.23l8.84-8.84a5.5 5.5 0 0 0 0-7.78z"/>
      </svg>
      Порно игры
    </h2>
  </div>
  <div class="guarded" id="adult-wrap">
    <section class="catalog" id="adult-catalog" aria-label="Список порно-игр" inert aria-hidden="true">
      <article class="card reveal">
        <div class="thumb" style="background-image:url('https://i.ytimg.com/vi/YOROzc-8Uqg/maxresdefault.jpg');"></div>
        <div class="card-body">
          <h3 class="card-title">furry hitler</h3>
          <div class="meta"><span class="badge">Онлайн: нет</span></div>
          <a class="btn" href="https://mega.nz/file/L4YSRCDK#f2ulGEi7JEO6N6friM_t_XvyxgKDHBCXZSeRcwzY96M" target="_blank" rel="noopener noreferrer nofollow">Скачать</a>
        </div>
      </article>
    </section>
    <div class="guard-overlay" id="adult-guard">
      <div class="guard-box">
        <h3>Раздел 18+</h3>
        <p style="margin:0; color:var(--muted)">Материалы для взрослых. Подтвердите, что вам 18 лет.</p>
        <div class="guard-actions">
          <button class="btn" id="btn-allow-adult">Мне 18+</button>
          <button class="btn btn-ghost" id="btn-hide-adult">Скрыть раздел</button>
        </div>
        <small style="color:var(--muted); display:block; margin-top:8px;">Настройка сохраняется в браузере.</small>
      </div>
    </div>
  </div>

  <!-- Читы -->
  <div class="section">
    <h2 class="section-title reveal">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 20l9-16H3l9 16z"/><path d="M12 8v4"/></svg>
      Читы
    </h2>
  </div>
  <section class="catalog" aria-label="Список читов">
    <article class="card reveal">
      <div class="thumb" style="background-image:url('https://rscripts.net/assets/executors/XenoLogo.webp');"></div>
      <div class="card-body">
        <h3 class="card-title">xeno</h3>
        <div class="meta"><span class="badge">Для: Roblox</span></div>
        <a class="btn" href="https://mega.nz/file/jg4m2BQb#sBgZ5Pgilrdtv1Pp2-uYAN_-OTLYN8W29pta9hpoQ8E" target="_blank" rel="noopener noreferrer nofollow">Скачать</a>
      </div>
    </article>

    <article class="card reveal">
      <div class="thumb" style="background-image:url('https://getsolara.dev/images/iconfull.png'); background-size:contain; background-color:rgba(0,255,136,.06);"></div>
      <div class="card-body">
        <h3 class="card-title">solara</h3>
        <div class="meta"><span class="badge">Для: Roblox</span></div>
        <a class="btn" href="https://mega.nz/file/TwARXBQL#n-Ht5S4lY6whFMz17sM8RhvaXuOAAKoB6Q60vthqSok" target="_blank" rel="noopener noreferrer nofollow">Скачать</a>
      </div>
    </article>

    <article class="card reveal">
      <div class="thumb" style="background-image:url('https://cdn4.telesco.pe/file/DGNmtilFqeS0gU9OGta0qPnOv4MgWavbi_Ermfgn8YoBmVXdxtJrAL695NCCIqx5BemV2yw1aMheU2lyhU64bPtKyWJJogtjGHwGj9_FcVda3n7oNhfRQ81r4-pu9vorcZNvbxyxvz6pEEoy4CqT29HjJhlFPmmzWmEGqvmVnZGIGGKNbM2GtIKmX-Eme5EJ4tqHFbXg0NW0zzLlMXMsMwdCQEYid9Qk9vVBsPiRDNQxONa8RTlcJEECuLmGoZ7N9OWaVXV-h3ZI5MZPSBFmVs1vQ_eXzubiarBWUcu8LPdrwzVJJijNnQREDeVOh4SdGv2CKSMJ7YHSFr7wons0iQ.jpg');"></div>
      <div class="card-body">
        <h3 class="card-title">sharkhack</h3>
        <div class="meta"><span class="badge">Для: Counter-Strike 2</span></div>
        <a class="btn" href="https://mega.nz/file/OhBRRSQR#DC9RjxDpa7fCKd27sFjLPfBBvl4q3rh6fajcwDH2ml4" target="_blank" rel="noopener noreferrer nofollow">Скачать</a>
      </div>
    </article>
  </section>

  <!-- Ссылки -->
  <div class="section">
    <h2 class="section-title reveal">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M10 13a5 5 0 0 1 0-7l1-1a5 5 0 0 1 7 7l-1 1"/><path d="M14 11a5 5 0 0 1 0 7l-1 1a5 5 0 0 1-7-7l1-1"/></svg>
      Ссылки
    </h2>
  </div>
  <section class="catalog" aria-label="Полезные ссылки">
    <article class="card reveal">
      <div class="thumb" id="thumb-manilua"></div>
      <div class="card-body">
        <h3 class="card-title">manilua</h3>
        <a class="btn" href="https://www.piracybound.com/manilua" target="_blank" rel="noopener noreferrer">Перейти</a>
      </div>
    </article>

    <article class="card reveal">
      <div class="thumb" style="background-image:url('https://steamdb.info/static/logos/512px.png'); background-size:contain; background-color:rgba(0,255,136,.06);"></div>
      <div class="card-body">
        <h3 class="card-title">Steam DB</h3>
        <a class="btn" href="https://steamdb.info/" target="_blank" rel="noopener noreferrer">Перейти</a>
      </div>
    </article>
  </section>

  <!-- Предупреждение при внешнем переходе -->
  <div id="ext-guard" class="link-guard hidden" aria-hidden="true" role="dialog" aria-modal="true">
    <div class="box">
      <h3 style="margin:0 0 8px; font-size:20px; font-weight:800;">Переход на внешний сайт</h3>
      <p style="margin:0 0 12px; color:var(--muted);">Вы покидаете fluxe и переходите на: <strong id="ext-host"></strong></p>
      <div class="actions">
        <button class="btn" id="ext-continue">Продолжить</button>
        <button class="btn btn-ghost" id="ext-cancel">Отмена</button>
      </div>
      <small style="display:block; margin-top:10px; color:var(--muted);">Проверяйте файлы антивирусом и не вводите личные данные на подозрительных сайтах.</small>
    </div>
  </div>

  <footer class="footer reveal">
    <small>by pelemeuu</small>
  </footer>
</div>

<script nonce="LEAVES">
document.addEventListener('DOMContentLoaded', () => {
  // Скрываем нативный скроллбар (второй ползунок)
  document.documentElement.classList.add('no-native-scrollbar');
  document.body.classList.add('no-native-scrollbar');

  // Reveal
  const animated = document.querySelectorAll('.reveal');
  const io = new IntersectionObserver((entries, obs) => {
    entries.forEach(e => { if(e.isIntersecting){ e.target.classList.add('in'); obs.unobserve(e.target); } });
  }, { threshold: .12, rootMargin: "0px 0px -8% 0px" });
  animated.forEach(el => io.observe(el));
  setTimeout(() => document.querySelectorAll('.hero .reveal').forEach(el => el.classList.add('in')), 80);

  // Рандом для manilua
  const m = document.getElementById('thumb-manilua');
  if(m){
    const r = Math.floor(Math.random()*1e7);
    m.style.background = `url('https://picsum.photos/800/600?random=${r}') center/cover no-repeat`;
    m.style.paddingTop = '58%';
    m.classList.remove('placeholder');
  }

  // Кастомный курсор — всегда виден
  const hasFine = window.matchMedia('(pointer: fine)').matches;
  if(hasFine){
    const c = document.getElementById('cursor');
    if (c){
      let x=window.innerWidth/2, y=window.innerHeight/2, tx=x, ty=y;
      const follow = 0.35;
      function loop(){
        x += (tx - x) * follow;
        y += (ty - y) * follow;
        c.style.transform = `translate(${x}px, ${y}px) translate(-50%,-50%)`;
        requestAnimationFrame(loop);
      }
      window.addEventListener('mousemove', e => { tx = e.clientX; ty = e.clientY; }, {passive:true});
      loop();
    }
  }

  // Фон-листья — всегда работают, не пропадают при resize
  (function(){
    const cv = document.getElementById('bg-space'); if(!cv) return;
    const ctx = cv.getContext('2d');
    let leaves = [], w=0, h=0, dpr=1, last=0;

    function density(){ return window.matchMedia('(max-width:768px)').matches ? 0.00006 : 0.0001; }
    function rand(a,b){ return a + Math.random()*(b-a); }

    function createLeaf(){
      const mobile = window.matchMedia('(max-width:768px)').matches;
      return {
        x: rand(0, w),
        y: rand(-h, h),
        size: rand(6, mobile ? 14 : 18),
        speedY: rand(20, 45),
        swayF: rand(0.12, 0.35),
        swayAmp: rand(10, 22),
        phase: rand(0, Math.PI*2),
        hue: rand(120, 160)
      };
    }

    function ensureCount(){
      const target = Math.max(12, Math.floor(w*h*density()));
      if(leaves.length < target){
        const add = target - leaves.length;
        for(let i=0;i<add;i++) leaves.push(createLeaf());
      }else if(leaves.length > target){
        leaves.length = target;
      }
    }

    function setSize(){
      const oldW = w || 1, oldH = h || 1;
      dpr = Math.max(1, window.devicePixelRatio||1);
      w = Math.max(document.documentElement.clientWidth, window.innerWidth||0);
      h = Math.max(document.documentElement.clientHeight, window.innerHeight||0);
      cv.width = Math.floor(w*dpr); cv.height = Math.floor(h*dpr);
      cv.style.width = w+'px'; cv.style.height = h+'px';
      ctx.setTransform(1,0,0,1,0,0); ctx.scale(dpr,dpr);

      const sx = w/oldW, sy = h/oldH;
      for(const l of leaves){ l.x *= sx; l.y *= sy; }

      ensureCount();
    }

    function drawLeaf(l){
      const s = l.size;
      ctx.save();
      ctx.translate(l.x, l.y);

      const grad = ctx.createLinearGradient(0, -s/2, 0, s/2);
      grad.addColorStop(0, `hsla(${l.hue}, 80%, 52%, 0.32)`);
      grad.addColorStop(1, `hsla(${l.hue+20}, 70%, 40%, 0.22)`);
      ctx.fillStyle = grad;

      ctx.beginPath();
      ctx.ellipse(0, 0, s/2, s, 0, 0, Math.PI*2);
      ctx.fill();

      ctx.globalAlpha = 0.28;
      ctx.strokeStyle = `hsla(${l.hue}, 40%, 30%, 1)`;
      ctx.lineWidth = Math.max(0.6, s*0.06);
      ctx.beginPath();
      ctx.moveTo(0, -s*0.6);
      ctx.lineTo(0,  s*0.6);
      ctx.stroke();
      ctx.globalAlpha = 1;

      ctx.restore();
    }

    function step(t){
      if(!last) last = t;
      const dt = Math.min(0.033, (t - last)/1000);
      last = t;
      const time = t*0.001;

      ctx.clearRect(0,0,w,h);
      for(const leaf of leaves){
        leaf.y += leaf.speedY * dt;
        leaf.x += Math.sin((Math.PI*2)*leaf.swayF * time + leaf.phase) * (leaf.swayAmp * dt);

        if(leaf.y > h + leaf.size){
          leaf.y = -leaf.size*4;
          leaf.x = rand(0, w);
        }
        drawLeaf(leaf);
      }
      requestAnimationFrame(step);
    }

    window.addEventListener('resize', setSize, {passive:true});
    setSize(); ensureCount(); requestAnimationFrame(step);
  })();

  // Защита 18+
  (function(){
    const wrap = document.getElementById('adult-wrap');
    const catalog = document.getElementById('adult-catalog');
    const guard = document.getElementById('adult-guard');
    const accept = document.getElementById('btn-allow-adult');
    const hide = document.getElementById('btn-hide-adult');
    if(!wrap || !catalog || !guard) return;
    function openAdult(){ catalog.removeAttribute('inert'); catalog.removeAttribute('aria-hidden'); guard.classList.add('hidden'); }
    function lockAdult(){ catalog.setAttribute('inert',''); catalog.setAttribute('aria-hidden','true'); guard.classList.remove('hidden'); }
    if(localStorage.getItem('adult-ok') === '1') openAdult(); else lockAdult();
    accept && accept.addEventListener('click', () => { localStorage.setItem('adult-ok','1'); openAdult(); });
    hide && hide.addEventListener('click', () => { localStorage.removeItem('adult-ok'); wrap.classList.add('hidden'); });
  })();

  // Внешние ссылки (без доверенных доменов)
  (function(){
    const modal = document.getElementById('ext-guard');
    const hostEl = document.getElementById('ext-host');
    const go = document.getElementById('ext-continue');
    const cancel = document.getElementById('ext-cancel');
    if(!modal || !hostEl || !go || !cancel) return;

    let pendingURL = null, pendingTarget = '_blank';

    function close(){ modal.classList.add('hidden'); modal.setAttribute('aria-hidden','true'); pendingURL=null; }
    function open(url, target){
      const u = new URL(url, location.href);
      hostEl.textContent = u.hostname;
      pendingURL = url; pendingTarget = target || '_blank';
      modal.classList.remove('hidden'); modal.removeAttribute('aria-hidden');
      setTimeout(()=> go.focus(), 0);
    }

    document.addEventListener('click', (e) => {
      const a = e.target.closest('a[href]');
      if(!a) return;
      const u = new URL(a.href, location.href);
      if(u.origin === location.origin || u.hash) return;
      if(a.hasAttribute('data-skip-guard')) return;
      if(e.button!==0 || e.metaKey || e.ctrlKey || e.shiftKey || e.altKey) return;
      e.preventDefault();
      open(a.href, a.target);
    }, true);

    go.addEventListener('click', () => {
      if(!pendingURL) return close();
      const win = window.open('', pendingTarget || '_blank', 'noopener,noreferrer');
      if(win) { win.location = pendingURL; }
      close();
    });
    cancel.addEventListener('click', close);
    document.addEventListener('keydown', e => { if(e.key==='Escape') close(); });
  })();

  // Кастомный ползунок
  (function(){
    const bar = document.getElementById('scrollbar');
    const track = document.getElementById('scrollbarTrack');
    const handle = document.getElementById('scrollbarHandle');
    if(!bar || !track || !handle) return;

    let trackRect = null, handleH = 48, maxHandleY = 0, dragging = false, dragOffsetY = 0;

    function sizes(){
      trackRect = track.getBoundingClientRect();
      const doc = document.documentElement;
      const vh = window.innerHeight;
      const sh = Math.max(doc.scrollHeight, document.body.scrollHeight);
      const ratio = Math.min(1, vh / sh);
      handleH = Math.max(38, Math.floor(trackRect.height * ratio));
      maxHandleY = Math.max(0, trackRect.height - handleH);
      handle.style.height = handleH + 'px';
      bar.style.display = (sh <= vh + 2) ? 'none' : '';
      update();
    }
    function update(){
      const doc = document.documentElement;
      const vh = window.innerHeight;
      const sh = Math.max(doc.scrollHeight, document.body.scrollHeight);
      const st = window.scrollY || doc.scrollTop || 0;
      const maxScroll = Math.max(1, sh - vh);
      const progress = Math.min(1, Math.max(0, st / maxScroll));
      const y = progress * maxHandleY;
      handle.style.transform = `translateY(${y}px)`;
      handle.setAttribute('aria-valuenow', Math.round(progress*100));
    }
    function scrollToHandleY(y){
      y = Math.min(maxHandleY, Math.max(0, y));
      const doc = document.documentElement;
      const vh = window.innerHeight;
      const sh = Math.max(doc.scrollHeight, document.body.scrollHeight);
      const maxScroll = Math.max(1, sh - vh);
      const progress = (maxHandleY ? (y / maxHandleY) : 0);
      window.scrollTo({ top: progress * maxScroll, behavior: 'instant' in window ? 'instant' : 'auto' });
    }
    function onDown(clientY, targetIsHandle){
      dragging = true;
      const handleTop = (handle.getBoundingClientRect().top - trackRect.top);
      dragOffsetY = targetIsHandle ? (clientY - (trackRect.top + handleTop)) : (handleH/2);
      document.addEventListener('mousemove', onMove, {passive:false});
      document.addEventListener('mouseup', onUp, {passive:true});
      document.addEventListener('touchmove', onTouchMove, {passive:false});
      document.addEventListener('touchend', onUp, {passive:true});
      if(!targetIsHandle){
        const desiredY = clientY - trackRect.top - dragOffsetY;
        scrollToHandleY(desiredY);
      }
    }
    function onMove(e){
      if(!dragging) return;
      e.preventDefault();
      const clientY = e.clientY;
      scrollToHandleY(clientY - trackRect.top - dragOffsetY);
    }
    function onTouchMove(e){
      if(!dragging) return;
      e.preventDefault();
      const t = e.touches[0];
      scrollToHandleY(t.clientY - trackRect.top - dragOffsetY);
    }
    function onUp(){
      dragging = false;
      document.removeEventListener('mousemove', onMove);
      document.removeEventListener('mouseup', onUp);
      document.removeEventListener('touchmove', onTouchMove);
      document.removeEventListener('touchend', onUp);
    }
    track.addEventListener('mousedown', e => onDown(e.clientY, e.target === handle), {passive:true});
    handle.addEventListener('mousedown', e => onDown(e.clientY, true), {passive:true});
    track.addEventListener('touchstart', e => onDown(e.touches[0].clientY, e.target === handle), {passive:true});
    handle.addEventListener('touchstart', e => onDown(e.touches[0].clientY, true), {passive:true});
    handle.addEventListener('keydown', (e) => {
      const stepPx = 60;
      const pagePx = window.innerHeight * 0.85;
      if(['ArrowUp','ArrowDown','PageUp','PageDown','Home','End'].includes(e.key)){ e.preventDefault(); }
      if(e.key==='ArrowUp') window.scrollBy(0, -stepPx);
      if(e.key==='ArrowDown') window.scrollBy(0, stepPx);
      if(e.key==='PageUp') window.scrollBy(0, -pagePx);
      if(e.key==='PageDown') window.scrollBy(0, pagePx);
      if(e.key==='Home') window.scrollTo({top:0, behavior:'auto'});
      if(e.key==='End') window.scrollTo({top:document.documentElement.scrollHeight, behavior:'auto'});
    });
    window.addEventListener('scroll', update, {passive:true});
    window.addEventListener('resize', () => { sizes(); }, {passive:true});
    const ro = new ResizeObserver(()=> sizes());
    ro.observe(document.documentElement);
    setTimeout(sizes, 0);
  })();

  // 3D-наклон карточек (переключаемый)
  (function(){
    const fine = window.matchMedia('(pointer: fine)').matches;
    if(!fine) return;
    const cards = document.querySelectorAll('.card');
    let enabled = localStorage.getItem('opt-tilt') !== '0';
    function on(e){
      if(!enabled) return;
      const card = e.currentTarget;
      const rect = card.getBoundingClientRect();
      const cx = rect.left + rect.width/2;
      const cy = rect.top + rect.height/2;
      const dx = (e.clientX - cx) / (rect.width/2);
      const dy = (e.clientY - cy) / (rect.height/2);
      const max = 7;
      card.style.transform = `rotateX(${-dy*max}deg) rotateY(${dx*max}deg) translateY(-2px)`;
    }
    const off = e => { e.currentTarget.style.transform = ''; };
    cards.forEach(c => { c.addEventListener('mousemove', on); c.addEventListener('mouseleave', off); });
    window.__setTilt = (v)=>{ enabled = !!v; };
  })();

  // Кнопка «Вверх»
  (function(){
    const btn = document.getElementById('backTop'); if(!btn) return;
    const showAt = 320;
    function onScroll(){
      (window.scrollY || document.documentElement.scrollTop || 0) > showAt
        ? btn.classList.add('show') : btn.classList.remove('show');
    }
    window.addEventListener('scroll', onScroll, {passive:true});
    btn.addEventListener('click', () => window.scrollTo({top:0, behavior:'smooth'}));
    onScroll();
  })();

  // Панель настроек (урезанная)
  (function(){
    const panel = document.getElementById('settings');
    const btn = document.getElementById('btn-settings');
    const swReduce = document.getElementById('sw-reduce-motion');
    const swTilt = document.getElementById('sw-tilt');
    const btnAdultLock = document.getElementById('btn-adult-lock');
    if(!panel || !btn) return;

    const KEYS = { reduce: 'opt-reduce-motion', tilt: 'opt-tilt' };
    const applyReduce = v => {
      document.documentElement.style.setProperty('scroll-behavior', v ? 'auto' : 'smooth');
      document.documentElement.toggleAttribute('data-reduce', v);
    };
    const stReduce = localStorage.getItem(KEYS.reduce) === '1';
    const stTilt = localStorage.getItem(KEYS.tilt) !== '0';
    swReduce && (swReduce.checked = stReduce, applyReduce(stReduce));
    swTilt && (swTilt.checked = stTilt, window.__setTilt?.(stTilt));
    swReduce && swReduce.addEventListener('change', e => { localStorage.setItem(KEYS.reduce, e.target.checked ? '1':'0'); applyReduce(e.target.checked); });
    swTilt && swTilt.addEventListener('change', e => { localStorage.setItem(KEYS.tilt, e.target.checked ? '1':'0'); window.__setTilt?.(e.target.checked); });

    btn.addEventListener('click', () => { panel.classList.toggle('hidden'); if(!panel.classList.contains('hidden')){ panel.querySelector('button, input')?.focus(); } });
    document.addEventListener('keydown', e => { if(e.key==='Escape'){ panel.classList.add('hidden'); } });

    btnAdultLock && btnAdultLock.addEventListener('click', () => { localStorage.removeItem('adult-ok'); location.reload(); });
  })();

  // Усиленный запрет копирования/выделения
  document.addEventListener('copy', e => e.preventDefault());
  document.addEventListener('cut', e => e.preventDefault());
  document.addEventListener('selectstart', e => e.preventDefault());
  document.addEventListener('dragstart', e => e.preventDefault());

  // Авто-подгон заголовка под одну строку
  (function(){
    const t = document.querySelector('.title'); if(!t) return;
    function fit(){
      t.style.fontSize = '';
      let i = 0, min = 14, fs = parseFloat(getComputedStyle(t).fontSize) || 24;
      while(t.scrollWidth > t.clientWidth && fs > min && i < 40){
        fs -= 1; i++;
        t.style.fontSize = fs+'px';
      }
    }
    window.addEventListener('resize', () => { requestAnimationFrame(fit); }, {passive:true});
    setTimeout(fit, 50);
  })();
});
</script>
</body>
</html>
