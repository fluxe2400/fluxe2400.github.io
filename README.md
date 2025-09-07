<!doctype html>
<html lang="ru">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover">
<title>fluxe — предложить игру/программу</title>
<meta name="theme-color" content="#07140e">
<style>
  :root{ --bg:#07140e; --green:#00ff88; --text:#eaf9f1; --muted:#b6e3c8; --accent:#7afdd0; }

  body{
    margin:0; color:var(--text);
    font-family:Inter, system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
    background:
      radial-gradient(1200px 800px at 10% -10%, #0b2a1c 0%, var(--bg) 40%),
      radial-gradient(1000px 700px at 110% 10%, #0c3a25 0%, var(--bg) 30%),
      var(--bg);
    -webkit-tap-highlight-color: transparent;
  }

  /* Космос и курсор */
  #bg-space{ position:fixed; inset:0; width:100vw; height:100vh; z-index:0; pointer-events:none; display:block; }
  @media (pointer: fine){
    html, body{ cursor:none; }
    #cursor{
      position:fixed; left:0; top:0; width:18px; height:18px; border-radius:50%;
      background:rgba(255,255,255,.6); box-shadow:0 0 12px rgba(255,255,255,.35);
      transform: translate(-50%,-50%); pointer-events:none; z-index:5; transition: width .18s ease, height .18s ease, background .18s ease, box-shadow .18s ease;
      mix-blend-mode:screen;
    }
    .cursor-big{ width:28px!important; height:28px!important; background:rgba(255,255,255,.5)!important; box-shadow:0 0 18px rgba(255,255,255,.45)!important; }
  }

  .wrap{ position:relative; z-index:1; max-width:720px; margin:40px auto; padding:0 16px; }
  .box{ background: rgba(5,18,12,.8); border:1px solid rgba(0,255,136,.25); border-radius:16px; padding:18px; box-shadow:0 8px 24px rgba(0,0,0,.35); }
  .header{ display:flex; align-items:center; justify-content:space-between; margin-bottom:16px; }

  .logo{
    font-weight:900; font-size:24px; letter-spacing:.6px; line-height:1;
    background: linear-gradient(90deg, #eafff7 0%, #6bffb5 30%, #00ff88 50%, #9fffd8 70%, #eafff7 100%);
    -webkit-background-clip:text; background-clip:text; color:transparent;
    filter: drop-shadow(0 0 10px rgba(0,255,136,.35)); animation: logoGlow 8s ease-in-out infinite;
    user-select:none;
  }
  @keyframes logoGlow{ 0%,100%{ background-position:0% 50%; } 50%{ background-position:100% 50%; } }

  .icon-btn{ width:44px; height:44px; border-radius:50%; background: rgba(0,255,136,.12); border:1px solid rgba(0,255,136,.25); box-shadow: 0 0 12px rgba(0,255,136,.35), 0 0 24px rgba(0,255,136,.15); display:inline-flex; align-items:center; justify-content:center; color:var(--green); text-decoration:none; touch-action: manipulation; }

  .title{ margin:0 0 14px; font-size:26px; font-weight:900; color:#dffdf0; text-shadow:0 0 12px rgba(0,255,136,.25); }
  label{ display:block; margin:10px 0 6px; color:#cfeede; font-size:14px; }
  input[type="text"], input[type="url"], input[type="number"]{
    width:100%; padding:12px 12px; border-radius:12px; border:1px solid rgba(0,255,136,.25);
    background:rgba(0,255,136,.06); color:#eaf9f1; outline:none; font-size:16px;
  }
  .row{ display:grid; gap:10px; }

  /* Капча v2 */
  .captcha-block{ display:grid; gap:10px; margin-top:6px; }
  .cap-human{ display:flex; align-items:center; gap:10px; }
  .cap-human input{ width:20px; height:20px; }
  .cap-wrap{ display:grid; grid-template-columns: 1fr auto; align-items:end; gap:10px; }
  .cap-box{ display:flex; align-items:center; gap:10px; padding:10px 12px; border-radius:12px; border:1px solid rgba(0,255,136,.25); background:rgba(0,255,136,.06); }
  .cap-q{ font-weight:800; color:#bfffe1; letter-spacing:.3px; }
  .cap-field{ width:140px; }
  .cap-refresh{ height:44px; border-radius:10px; padding:0 12px; border:1px solid rgba(0,255,136,.25); background:transparent; color:#bfffe1; cursor:pointer; touch-action: manipulation; }
  .cap-note{ font-size:12px; color:#8acfb1; }

  .actions{ display:flex; gap:8px; margin-top:14px; }
  .btn{
    position:relative; overflow:hidden;
    display:inline-flex; align-items:center; justify-content:center; gap:8px; height:48px; padding:0 16px; border-radius:12px;
    background: linear-gradient(180deg, rgba(170,255,221,.95), rgba(122,253,208,.9)); color:#042d16; font-weight:800; border:1px solid rgba(255,255,255,.18); cursor:pointer; touch-action: manipulation; font-size:16px;
    box-shadow: 0 0 0 2px rgba(122,253,208,.35) inset, 0 0 16px rgba(122,253,208,.6), 0 0 44px rgba(122,253,208,.25);
  }
  .btn::before{ content:""; position:absolute; inset:-200% -20%; background: linear-gradient(90deg, rgba(255,255,255,0) 10%, rgba(255,255,255,.35) 50%, rgba(255,255,255,0) 90%); transform:translateX(-60%); transition: transform .8s ease; }
  .btn:hover::before{ transform:translateX(60%); }
  .btn.secondary{ background: transparent; color:#bfffe1; border:1px solid rgba(0,255,136,.25); box-shadow:none; }

  .ok{ padding:12px; border-radius:12px; background:rgba(0,255,136,.12); border:1px solid rgba(0,255,136,.3); color:#bfffe1; margin-top:12px; transition: opacity .3s ease; }

  .reveal{ opacity:0; transform: translateY(12px); transition: opacity .6s cubic-bezier(.2,.7,.2,1), transform .6s cubic-bezier(.2,.7,.2,1); }
  .reveal.in{ opacity:1; transform:none; }

  @media (max-width:768px){
    .wrap{padding:0 14px}
    .btn{width:100%}
    .cap-field{width:120px}
  }
  @media (prefers-reduced-motion: reduce){ *{animation:none!important; transition:none!important} }
</style>
</head>
<body>
<canvas id="bg-space" aria-hidden="true"></canvas>
<div id="cursor" aria-hidden="true"></div>

<div class="wrap">
  <div class="header reveal">
    <div class="logo">fluxe</div>
    <a class="icon-btn" href="https://fluxe240.github.io/" aria-label="На главную">
      <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M15 18l-6-6 6-6"/></svg>
    </a>
  </div>

  <div class="box reveal">
    <h1 class="title">Подача заявки</h1>
    <form id="appForm" class="row" autocomplete="off" novalidate>
      <div>
        <label for="nick">Ваш ник</label>
        <input type="text" id="nick" required placeholder="например, (рандомный ник)">
      </div>
      <div>
        <label for="title">Название игры/программы</label>
        <input type="text" id="title" required placeholder="например, Buckshot Roulette">
      </div>
      <div>
        <label for="vt">Ссылка на VirusTotal</label>
        <input type="url" id="vt" required placeholder="https://www.virustotal.com/..." inputmode="url">
      </div>
      <div>
        <label for="link">Ссылка на скачивание</label>
        <input type="url" id="link" required placeholder="https://..." inputmode="url">
      </div>

      <!-- Капча v2 -->
      <div class="captcha-block">
        <div class="cap-human">
          <input type="checkbox" id="capHuman">
          <label for="capHuman">Я человек</label>
        </div>

        <div id="capChallenge" class="cap-wrap" style="display:none;">
          <div class="cap-box">
            <span class="cap-q" id="capQ">(2 + 3) × 2 = ?</span>
            <input class="cap-field" type="number" id="capA" inputmode="numeric" placeholder="Ответ" aria-label="Ответ на пример">
          </div>
          <button type="button" class="cap-refresh" id="capR">Обновить</button>
          <div class="cap-note" style="grid-column:1/-1;">Подождите 2 секунды и решите пример.</div>
        </div>

        <!-- honeypot -->
        <div style="position:absolute; left:-5000px; top:auto; width:1px; height:1px; overflow:hidden;" aria-hidden="true">
          <label>Оставьте пустым</label>
          <input type="text" id="hp_field" tabindex="-1" autocomplete="off">
        </div>
      </div>

      <div class="actions">
        <button class="btn" type="submit" id="submitBtn" disabled>Отправить</button>
        <button class="btn secondary" type="reset" id="resetBtn">Сброс</button>
      </div>

      <div id="result" class="ok" style="display:none;"></div>
    </form>
  </div>
</div>

<script>
document.addEventListener('DOMContentLoaded', () => {
  // Reveal
  const animated = document.querySelectorAll('.reveal');
  const io = new IntersectionObserver((entries, obs) => {
    entries.forEach(e => { if(e.isIntersecting){ e.target.classList.add('in'); obs.unobserve(e.target); } });
  }, { threshold: .1 });
  animated.forEach(el => io.observe(el));

  // Космос
  const prefersReduce = window.matchMedia('(prefers-reduced-motion: reduce)').matches;
  if(!prefersReduce){
    const cv = document.getElementById('bg-space');
    const ctx = cv.getContext('2d');
    let stars=[], raf=null;
    function density(){ return window.matchMedia('(max-width:768px)').matches ? 0.0001 : 0.00018; }
    function setSize(){
      const dpr = Math.max(1, window.devicePixelRatio||1);
      const w = Math.max(document.documentElement.clientWidth, window.innerWidth||0);
      const h = Math.max(document.documentElement.clientHeight, window.innerHeight||0);
      cv.width = Math.floor(w*dpr); cv.height = Math.floor(h*dpr);
      cv.style.width = w+'px'; cv.style.height = h+'px';
      ctx.setTransform(1,0,0,1,0,0); ctx.scale(dpr,dpr);
      build(w,h);
    }
    function build(w,h){
      const n = Math.floor(w*h*density());
      stars = new Array(n).fill(0).map(()=>({
        x: Math.random()*w,
        y: Math.random()*h,
        r: Math.random()<0.8 ? (Math.random()*1.2+0.6) : (Math.random()*1.8+1.0),
        hue: 160 + Math.random()*60,
        phase: Math.random()*Math.PI*2,
        speed: 0.5 + Math.random()*1.3
      }));
    }
    function step(t){
      const w=cv.clientWidth,h=cv.clientHeight;
      ctx.clearRect(0,0,w,h);
      for(const s of stars){
        const time = (t||0)*0.001;
        const tw = 0.4 + 0.6*Math.sin(s.phase + time*s.speed*2.2);
        const alpha = 0.25 + 0.75*tw;
        ctx.beginPath();
        ctx.fillStyle = `hsla(${s.hue}, 80%, 85%, ${alpha.toFixed(3)})`;
        ctx.arc(s.x, s.y, s.r*(0.9 + 0.15*tw), 0, Math.PI*2);
        ctx.fill();
      }
      raf = requestAnimationFrame(step);
    }
    function start(){ if(raf) return; setSize(); raf=requestAnimationFrame(step); }
    function stop(){ if(raf){ cancelAnimationFrame(raf); raf=null; } }
    window.addEventListener('resize', setSize, {passive:true});
    document.addEventListener('visibilitychange', ()=>{ if(document.hidden) stop(); else start(); });
    start();
  }

  // Кастомный курсор
  const hasFine = window.matchMedia('(pointer: fine)').matches;
  if(hasFine){
    const c = document.getElementById('cursor');
    let x=window.innerWidth/2, y=window.innerHeight/2, tx=x, ty=y, raf=null;
    function loop(){ x+=(tx-x)*0.18; y+=(ty-y)*0.18; c.style.transform=`translate(${x}px, ${y}px) translate(-50%,-50%)`; raf=requestAnimationFrame(loop); }
    window.addEventListener('mousemove', e => { tx=e.clientX; ty=e.clientY; }, {passive:true});
    document.addEventListener('mouseover', e => {
      if(e.target.closest('a, button, .btn, .icon-btn, input, label')) c.classList.add('cursor-big'); else c.classList.remove('cursor-big');
    });
    loop();
  }

  // Рандомный ник
  const nick = document.getElementById('nick');
  function randomNick(){
    const adj = ['Neo','Iron','Dark','Hyper','Aqua','Crimson','Pixel','Shadow','Ghost','Omega','Cyber','Glitch','Turbo'];
    const noun= ['Wolf','Ninja','Wizard','Rider','Dragon','Falcon','Hunter','Agent','Phoenix','Knight','Samurai','Rogue','Viper'];
    const n = Math.floor(Math.random()*90 + 10);
    return `${adj[Math.floor(Math.random()*adj.length)]}${noun[Math.floor(Math.random()*noun.length)]}${n}`;
  }
  nick.placeholder = `например, (${randomNick()})`;

  // Капча v2
  const capHuman = document.getElementById('capHuman');
  const capChallenge = document.getElementById('capChallenge');
  const capQ = document.getElementById('capQ');
  const capA = document.getElementById('capA');
  const capR = document.getElementById('capR');
  const hp = document.getElementById('hp_field');
  const submitBtn = document.getElementById('submitBtn');

  let expected = 0, unlockAt = 0, solved = false;

  function ri(min,max){ return Math.floor(Math.random()*(max-min+1))+min; }
  function genExpr(){
    const p = ri(1,3);
    let a=ri(2,9), b=ri(2,9), c=ri(1,8), d=ri(1,8);
    if(c<d){ const t=c; c=d; d=t; }
    let text='', val=0;
    if(p===1){ text=`${a} + ${b} × (${c} - ${d})`; val = a + b*(c-d); }
    else if(p===2){ text=`(${a} + ${b}) × ${c} - ${d}`; val = (a+b)*c - d; }
    else { text=`${a} × (${b} + ${c}) - ${d}`; val = a*(b+c) - d; }
    if(val<0) return genExpr();
    expected = val; capQ.textContent=text+' = ?'; capA.value=''; solved=false; unlockAt = Date.now()+2000;
  }
  capHuman.addEventListener('change', ()=>{ capChallenge.style.display = capHuman.checked ? 'grid' : 'none'; submitBtn.disabled = true; if(capHuman.checked) genExpr(); });
  capR.addEventListener('click', ()=>{ genExpr(); submitBtn.disabled=true; capA.focus(); });
  capA.addEventListener('input', ()=>{ const v = parseInt(capA.value,10); if(!Number.isFinite(v) || Date.now()<unlockAt){ submitBtn.disabled=true; solved=false; return; } solved = (v===expected); submitBtn.disabled=!solved; });

  // Отправка
  const form = document.getElementById('appForm');
  const res = document.getElementById('result');
  const resetBtn = document.getElementById('resetBtn');

  form.addEventListener('submit', e => {
    e.preventDefault();
    const title = document.getElementById('title').value.trim();
    const vt = document.getElementById('vt').value.trim();
    const link = document.getElementById('link').value.trim();
    const nickVal = nick.value.trim();

    if(hp.value){ alert('Ошибка проверки.'); return; }
    if(!capHuman.checked || !solved){ alert('Подтвердите капчу.'); return; }
    if(!nickVal || !title || !vt || !link){ alert('Заполните все поля.'); return; }
    if(!/^https?:\/\//i.test(vt) || vt.indexOf('virustotal.com')===-1){ alert('Укажите корректную ссылку на VirusTotal.'); return; }
    if(!/^https?:\/\//i.test(link)){ alert('Укажите корректную ссылку на скачивание.'); return; }

    const app = { id: 'app_' + Date.now() + '_' + Math.random().toString(36).slice(2,8),
                  nick: nickVal, title, virustotal: vt, link, status: 'pending', ts: Date.now() };
    try{
      const db = JSON.parse(localStorage.getItem('fluxeApplications')) || [];
      db.unshift(app);
      localStorage.setItem('fluxeApplications', JSON.stringify(db));
    }catch(_){ alert('Не удалось сохранить заявку.'); return; }

    res.textContent = 'Заявка отправлена!';
    res.style.display = 'block';
    form.reset();
    capChallenge.style.display = 'none';
    capHuman.checked = false;
    submitBtn.disabled = true;

    setTimeout(() => { res.style.opacity = '0'; }, 6500);
    setTimeout(() => { res.style.display = 'none'; res.textContent=''; res.style.opacity=''; }, 7000);
  });

  resetBtn.addEventListener('click', () => {
    capChallenge.style.display = 'none';
    capHuman.checked = false;
    submitBtn.disabled = true;
  });
});
</script>
</body>
</html>
