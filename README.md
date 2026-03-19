[משחקי-חסידות (11).html](https://github.com/user-attachments/files/26121509/-.11.html)
<!DOCTYPE html>
<html lang="he" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>משחקי חסידות</title>
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-HDWWMFNS9E"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-HDWWMFNS9E');
</script>
<link href="https://fonts.googleapis.com/css2?family=Heebo:wght@300;400;700;900&family=Frank+Ruhl+Libre:wght@300;400;700;900&family=Secular+One&display=swap" rel="stylesheet">
<style>
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
:root {
  --bg: #0f0e17;
  --surface: #1a1828;
  --text: #fffffe;
  --muted: #a7a9be;
  --gold: #c9a84c;
  --gold-light: #f0d080;
  --parchment: #f5ead0;
  --dark: #1a1209;
  --red: #8b1a1a;
  --c1: #ff8906;
  --c2: #3da9fc;
  --c3: #ef4565;
  --c4: #44cf6c;
  --selected: #f3d060;
}

body {
  font-family: 'Heebo', sans-serif;
  background: var(--bg);
  color: var(--text);
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
}

/* ══════════════════════════════
   MENU SCREEN
══════════════════════════════ */
#menu-screen {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  padding: 30px 20px;
  text-align: center;
  animation: fadeIn 0.6s ease;
}
#menu-screen .menu-emoji { font-size: 3.5rem; margin-bottom: 16px; animation: float 3s ease-in-out infinite; }
#menu-screen h1 {
  font-family: 'Secular One', sans-serif;
  font-size: clamp(2rem, 6vw, 3.5rem);
  font-weight: 900;
  background: linear-gradient(135deg, var(--c1), var(--c2), var(--c3), var(--c4));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  margin-bottom: 10px;
}
#menu-screen .menu-sub {
  color: var(--muted);
  font-size: 1rem;
  margin-bottom: 40px;
}
.game-cards {
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
  justify-content: center;
  max-width: 620px;
}
.game-card {
  background: var(--surface);
  border-radius: 20px;
  padding: 32px 28px;
  width: 260px;
  cursor: pointer;
  transition: transform 0.2s, box-shadow 0.2s;
  border: 2px solid transparent;
  text-align: center;
}
.game-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 12px 40px rgba(0,0,0,0.5);
}
.game-card.card-kesher { border-color: rgba(255,137,6,0.4); }
.game-card.card-kesher:hover { border-color: var(--c1); box-shadow: 0 12px 40px rgba(255,137,6,0.25); }
.game-card.card-tzaddik { border-color: rgba(201,168,76,0.4); }
.game-card.card-tzaddik:hover { border-color: var(--gold); box-shadow: 0 12px 40px rgba(201,168,76,0.25); }
.game-card .card-emoji { font-size: 3rem; margin-bottom: 14px; }
.game-card h2 {
  font-size: 1.4rem;
  font-weight: 900;
  margin-bottom: 8px;
}
.card-kesher h2 {
  background: linear-gradient(135deg, var(--c1), var(--c3));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
.card-tzaddik h2 {
  color: var(--gold);
}
.game-card p {
  color: var(--muted);
  font-size: 0.88rem;
  line-height: 1.5;
}
.play-btn {
  display: inline-block;
  margin-top: 18px;
  padding: 9px 24px;
  border-radius: 50px;
  font-family: 'Heebo', sans-serif;
  font-weight: 700;
  font-size: 0.95rem;
  border: none;
  cursor: pointer;
  transition: transform 0.15s;
}
.play-btn:hover { transform: scale(1.05); }
.card-kesher .play-btn { background: linear-gradient(135deg, var(--c1), var(--c3)); color: white; }
.card-tzaddik .play-btn { background: linear-gradient(135deg, var(--gold), var(--gold-light)); color: var(--dark); }

/* ══════════════════════════════
   CROSS-GAME PROMO BANNER
══════════════════════════════ */
.promo-banner {
  display: none;
  background: var(--surface);
  border-radius: 16px;
  padding: 20px 24px;
  text-align: center;
  margin-top: 16px;
  width: 100%;
  border: 1px solid rgba(255,255,255,0.08);
  animation: popIn 0.4s ease;
}
.promo-banner.visible { display: block; }
.promo-banner p {
  color: var(--muted);
  font-size: 0.95rem;
  margin-bottom: 14px;
}
.promo-banner strong {
  color: var(--text);
}

/* ══════════════════════════════
   MA HAKESHER GAME
══════════════════════════════ */
#kesher-screen {
  display: none;
  flex-direction: column;
  align-items: center;
  width: 100%;
  padding: 20px 12px 40px;
  animation: fadeIn 0.4s ease;
}
#kesher-screen header { text-align: center; margin-bottom: 28px; width: 100%; }
#kesher-screen h1 {
  font-size: clamp(2.2rem, 6vw, 3.5rem);
  font-weight: 900;
  letter-spacing: -1px;
  background: linear-gradient(135deg, var(--c1), var(--c2), var(--c3), var(--c4));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  line-height: 1.1;
}
#kesher-screen .subtitle { color: var(--muted); font-size: 1rem; margin-top: 6px; }
#kesher-game-area { width: 100%; max-width: 580px; }
.mistakes-row {
  display: flex; justify-content: center; align-items: center;
  gap: 8px; margin-bottom: 18px; font-size: 0.9rem; color: var(--muted);
}
.dot { width: 14px; height: 14px; border-radius: 50%; background: var(--muted); transition: background 0.3s; }
.dot.used { background: var(--c3); }
#solved-groups { display: flex; flex-direction: column; gap: 8px; margin-bottom: 8px; }
.solved-card {
  border-radius: 14px; padding: 16px 20px; text-align: center;
  animation: popIn 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}
.solved-card .cat-name { font-weight: 900; font-size: 1.05rem; letter-spacing: 0.5px; margin-bottom: 4px; }
.solved-card .cat-words { font-size: 0.88rem; opacity: 0.85; }
#grid {
  display: grid; grid-template-columns: repeat(4, 1fr);
  gap: 8px; margin-bottom: 16px;
}
.word-tile {
  background: var(--surface); border: 2px solid transparent; border-radius: 12px;
  padding: 6px; aspect-ratio: 1 / 0.75; display: flex; align-items: center;
  justify-content: center; text-align: center;
  font-size: clamp(0.78rem, 2.2vw, 1rem); font-weight: 700;
  cursor: pointer; user-select: none; line-height: 1.2;
  transition: transform 0.15s, background 0.15s, border-color 0.15s, box-shadow 0.15s;
}
.word-tile:hover { transform: translateY(-3px); box-shadow: 0 6px 20px rgba(0,0,0,0.4); }
.word-tile.selected {
  background: var(--selected); color: #0f0e17; border-color: var(--selected);
  transform: translateY(-4px) scale(1.04);
  box-shadow: 0 8px 24px rgba(243, 208, 96, 0.35);
}
.word-tile.wrong-shake { animation: shake 0.45s ease; }
.word-tile.correct-pop { animation: popIn 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275); }
.actions { display: flex; gap: 10px; justify-content: center; margin-bottom: 20px; flex-wrap: wrap; }
.btn {
  font-family: 'Heebo', sans-serif; font-size: 0.95rem; font-weight: 700;
  padding: 10px 24px; border-radius: 50px; border: none; cursor: pointer;
  transition: transform 0.15s, opacity 0.15s;
}
.btn:hover { transform: scale(1.05); }
.btn:active { transform: scale(0.97); }
.btn:disabled { opacity: 0.35; cursor: not-allowed; transform: none; }
.btn-primary { background: var(--text); color: var(--bg); }
.btn-ghost { background: transparent; color: var(--muted); border: 2px solid #333; }
#k-message {
  text-align: center; font-size: 1rem; font-weight: 700;
  min-height: 28px; margin-bottom: 10px; transition: opacity 0.3s; color: var(--selected);
}
#kesher-win-screen {
  display: none; text-align: center; animation: fadeIn 0.5s ease;
}
#kesher-win-screen h2 { font-size: 2rem; font-weight: 900; margin-bottom: 10px; }
#kesher-win-screen p { color: var(--muted); margin-bottom: 20px; }

/* back button */
.back-btn {
  background: transparent; border: 1px solid #333; color: var(--muted);
  font-family: 'Heebo', sans-serif; font-size: 0.85rem; padding: 6px 16px;
  border-radius: 50px; cursor: pointer; margin-bottom: 16px;
  transition: border-color 0.2s, color 0.2s;
}
.back-btn:hover { border-color: var(--muted); color: var(--text); }

/* ══════════════════════════════
   ZEHEH ET HADMUT GAME
══════════════════════════════ */
#tzaddik-screen {
  display: none;
  flex-direction: column;
  align-items: center;
  width: 100%;
  min-height: 100vh;
  background-image: radial-gradient(ellipse at 20% 50%,rgba(201,168,76,.07) 0%,transparent 50%),
                    radial-gradient(ellipse at 80% 20%,rgba(201,168,76,.04) 0%,transparent 40%);
  animation: fadeIn 0.4s ease;
}
#tzaddik-screen header {
  text-align: center; padding: 28px 20px 10px; width: 100%;
}
#tzaddik-screen header h1 {
  font-family: 'Secular One', sans-serif;
  font-size: clamp(2rem, 5vw, 3rem);
  color: var(--gold); letter-spacing: 2px;
  text-shadow: 0 0 30px rgba(201,168,76,.4);
  -webkit-text-fill-color: var(--gold);
  background: none;
}
#tzaddik-screen header p { color: rgba(245,234,208,.55); font-size: .9rem; margin-top: 4px; }
.tz-divider { width: 200px; height: 1px; background: linear-gradient(to right,transparent,var(--gold),transparent); margin: 14px auto; }
#tz-game-screen {
  display: flex; flex-direction: column; align-items: center;
  gap: 18px; padding: 16px; width: 100%; max-width: 540px;
}
.level-bar { display: flex; gap: 7px; align-items: center; justify-content: center; }
.level-dot { width: 11px; height: 11px; border-radius: 50%; border: 1.5px solid rgba(201,168,76,.3); transition: all .3s; }
.level-dot.active { background: var(--gold); border-color: var(--gold); box-shadow: 0 0 8px rgba(201,168,76,.6); }
.level-dot.done { background: rgba(201,168,76,.25); border-color: transparent; }
.canvas-wrap { position: relative; border: 2px solid rgba(201,168,76,.3); border-radius: 12px; overflow: hidden; box-shadow: 0 8px 40px rgba(0,0,0,.55); }
#game-canvas { display: block; image-rendering: pixelated; image-rendering: crisp-edges; width: min(460px,92vw); height: min(460px,92vw); }
#offscreen { display: none; }
.tz-badge { position: absolute; top: 10px; left: 10px; background: rgba(26,18,9,.88); border: 1px solid rgba(201,168,76,.3); border-radius: 6px; padding: 3px 10px; font-family: 'Secular One',sans-serif; font-size: .78rem; color: var(--gold); }
.pts-badge { position: absolute; top: 10px; right: 10px; background: rgba(26,18,9,.88); border: 1px solid rgba(201,168,76,.3); border-radius: 6px; padding: 3px 10px; font-family: 'Secular One',sans-serif; font-size: .78rem; color: var(--gold-light); }
.answer-row { display: flex; gap: 10px; width: 100%; }
.tz-input {
  flex: 1; background: rgba(255,255,255,.06); border: 1.5px solid rgba(201,168,76,.28);
  border-radius: 8px; padding: 10px 14px; color: var(--parchment);
  font-family: 'Frank Ruhl Libre',serif; font-size: 1.05rem; outline: none;
  direction: rtl; transition: border-color .2s;
}
.tz-input:focus { border-color: var(--gold); }
.tz-input::placeholder { color: rgba(245,234,208,.3); }
.tz-input.correct { border-color: #4caf50; background: rgba(76,175,80,.1); }
.tz-input.wrong { border-color: var(--red); background: rgba(139,26,26,.1); animation: tzShake .3s; }
@keyframes tzShake { 0%,100%{transform:translateX(0)} 25%{transform:translateX(-6px)} 75%{transform:translateX(6px)} }
.tz-btn {
  font-family: 'Secular One',sans-serif; border: none; border-radius: 8px;
  cursor: pointer; transition: all .2s; font-size: 1rem; padding: 11px 22px; white-space: nowrap;
}
.tz-btn-gold { background: linear-gradient(135deg,var(--gold),var(--gold-light)); color: var(--dark); }
.tz-btn-gold:hover { transform: translateY(-1px); box-shadow: 0 4px 20px rgba(201,168,76,.35); }
.tz-btn-gold:disabled { opacity:.4; cursor:not-allowed; transform:none!important; box-shadow:none!important; }
.tz-btn-outline { background: transparent; border: 1px solid rgba(201,168,76,.35); color: var(--gold); font-size: .9rem; padding: 9px 18px; }
.tz-btn-outline:hover { border-color: var(--gold); background: rgba(201,168,76,.07); }
.tz-btn-outline:disabled { opacity:.35; cursor:not-allowed; }
.tz-feedback { font-family: 'Secular One',sans-serif; font-size: 1rem; text-align: center; min-height: 24px; }
.tz-feedback.ok { color: #6bcf6b; } .tz-feedback.err { color: #e07070; }
.action-row { display: flex; gap: 12px; justify-content: center; }
#tz-result-screen {
  display: none; flex-direction: column; align-items: center;
  gap: 22px; padding: 20px; max-width: 480px; width: 100%;
}
.result-card {
  background: rgba(255,255,255,.04); border: 1px solid rgba(201,168,76,.25);
  border-radius: 14px; padding: 28px; width: 100%; text-align: center;
}
.result-card img { width: 150px; height: 150px; object-fit: cover; border-radius: 10px; border: 2px solid var(--gold); margin: 0 auto 16px; display: block; box-shadow: 0 0 30px rgba(201,168,76,.25); }
.result-card .rname { font-family: 'Secular One',sans-serif; font-size: 1.8rem; color: var(--gold); margin-bottom: 6px; }
.result-card .rverdict { font-size: 1rem; color: rgba(245,234,208,.65); margin-bottom: 16px; }
.score-big { font-family: 'Secular One',sans-serif; font-size: 3rem; color: var(--gold); text-shadow: 0 0 30px rgba(201,168,76,.4); line-height: 1; }
.score-big small { display: block; font-size: .9rem; color: rgba(245,234,208,.55); margin-top: 4px; }

/* confetti */
@keyframes cf { 0%{transform:translateY(0) rotate(0deg);opacity:1} 100%{transform:translateY(120px) rotate(720deg);opacity:0} }
.cf-wrap { position: fixed; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; z-index: 999; }
.cf { position: absolute; width: 8px; height: 8px; animation: cf 1.4s ease-out forwards; }

/* ══════════════════════════════
   SHARED ANIMATIONS
══════════════════════════════ */
@keyframes float { 0%,100%{transform:translateY(0)} 50%{transform:translateY(-10px)} }
@keyframes fadeIn { from{opacity:0;transform:translateY(10px)} to{opacity:1;transform:translateY(0)} }
@keyframes popIn { 0%{transform:scale(0.7);opacity:0} 100%{transform:scale(1);opacity:1} }
@keyframes shake {
  0%,100%{transform:translateX(0)} 20%{transform:translateX(-6px)}
  40%{transform:translateX(6px)} 60%{transform:translateX(-4px)} 80%{transform:translateX(4px)}
}
</style>
</head>
<body>

<!-- ═══ MENU ═══ -->
<div id="menu-screen">
  <div class="menu-emoji">✡️</div>
  <h1>משחקי חסידות</h1>
  <p class="menu-sub">בחר משחק</p>
  <div class="game-cards">
    <div class="game-card card-kesher" onclick="showGame('kesher')">
      <div class="card-emoji">🧠</div>
      <h2>מה הקשר?</h2>
      <p>16 מילים, 4 קבוצות נסתרות — האם תמצא את הקשר?</p>
      <button class="play-btn">בוא נשחק 🎮</button>
    </div>
    <div class="game-card card-tzaddik" onclick="showGame('tzaddik')">
      <div class="card-emoji">🕍</div>
      <h2>זהה את הדמות</h2>
      <p>זהה את הדמות החסידית לפי תמונה מטושטשת</p>
      <button class="play-btn">בוא נשחק 👁</button>
    </div>
  </div>
</div>

<!-- ═══ MA HAKESHER SCREEN ═══ -->
<div id="kesher-screen">
  <button class="back-btn" onclick="backToMenu()">← חזור לתפריט</button>
  <header>
    <h1>מה הקשר?</h1>
    <p class="subtitle">מצא את ארבע הקבוצות המסתתרות בין 16 המילים</p>
  </header>
  <div id="kesher-game-area">
    <div id="solved-groups"></div>
    <div id="grid"></div>
    <div id="k-message"></div>
    <div class="actions">
      <button class="btn btn-ghost" id="btn-shuffle">ערבב</button>
      <button class="btn btn-ghost" id="btn-clear">נקה בחירה</button>
      <button class="btn btn-primary" id="btn-guess" disabled>נחש!</button>
    </div>
    <div class="actions">
      <button class="btn btn-ghost" id="btn-restart">🔄 התחל מחדש</button>
    </div>
    <div id="kesher-win-screen">
      <h2>🎉 כל הכבוד!</h2>
      <p id="k-win-msg"></p>
      <button class="btn btn-primary" id="btn-play-again">שחק שוב</button>
      <div class="promo-banner" id="kesher-promo">
        <p>רוצה לשחק גם את <strong>זהה את הדמות</strong>? 🕍</p>
        <button class="play-btn" style="background:linear-gradient(135deg,var(--gold),var(--gold-light));color:#1a1209" onclick="showGame('tzaddik')">בוא נשחק 👁</button>
      </div>
    </div>
  </div>
</div>

<!-- ═══ ZEHEH ET HADMUT SCREEN ═══ -->
<div id="tzaddik-screen">
  <button class="back-btn" style="margin-top:16px" onclick="backToMenu()">← חזור לתפריט</button>
  <header>
    <h1>🕍 זהה את הדמות</h1>
    <p>זהה את הדמות לפי תמונה מטושטשת</p>
    <div class="tz-divider"></div>
  </header>
  <div id="tz-game-screen">
    <div class="level-bar" id="level-bar"></div>
    <div class="canvas-wrap">
      <canvas id="game-canvas" style="position:relative;z-index:2;transition:opacity 0.6s ease;"></canvas>
      <canvas id="game-canvas-prev" style="position:absolute;top:0;left:0;z-index:1;width:min(460px,92vw);height:min(460px,92vw);image-rendering:pixelated;image-rendering:crisp-edges;display:block;"></canvas>
      <canvas id="offscreen"></canvas>
      <div class="tz-badge" id="lvl-badge">רמה 1</div>
      <div class="pts-badge" id="pts-badge">60 נק׳</div>
    </div>
    <div class="answer-row">
      <input type="text" class="tz-input" id="guess-input" placeholder="מי זה...?" autocomplete="off"
        onkeydown="if(event.key==='Enter') tzCheckGuess()" />
      <button class="tz-btn tz-btn-gold" onclick="tzCheckGuess()">✓</button>
    </div>
    <div class="tz-feedback" id="tz-feedback"></div>
    <div class="action-row">
      <button class="tz-btn tz-btn-outline" id="reveal-btn" onclick="tzNextLevel()">גלה יותר 👁</button>
      <button class="tz-btn tz-btn-outline" onclick="tzGiveUp()">מתייאש 🏳</button>
    </div>
  </div>
  <div id="tz-result-screen">
    <div class="result-card">
      <img id="result-img" />
      <div class="rname" id="result-name"></div>
      <div class="rverdict" id="result-verdict"></div>
      <div class="score-big" id="result-score">0<small>נקודות</small></div>
    </div>
    <div class="promo-banner" id="tzaddik-promo">
      <p>רוצה לשחק גם את <strong>מה הקשר?</strong> 🧠</p>
      <button class="play-btn" style="background:linear-gradient(135deg,var(--c1),var(--c3));color:white" onclick="showGame('kesher')">בוא נשחק 🎮</button>
    </div>
  </div>
</div>

<div class="cf-wrap" id="cf-wrap"></div>

<script>
/* ══════════════════════════════
   NAVIGATION
══════════════════════════════ */
function showGame(game) {
  document.getElementById('menu-screen').style.display = 'none';
  document.getElementById('kesher-screen').style.display = 'none';
  document.getElementById('tzaddik-screen').style.display = 'none';
  document.getElementById('kesher-promo').classList.remove('visible');
  document.getElementById('tzaddik-promo').classList.remove('visible');

  if (game === 'kesher') {
    document.getElementById('kesher-screen').style.display = 'flex';
    gtag('event', 'game_start', { game_name: 'מה הקשר' });
    kInit();
  } else {
    document.getElementById('tzaddik-screen').style.display = 'flex';
    gtag('event', 'game_start', { game_name: 'זהה את הדמות' });
    tzStartGame();
  }
}

function backToMenu() {
  document.getElementById('kesher-screen').style.display = 'none';
  document.getElementById('tzaddik-screen').style.display = 'none';
  document.getElementById('menu-screen').style.display = 'flex';
}

/* ══════════════════════════════
   MA HAKESHER LOGIC
══════════════════════════════ */
const PALETTE = ['#ff8906','#3da9fc','#ef4565','#44cf6c','#f3d060','#9b5de5','#f15bb5','#00bbf9'];
const DEFAULT_GROUPS = [
  { name: 'מ׳דארף', color: '#ff8906', words: ['תשובה טאן','לעבן מיט דער צייט','וויסן וואו מ׳שטייט...','גיין לכתחילה אריבער'] },
  { name: 'א חסידישע', color: '#3da9fc', words: ['פארבריינגען','גניבה','חלומות','פרשה'] },
  { name: 'ניגונים בעלי מקצב של 3/4 פעימות', color: '#ef4565', words: ['שאמיל','הכנה למאמר','עסן עסט זיך','אבינו מלכנו'] },
  { name: 'ניגונים שחסידים התאימו להם מילים', color: '#44cf6c', words: ['ופרצת','הרבי שליט״א','אימתי קאתי מר','כתיבה וחתימה טובה'] },
];
let kGroups = JSON.parse(JSON.stringify(DEFAULT_GROUPS));
let kTiles = [], kSelected = new Set(), kMistakes = 0, kSolvedGroups = [];
const MAX_MISTAKES = 4;

function kShuffle(arr) {
  const a = [...arr];
  for (let i = a.length-1; i > 0; i--) {
    const j = Math.floor(Math.random()*(i+1));
    [a[i],a[j]] = [a[j],a[i]];
  }
  return a;
}

function kInit() {
  kMistakes = 0; kSolvedGroups = []; kSelected.clear();
  document.getElementById('solved-groups').innerHTML = '';
  document.getElementById('kesher-win-screen').style.display = 'none';
  document.getElementById('kesher-promo').classList.remove('visible');
  document.getElementById('grid').style.display = 'grid';
  document.querySelectorAll('#kesher-screen .actions').forEach(a => a.style.display = 'flex');
  document.getElementById('k-message').textContent = '';
  kTiles = kShuffle(kGroups.flatMap(g => g.words.map(w => ({ word: w, group: g.name }))));
  kRenderGrid();
}

function kRenderGrid() {
  const grid = document.getElementById('grid');
  grid.innerHTML = '';
  kTiles.forEach((t, i) => {
    const div = document.createElement('div');
    div.className = 'word-tile' + (kSelected.has(i) ? ' selected' : '');
    div.textContent = t.word;
    div.dataset.index = i;
    div.addEventListener('click', () => kToggle(i, div));
    grid.appendChild(div);
  });
  document.getElementById('btn-guess').disabled = kSelected.size !== 4;
}

function kToggle(i, el) {
  if (kSelected.has(i)) { kSelected.delete(i); el.classList.remove('selected'); }
  else { if (kSelected.size >= 4) return; kSelected.add(i); el.classList.add('selected'); }
  document.getElementById('btn-guess').disabled = kSelected.size !== 4;
}

function kGuess() {
  const indices = [...kSelected];
  const groupNames = indices.map(i => kTiles[i].group);
  const allSame = groupNames.every(g => g === groupNames[0]);
  if (allSame) {
    const gData = kGroups.find(g => g.name === groupNames[0]);
    kShowMsg('✅ נכון! ' + gData.name, gData.color);
    indices.forEach(i => { const el = document.querySelector(`.word-tile[data-index="${i}"]`); if(el) el.classList.add('correct-pop'); });
    setTimeout(() => {
      kSolvedGroups.push(gData);
      kTiles = kTiles.filter((_,i) => !kSelected.has(i));
      kSelected.clear();
      kRenderSolved(gData);
      kRenderGrid();
      if (kSolvedGroups.length === kGroups.length) kShowWin();
    }, 400);
  } else {
    kMistakes++;
    const counts = {};
    groupNames.forEach(g => counts[g] = (counts[g]||0)+1);
    const maxCount = Math.max(...Object.values(counts));
    kShowMsg(maxCount === 3 ? '😬 כמעט! פספסת בקושי אחד' : '❌ לא נכון, נסה שוב', '#ef4565');
    indices.forEach(i => { const el = document.querySelector(`.word-tile[data-index="${i}"]`); if(el){el.classList.remove('wrong-shake');void el.offsetWidth;el.classList.add('wrong-shake');} });
    kSelected.clear();
    setTimeout(() => { document.querySelectorAll('.word-tile').forEach(el => el.classList.remove('selected','wrong-shake')); document.getElementById('btn-guess').disabled = true; }, 450);
  }
}

function kShowMsg(msg, color) {
  const el = document.getElementById('k-message');
  el.textContent = msg; el.style.color = color || 'var(--selected)';
  clearTimeout(el._t); el._t = setTimeout(() => el.textContent = '', 3000);
}

function kRenderSolved(g) {
  const container = document.getElementById('solved-groups');
  const card = document.createElement('div');
  card.className = 'solved-card';
  card.style.background = g.color + '22';
  card.style.border = '2px solid ' + g.color;
  card.innerHTML = `<div class="cat-name" style="color:${g.color}">${g.name}</div><div class="cat-words">${g.words.join(' • ')}</div>`;
  container.appendChild(card);
}

function kShowWin() {
  const txt = kMistakes === 0 ? 'ללא טעויות! מדהים 🏆' : `עם ${kMistakes} טעות${kMistakes > 1 ? 'יות' : ''}`;
  document.getElementById('k-win-msg').textContent = 'סיימת את המשחק ' + txt;
  document.getElementById('kesher-win-screen').style.display = 'block';
  document.getElementById('grid').style.display = 'none';
  document.querySelectorAll('#kesher-screen .actions').forEach(a => a.style.display = 'none');
  gtag('event', 'game_complete', { game_name: 'מה הקשר', mistakes: kMistakes });
  setTimeout(() => document.getElementById('kesher-promo').classList.add('visible'), 600);
}

document.getElementById('btn-shuffle').addEventListener('click', () => { kTiles = kShuffle(kTiles); kSelected.clear(); kRenderGrid(); });
document.getElementById('btn-clear').addEventListener('click', () => { kSelected.clear(); kRenderGrid(); });
document.getElementById('btn-guess').addEventListener('click', kGuess);
document.getElementById('btn-restart').addEventListener('click', kInit);
document.getElementById('btn-play-again').addEventListener('click', kInit);

/* ══════════════════════════════
   ZEHEH ET HADMUT LOGIC
══════════════════════════════ */
const TZ_IMG = 'data:image/png;base64,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';
const TZ_ANSWER = "ר' מאיר הארליג";
const TZ_ALIASES = ["מאירהארליג","מאירהרליג","הארליג","הרליג"];
const PIXEL_SIZES = [20,14,10,7,4,1];
const POINTS = [60,45,30,20,10,5];
const TZ_LEVELS = 6;
let tzLevel = 0, tzPoints = 0, tzSolved = false;

function tzNorm(s) { return s.replace(/[״׳"'\-\s]/g,'').toLowerCase(); }
function tzIsCorrect(val) {
  const n = tzNorm(val);
  if (n === tzNorm(TZ_ANSWER)) return true;
  return TZ_ALIASES.some(a => n === a);
}

function tzStartGame() {
  tzLevel = 0; tzPoints = 0; tzSolved = false;
  document.getElementById('tz-result-screen').style.display = 'none';
  document.getElementById('tzaddik-promo').classList.remove('visible');
  document.getElementById('tz-game-screen').style.display = 'flex';
  document.getElementById('tz-feedback').textContent = '';
  document.getElementById('tz-feedback').className = 'tz-feedback';
  document.getElementById('guess-input').value = '';
  document.getElementById('guess-input').className = 'tz-input';
  const bar = document.getElementById('level-bar');
  bar.innerHTML = PIXEL_SIZES.map((_,i) => `<div class="level-dot" id="dot-${i}"></div>`).join('');
  tzLoadOffscreen().then(() => tzRenderPixel());
}

function tzLoadOffscreen() {
  return new Promise(resolve => {
    const img = new Image();
    img.onload = () => {
      const off = document.getElementById('offscreen');
      const SZ = 460; off.width = SZ; off.height = SZ;
      const ctx = off.getContext('2d');
      const ar = img.width/img.height;
      let sw=SZ,sh=SZ,sx=0,sy=0;
      if(ar>1){sh=SZ/ar;sy=(SZ-sh)/2;}else{sw=SZ*ar;sx=(SZ-sw)/2;}
      ctx.fillStyle='#1a1209'; ctx.fillRect(0,0,SZ,SZ);
      ctx.drawImage(img,sx,sy,sw,sh);
      resolve();
    };
    img.src = TZ_IMG;
  });
}

function tzDrawToCanvas(canvas, level) {
  const off = document.getElementById('offscreen');
  const SZ = 460, block = PIXEL_SIZES[level];
  canvas.width = SZ; canvas.height = SZ;
  const ctx = canvas.getContext('2d');
  ctx.imageSmoothingEnabled = false;
  if (block === 1) { ctx.drawImage(off,0,0); }
  else {
    const small = Math.ceil(SZ/block);
    const tmp = document.createElement('canvas');
    tmp.width = small; tmp.height = small;
    tmp.getContext('2d').drawImage(off,0,0,small,small);
    ctx.drawImage(tmp,0,0,SZ,SZ);
  }
}

function tzRenderPixel() {
  const gc = document.getElementById('game-canvas');
  const prev = document.getElementById('game-canvas-prev');

  // Copy current to prev
  if (prev) {
    prev.width = gc.width || 460;
    prev.height = gc.height || 460;
    const pctx = prev.getContext('2d');
    pctx.drawImage(gc, 0, 0);
  }

  // Draw new frame on main canvas (hidden)
  gc.style.opacity = '0';
  tzDrawToCanvas(gc, tzLevel);

  // Fade in
  requestAnimationFrame(() => {
    gc.style.transition = 'opacity 0.7s ease';
    gc.style.opacity = '1';
  });

  for (let i=0;i<TZ_LEVELS;i++) {
    const d = document.getElementById(`dot-${i}`);
    if(!d) continue;
    d.className = 'level-dot'+(i<tzLevel?' done':i===tzLevel?' active':'');
  }
  document.getElementById('lvl-badge').textContent = `רמה ${tzLevel+1}`;
  document.getElementById('pts-badge').textContent = `${POINTS[tzLevel]} נק׳`;
  document.getElementById('reveal-btn').disabled = tzLevel >= TZ_LEVELS-1;
}

function tzCheckGuess() {
  const inp = document.getElementById('guess-input');
  const val = inp.value.trim(); if(!val) return;
  if (tzIsCorrect(val)) {
    tzPoints = POINTS[tzLevel]; tzSolved = true;
    inp.className = 'tz-input correct';
    tzSetFb(`✅ כל הכבוד! +${tzPoints} נקודות`,'ok');
    tzConfetti(22);
    setTimeout(() => tzShowResult(), 1500);
  } else {
    inp.className = 'tz-input wrong';
    tzSetFb('❌ לא נכון, נסה שוב','err');
    setTimeout(() => { inp.className = 'tz-input'; }, 600);
  }
}

function tzSetFb(msg,cls) { const el=document.getElementById('tz-feedback'); el.textContent=msg; el.className='tz-feedback '+cls; }

function tzNextLevel() {
  if (tzLevel < TZ_LEVELS-1) { tzLevel++; tzRenderPixel(); tzSetFb(`💡 רמה ${tzLevel+1} — ${POINTS[tzLevel]} נק׳ אפשריות`,''); }
}

function tzGiveUp() { tzSolved=false; tzPoints=0; tzShowResult(); }

function tzShowResult() {
  document.getElementById('tz-game-screen').style.display = 'none';
  document.getElementById('tz-result-screen').style.display = 'flex';
  document.getElementById('result-img').src = TZ_IMG;
  document.getElementById('result-name').textContent = TZ_ANSWER;
  if (tzSolved) {
    document.getElementById('result-verdict').textContent = `ניחשת ברמה ${tzLevel+1} 🎉`;
    document.getElementById('result-score').innerHTML = `${tzPoints}<small>נקודות</small>`;
    gtag('event', 'game_complete', { game_name: 'זהה את הדמות', solved: true, level: tzLevel+1, points: tzPoints });
  } else {
    document.getElementById('result-verdict').textContent = 'לא ניחשת הפעם 😔';
    document.getElementById('result-score').innerHTML = `0<small>נקודות</small>`;
    gtag('event', 'game_complete', { game_name: 'זהה את הדמות', solved: false, level: tzLevel+1, points: 0 });
  }
  setTimeout(() => document.getElementById('tzaddik-promo').classList.add('visible'), 600);
}

function tzConfetti(n) {
  const wrap = document.getElementById('cf-wrap');
  const colors = ['#c9a84c','#f0d080','#fff','#e8a020','#ffd700'];
  for (let i=0;i<n;i++) {
    const el = document.createElement('div'); el.className='cf';
    el.style.cssText=`left:${Math.random()*100}%;top:${Math.random()*30}%;background:${colors[Math.floor(Math.random()*colors.length)]};border-radius:${Math.random()>.5?'50%':'2px'};animation-delay:${Math.random()*.5}s;animation-duration:${1.2+Math.random()*.6}s;`;
    wrap.appendChild(el);
    el.addEventListener('animationend', () => el.remove());
  }
}
</script>
</body>
</html>
