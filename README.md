<!doctype html>
<html lang="ru">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>fluxe — предложить игру/программу</title>
<meta name="theme-color" content="#07140e">
<style>
  :root{ --bg:#07140e; --green:#00ff88; --text:#eaf9f1; --muted:#b6e3c8; }
  body{
    margin:0; color:var(--text);
    font-family:Inter, system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
    background:
      radial-gradient(1200px 800px at 10% -10%, #0b2a1c 0%, var(--bg) 40%),
      radial-gradient(1000px 700px at 110% 10%, #0c3a25 0%, var(--bg) 30%),
      var(--bg);
  }

  #bg-snow{ position:fixed; inset:0; width:100vw; height:100vh; z-index:0; pointer-events:none; display:block; }

  .wrap{ position:relative; z-index:1; max-width:720px; margin:40px auto; padding:0 16px; }
  .box{ background: rgba(5,18,12,.8); border:1px solid rgba(0,255,136,.25); border-radius:16px; padding:18px; box-shadow:0 8px 24px rgba(0,0,0,.35); }

  /* Обновлённый дизайн логотипа fluxe */
  .header{ display:flex; align-items:center; justify-content:space-between; margin-bottom:16px; }
  .logo{
    font-weight:900; font-size:24px; letter-spacing:.6px; line-height:1;
    background: linear-gradient(90deg, #eafff7 0%, #6bffb5 30%, #00ff88 50%, #9fffd8 70%, #eafff7 100%);
    background-size:200% auto;
    -webkit-background-clip:text; background-clip:text; color:transparent;
    filter: drop-shadow(0 0 10px rgba(0,255,136,.35));
    animation: logoGlow 8s ease-in-out infinite;
    user-select:none;
  }
  @keyframes logoGlow{
    0%,100%{ background-position:0% 50%; filter: drop-shadow(0 0 8px rgba(0,255,136,.3)); }
    50%{ background-position:100% 50%; filter: drop-shadow(0 0 14px rgba(0,255,136,.6)); }
  }

  .icon-btn{ width:40px; height:40px; border-radius:50%; background: rgba(0,255,136,.12); border:1px solid rgba(0,255,136,.25); box-shadow: 0 0 12px rgba(0,255,136,.35), 0 0 24px rgba(0,255,136,.15); display:inline-flex; align-items:center; justify-content:center; color:var(--green); text-decoration:none; }

  .title{ margin:0 0 14px; font-size:26px; font-weight:900; color:#bfffe1; text-shadow:0 0 12px rgba(0,255,136,.25); }
  label{ display:block; margin:10px 0 6px; color:#cfeede; font-size:14px; }
  input[type="text"], input[type="url"]{
    width:100%; padding:12px 12px; border-radius:12px; border:1px solid rgba(0,255,136,.25);
    background:rgba(0,255,136,.06); color:#eaf9f1; outline:none;
  }
  .row{ display:grid; gap:10px; }

  /* Капча */
  .captcha{ display:grid; grid-template-columns: 1fr auto; align-items:end; gap:10px; margin-top:6px; }
  .captcha-box{ display:flex; align-items:center; gap:10px; padding:10px 12px; border-radius:12px; border:1px solid rgba(0,255,136,.25); background:rgba(0,255,136,.06); }
  .captcha-q{ font-weight:800; color:#bfffe1; letter-spacing:.3px; }
  .cap-field{ width:120px; }
  .cap-refresh{ height:40px; border-radius:10px; padding:0 12px; border:1px solid rgba(0,255,136,.25); background:transparent; color:#bfffe1; cursor:pointer; }

  .actions{ display:flex; gap:8px; margin-top:14px; }
  .btn{ display:inline-flex; align-items:center; justify-content:center; gap:8px; height:44px; padding:0 16px; border-radius:12px;
    background: linear-gradient(180deg, rgba(0,255,136,.95), rgba(0,230,120,.9)); color:#042d16; font-weight:800; border:none; cursor:pointer; }
  .btn.secondary{ background: transparent; color:#bfffe1; border:1px solid rgba(0,255,136,.25); }
  .ok{ padding:12px; border-radius:12px; background:rgba(0,255,136,.12); border:1px solid rgba(0,255,136,.3); color:#bfffe1; margin-top:12px; }

  .reveal{ opacity:0; transform: translateY(12px); transition: opacity .6s cubic-bezier(.2,.7,.2,1), transform .6s cubic-bezier(.2,.7,.2,1); }
  .reveal.in{ opacity:1; transform:none; }
</style>
</head>
<body>
<canvas id="bg-snow" aria-hidden="true"></canvas>

<div class="wrap">
  <div class="header reveal">
    <div class="logo">fluxe</div>
    <a class="icon-btn" href="index.html" aria-label="На главную">
      <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M15 18l-6-6 6-6"/></svg>
    </a>
  </div>

  <div class="box reveal">
    <h1 class="title">Подача заявки</h1>
    <form id="appForm" class="row" autocomplete="off" novalidate>
      <div>
        <label for="nick">Ваш ник</label>
        <input type="text" id="nick" required placeholder="например, pelemeuu">
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

      <!-- Капча -->
      <div>
        <label>Подтвердите, что вы не робот</label>
        <div class="captcha">
          <div class="captcha-box">
            <span class="captcha-q" id="capQ">2 + 3 = ?</span>
            <input class="cap-field" type="text" id="capA" inputmode="numeric" placeholder="Ответ" required>
          </div>
          <button type="button" class="cap-refresh" id="capR">Обновить</button>
        </div>
      </div>

      <div class="actions">
        <button class="btn" type="submit">Отправить</button>
        <button class="btn secondary" type="reset" id="resetBtn">Сброс</button>
      </div>

      <!-- Убрано сообщение про LocalStorage и ID -->
      <div id="result" class="ok" style="display:none;"></div>
    </form>
  </div>
</div>

<script>
document.addEventListener('DOMContentLoaded', () => {
  // Reveal
  const animated = document.querySelectorAll('.reveal');
  const io = new IntersectionObserver((entries, obs) => {
    entries.forEach(entry => { if(entry.isIntersecting){ entry.target.classList.add('in'); obs.unobserve(entry.target); } });
  }, { threshold: .1 });
  animated.forEach(el => io.observe(el));

  // Снег (HiDPI, ресайз)
  const prefersReduce = window.matchMedia('(prefers-reduced-motion: reduce)').matches;
  if(!prefersReduce){
    const c = document.getElementById('bg-snow');
    const ctx = c.getContext('2d');
    let flakes = [], raf=null;

    function setCanvasSize(){
      const dpr = Math.max(1, window.devicePixelRatio || 1);
      const w = Math.max(document.documentElement.clientWidth, window.innerWidth || 0);
      const h = Math.max(document.documentElement.clientHeight, window.innerHeight || 0);
      c.width = Math.floor(w*dpr); c.height = Math.floor(h*dpr);
      c.style.width = w+'px'; c.style.height = h+'px';
      ctx.setTransform(1,0,0,1,0,0); ctx.scale(dpr,dpr);
      adjustFlakes(w,h);
    }

    function makeFlake(w,h){ return { x:Math.random()*w, y:Math.random()*h, r:1+Math.random()*2.2, s:.4+Math.random()*1.2, d:Math.random()*1.5 }; }
    function adjustFlakes(w,h){
      const target = Math.floor(w*h*0.00012);
      if(flakes.length===0){ flakes = new Array(target).fill(0).map(()=>makeFlake(w,h)); return; }
      if(flakes.length<target){ for(let i=flakes.length;i<target;i++) flakes.push(makeFlake(w,h)); }
      else if(flakes.length>target){ flakes.length = target; }
    }

    function step(){
      const w = c.clientWidth, h = c.clientHeight;
      ctx.clearRect(0,0,w,h);
      ctx.fillStyle = 'rgba(255,255,255,.9)';
      for(const f of flakes){
        f.y += f.s; f.x += Math.sin((f.y+f.d)*0.01)*0.6;
        if(f.y > h+5){ f.y = -10; f.x = Math.random()*w; }
        ctx.beginPath(); ctx.arc(f.x, f.y, f.r, 0, Math.PI*2); ctx.fill();
      }
      raf = requestAnimationFrame(step);
    }

    function start(){ if(raf) return; setCanvasSize(); raf = requestAnimationFrame(step); }
    function stop(){ if(raf){ cancelAnimationFrame(raf); raf = null; } }
    window.addEventListener('resize', setCanvasSize);
    document.addEventListener('visibilitychange', () => { if(document.hidden) stop(); else start(); });
    start();
  }

  // Капча
  const capQ = document.getElementById('capQ');
  const capA = document.getElementById('capA');
  const capR = document.getElementById('capR');
  let capSum = 0;

  function genCap(){
    const a = Math.floor(2 + Math.random()*8);
    const b = Math.floor(2 + Math.random()*8);
    capSum = a + b;
    capQ.textContent = `${a} + ${b} = ?`;
    capA.value = '';
  }
  capR.addEventListener('click', genCap);
  genCap();

  // Локальная "отправка"
  const form = document.getElementById('appForm');
  const res = document.getElementById('result');
  const resetBtn = document.getElementById('resetBtn');

  form.addEventListener('submit', e => {
    e.preventDefault();
    const nick = document.getElementById('nick').value.trim();
    const title = document.getElementById('title').value.trim();
    const vt = document.getElementById('vt').value.trim();
    const link = document.getElementById('link').value.trim();

    if(!nick || !title || !vt || !link){ alert('Заполните все поля.'); return; }
    if(!/^https?:\/\//i.test(vt) || vt.indexOf('virustotal.com')===-1){ alert('Укажите корректную ссылку на VirusTotal.'); return; }
    if(!/^https?:\/\//i.test(link)){ alert('Укажите корректную ссылку на скачивание.'); return; }
    if(parseInt(capA.value,10) !== capSum){ alert('Неверная капча. Попробуйте ещё раз.'); genCap(); capA.focus(); return; }

    const app = { id: 'app_' + Date.now() + '_' + Math.random().toString(36).slice(2,8),
                  nick, title, virustotal: vt, link, status: 'pending', ts: Date.now() };

    try{
      const db = JSON.parse(localStorage.getItem('fluxeApplications')) || [];
      db.unshift(app);
      localStorage.setItem('fluxeApplications', JSON.stringify(db));
    }catch(e){
      alert('Не удалось сохранить заявку. Проверьте настройки браузера.');
      return;
    }

    res.style.display = 'block';
    res.textContent = 'Заявка отправлена!'; // без ID и без текста про LocalStorage
    form.reset();
    genCap();
  });

  resetBtn.addEventListener('click', genCap);
});
</script>
</body>
</html>
