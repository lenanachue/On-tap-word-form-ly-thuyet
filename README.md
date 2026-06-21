<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Word Forms – Retrieval Practice</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Outfit:wght@400;500;600;700;800;900&family=Lora:ital,wght@0,600;0,700;1,500&family=JetBrains+Mono:wght@500;700&display=swap');

/* ── DESIGN TOKENS ── */
:root {
  --o50:  #fff7ed;
  --o100: #ffedd5;
  --o200: #fed7aa;
  --o300: #fdba74;
  --o400: #fb923c;
  --o500: #f97316;
  --o600: #ea580c;
  --o700: #c2410c;
  --o800: #9a3412;
  --o900: #431407;

  --ink:      #1c0a00;
  --ink-mid:  #5c2a0e;
  --ink-soft: #92400e;
  --paper:    #fffaf4;
  --rule:     rgba(234,88,12,.14);
  --white:    #ffffff;

  --green:    #15803d;
  --green-bg: #dcfce7;
  --red:      #b91c1c;
  --red-bg:   #fee2e2;
  --blue:     #1d4ed8;
  --blue-bg:  #dbeafe;
  --amber:    #d97706;
  --amber-bg: #fef3c7;

  --radius-s: 8px;
  --radius-m: 14px;
  --radius-l: 22px;
  --shadow-s: 0 2px 8px rgba(194,65,12,.10);
  --shadow-m: 0 6px 24px rgba(194,65,12,.13);
  --shadow-l: 0 16px 48px rgba(154,52,18,.18);
}

*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}

body {
  font-family: 'Outfit', sans-serif;
  background: var(--o50);
  color: var(--ink);
  min-height: 100vh;
  /* subtle graph-paper lines */
  background-image:
    linear-gradient(var(--rule) 1px, transparent 1px),
    linear-gradient(90deg, var(--rule) 1px, transparent 1px);
  background-size: 32px 32px;
}

/* ══════════ HERO ══════════ */
.hero {
  position: relative;
  overflow: hidden;
  background: linear-gradient(135deg, var(--o800) 0%, var(--o600) 60%, var(--o400) 100%);
  padding: 64px 24px 100px;
  text-align: center;
}
/* pencil-line texture */
.hero::before {
  content:'';
  position:absolute;inset:0;
  background-image: repeating-linear-gradient(
    -55deg,
    transparent, transparent 20px,
    rgba(255,255,255,.04) 20px, rgba(255,255,255,.04) 21px
  );
}
/* wave bottom */
.hero::after {
  content:'';
  position:absolute;bottom:-2px;left:0;right:0;height:72px;
  background:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 1440 72'%3E%3Cpath fill='%23fff7ed' d='M0,36 C200,72 400,0 600,36 C800,72 1000,4 1200,36 C1320,54 1400,22 1440,32 L1440,72 L0,72Z'/%3E%3C/svg%3E") center/cover;
}

/* floating study icons */
.f-icon {
  position:absolute;
  font-size:2rem;opacity:.17;
  animation:floatUp 8s ease-in-out infinite;
  pointer-events:none;
}
.f-icon:nth-child(1){left:6%;top:20%;animation-delay:0s;font-size:2.6rem}
.f-icon:nth-child(2){left:91%;top:18%;animation-delay:2s;font-size:1.8rem}
.f-icon:nth-child(3){left:18%;top:70%;animation-delay:4s;font-size:1.5rem}
.f-icon:nth-child(4){left:82%;top:65%;animation-delay:1s;font-size:2.2rem}
.f-icon:nth-child(5){left:50%;top:12%;animation-delay:3s;font-size:1.7rem}
.f-icon:nth-child(6){left:38%;top:75%;animation-delay:5s;font-size:1.4rem}
.f-icon:nth-child(7){left:72%;top:28%;animation-delay:1.5s;font-size:1.9rem}

@keyframes floatUp{
  0%,100%{transform:translateY(0) rotate(-5deg)}
  50%{transform:translateY(-18px) rotate(5deg)}
}

.hero-inner{position:relative;z-index:2}
.hero-eyebrow {
  display:inline-flex;align-items:center;gap:8px;
  background:rgba(255,255,255,.15);border:1px solid rgba(255,255,255,.28);
  color:#fde8cf;font-size:.72rem;font-weight:700;letter-spacing:.18em;text-transform:uppercase;
  padding:5px 16px;border-radius:20px;margin-bottom:22px;
}
.hero h1 {
  font-family:'Lora',serif;
  font-size:clamp(2rem,5.5vw,3.4rem);
  color:#fff;font-weight:700;line-height:1.18;
  text-shadow:0 2px 20px rgba(0,0,0,.25);
  margin-bottom:12px;
}
.hero h1 em{font-style:italic;color:#fed7aa}
.hero-sub {
  color:#fde8cf;font-size:.97rem;max-width:520px;
  margin:0 auto 28px;line-height:1.75;font-weight:500;
}
.hero-chips{
  display:inline-flex;gap:10px;flex-wrap:wrap;justify-content:center;
}
.chip{
  background:rgba(255,255,255,.18);border:1px solid rgba(255,255,255,.3);
  color:#fff;font-size:.82rem;font-weight:700;
  padding:7px 16px;border-radius:20px;
  display:flex;align-items:center;gap:6px;
}

/* ══════════ STICKY NAV ══════════ */
.snav{
  position:sticky;top:0;z-index:99;
  background:rgba(255,247,237,.95);
  backdrop-filter:blur(12px);
  border-bottom:2px solid var(--o200);
  box-shadow:var(--shadow-s);
}
.snav-inner{
  max-width:960px;margin:0 auto;
  display:flex;align-items:center;justify-content:space-between;
  padding:10px 20px;gap:12px;
}
.snav-pills{display:flex;gap:6px;overflow-x:auto;scrollbar-width:none}
.snav-pills::-webkit-scrollbar{display:none}
.snav-pill{
  flex-shrink:0;padding:6px 14px;border-radius:16px;
  font-size:.78rem;font-weight:700;
  border:2px solid var(--o200);
  background:var(--o50);color:var(--o700);
  cursor:pointer;text-decoration:none;transition:all .18s;
}
.snav-pill:hover,.snav-pill.active{background:var(--o600);color:#fff;border-color:var(--o600)}
.score-pill{
  flex-shrink:0;
  background:var(--amber-bg);border:1.5px solid #fcd34d;
  color:var(--amber);border-radius:12px;
  padding:5px 14px;font-size:.78rem;font-weight:800;
  white-space:nowrap;
}

/* ══════════ LAYOUT ══════════ */
.main{max-width:960px;margin:0 auto;padding:36px 20px 80px}

/* section header */
.sec-head{
  display:flex;align-items:center;gap:14px;
  margin:52px 0 24px;
  padding-bottom:12px;
  border-bottom:3px solid var(--o300);
}
.sec-icon{
  width:48px;height:48px;border-radius:14px;flex-shrink:0;
  background:linear-gradient(135deg,var(--o500),var(--o700));
  display:flex;align-items:center;justify-content:center;
  font-size:1.4rem;box-shadow:0 3px 12px rgba(234,88,12,.3);
}
.sec-meta h2{font-size:1.22rem;font-weight:800;color:var(--o800)}
.sec-meta p{font-size:.82rem;color:var(--ink-soft);margin-top:3px;font-weight:500}

/* science badge */
.sci-badge{
  display:inline-flex;align-items:center;gap:7px;
  background:var(--blue-bg);border:1.5px solid #93c5fd;
  color:var(--blue);font-size:.76rem;font-weight:700;
  padding:5px 12px;border-radius:10px;margin-bottom:20px;
}

/* ══════════ ROUND CARD ══════════ */
.round-card{
  background:var(--white);
  border:1.5px solid var(--o200);
  border-radius:var(--radius-l);
  overflow:hidden;
  box-shadow:var(--shadow-m);
  margin-bottom:24px;
}
.round-card-head{
  background:linear-gradient(90deg,var(--o100),var(--o50));
  padding:16px 24px;
  border-bottom:1.5px solid var(--o200);
  display:flex;align-items:center;gap:10px;
}
.round-label{
  background:var(--o600);color:#fff;
  font-size:.7rem;font-weight:800;letter-spacing:.12em;text-transform:uppercase;
  padding:3px 12px;border-radius:10px;
}
.round-card-head h3{font-size:.97rem;font-weight:800;color:var(--o800)}
.round-body{padding:26px 24px}

/* ══════════ QUESTION TYPES ══════════ */

/* — MCQ — */
.q-wrap{margin-bottom:28px}
.q-wrap:last-child{margin-bottom:0}
.q-stem{
  display:flex;gap:10px;align-items:flex-start;margin-bottom:12px;
}
.q-badge{
  min-width:28px;height:28px;border-radius:50%;
  background:var(--o200);color:var(--o700);
  font-size:.78rem;font-weight:900;
  display:flex;align-items:center;justify-content:center;flex-shrink:0;margin-top:2px;
}
.q-text{font-size:.93rem;font-weight:600;line-height:1.7;color:var(--ink)}
.q-text .blank{color:var(--o600);font-weight:900;font-family:'JetBrains Mono',monospace;font-size:.9rem}
.q-text .keyword{color:var(--o700);font-weight:800}

.opts{display:grid;grid-template-columns:1fr 1fr;gap:8px;margin-left:38px}
@media(max-width:540px){.opts{grid-template-columns:1fr}}

.opt{
  display:flex;align-items:center;gap:9px;
  background:var(--o50);border:2px solid var(--o200);
  border-radius:10px;padding:9px 13px;
  cursor:pointer;font-family:'Outfit',sans-serif;
  font-size:.87rem;font-weight:600;color:var(--ink);
  transition:all .16s;text-align:left;line-height:1.4;
}
.opt-key{
  min-width:24px;height:24px;border-radius:50%;
  background:var(--o200);color:var(--o700);
  font-size:.73rem;font-weight:900;
  display:flex;align-items:center;justify-content:center;flex-shrink:0;
  transition:all .16s;
}
.opt:hover:not(:disabled){border-color:var(--o400);background:var(--o100)}
.opt.picked{border-color:var(--o500);background:var(--o100)}
.opt.picked .opt-key{background:var(--o500);color:#fff}
.opt.correct{border-color:var(--green);background:var(--green-bg);color:#14532d}
.opt.correct .opt-key{background:var(--green);color:#fff}
.opt.wrong{border-color:var(--red);background:var(--red-bg);color:var(--red)}
.opt.wrong .opt-key{background:var(--red);color:#fff}
.opt:disabled{cursor:default}

.q-fb{
  margin-left:38px;margin-top:7px;
  font-size:.81rem;font-weight:700;
  padding:6px 12px;border-radius:9px;display:none;line-height:1.5;
}
.q-fb.ok {display:block;background:var(--green-bg);color:var(--green)}
.q-fb.err{display:block;background:var(--red-bg);color:var(--red)}

/* — FILL — */
.fill-wrap{margin-bottom:24px;display:flex;gap:10px;align-items:flex-start}
.fill-wrap:last-child{margin-bottom:0}
.fill-body{flex:1}
.fill-row{
  display:flex;flex-wrap:wrap;align-items:center;gap:5px;
  font-size:.93rem;font-weight:600;color:var(--ink);line-height:2;
}
.fill-inp{
  border:none;
  border-bottom:2.5px solid var(--o300);
  background:transparent;
  font-family:'JetBrains Mono',monospace;
  font-size:.88rem;font-weight:700;color:var(--o700);
  min-width:110px;max-width:180px;padding:2px 4px;
  outline:none;text-align:center;transition:border-color .2s;
}
.fill-inp:focus{border-color:var(--o600)}
.fill-inp.correct{border-color:var(--green);color:var(--green);background:var(--green-bg);border-bottom-width:2px;border-radius:5px;padding:2px 8px}
.fill-inp.wrong  {border-color:var(--red);color:var(--red);background:var(--red-bg);border-bottom-width:2px;border-radius:5px;padding:2px 8px}
.fill-tag{font-size:.74rem;font-weight:800;background:var(--o100);color:var(--o700);padding:2px 8px;border-radius:8px}
.fill-fb{font-size:.8rem;font-weight:700;margin-top:4px;padding:4px 10px;border-radius:8px;display:none}
.fill-fb.ok {display:block;background:var(--green-bg);color:var(--green)}
.fill-fb.err{display:block;background:var(--red-bg);color:var(--red)}

/* — MATCH — */
.match-grid{display:grid;grid-template-columns:1fr 1fr;gap:10px}
@media(max-width:560px){.match-grid{grid-template-columns:1fr}}
.match-col-head{font-size:.74rem;font-weight:800;letter-spacing:.1em;text-transform:uppercase;color:var(--ink-soft);margin-bottom:8px}
.match-item{
  padding:10px 14px;border-radius:10px;font-size:.87rem;font-weight:700;
  border:2px solid var(--o200);background:var(--o50);cursor:pointer;
  transition:all .18s;user-select:none;
}
.match-item.selectable:hover{border-color:var(--o400);background:var(--o100)}
.match-item.selected{border-color:var(--o500);background:var(--o100);color:var(--o700)}
.match-item.matched-ok{border-color:var(--green);background:var(--green-bg);color:var(--green);cursor:default}
.match-item.matched-err{border-color:var(--red);background:var(--red-bg);color:var(--red)}
.match-item.dim{opacity:.4;cursor:default}

.match-btn{
  margin-top:14px;
  background:var(--o100);border:2px solid var(--o300);color:var(--o700);
  border-radius:12px;padding:9px 22px;
  font-family:'Outfit',sans-serif;font-size:.85rem;font-weight:800;
  cursor:pointer;transition:all .18s;
}
.match-btn:hover:not(:disabled){background:var(--o200)}
.match-btn:disabled{opacity:.4;cursor:not-allowed}

/* — SORT (drag-free version: click-to-order) — */
.sort-prompt{font-size:.9rem;font-weight:700;color:var(--ink-mid);margin-bottom:12px;line-height:1.6}
.sort-pool{display:flex;flex-wrap:wrap;gap:8px;margin-bottom:14px}
.sort-tile{
  padding:7px 16px;border-radius:10px;
  background:var(--o100);border:2px solid var(--o300);
  color:var(--o800);font-size:.85rem;font-weight:800;
  cursor:pointer;transition:all .16s;user-select:none;
  font-family:'JetBrains Mono',monospace;
}
.sort-tile:hover:not(.used):not(:disabled){background:var(--o200);border-color:var(--o500)}
.sort-tile.used{opacity:.35;cursor:default;text-decoration:line-through}
.sort-slots{display:flex;flex-wrap:wrap;gap:8px;margin-bottom:12px}
.sort-slot{
  min-width:80px;padding:7px 12px;border-radius:10px;
  border:2px dashed var(--o300);background:transparent;
  font-size:.85rem;font-weight:800;font-family:'JetBrains Mono',monospace;
  color:var(--o600);text-align:center;cursor:pointer;transition:all .16s;
}
.sort-slot:hover:not(.filled){border-color:var(--o500);background:var(--o100)}
.sort-slot.filled{border-style:solid;border-color:var(--o400);background:var(--o100);color:var(--ink)}
.sort-slot.correct{border-color:var(--green);background:var(--green-bg);color:var(--green)}
.sort-slot.wrong{border-color:var(--red);background:var(--red-bg);color:var(--red)}

/* — EXCEPTION TOGGLE — */
.exception-card{
  background:var(--amber-bg);border:1.5px solid #fde68a;
  border-radius:14px;padding:18px 20px;margin-bottom:14px;
}
.exc-q{font-size:.93rem;font-weight:700;color:var(--ink);margin-bottom:10px}
.exc-choices{display:flex;gap:8px;flex-wrap:wrap}
.exc-btn{
  padding:7px 18px;border-radius:10px;
  border:2px solid #fcd34d;background:#fff;
  font-family:'Outfit',sans-serif;font-size:.85rem;font-weight:700;color:var(--ink);
  cursor:pointer;transition:all .16s;
}
.exc-btn:hover:not(:disabled){border-color:var(--o500);background:var(--o100)}
.exc-btn.correct{border-color:var(--green);background:var(--green-bg);color:var(--green)}
.exc-btn.wrong  {border-color:var(--red);background:var(--red-bg);color:var(--red)}
.exc-btn:disabled{cursor:default}
.exc-fb{margin-top:8px;font-size:.8rem;font-weight:700;padding:5px 10px;border-radius:8px;display:none}
.exc-fb.ok {display:block;background:var(--green-bg);color:var(--green)}
.exc-fb.err{display:block;background:var(--red-bg);color:var(--red)}

/* ══════════ SUBMIT BAR ══════════ */
.submit-bar{
  background:var(--white);border:1.5px solid var(--o200);
  border-radius:var(--radius-l);padding:24px 28px;margin-top:36px;
  box-shadow:var(--shadow-l);
  display:flex;flex-wrap:wrap;gap:14px;align-items:center;
}
.submit-btn{
  background:linear-gradient(135deg,var(--o600),var(--o800));
  color:#fff;border:none;border-radius:24px;
  padding:13px 32px;font-size:1rem;font-weight:800;
  cursor:pointer;font-family:'Outfit',sans-serif;
  display:flex;align-items:center;gap:8px;
  box-shadow:0 4px 18px rgba(194,65,12,.32);transition:all .2s;
}
.submit-btn:hover:not(:disabled){transform:translateY(-2px);box-shadow:0 6px 24px rgba(194,65,12,.42)}
.submit-btn:disabled{opacity:.45;cursor:not-allowed;transform:none}
.submit-note{font-size:.82rem;color:var(--ink-soft);line-height:1.55;flex:1;min-width:200px;font-weight:500}

/* ══════════ PROGRESS ══════════ */
.prog-wrap{margin-bottom:8px}
.prog-row{display:flex;justify-content:space-between;font-size:.8rem;font-weight:700;color:var(--o700);margin-bottom:5px}
.prog-track{background:var(--o100);border-radius:20px;height:8px;overflow:hidden}
.prog-fill{height:100%;background:linear-gradient(90deg,var(--o400),var(--o600));border-radius:20px;transition:width .4s ease}

/* ══════════ SCORE MODAL ══════════ */
.modal-overlay{
  display:none;position:fixed;inset:0;z-index:500;
  background:rgba(154,52,18,.45);backdrop-filter:blur(10px);
  align-items:center;justify-content:center;padding:20px;
}
.modal-overlay.open{display:flex}
.modal{
  background:var(--white);border-radius:28px;padding:44px 38px;
  max-width:500px;width:100%;text-align:center;
  box-shadow:var(--shadow-l);
  animation:popIn .38s cubic-bezier(.34,1.56,.64,1);
}
@keyframes popIn{from{transform:scale(.75);opacity:0}to{transform:scale(1);opacity:1}}
.modal-emoji{font-size:4.2rem;margin-bottom:16px}
.modal-score{font-family:'Lora',serif;font-size:3.4rem;font-weight:700;color:var(--o700);margin-bottom:4px}
.modal-of{font-size:.88rem;color:var(--ink-soft);margin-bottom:22px;font-weight:500}
.modal-bar-outer{background:var(--o100);border-radius:20px;height:12px;margin-bottom:22px;overflow:hidden}
.modal-bar-fill{height:100%;background:linear-gradient(90deg,var(--o400),var(--o700));border-radius:20px;transition:width 1.1s ease}
.modal-msg{font-size:1rem;font-weight:700;color:var(--o800);line-height:1.65;margin-bottom:26px}
.modal-close{
  background:linear-gradient(135deg,var(--o500),var(--o700));
  color:#fff;border:none;border-radius:18px;
  padding:12px 30px;font-size:.95rem;font-weight:800;
  cursor:pointer;font-family:'Outfit',sans-serif;
  box-shadow:0 4px 14px rgba(194,65,12,.3);
}

/* ══════════ TOAST ══════════ */
.toast{
  position:fixed;bottom:22px;left:50%;
  transform:translateX(-50%) translateY(80px);
  background:var(--o900);color:#fde8cf;
  border-radius:14px;padding:13px 22px;
  font-size:.86rem;font-weight:700;z-index:999;
  transition:transform .32s cubic-bezier(.34,1.56,.64,1);
  box-shadow:0 8px 28px rgba(0,0,0,.28);display:flex;align-items:center;gap:8px;
}
.toast.show{transform:translateX(-50%) translateY(0)}

/* ══════════ THEORY PEEK ══════════ */
.theory-peek{
  background:var(--o50);border:1.5px solid var(--o200);
  border-left:4px solid var(--o500);
  border-radius:0 12px 12px 0;
  padding:14px 18px;margin-bottom:22px;
  font-size:.84rem;color:var(--ink-mid);line-height:1.75;font-weight:500;
}
.theory-peek strong{color:var(--o700)}

/* pos tags */
.tag{display:inline-block;font-size:.7rem;font-weight:800;letter-spacing:.08em;text-transform:uppercase;padding:2px 7px;border-radius:7px;margin-right:3px}
.tag-n  {background:var(--blue-bg);color:var(--blue)}
.tag-v  {background:var(--green-bg);color:var(--green)}
.tag-a  {background:#fef3c7;color:#92400e}
.tag-adv{background:#fce7f3;color:#9d174d}

.divider{border:none;border-top:2px dashed var(--o200);margin:36px 0}

/* ══════════ RESPONSIVE ══════════ */
@media(max-width:640px){
  .round-body{padding:16px}
  .opts{grid-template-columns:1fr}
  .match-grid{grid-template-columns:1fr}
}
</style>
</head>
<body>

<div class="toast" id="toast">⚠️ <span id="toast-msg"></span></div>
<div class="modal-overlay" id="modal">
  <div class="modal">
    <div class="modal-emoji" id="m-emoji">🎉</div>
    <div class="modal-score" id="m-score">0</div>
    <div class="modal-of" id="m-of">/ 0 điểm</div>
    <div class="modal-bar-outer"><div class="modal-bar-fill" id="m-bar" style="width:0%"></div></div>
    <div class="modal-msg" id="m-msg"></div>
    <button class="modal-close" onclick="document.getElementById('modal').classList.remove('open')">Xem chi tiết kết quả →</button>
  </div>
</div>

<!-- ══ HERO ══ -->
<header class="hero">
  <span class="f-icon">📚</span>
  <span class="f-icon">✏️</span>
  <span class="f-icon">📝</span>
  <span class="f-icon">🖊️</span>
  <span class="f-icon">📖</span>
  <span class="f-icon">📐</span>
  <span class="f-icon">🗒️</span>
  <div class="hero-inner">
    <div class="hero-eyebrow">🧠 Retrieval Practice · Word Forms</div>
    <h1>Gợi Nhớ Kiến Thức<br><em>Cấu Tạo Từ – Word Forms</em></h1>
    <p class="hero-sub">Không phải đọc lại — mà là <strong>tự kéo kiến thức ra từ trí nhớ</strong>. Phương pháp được chứng minh giúp nhớ lâu gấp 2–3 lần so với đọc lại lý thuyết.</p>
    <div class="hero-chips">
      <div class="chip">🧠 Retrieval Practice</div>
      <div class="chip">📊 5 dạng câu hỏi</div>
      <div class="chip">⏱️ ~15 phút</div>
    </div>
  </div>
</header>

<!-- ══ NAV ══ -->
<nav class="snav">
  <div class="snav-inner">
    <div class="snav-pills">
      <a class="snav-pill" href="#sec1">🔵 Suffix → N</a>
      <a class="snav-pill" href="#sec2">🟢 Suffix → V</a>
      <a class="snav-pill" href="#sec3">🟡 Suffix → Adj</a>
      <a class="snav-pill" href="#sec4">🩷 Suffix → Adv</a>
      <a class="snav-pill" href="#sec5">🧭 Nhận vị trí</a>
    </div>
    <div class="score-pill">🏆 <span id="live-score">0</span> điểm</div>
  </div>
</nav>

<!-- ══ MAIN ══ -->
<main class="main">
  <div class="prog-wrap">
    <div class="prog-row"><span>Tiến độ</span><span id="prog-txt">0 / 35</span></div>
    <div class="prog-track"><div class="prog-fill" id="prog-fill" style="width:0%"></div></div>
  </div>

  <!-- ═══════════════════════════════
       SECTION 1 – NOUN SUFFIXES
  ════════════════════════════════ -->
  <section id="sec1">
    <div class="sec-head">
      <div class="sec-icon">🔵</div>
      <div class="sec-meta">
        <h2>Phần 1 – Hậu Tố Tạo Danh Từ</h2>
        <p>Gợi nhớ: từ gốc + hậu tố nào → Noun?</p>
      </div>
    </div>

    <div class="sci-badge">🔬 Cued recall (Brown et al., 2014) · nhớ qua gợi ý hậu tố</div>

    <div class="theory-peek">
      <strong>Nhớ lại:</strong> Verb + <strong>-ment / -ance / -ion / -al / -er / -age</strong> → N &nbsp;·&nbsp;
      Adj + <strong>-ness / -ity / -ty / -cy</strong> → N &nbsp;·&nbsp;
      N + <strong>-hood / -ship</strong> → N
    </div>

    <!-- 1A: MCQ – suffix identification -->
    <div class="round-card">
      <div class="round-card-head">
        <span class="round-label">A · MCQ</span>
        <h3>Chọn hậu tố đúng để tạo danh từ</h3>
      </div>
      <div class="round-body">

        <div class="q-wrap" id="q1">
          <div class="q-stem"><div class="q-badge">1</div>
            <div class="q-text">Từ động từ <span class="keyword">develop</span>, ta thêm hậu tố nào để tạo danh từ <em>"sự phát triển"</em>?</div></div>
          <div class="opts">
            <button class="opt" data-q="1" data-v="A" onclick="pick(this)"><span class="opt-key">A</span>-ness</button>
            <button class="opt" data-q="1" data-v="B" onclick="pick(this)"><span class="opt-key">B</span>-ment</button>
            <button class="opt" data-q="1" data-v="C" onclick="pick(this)"><span class="opt-key">C</span>-ive</button>
            <button class="opt" data-q="1" data-v="D" onclick="pick(this)"><span class="opt-key">D</span>-ful</button>
          </div>
          <div class="q-fb" id="fb1"></div>
        </div>

        <div class="q-wrap" id="q2">
          <div class="q-stem"><div class="q-badge">2</div>
            <div class="q-text">Từ <span class="keyword">attend</span> (v), hậu tố nào cho ta <em>"sự tham dự"</em>?</div></div>
          <div class="opts">
            <button class="opt" data-q="2" data-v="A" onclick="pick(this)"><span class="opt-key">A</span>-al</button>
            <button class="opt" data-q="2" data-v="B" onclick="pick(this)"><span class="opt-key">B</span>-ment</button>
            <button class="opt" data-q="2" data-v="C" onclick="pick(this)"><span class="opt-key">C</span>-ance</button>
            <button class="opt" data-q="2" data-v="D" onclick="pick(this)"><span class="opt-key">D</span>-age</button>
          </div>
          <div class="q-fb" id="fb2"></div>
        </div>

        <div class="q-wrap" id="q3">
          <div class="q-stem"><div class="q-badge">3</div>
            <div class="q-text">Từ nào dưới đây là danh từ chỉ <em>người thực hiện hành động</em>?</div></div>
          <div class="opts">
            <button class="opt" data-q="3" data-v="A" onclick="pick(this)"><span class="opt-key">A</span>arrival</button>
            <button class="opt" data-q="3" data-v="B" onclick="pick(this)"><span class="opt-key">B</span>invention</button>
            <button class="opt" data-q="3" data-v="C" onclick="pick(this)"><span class="opt-key">C</span>employer</button>
            <button class="opt" data-q="3" data-v="D" onclick="pick(this)"><span class="opt-key">D</span>freedom</button>
          </div>
          <div class="q-fb" id="fb3"></div>
        </div>

        <div class="q-wrap" id="q4">
          <div class="q-stem"><div class="q-badge">4</div>
            <div class="q-text">Hậu tố nào biến tính từ <span class="keyword">rich</span> thành danh từ trừu tượng?</div></div>
          <div class="opts">
            <button class="opt" data-q="4" data-v="A" onclick="pick(this)"><span class="opt-key">A</span>-ity</button>
            <button class="opt" data-q="4" data-v="B" onclick="pick(this)"><span class="opt-key">B</span>-ness</button>
            <button class="opt" data-q="4" data-v="C" onclick="pick(this)"><span class="opt-key">C</span>-ance</button>
            <button class="opt" data-q="4" data-v="D" onclick="pick(this)"><span class="opt-key">D</span>-hood</button>
          </div>
          <div class="q-fb" id="fb4"></div>
        </div>

        <div class="q-wrap" id="q5">
          <div class="q-stem"><div class="q-badge">5</div>
            <div class="q-text">Ghép đúng: <span class="keyword">friend</span> + _____ = danh từ chỉ <em>mối quan hệ</em></div></div>
          <div class="opts">
            <button class="opt" data-q="5" data-v="A" onclick="pick(this)"><span class="opt-key">A</span>-hood</button>
            <button class="opt" data-q="5" data-v="B" onclick="pick(this)"><span class="opt-key">B</span>-dom</button>
            <button class="opt" data-q="5" data-v="C" onclick="pick(this)"><span class="opt-key">C</span>-ship</button>
            <button class="opt" data-q="5" data-v="D" onclick="pick(this)"><span class="opt-key">D</span>-ism</button>
          </div>
          <div class="q-fb" id="fb5"></div>
        </div>

      </div>
    </div>

    <!-- 1B: Fill – noun transformation -->
    <div class="round-card">
      <div class="round-card-head">
        <span class="round-label">B · Điền từ</span>
        <h3>Điền dạng danh từ đúng</h3>
      </div>
      <div class="round-body">

        <div class="fill-wrap" id="f1">
          <div class="q-badge" style="margin-top:4px">6</div>
          <div class="fill-body">
            <div class="fill-row">
              invent → <input class="fill-inp" id="fi1" placeholder="danh từ" autocomplete="off">
              <span class="fill-tag">V → N</span>
            </div>
            <div class="fill-fb" id="fib1"></div>
          </div>
        </div>

        <div class="fill-wrap" id="f2">
          <div class="q-badge" style="margin-top:4px">7</div>
          <div class="fill-body">
            <div class="fill-row">
              able → <input class="fill-inp" id="fi2" placeholder="danh từ" autocomplete="off">
              <span class="fill-tag">Adj → N</span>
            </div>
            <div class="fill-fb" id="fib2"></div>
          </div>
        </div>

        <div class="fill-wrap" id="f3">
          <div class="q-badge" style="margin-top:4px">8</div>
          <div class="fill-body">
            <div class="fill-row">
              warm → <input class="fill-inp" id="fi3" placeholder="danh từ" autocomplete="off">
              <span class="fill-tag">Adj → N</span>
            </div>
            <div class="fill-fb" id="fib3"></div>
          </div>
        </div>

      </div>
    </div>
  </section>

  <hr class="divider">

  <!-- ═══════════════════════════════
       SECTION 2 – VERB SUFFIXES
  ════════════════════════════════ -->
  <section id="sec2">
    <div class="sec-head">
      <div class="sec-icon">🟢</div>
      <div class="sec-meta">
        <h2>Phần 2 – Hậu Tố Tạo Động Từ</h2>
        <p>Gợi nhớ: -en, en-, -ize/-ise, -fy</p>
      </div>
    </div>

    <div class="sci-badge">🔬 Elaborative interrogation (Pressley et al., 1987) · tại sao từ này có nghĩa đó?</div>

    <div class="theory-peek">
      <strong>Nhớ lại:</strong> Adj + <strong>-en</strong> → V (widen, shorten) &nbsp;·&nbsp;
      <strong>en-</strong> + Adj/N → V (enrich, enlarge) &nbsp;·&nbsp;
      N/Adj + <strong>-ize</strong> → V (socialize) &nbsp;·&nbsp;
      N + <strong>-fy</strong> → V (beautify)
    </div>

    <!-- 2A: MCQ -->
    <div class="round-card">
      <div class="round-card-head">
        <span class="round-label">C · MCQ</span>
        <h3>Chọn dạng động từ đúng</h3>
      </div>
      <div class="round-body">

        <div class="q-wrap" id="q9">
          <div class="q-stem"><div class="q-badge">9</div>
            <div class="q-text">Muốn nói <em>"làm đẹp"</em>, ta biến đổi <span class="keyword">beauty</span> bằng hậu tố nào?</div></div>
          <div class="opts">
            <button class="opt" data-q="9" data-v="A" onclick="pick(this)"><span class="opt-key">A</span>beautiness</button>
            <button class="opt" data-q="9" data-v="B" onclick="pick(this)"><span class="opt-key">B</span>beautize</button>
            <button class="opt" data-q="9" data-v="C" onclick="pick(this)"><span class="opt-key">C</span>beautify</button>
            <button class="opt" data-q="9" data-v="D" onclick="pick(this)"><span class="opt-key">D</span>beauten</button>
          </div>
          <div class="q-fb" id="fb9"></div>
        </div>

        <div class="q-wrap" id="q10">
          <div class="q-stem"><div class="q-badge">10</div>
            <div class="q-text">Câu nào dùng đúng tiền tố <span class="keyword">en-</span>?</div></div>
          <div class="opts">
            <button class="opt" data-q="10" data-v="A" onclick="pick(this)"><span class="opt-key">A</span>enness</button>
            <button class="opt" data-q="10" data-v="B" onclick="pick(this)"><span class="opt-key">B</span>enrich</button>
            <button class="opt" data-q="10" data-v="C" onclick="pick(this)"><span class="opt-key">C</span>enrichment</button>
            <button class="opt" data-q="10" data-v="D" onclick="pick(this)"><span class="opt-key">D</span>richly</button>
          </div>
          <div class="q-fb" id="fb10"></div>
        </div>

        <div class="q-wrap" id="q11">
          <div class="q-stem"><div class="q-badge">11</div>
            <div class="q-text">We will ______ our English vocabulary if we read books every day.</div></div>
          <div class="opts">
            <button class="opt" data-q="11" data-v="A" onclick="pick(this)"><span class="opt-key">A</span>rich</button>
            <button class="opt" data-q="11" data-v="B" onclick="pick(this)"><span class="opt-key">B</span>richness</button>
            <button class="opt" data-q="11" data-v="C" onclick="pick(this)"><span class="opt-key">C</span>enrich</button>
            <button class="opt" data-q="11" data-v="D" onclick="pick(this)"><span class="opt-key">D</span>richly</button>
          </div>
          <div class="q-fb" id="fb11"></div>
        </div>

        <div class="q-wrap" id="q12">
          <div class="q-stem"><div class="q-badge">12</div>
            <div class="q-text">Để tạo động từ từ <span class="keyword">wide</span> (adj), ta dùng hậu tố nào?</div></div>
          <div class="opts">
            <button class="opt" data-q="12" data-v="A" onclick="pick(this)"><span class="opt-key">A</span>-ize</button>
            <button class="opt" data-q="12" data-v="B" onclick="pick(this)"><span class="opt-key">B</span>-fy</button>
            <button class="opt" data-q="12" data-v="C" onclick="pick(this)"><span class="opt-key">C</span>-en</button>
            <button class="opt" data-q="12" data-v="D" onclick="pick(this)"><span class="opt-key">D</span>-ment</button>
          </div>
          <div class="q-fb" id="fb12"></div>
        </div>

      </div>
    </div>
  </section>

  <hr class="divider">

  <!-- ═══════════════════════════════
       SECTION 3 – ADJ SUFFIXES + -ing/-ed
  ════════════════════════════════ -->
  <section id="sec3">
    <div class="sec-head">
      <div class="sec-icon">🟡</div>
      <div class="sec-meta">
        <h2>Phần 3 – Hậu Tố Tạo Tính Từ &amp; Ngoại Lệ</h2>
        <p>-ing vs -ed · -ful vs -less · -ous · -able/-ible</p>
      </div>
    </div>

    <div class="sci-badge">🔬 Interleaved practice (Rohrer, 2012) · xáo trộn các loại hậu tố</div>

    <div class="theory-peek">
      <strong>Lưu ý then chốt:</strong> &nbsp;
      <span class="tag tag-a">-ing</span> = bản chất sự vật GÂY RA cảm xúc &nbsp;·&nbsp;
      <span class="tag tag-a">-ed</span> = chủ thể người CẢM THẤY cảm xúc
    </div>

    <!-- 3A: -ing/-ed critical distinction -->
    <div class="round-card">
      <div class="round-card-head">
        <span class="round-label">D · -ing vs -ed</span>
        <h3>Phân biệt: tính từ -ing và -ed</h3>
      </div>
      <div class="round-body">

        <div class="q-wrap" id="q13">
          <div class="q-stem"><div class="q-badge">13</div>
            <div class="q-text"><em>"The movie was very ____. I fell asleep."</em> — tính chất của <strong>bộ phim</strong></div></div>
          <div class="opts">
            <button class="opt" data-q="13" data-v="A" onclick="pick(this)"><span class="opt-key">A</span>bored</button>
            <button class="opt" data-q="13" data-v="B" onclick="pick(this)"><span class="opt-key">B</span>boring</button>
            <button class="opt" data-q="13" data-v="C" onclick="pick(this)"><span class="opt-key">C</span>boreness</button>
            <button class="opt" data-q="13" data-v="D" onclick="pick(this)"><span class="opt-key">D</span>boredom</button>
          </div>
          <div class="q-fb" id="fb13"></div>
        </div>

        <div class="q-wrap" id="q14">
          <div class="q-stem"><div class="q-badge">14</div>
            <div class="q-text"><em>"I am very ____ in this book."</em> — <strong>tôi</strong> cảm thấy</div></div>
          <div class="opts">
            <button class="opt" data-q="14" data-v="A" onclick="pick(this)"><span class="opt-key">A</span>interesting</button>
            <button class="opt" data-q="14" data-v="B" onclick="pick(this)"><span class="opt-key">B</span>interested</button>
            <button class="opt" data-q="14" data-v="C" onclick="pick(this)"><span class="opt-key">C</span>interest</button>
            <button class="opt" data-q="14" data-v="D" onclick="pick(this)"><span class="opt-key">D</span>interestful</button>
          </div>
          <div class="q-fb" id="fb14"></div>
        </div>

        <div class="q-wrap" id="q15">
          <div class="q-stem"><div class="q-badge">15</div>
            <div class="q-text"><em>"The news was very ____."</em> — tin tức GÂY RA sự ngạc nhiên</div></div>
          <div class="opts">
            <button class="opt" data-q="15" data-v="A" onclick="pick(this)"><span class="opt-key">A</span>surprised</button>
            <button class="opt" data-q="15" data-v="B" onclick="pick(this)"><span class="opt-key">B</span>surprising</button>
            <button class="opt" data-q="15" data-v="C" onclick="pick(this)"><span class="opt-key">C</span>surprise</button>
            <button class="opt" data-q="15" data-v="D" onclick="pick(this)"><span class="opt-key">D</span>surprisement</button>
          </div>
          <div class="q-fb" id="fb15"></div>
        </div>

      </div>
    </div>

    <!-- 3B: other adj suffixes MCQ -->
    <div class="round-card">
      <div class="round-card-head">
        <span class="round-label">E · MCQ</span>
        <h3>Hậu tố tính từ: -ful / -less / -ous / -able</h3>
      </div>
      <div class="round-body">

        <div class="q-wrap" id="q16">
          <div class="q-stem"><div class="q-badge">16</div>
            <div class="q-text"><span class="keyword">danger</span> + _____ = tính từ <em>"nguy hiểm"</em></div></div>
          <div class="opts">
            <button class="opt" data-q="16" data-v="A" onclick="pick(this)"><span class="opt-key">A</span>dangerful</button>
            <button class="opt" data-q="16" data-v="B" onclick="pick(this)"><span class="opt-key">B</span>dangerly</button>
            <button class="opt" data-q="16" data-v="C" onclick="pick(this)"><span class="opt-key">C</span>dangerous</button>
            <button class="opt" data-q="16" data-v="D" onclick="pick(this)"><span class="opt-key">D</span>dangeral</button>
          </div>
          <div class="q-fb" id="fb16"></div>
        </div>

        <div class="q-wrap" id="q17">
          <div class="q-stem"><div class="q-badge">17</div>
            <div class="q-text">Cặp đối lập: <span class="keyword">hope + -ful</span> = có hi vọng &nbsp;↔&nbsp; <span class="keyword">hope + ____</span> = vô vọng</div></div>
          <div class="opts">
            <button class="opt" data-q="17" data-v="A" onclick="pick(this)"><span class="opt-key">A</span>-ness</button>
            <button class="opt" data-q="17" data-v="B" onclick="pick(this)"><span class="opt-key">B</span>-less</button>
            <button class="opt" data-q="17" data-v="C" onclick="pick(this)"><span class="opt-key">C</span>-less than</button>
            <button class="opt" data-q="17" data-v="D" onclick="pick(this)"><span class="opt-key">D</span>-al</button>
          </div>
          <div class="q-fb" id="fb17"></div>
        </div>

        <div class="q-wrap" id="q18">
          <div class="q-stem"><div class="q-badge">18</div>
            <div class="q-text">You study very well. It's ______ that you will fail the exam.</div></div>
          <div class="opts">
            <button class="opt" data-q="18" data-v="A" onclick="pick(this)"><span class="opt-key">A</span>possible</button>
            <button class="opt" data-q="18" data-v="B" onclick="pick(this)"><span class="opt-key">B</span>impossible</button>
            <button class="opt" data-q="18" data-v="C" onclick="pick(this)"><span class="opt-key">C</span>possibility</button>
            <button class="opt" data-q="18" data-v="D" onclick="pick(this)"><span class="opt-key">D</span>impossibility</button>
          </div>
          <div class="q-fb" id="fb18"></div>
        </div>

        <div class="q-wrap" id="q19">
          <div class="q-stem"><div class="q-badge">19</div>
            <div class="q-text"><span class="keyword">reason</span> + _____ → <em>"có lý, hợp lý"</em></div></div>
          <div class="opts">
            <button class="opt" data-q="19" data-v="A" onclick="pick(this)"><span class="opt-key">A</span>-ous</button>
            <button class="opt" data-q="19" data-v="B" onclick="pick(this)"><span class="opt-key">B</span>-ible</button>
            <button class="opt" data-q="19" data-v="C" onclick="pick(this)"><span class="opt-key">C</span>-able</button>
            <button class="opt" data-q="19" data-v="D" onclick="pick(this)"><span class="opt-key">D</span>-ive</button>
          </div>
          <div class="q-fb" id="fb19"></div>
        </div>

      </div>
    </div>

    <!-- 3C: MATCH – suffix to example -->
    <div class="round-card">
      <div class="round-card-head">
        <span class="round-label">F · Nối từ</span>
        <h3>Nối hậu tố với ví dụ tương ứng</h3>
      </div>
      <div class="round-body">
        <p style="font-size:.85rem;color:var(--ink-soft);margin-bottom:16px;font-weight:500">
          Nhấn một hậu tố ở cột trái → nhấn ví dụ tương ứng ở cột phải.
        </p>
        <div class="match-grid">
          <div>
            <div class="match-col-head">Hậu tố</div>
            <div id="ml-left" style="display:flex;flex-direction:column;gap:8px">
              <div class="match-item selectable" id="ml-a" data-id="a" onclick="matchPick(this,'left')">-ful</div>
              <div class="match-item selectable" id="ml-b" data-id="b" onclick="matchPick(this,'left')">-ous</div>
              <div class="match-item selectable" id="ml-c" data-id="c" onclick="matchPick(this,'left')">-able</div>
              <div class="match-item selectable" id="ml-d" data-id="d" onclick="matchPick(this,'left')">-ic</div>
              <div class="match-item selectable" id="ml-e" data-id="e" onclick="matchPick(this,'left')">-ish</div>
            </div>
          </div>
          <div>
            <div class="match-col-head">Ví dụ từ</div>
            <div id="ml-right" style="display:flex;flex-direction:column;gap:8px">
              <div class="match-item selectable" id="mr-3" data-id="c" onclick="matchPick(this,'right')">reasonable</div>
              <div class="match-item selectable" id="mr-1" data-id="a" onclick="matchPick(this,'right')">successful</div>
              <div class="match-item selectable" id="mr-5" data-id="e" onclick="matchPick(this,'right')">foolish</div>
              <div class="match-item selectable" id="mr-2" data-id="b" onclick="matchPick(this,'right')">industrious</div>
              <div class="match-item selectable" id="mr-4" data-id="d" onclick="matchPick(this,'right')">economic</div>
            </div>
          </div>
        </div>
        <div style="font-size:.8rem;color:var(--ink-soft);margin-top:10px" id="match-status"></div>
      </div>
    </div>

  </section>

  <hr class="divider">

  <!-- ═══════════════════════════════
       SECTION 4 – ADV + EXCEPTIONS
  ════════════════════════════════ -->
  <section id="sec4">
    <div class="sec-head">
      <div class="sec-icon">🩷</div>
      <div class="sec-meta">
        <h2>Phần 4 – Trạng Từ &amp; Ngoại Lệ Quan Trọng</h2>
        <p>-ly · fast · hard/hardly · good/well</p>
      </div>
    </div>

    <div class="sci-badge">🔬 Error-based learning (Metcalfe, 2017) · học từ bẫy ngôn ngữ</div>

    <div class="theory-peek">
      <strong>Ngoại lệ bắt buộc nhớ:</strong> &nbsp;
      <strong>fast</strong> = adj &amp; adv (không có <em>fastly</em>) &nbsp;·&nbsp;
      <strong>hard</strong> (adj/adv = chăm chỉ) ≠ <strong>hardly</strong> (hầu như không) &nbsp;·&nbsp;
      <strong>good</strong> (adj) → <strong>well</strong> (adv, không có <em>goodly</em>)
    </div>

    <div class="round-card">
      <div class="round-card-head">
        <span class="round-label">G · Bẫy ngoại lệ</span>
        <h3>Chọn đúng – không bị bẫy!</h3>
      </div>
      <div class="round-body">

        <!-- exception cards -->
        <div class="exception-card">
          <div class="exc-q">20 · <em>"She drives very ____."</em> → Chọn trạng từ đúng của <strong>fast</strong></div>
          <div class="exc-choices">
            <button class="exc-btn" data-eq="20" data-v="A" onclick="pickExc(this)">fastly</button>
            <button class="exc-btn" data-eq="20" data-v="B" onclick="pickExc(this)">fast</button>
            <button class="exc-btn" data-eq="20" data-v="C" onclick="pickExc(this)">faster</button>
          </div>
          <div class="exc-fb" id="efb20"></div>
        </div>

        <div class="exception-card">
          <div class="exc-q">21 · <em>"He works very ____."</em> → chăm chỉ</div>
          <div class="exc-choices">
            <button class="exc-btn" data-eq="21" data-v="A" onclick="pickExc(this)">hardly</button>
            <button class="exc-btn" data-eq="21" data-v="B" onclick="pickExc(this)">hard</button>
            <button class="exc-btn" data-eq="21" data-v="C" onclick="pickExc(this)">hardness</button>
          </div>
          <div class="exc-fb" id="efb21"></div>
        </div>

        <div class="exception-card">
          <div class="exc-q">22 · <em>"He ____ studies. He's always on his phone."</em> → hầu như không</div>
          <div class="exc-choices">
            <button class="exc-btn" data-eq="22" data-v="A" onclick="pickExc(this)">hard</button>
            <button class="exc-btn" data-eq="22" data-v="B" onclick="pickExc(this)">hardly</button>
            <button class="exc-btn" data-eq="22" data-v="C" onclick="pickExc(this)">hardful</button>
          </div>
          <div class="exc-fb" id="efb22"></div>
        </div>

        <div class="exception-card">
          <div class="exc-q">23 · <em>"She speaks English very ____."</em> → dạng trạng từ của <strong>good</strong></div>
          <div class="exc-choices">
            <button class="exc-btn" data-eq="23" data-v="A" onclick="pickExc(this)">good</button>
            <button class="exc-btn" data-eq="23" data-v="B" onclick="pickExc(this)">goodly</button>
            <button class="exc-btn" data-eq="23" data-v="C" onclick="pickExc(this)">well</button>
          </div>
          <div class="exc-fb" id="efb23"></div>
        </div>

        <div class="exception-card">
          <div class="exc-q">24 · <em>"She has ____ hair."</em> (adj) ↔ <em>"She sings ____."</em> (adv) → cùng một từ nào?</div>
          <div class="exc-choices">
            <button class="exc-btn" data-eq="24" data-v="A" onclick="pickExc(this)">fast</button>
            <button class="exc-btn" data-eq="24" data-v="B" onclick="pickExc(this)">friendly</button>
            <button class="exc-btn" data-eq="24" data-v="C" onclick="pickExc(this)">hard</button>
          </div>
          <div class="exc-fb" id="efb24"></div>
        </div>

      </div>
    </div>

    <!-- Adv fill -->
    <div class="round-card">
      <div class="round-card-head">
        <span class="round-label">H · Điền trạng từ</span>
        <h3>Viết dạng trạng từ đúng</h3>
      </div>
      <div class="round-body">

        <div class="fill-wrap" id="f4">
          <div class="q-badge" style="margin-top:4px">25</div>
          <div class="fill-body">
            <div class="fill-row">
              careful → <input class="fill-inp" id="fi4" placeholder="adv" autocomplete="off">
              <span class="fill-tag">Adj → Adv</span>
            </div>
            <div class="fill-fb" id="fib4"></div>
          </div>
        </div>

        <div class="fill-wrap" id="f5">
          <div class="q-badge" style="margin-top:4px">26</div>
          <div class="fill-body">
            <div class="fill-row">
              rapid → <input class="fill-inp" id="fi5" placeholder="adv" autocomplete="off">
              <span class="fill-tag">Adj → Adv</span>
            </div>
            <div class="fill-fb" id="fib5"></div>
          </div>
        </div>

        <div class="fill-wrap" id="f6">
          <div class="q-badge" style="margin-top:4px">27</div>
          <div class="fill-body">
            <div class="fill-row">
              good → <input class="fill-inp" id="fi6" placeholder="adv" autocomplete="off">
              <span class="fill-tag">Adj → Adv ⚠️</span>
            </div>
            <div class="fill-fb" id="fib6"></div>
          </div>
        </div>

      </div>
    </div>

  </section>

  <hr class="divider">

  <!-- ═══════════════════════════════
       SECTION 5 – POSITIONAL CLUES
  ════════════════════════════════ -->
  <section id="sec5">
    <div class="sec-head">
      <div class="sec-icon">🧭</div>
      <div class="sec-meta">
        <h2>Phần 5 – Nhận Vị Trí → Chọn Từ Loại</h2>
        <p>Dấu hiệu xung quanh chỗ trống quyết định từ loại</p>
      </div>
    </div>

    <div class="sci-badge">🔬 Contextual inference (Nation, 2001 · TESOL) · suy từ ngữ cảnh</div>

    <div class="theory-peek">
      <strong>to be + ___</strong> → <span class="tag tag-a">ADJ</span> &nbsp;·&nbsp;
      <strong>V thường + ___</strong> → <span class="tag tag-adv">ADV</span> &nbsp;·&nbsp;
      <strong>a/an/the + ___</strong> → <span class="tag tag-n">N</span> &nbsp;·&nbsp;
      <strong>___ + danh từ</strong> → <span class="tag tag-a">ADJ</span> &nbsp;·&nbsp;
      <strong>will/can + ___</strong> → <span class="tag tag-v">V</span>
    </div>

    <!-- 5A: identify word class needed -->
    <div class="round-card">
      <div class="round-card-head">
        <span class="round-label">I · Nhận biết từ loại</span>
        <h3>Nhìn vào vị trí trống — cần từ loại gì?</h3>
      </div>
      <div class="round-body">

        <div class="q-wrap" id="q28">
          <div class="q-stem"><div class="q-badge">28</div>
            <div class="q-text"><em>"He failed the exam because of his ______."</em><br>Vị trí này cần từ loại gì?</div></div>
          <div class="opts">
            <button class="opt" data-q="28" data-v="A" onclick="pick(this)"><span class="opt-key">A</span><span class="tag tag-n">N</span> Danh từ</button>
            <button class="opt" data-q="28" data-v="B" onclick="pick(this)"><span class="opt-key">B</span><span class="tag tag-a">ADJ</span> Tính từ</button>
            <button class="opt" data-q="28" data-v="C" onclick="pick(this)"><span class="opt-key">C</span><span class="tag tag-adv">ADV</span> Trạng từ</button>
            <button class="opt" data-q="28" data-v="D" onclick="pick(this)"><span class="opt-key">D</span><span class="tag tag-v">V</span> Động từ</button>
          </div>
          <div class="q-fb" id="fb28"></div>
        </div>

        <div class="q-wrap" id="q29">
          <div class="q-stem"><div class="q-badge">29</div>
            <div class="q-text"><em>"The matter is comparatively ______."</em><br>Sau "is" và trạng từ "comparatively" → cần gì?</div></div>
          <div class="opts">
            <button class="opt" data-q="29" data-v="A" onclick="pick(this)"><span class="opt-key">A</span><span class="tag tag-n">N</span> Danh từ</button>
            <button class="opt" data-q="29" data-v="B" onclick="pick(this)"><span class="opt-key">B</span><span class="tag tag-a">ADJ</span> Tính từ</button>
            <button class="opt" data-q="29" data-v="C" onclick="pick(this)"><span class="opt-key">C</span><span class="tag tag-adv">ADV</span> Trạng từ</button>
            <button class="opt" data-q="29" data-v="D" onclick="pick(this)"><span class="opt-key">D</span><span class="tag tag-v">V</span> Động từ</button>
          </div>
          <div class="q-fb" id="fb29"></div>
        </div>

        <div class="q-wrap" id="q30">
          <div class="q-stem"><div class="q-badge">30</div>
            <div class="q-text"><em>"We will ______ our vocabulary."</em><br>Sau "will" → cần gì?</div></div>
          <div class="opts">
            <button class="opt" data-q="30" data-v="A" onclick="pick(this)"><span class="opt-key">A</span><span class="tag tag-n">N</span> Danh từ</button>
            <button class="opt" data-q="30" data-v="B" onclick="pick(this)"><span class="opt-key">B</span><span class="tag tag-a">ADJ</span> Tính từ</button>
            <button class="opt" data-q="30" data-v="C" onclick="pick(this)"><span class="opt-key">C</span><span class="tag tag-adv">ADV</span> Trạng từ</button>
            <button class="opt" data-q="30" data-v="D" onclick="pick(this)"><span class="opt-key">D</span><span class="tag tag-v">V</span> Động từ</button>
          </div>
          <div class="q-fb" id="fb30"></div>
        </div>

      </div>
    </div>

    <!-- 5B: sort suffixes into buckets -->
    <div class="round-card">
      <div class="round-card-head">
        <span class="round-label">J · Phân loại</span>
        <h3>Xếp các hậu tố sau vào đúng nhóm từ loại</h3>
      </div>
      <div class="round-body">
        <p class="sort-prompt">Nhấn hậu tố, rồi nhấn ô phù hợp để xếp vào nhóm. Nhấn ô đã điền để xóa.</p>

        <div class="sort-pool" id="sort-pool">
          <div class="sort-tile" data-val="-ness" onclick="sortPick(this)">-ness</div>
          <div class="sort-tile" data-val="-ize" onclick="sortPick(this)">-ize</div>
          <div class="sort-tile" data-val="-ly" onclick="sortPick(this)">-ly</div>
          <div class="sort-tile" data-val="-ful" onclick="sortPick(this)">-ful</div>
          <div class="sort-tile" data-val="-ment" onclick="sortPick(this)">-ment</div>
          <div class="sort-tile" data-val="-en" onclick="sortPick(this)">-en</div>
          <div class="sort-tile" data-val="-ous" onclick="sortPick(this)">-ous</div>
          <div class="sort-tile" data-val="-tion" onclick="sortPick(this)">-tion</div>
        </div>

        <div style="display:grid;grid-template-columns:1fr 1fr;gap:16px" id="sort-buckets">
          <div>
            <div style="font-size:.78rem;font-weight:800;color:var(--blue);margin-bottom:8px"><span class="tag tag-n">N</span> Danh từ</div>
            <div style="display:flex;flex-direction:column;gap:6px">
              <div class="sort-slot" id="ss-n1" data-bucket="N" onclick="sortDrop(this)">___</div>
              <div class="sort-slot" id="ss-n2" data-bucket="N" onclick="sortDrop(this)">___</div>
              <div class="sort-slot" id="ss-n3" data-bucket="N" onclick="sortDrop(this)">___</div>
            </div>
          </div>
          <div>
            <div style="font-size:.78rem;font-weight:800;color:var(--green);margin-bottom:8px"><span class="tag tag-v">V</span> Động từ</div>
            <div style="display:flex;flex-direction:column;gap:6px">
              <div class="sort-slot" id="ss-v1" data-bucket="V" onclick="sortDrop(this)">___</div>
              <div class="sort-slot" id="ss-v2" data-bucket="V" onclick="sortDrop(this)">___</div>
            </div>
          </div>
          <div>
            <div style="font-size:.78rem;font-weight:800;color:#92400e;margin-bottom:8px"><span class="tag tag-a">ADJ</span> Tính từ</div>
            <div style="display:flex;flex-direction:column;gap:6px">
              <div class="sort-slot" id="ss-a1" data-bucket="A" onclick="sortDrop(this)">___</div>
              <div class="sort-slot" id="ss-a2" data-bucket="A" onclick="sortDrop(this)">___</div>
            </div>
          </div>
          <div>
            <div style="font-size:.78rem;font-weight:800;color:#9d174d;margin-bottom:8px"><span class="tag tag-adv">ADV</span> Trạng từ</div>
            <div style="display:flex;flex-direction:column;gap:6px">
              <div class="sort-slot" id="ss-d1" data-bucket="D" onclick="sortDrop(this)">___</div>
            </div>
          </div>
        </div>

        <button class="match-btn" id="sort-check-btn" onclick="checkSort()" style="margin-top:16px">✅ Kiểm tra phân loại</button>
        <div style="font-size:.82rem;font-weight:700;margin-top:10px;display:none" id="sort-result"></div>
      </div>
    </div>

    <!-- 5C: In-context fill -->
    <div class="round-card">
      <div class="round-card-head">
        <span class="round-label">K · Ngữ cảnh thực</span>
        <h3>Điền từ đúng từ gợi ý trong ngoặc</h3>
      </div>
      <div class="round-body">

        <div class="fill-wrap" id="f7">
          <div class="q-badge" style="margin-top:4px">32</div>
          <div class="fill-body">
            <div class="fill-row">
              Lan always shares her <input class="fill-inp" id="fi7" placeholder="..." autocomplete="off"> with me.
              <span class="fill-tag">sad</span>
            </div>
            <div class="fill-fb" id="fib7"></div>
          </div>
        </div>

        <div class="fill-wrap" id="f8">
          <div class="q-badge" style="margin-top:4px">33</div>
          <div class="fill-body">
            <div class="fill-row">
              Money doesn't bring <input class="fill-inp" id="fi8" placeholder="..." autocomplete="off"> to man.
              <span class="fill-tag">happy</span>
            </div>
            <div class="fill-fb" id="fib8"></div>
          </div>
        </div>

        <div class="fill-wrap" id="f9">
          <div class="q-badge" style="margin-top:4px">34</div>
          <div class="fill-body">
            <div class="fill-row">
              Good students aren't <input class="fill-inp" id="fi9" placeholder="..." autocomplete="off"> intelligent students.
              <span class="fill-tag">necessary</span>
            </div>
            <div class="fill-fb" id="fib9"></div>
          </div>
        </div>

        <div class="fill-wrap" id="f10">
          <div class="q-badge" style="margin-top:4px">35</div>
          <div class="fill-body">
            <div class="fill-row">
              The teacher does everything to <input class="fill-inp" id="fi10" placeholder="..." autocomplete="off"> her students.
              <span class="fill-tag">courage</span>
            </div>
            <div class="fill-fb" id="fib10"></div>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- ══ SUBMIT ══ -->
  <div class="submit-bar">
    <button class="submit-btn" id="sub-btn" onclick="submitAll()">🎯 Nộp &amp; Xem Kết Quả</button>
    <div class="submit-note">
      Hoàn thành tất cả câu trước khi nộp.<br>
      <span id="sub-note">Còn <strong id="sub-remain">35</strong> câu chưa trả lời.</span>
    </div>
  </div>

</main>

<!-- ══════════ JAVASCRIPT ══════════ -->
<script>
/* ── ANSWER KEYS ── */
const MCQ_KEY = {
  1:'B', 2:'C', 3:'C', 4:'B', 5:'C',
  9:'C', 10:'B', 11:'C', 12:'C',
  13:'B', 14:'B', 15:'B',
  16:'C', 17:'B', 18:'B', 19:'C',
  28:'A', 29:'B', 30:'D'
};

const MCQ_EXPLAIN = {
  1: 'develop + <strong>-ment</strong> = development (sự phát triển). -ment thường đi với động từ.',
  2: 'attend + <strong>-ance</strong> = attendance (sự tham dự). -ance thường đi với động từ.',
  3: '<strong>employer</strong> (V + -er = người làm). arrival, invention là sự kiện; freedom là trạng thái.',
  4: 'rich + <strong>-ness</strong> = richness. -ness đi với tính từ tạo danh từ trừu tượng.',
  5: 'friend + <strong>-ship</strong> = friendship (tình bạn). -ship chỉ mối quan hệ.',
  9: 'beauty + <strong>-fy</strong> = beautify (làm đẹp). Quy tắc N/-fy → V.',
  10: '<strong>enrich</strong> = en- + rich (làm giàu). en- + adj/n → động từ.',
  11: '<strong>enrich</strong> = en + rich → động từ. Sau "will" cần động từ nguyên thể.',
  12: 'wide + <strong>-en</strong> = widen (mở rộng). -en đi với tính từ ngắn.',
  13: 'Phim GÂY RA buồn ngủ → dùng <strong>-ing</strong>: boring. -ing mô tả bản chất sự vật.',
  14: 'I (người) CẢM THẤY → dùng <strong>-ed</strong>: interested. -ed mô tả cảm xúc của người.',
  15: 'Tin tức GÂY RA ngạc nhiên → <strong>surprising</strong> (-ing = tính chất của sự vật).',
  16: 'danger + <strong>-ous</strong> = dangerous. Hậu tố -ous rất phổ biến với danh từ.',
  17: 'hopeful ↔ hope<strong>less</strong>. -less = không có, đối lập với -ful.',
  18: '<strong>impossible</strong> = im- (phủ định) + possible. Nghĩa: không thể xảy ra.',
  19: 'reason + <strong>-able</strong> = reasonable (hợp lý). -able phổ biến hơn -ible với "reason".',
  28: 'Sau "of" (giới từ) → cần <strong>Danh từ</strong>. "because of his laziness".',
  29: 'Sau "is" + trạng từ "comparatively" → cần <strong>Tính từ</strong> vị ngữ.',
  30: 'Sau "will" → cần <strong>Động từ</strong> nguyên thể. "will enrich".'
};

const FILL_KEY = {
  fi1: { ans: ['invention'], display: 'invention', explain: 'invent + <strong>-ion</strong> = invention.' },
  fi2: { ans: ['ability'], display: 'ability',   explain: 'able → abil<strong>ity</strong>. (-ity với adjective)' },
  fi3: { ans: ['warmth'], display: 'warmth',    explain: 'warm + <strong>-th</strong> = warmth. Hậu tố ít gặp.' },
  fi4: { ans: ['carefully'], display: 'carefully',  explain: 'careful + <strong>-ly</strong> = carefully.' },
  fi5: { ans: ['rapidly'], display: 'rapidly',    explain: 'rapid + <strong>-ly</strong> = rapidly.' },
  fi6: { ans: ['well'], display: 'well',       explain: '<strong>good</strong> (adj) → <strong>well</strong> (adv). Không có "goodly"!' },
  fi7: { ans: ['sadness'], display: 'sadness',    explain: 'sad + <strong>-ness</strong> = sadness. Sau "her" → cần N.' },
  fi8: { ans: ['happiness'], display: 'happiness',  explain: 'happy → happi<strong>ness</strong>. Sau "bring" → N.' },
  fi9: { ans: ['necessarily'], display: 'necessarily', explain: 'necessary → <strong>necessarily</strong>. Bổ nghĩa adj "intelligent" → ADV.' },
  fi10:{ ans: ['encourage'], display: 'encourage',  explain: 'en- + courage → <strong>encourage</strong>. Sau "to" → V nguyên thể.' }
};

const EXC_KEY = {
  20: { ans: 'B', explain: '<strong>fast</strong> = adj và adv. Không có "fastly" trong tiếng Anh!' },
  21: { ans: 'B', explain: '<strong>hard</strong> (adv) = chăm chỉ. "Hardly" lại có nghĩa khác.' },
  22: { ans: 'B', explain: '<strong>hardly</strong> = hầu như không. Đây là trạng từ tần suất phủ định.' },
  23: { ans: 'C', explain: '<strong>well</strong> là trạng từ của good. "Goodly" không tồn tại.' },
  24: { ans: 'A', explain: '<strong>fast</strong> vừa là adj ("fast car") vừa là adv ("drive fast").' }
};

/* ── MATCH STATE ── */
const MATCH_KEY = { a:'a', b:'b', c:'c', d:'d', e:'e' };
let matchLeft = null, matchRight = null, matchDone = new Set();

/* ── SORT STATE ── */
const SORT_KEY = {
  N: ['-ness', '-ment', '-tion'],
  V: ['-ize', '-en'],
  A: ['-ful', '-ous'],
  D: ['-ly']
};
let sortSelected = null;
const sortSlots = {}; // slotId → value

/* ── TRACKING ── */
const answered = new Set();
const TOTAL_Q = 35;
let totalScore = 0;

function markAnswered(id) {
  answered.add(id);
  updateProg();
}
function updateProg() {
  const n = answered.size;
  const pct = Math.round(n / TOTAL_Q * 100);
  document.getElementById('prog-fill').style.width = pct + '%';
  document.getElementById('prog-txt').textContent = `${n} / ${TOTAL_Q}`;
  const rem = TOTAL_Q - n;
  document.getElementById('sub-remain').textContent = rem;
  if (rem === 0) {
    document.getElementById('sub-note').innerHTML = '✅ Sẵn sàng nộp bài!';
  }
}
function addScore(pts) {
  totalScore += pts;
  document.getElementById('live-score').textContent = totalScore;
}

/* ── MCQ ── */
function pick(btn) {
  const q = btn.dataset.q;
  if (document.querySelector(`.opt[data-q="${q}"].correct`) || document.querySelector(`.opt[data-q="${q}"].wrong`)) return;
  document.querySelectorAll(`.opt[data-q="${q}"]`).forEach(b => b.classList.remove('picked'));
  btn.classList.add('picked');
}

/* ── EXC BTN ── */
function pickExc(btn) {
  const eq = btn.dataset.eq;
  if (document.getElementById('efb'+eq).classList.contains('ok') ||
      document.getElementById('efb'+eq).classList.contains('err')) return;
  document.querySelectorAll(`.exc-btn[data-eq="${eq}"]`).forEach(b => b.classList.remove('selected'));
  btn.classList.add('selected');
}

/* ── MATCH ── */
function matchPick(el, side) {
  if (el.classList.contains('matched-ok') || el.classList.contains('dim')) return;
  if (side === 'left') {
    document.querySelectorAll('#ml-left .match-item').forEach(e => e.classList.remove('selected'));
    el.classList.add('selected');
    matchLeft = el;
  } else {
    document.querySelectorAll('#ml-right .match-item').forEach(e => e.classList.remove('selected'));
    el.classList.add('selected');
    matchRight = el;
  }
  if (matchLeft && matchRight) {
    const isOk = matchLeft.dataset.id === matchRight.dataset.id;
    if (isOk) {
      matchLeft.classList.remove('selected'); matchLeft.classList.add('matched-ok','dim');
      matchRight.classList.remove('selected'); matchRight.classList.add('matched-ok','dim');
      matchDone.add(matchLeft.dataset.id);
      addScore(1);
      if (matchDone.size === 5) {
        markAnswered('match');
        document.getElementById('match-status').textContent = '✅ Khớp hết rồi!';
      }
    } else {
      [matchLeft, matchRight].forEach(e => {
        e.classList.add('matched-err');
        setTimeout(() => e.classList.remove('matched-err','selected'), 700);
      });
    }
    matchLeft = null; matchRight = null;
  }
}

/* ── SORT ── */
function sortPick(tile) {
  if (tile.classList.contains('used')) return;
  document.querySelectorAll('.sort-tile').forEach(t => t.classList.remove('selected'));
  tile.classList.add('selected');
  sortSelected = tile;
}

function sortDrop(slot) {
  if (!sortSelected) return;
  // If slot already filled, return tile to pool
  if (sortSlots[slot.id]) {
    const old = sortSlots[slot.id];
    const oldTile = document.querySelector(`.sort-tile[data-val="${old}"]`);
    if (oldTile) oldTile.classList.remove('used','selected');
  }
  sortSlots[slot.id] = sortSelected.dataset.val;
  slot.textContent = sortSelected.dataset.val;
  slot.classList.add('filled');
  slot.classList.remove('correct','wrong');
  sortSelected.classList.add('used');
  sortSelected.classList.remove('selected');
  sortSelected = null;
}

function checkSort() {
  const buckets = { N: [], V: [], A: [], D: [] };
  ['ss-n1','ss-n2','ss-n3'].forEach(id => { if(sortSlots[id]) buckets.N.push(sortSlots[id]); });
  ['ss-v1','ss-v2'].forEach(id => { if(sortSlots[id]) buckets.V.push(sortSlots[id]); });
  ['ss-a1','ss-a2'].forEach(id => { if(sortSlots[id]) buckets.A.push(sortSlots[id]); });
  ['ss-d1'].forEach(id => { if(sortSlots[id]) buckets.D.push(sortSlots[id]); });

  let ok = 0, total = 8;
  // Mark slots
  ['ss-n1','ss-n2','ss-n3'].forEach(id => {
    const sl = document.getElementById(id);
    const v = sortSlots[id];
    if (!v) return;
    const correct = SORT_KEY.N.includes(v);
    sl.classList.toggle('correct', correct);
    sl.classList.toggle('wrong', !correct);
    if (correct) ok++;
  });
  ['ss-v1','ss-v2'].forEach(id => {
    const sl = document.getElementById(id); const v = sortSlots[id];
    if (!v) return;
    const correct = SORT_KEY.V.includes(v);
    sl.classList.toggle('correct', correct); sl.classList.toggle('wrong', !correct);
    if (correct) ok++;
  });
  ['ss-a1','ss-a2'].forEach(id => {
    const sl = document.getElementById(id); const v = sortSlots[id];
    if (!v) return;
    const correct = SORT_KEY.A.includes(v);
    sl.classList.toggle('correct', correct); sl.classList.toggle('wrong', !correct);
    if (correct) ok++;
  });
  ['ss-d1'].forEach(id => {
    const sl = document.getElementById(id); const v = sortSlots[id];
    if (!v) return;
    const correct = SORT_KEY.D.includes(v);
    sl.classList.toggle('correct', correct); sl.classList.toggle('wrong', !correct);
    if (correct) ok++;
  });

  const res = document.getElementById('sort-result');
  res.style.display = 'block';
  res.innerHTML = `${ok === total ? '✅' : '⚠️'} Đúng ${ok}/${total}. ${ok < total ? 'Hãy kiểm tra lại các ô đỏ.' : 'Hoàn hảo!'}`;
  res.style.color = ok === total ? 'var(--green)' : 'var(--amber)';
  addScore(ok);
  markAnswered('sort');
  document.getElementById('sort-check-btn').disabled = true;
}

/* ── FILL ENTER KEY ── */
document.addEventListener('DOMContentLoaded', () => {
  document.querySelectorAll('.fill-inp').forEach((inp, i, all) => {
    inp.addEventListener('input', updateProg);
    inp.addEventListener('keydown', e => {
      if (e.key === 'Enter') { e.preventDefault(); if(all[i+1]) all[i+1].focus(); }
    });
  });
});

/* ── TOAST ── */
let toastT;
function toast(msg) {
  const el = document.getElementById('toast');
  document.getElementById('toast-msg').textContent = msg;
  el.classList.add('show');
  clearTimeout(toastT);
  toastT = setTimeout(() => el.classList.remove('show'), 3000);
}

/* ── SUBMIT ALL ── */
function submitAll() {
  let miss = 0;

  // Grade MCQ
  [1,2,3,4,5,9,10,11,12,13,14,15,16,17,18,19,28,29,30].forEach(q => {
    const picked = document.querySelector(`.opt[data-q="${q}"].picked`);
    const correct = MCQ_KEY[q];
    const fb = document.getElementById('fb'+q);
    if (!picked) { miss++; document.getElementById('q'+q)?.scrollIntoView({behavior:'smooth',block:'center'}); return; }
    document.querySelectorAll(`.opt[data-q="${q}"]`).forEach(b => {
      b.disabled = true;
      if (b.dataset.v === correct) b.classList.add('correct');
      else if (b.classList.contains('picked')) b.classList.add('wrong');
      b.classList.remove('picked');
    });
    const isOk = picked.dataset.v === correct;
    if (isOk) addScore(1);
    fb.innerHTML = isOk
      ? `✅ Đúng! ${MCQ_EXPLAIN[q]||''}`
      : `❌ Đáp án: <strong>${correct}</strong>. ${MCQ_EXPLAIN[q]||''}`;
    fb.className = 'q-fb ' + (isOk ? 'ok' : 'err');
    markAnswered('q'+q);
  });

  // Grade Fill
  Object.entries(FILL_KEY).forEach(([id, data]) => {
    const inp = document.getElementById(id);
    const fb  = document.getElementById('fib'+id.replace('fi',''));
    if (!inp) return;
    const user = inp.value.trim().toLowerCase();
    const isOk = data.ans.map(a=>a.toLowerCase()).includes(user);
    if (!user) { miss++; inp.focus(); return; }
    inp.disabled = true;
    inp.className = 'fill-inp ' + (isOk ? 'correct' : 'wrong');
    if (isOk) addScore(1);
    if (fb) {
      fb.innerHTML = isOk
        ? `✅ Chính xác! ${data.explain}`
        : `❌ Đáp án: <strong>${data.display}</strong>. ${data.explain}`;
      fb.className = 'fill-fb ' + (isOk ? 'ok' : 'err');
    }
    markAnswered(id);
  });

  // Grade Exceptions
  [20,21,22,23,24].forEach(eq => {
    const picked = document.querySelector(`.exc-btn[data-eq="${eq}"].selected`);
    const fb = document.getElementById('efb'+eq);
    if (!picked) { miss++; return; }
    const isOk = picked.dataset.v === EXC_KEY[eq].ans;
    document.querySelectorAll(`.exc-btn[data-eq="${eq}"]`).forEach(b => {
      b.disabled = true;
      if (b.dataset.v === EXC_KEY[eq].ans) b.classList.add('correct');
      else if (b.classList.contains('selected')) b.classList.add('wrong');
      b.classList.remove('selected');
    });
    if (isOk) addScore(1);
    fb.innerHTML = isOk
      ? `✅ Đúng! ${EXC_KEY[eq].explain}`
      : `❌ Đáp án: <strong>${EXC_KEY[eq].ans === 'A'?'phương án 1':EXC_KEY[eq].ans==='B'?'phương án 2':'phương án 3'}</strong>. ${EXC_KEY[eq].explain}`;
    fb.className = 'exc-fb ' + (isOk ? 'ok' : 'err');
    markAnswered('exc'+eq);
  });

  if (miss > 0) {
    toast(`⚠️ Còn ${miss} câu chưa trả lời!`);
    return;
  }

  // Show modal
  const pct = Math.round(totalScore / TOTAL_Q * 100);
  document.getElementById('m-score').textContent = totalScore;
  document.getElementById('m-of').textContent = `/ ${TOTAL_Q} điểm  (${pct}%)`;
  setTimeout(() => { document.getElementById('m-bar').style.width = pct + '%'; }, 120);

  let emoji, msg;
  if (pct === 100)     { emoji='🏆'; msg='Hoàn hảo! Em đã gợi nhớ thành công toàn bộ kiến thức Word Forms!'; }
  else if (pct >= 85)  { emoji='⭐'; msg='Rất tốt! Kiến thức nền vững chắc, chỉ còn vài điểm nhỏ cần ôn.'; }
  else if (pct >= 70)  { emoji='👍'; msg='Khá! Xem lại giải thích các câu sai để củng cố thêm.'; }
  else if (pct >= 55)  { emoji='💪'; msg='Cần luyện thêm. Đọc lại lý thuyết, đặc biệt ngoại lệ và -ing/-ed.'; }
  else                  { emoji='📖'; msg='Hãy quay lại đọc lý thuyết kỹ hơn, rồi thử lại bài này!'; }

  document.getElementById('m-emoji').textContent = emoji;
  document.getElementById('m-msg').textContent = msg;
  document.getElementById('modal').classList.add('open');
  document.getElementById('sub-btn').disabled = true;
}

/* NAV ACTIVE */
window.addEventListener('scroll', () => {
  const ids = ['sec1','sec2','sec3','sec4','sec5'];
  let cur = '';
  ids.forEach(id => {
    const el = document.getElementById(id);
    if (el && el.getBoundingClientRect().top < 130) cur = '#' + id;
  });
  document.querySelectorAll('.snav-pill').forEach(p => {
    p.classList.remove('active');
    if (p.getAttribute('href') === cur) p.classList.add('active');
  });
});
</script>
</body>
</html>
