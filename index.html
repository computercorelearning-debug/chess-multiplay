<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>♛ Chess Arena</title>
<script src="https://unpkg.com/peerjs@1.5.4/dist/peerjs.min.js"></script>
<style>
  :root {
    --bg: #0f0f13;
    --bg2: #1a1a24;
    --glass: rgba(255,255,255,0.06);
    --glass-border: rgba(255,255,255,0.12);
    --text: #e8e8f0;
    --text-muted: #9a9ab0;
    --accent: #7c5cff;
    --accent2: #00d4aa;
    --danger: #ff5c7a;
    --warning: #ffb84d;
    --board-light: #e8d5b5;
    --board-dark: #b58863;
    --highlight: rgba(124,92,255,0.45);
    --lastmove: rgba(0,212,170,0.35);
    --check: rgba(255,92,122,0.55);
    --legal: rgba(0,0,0,0.25);
    --shadow: 0 8px 32px rgba(0,0,0,0.4);
    --radius: 16px;
    --font: 'Segoe UI', system-ui, -apple-system, sans-serif;
  }
  [data-theme="light"] {
    --bg: #f0f2f5;
    --bg2: #ffffff;
    --glass: rgba(255,255,255,0.7);
    --glass-border: rgba(0,0,0,0.08);
    --text: #1a1a24;
    --text-muted: #5a5a70;
    --board-light: #f0d9b5;
    --board-dark: #b58863;
    --shadow: 0 8px 32px rgba(0,0,0,0.12);
  }
  * { box-sizing: border-box; margin: 0; padding: 0; }
  html, body {
    height: 100%;
    font-family: var(--font);
    background: var(--bg);
    color: var(--text);
    overflow-x: hidden;
    -webkit-tap-highlight-color: transparent;
  }
  body {
    background:
      radial-gradient(ellipse at 20% 20%, rgba(124,92,255,0.15) 0%, transparent 50%),
      radial-gradient(ellipse at 80% 80%, rgba(0,212,170,0.1) 0%, transparent 50%),
      var(--bg);
    min-height: 100dvh;
  }
  .screen { display: none; min-height: 100dvh; padding: 16px; }
  .screen.active { display: flex; flex-direction: column; align-items: center; justify-content: center; }
  #homeScreen { gap: 28px; }
  .logo {
    font-size: clamp(2.2rem, 8vw, 3.5rem);
    font-weight: 800;
    letter-spacing: -1px;
    background: linear-gradient(135deg, #fff 0%, var(--accent) 50%, var(--accent2) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    text-align: center;
  }
  .logo span { display: block; font-size: 0.35em; font-weight: 500; letter-spacing: 4px; opacity: 0.7; margin-top: 4px; -webkit-text-fill-color: var(--text-muted); }
  .menu-btns { display: flex; flex-direction: column; gap: 12px; width: min(320px, 90vw); }
  .btn {
    background: var(--glass);
    border: 1px solid var(--glass-border);
    color: var(--text);
    padding: 14px 20px;
    border-radius: 12px;
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    backdrop-filter: blur(12px);
    transition: all 0.2s;
    display: flex; align-items: center; justify-content: center; gap: 10px;
  }
  .btn:hover { background: rgba(124,92,255,0.2); border-color: var(--accent); transform: translateY(-2px); }
  .btn:active { transform: scale(0.98); }
  .btn.primary { background: linear-gradient(135deg, var(--accent), #5a3fd4); border: none; color: #fff; }
  .btn.primary:hover { filter: brightness(1.1); }
  .btn.danger { background: rgba(255,92,122,0.15); border-color: var(--danger); color: var(--danger); }
  .btn.small { padding: 8px 14px; font-size: 0.85rem; }
  .btn:disabled { opacity: 0.45; pointer-events: none; }
  .panel {
    background: var(--glass);
    border: 1px solid var(--glass-border);
    border-radius: var(--radius);
    padding: 24px;
    backdrop-filter: blur(20px);
    box-shadow: var(--shadow);
    width: min(400px, 94vw);
    max-height: 90dvh;
    overflow-y: auto;
  }
  .panel h2 { font-size: 1.3rem; margin-bottom: 16px; text-align: center; }
  .form-group { margin-bottom: 14px; }
  .form-group label { display: block; font-size: 0.8rem; color: var(--text-muted); margin-bottom: 6px; }
  .form-group input, .form-group select {
    width: 100%;
    padding: 11px 14px;
    border-radius: 10px;
    border: 1px solid var(--glass-border);
    background: rgba(0,0,0,0.25);
    color: var(--text);
    font-size: 1rem;
  }
  [data-theme="light"] .form-group input,
  [data-theme="light"] .form-group select { background: rgba(255,255,255,0.8); }
  .form-group input:focus, .form-group select:focus { outline: 2px solid var(--accent); }
  .row { display: flex; gap: 10px; flex-wrap: wrap; }
  .row > * { flex: 1; min-width: 120px; }
  .hint { font-size: 0.78rem; color: var(--text-muted); margin-top: 8px; line-height: 1.4; }
  .code-display {
    background: rgba(0,0,0,0.35);
    border: 2px solid var(--accent);
    border-radius: 12px;
    padding: 16px;
    font-size: 2rem;
    font-weight: 800;
    letter-spacing: 6px;
    text-align: center;
    margin: 12px 0;
    color: var(--accent2);
    user-select: all;
  }
  .status-dot {
    width: 10px; height: 10px; border-radius: 50%;
    display: inline-block; margin-right: 6px;
  }
  .status-dot.online { background: var(--accent2); box-shadow: 0 0 8px var(--accent2); }
  .status-dot.offline { background: var(--danger); }
  .status-dot.connecting { background: var(--warning); animation: pulse 1s infinite; }
  @keyframes pulse { 50% { opacity: 0.4; } }
  #gameScreen {
    display: none;
    flex-direction: column;
    align-items: center;
    padding: 8px;
    gap: 8px;
    min-height: 100dvh;
  }
  #gameScreen.active { display: flex; }
  .game-header {
    width: min(560px, 100%);
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 8px 12px;
    background: var(--glass);
    border: 1px solid var(--glass-border);
    border-radius: 12px;
    backdrop-filter: blur(12px);
  }
  .player-info { display: flex; flex-direction: column; gap: 2px; }
  .player-name { font-weight: 700; font-size: 0.95rem; }
  .player-clock {
    font-family: ui-monospace, monospace;
    font-size: 1.15rem;
    font-weight: 600;
    color: var(--accent2);
  }
  .player-clock.low { color: var(--danger); animation: pulse 0.8s infinite; }
  .turn-badge {
    background: var(--accent);
    color: #fff;
    font-size: 0.7rem;
    padding: 3px 8px;
    border-radius: 20px;
    font-weight: 600;
  }
  .captured { font-size: 0.85rem; letter-spacing: -1px; min-height: 1.2em; opacity: 0.85; }
  .board-wrap {
    position: relative;
    width: min(560px, 96vw, 96dvh - 220px);
    aspect-ratio: 1;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: var(--shadow), 0 0 0 1px var(--glass-border);
  }
  #board {
    display: grid;
    grid-template-columns: repeat(8, 1fr);
    grid-template-rows: repeat(8, 1fr);
    width: 100%;
    height: 100%;
    user-select: none;
  }
  .sq {
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: clamp(1.8rem, 7vw, 3.2rem);
    cursor: pointer;
    position: relative;
  }
  .sq.light { background: var(--board-light); }
  .sq.dark { background: var(--board-dark); }
  .sq.highlight { background: var(--highlight) !important; }
  .sq.lastmove { box-shadow: inset 0 0 0 999px var(--lastmove); }
  .sq.check { box-shadow: inset 0 0 0 999px var(--check); }
  .sq .legal-dot {
    width: 28%; height: 28%;
    border-radius: 50%;
    background: var(--legal);
    position: absolute;
  }
  .sq .legal-cap {
    width: 100%; height: 100%;
    border-radius: 50%;
    box-shadow: inset 0 0 0 4px rgba(0,0,0,0.3);
    position: absolute;
  }
  .piece {
    z-index: 2;
    line-height: 1;
    filter: drop-shadow(0 2px 3px rgba(0,0,0,0.35));
  }
  .game-footer {
    width: min(560px, 100%);
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    justify-content: center;
  }
  .side-panel {
    width: min(560px, 100%);
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 8px;
  }
  @media (max-width: 500px) {
    .side-panel { grid-template-columns: 1fr; }
  }
  .moves-box, .chat-box {
    background: var(--glass);
    border: 1px solid var(--glass-border);
    border-radius: 12px;
    padding: 10px;
    max-height: 140px;
    overflow-y: auto;
    font-size: 0.8rem;
    backdrop-filter: blur(10px);
  }
  .moves-box { font-family: ui-monospace, monospace; }
  .chat-messages { max-height: 90px; overflow-y: auto; margin-bottom: 6px; }
  .chat-msg { margin-bottom: 4px; }
  .chat-msg .who { font-weight: 600; color: var(--accent); }
  .chat-input-row { display: flex; gap: 6px; }
  .chat-input-row input {
    flex: 1; padding: 7px 10px; border-radius: 8px;
    border: 1px solid var(--glass-border); background: rgba(0,0,0,0.25); color: var(--text);
  }
  .promo-overlay {
    position: fixed; inset: 0;
    background: rgba(0,0,0,0.6);
    display: none; align-items: center; justify-content: center;
    z-index: 100;
  }
  .promo-overlay.show { display: flex; }
  .promo-choices {
    display: flex; gap: 8px;
    background: var(--bg2);
    padding: 16px;
    border-radius: 16px;
    border: 1px solid var(--glass-border);
  }
  .promo-choices button {
    font-size: 2.5rem;
    background: var(--glass);
    border: 1px solid var(--glass-border);
    border-radius: 12px;
    padding: 8px 14px;
    cursor: pointer;
    color: var(--text);
  }
  .result-overlay {
    position: fixed; inset: 0;
    background: rgba(0,0,0,0.7);
    display: none; align-items: center; justify-content: center;
    z-index: 110;
    backdrop-filter: blur(6px);
  }
  .result-overlay.show { display: flex; }
  .result-card {
    background: var(--bg2);
    border: 1px solid var(--glass-border);
    border-radius: 20px;
    padding: 28px;
    text-align: center;
    max-width: 340px;
    width: 90%;
  }
  .result-card h2 { font-size: 1.6rem; margin-bottom: 8px; }
  .result-card p { color: var(--text-muted); margin-bottom: 18px; }
  .theme-toggle {
    position: fixed; top: 12px; right: 12px;
    width: 42px; height: 42px;
    border-radius: 50%;
    background: var(--glass);
    border: 1px solid var(--glass-border);
    color: var(--text);
    font-size: 1.2rem;
    cursor: pointer;
    z-index: 50;
    display: flex; align-items: center; justify-content: center;
    backdrop-filter: blur(10px);
  }
  .back-btn { position: fixed; top: 12px; left: 12px; z-index: 50; }
  .conn-status { font-size: 0.8rem; display: flex; align-items: center; gap: 4px; }
</style>
</head>
<body>

<button class="theme-toggle" id="themeBtn" title="Toggle theme">🌙</button>

<!-- HOME -->
<div id="homeScreen" class="screen active">
  <div class="logo">♛ CHESS ARENA<span>ONLINE & LOCAL</span></div>
  <div class="menu-btns">
    <button class="btn primary" onclick="showScreen('botSetup')">🤖 Play vs Bot</button>
    <button class="btn" onclick="showScreen('createRoom')">🌐 Create Room</button>
    <button class="btn" onclick="showScreen('joinRoom')">🔗 Join Room</button>
    <button class="btn" onclick="startLocal()">👥 Local 2 Player</button>
    <button class="btn" onclick="showScreen('settings')">⚙️ Settings</button>
  </div>
</div>

<!-- BOT SETUP -->
<div id="botSetup" class="screen">
  <div class="panel">
    <h2>🤖 Play vs Bot</h2>
    <div class="form-group">
      <label>Your Name</label>
      <input id="botName" value="Player" maxlength="16">
    </div>
    <div class="form-group">
      <label>Difficulty</label>
      <select id="botDiff">
        <option value="easy">Easy</option>
        <option value="medium" selected>Medium</option>
        <option value="hard">Hard</option>
      </select>
    </div>
    <div class="form-group">
      <label>Time Control</label>
      <select id="botTime">
        <option value="0">Unlimited</option>
        <option value="60">1 min</option>
        <option value="180">3 min</option>
        <option value="300" selected>5 min</option>
        <option value="600">10 min</option>
      </select>
    </div>
    <div class="form-group">
      <label>Play as</label>
      <select id="botColor">
        <option value="w">White</option>
        <option value="b">Black</option>
        <option value="random">Random</option>
      </select>
    </div>
    <div class="row">
      <button class="btn" onclick="showScreen('homeScreen')">Back</button>
      <button class="btn primary" onclick="startBotGame()">Start</button>
    </div>
  </div>
</div>

<!-- CREATE ROOM -->
<div id="createRoom" class="screen">
  <div class="panel">
    <h2>🌐 Create Room</h2>
    <p class="hint" style="margin-bottom:14px;">
      You will get a short code (example: <strong>K7P2X9</strong>).<br>
      Just tell this code to your friend.
    </p>
    <div class="form-group">
      <label>Your Name</label>
      <input id="hostName" value="Host" maxlength="16">
    </div>
    <div class="form-group">
      <label>Optional Password</label>
      <input id="hostPass" type="password" placeholder="Leave empty for none">
    </div>
    <div class="form-group">
      <label>Time Control</label>
      <select id="hostTime">
        <option value="0">Unlimited</option>
        <option value="60">1 min</option>
        <option value="180">3 min</option>
        <option value="300" selected>5 min</option>
        <option value="600">10 min</option>
      </select>
    </div>
    <div class="row">
      <button class="btn" onclick="showScreen('homeScreen')">Back</button>
      <button class="btn primary" id="createRoomBtn" onclick="createRoom()">Create Room</button>
    </div>
    <div id="hostCodeArea" style="display:none;margin-top:18px;">
      <label>Your Room Code (tell this to your friend):</label>
      <div class="code-display" id="roomCodeDisplay">------</div>
      <button class="btn small" onclick="copyRoomCode()">📋 Copy Code</button>
      <div class="conn-status" id="hostStatus" style="margin-top:12px;">
        <span class="status-dot connecting"></span> Waiting for opponent...
      </div>
    </div>
  </div>
</div>

<!-- JOIN ROOM -->
<div id="joinRoom" class="screen">
  <div class="panel">
    <h2>🔗 Join Room</h2>
    <p class="hint" style="margin-bottom:14px;">
      Enter the short code your friend told you.
    </p>
    <div class="form-group">
      <label>Your Name</label>
      <input id="guestName" value="Guest" maxlength="16">
    </div>
    <div class="form-group">
      <label>Room Code</label>
      <input id="joinCode" placeholder="e.g. K7P2X9" maxlength="10" style="text-transform:uppercase; letter-spacing:3px; font-weight:700;">
    </div>
    <div class="form-group">
      <label>Password (if required)</label>
      <input id="guestPass" type="password" placeholder="Optional">
    </div>
    <div class="row">
      <button class="btn" onclick="showScreen('homeScreen')">Back</button>
      <button class="btn primary" onclick="joinRoom()">Join Room</button>
    </div>
    <div class="conn-status" id="guestStatus" style="margin-top:14px;display:none;">
      <span class="status-dot connecting"></span> Connecting...
    </div>
  </div>
</div>

<!-- SETTINGS -->
<div id="settings" class="screen">
  <div class="panel">
    <h2>⚙️ Settings</h2>
    <div class="form-group">
      <label>Theme</label>
      <button class="btn" onclick="toggleTheme()">Toggle Dark / Light</button>
    </div>
    <div class="form-group">
      <label>Board Orientation (Local / Bot)</label>
      <select id="orientPref">
        <option value="white">White at bottom</option>
        <option value="black">Black at bottom</option>
      </select>
    </div>
    <button class="btn" onclick="showScreen('homeScreen')" style="margin-top:12px;width:100%;">Back</button>
  </div>
</div>

<!-- GAME -->
<div id="gameScreen">
  <button class="btn small back-btn" onclick="confirmLeave()">← Menu</button>

  <div class="game-header" id="topPlayer">
    <div class="player-info">
      <div class="player-name" id="topName">Opponent</div>
      <div class="captured" id="topCaptured"></div>
    </div>
    <div style="text-align:right;">
      <div class="player-clock" id="topClock">--:--</div>
      <div class="turn-badge" id="topTurn" style="display:none;">TURN</div>
    </div>
  </div>

  <div class="board-wrap">
    <div id="board"></div>
  </div>

  <div class="game-header" id="botPlayer">
    <div class="player-info">
      <div class="player-name" id="botNameDisp">You</div>
      <div class="captured" id="botCaptured"></div>
    </div>
    <div style="text-align:right;">
      <div class="player-clock" id="botClock">--:--</div>
      <div class="turn-badge" id="botTurn" style="display:none;">TURN</div>
    </div>
  </div>

  <div class="game-footer">
    <button class="btn small" onclick="offerDraw()">🤝 Draw</button>
    <button class="btn small danger" onclick="resign()">🏳️ Resign</button>
    <button class="btn small" id="rematchBtn" style="display:none;" onclick="rematch()">🔄 Rematch</button>
    <span class="conn-status" id="mpStatus" style="display:none;">
      <span class="status-dot"></span><span id="mpStatusText"></span>
    </span>
  </div>

  <div class="side-panel">
    <div class="moves-box" id="movesList"><strong>Moves</strong><div id="movesContent"></div></div>
    <div class="chat-box" id="chatBox" style="display:none;">
      <div class="chat-messages" id="chatMessages"></div>
      <div class="chat-input-row">
        <input id="chatInput" placeholder="Chat..." maxlength="120" onkeydown="if(event.key==='Enter')sendChat()">
        <button class="btn small" onclick="sendChat()">Send</button>
      </div>
    </div>
  </div>
</div>

<!-- Promotion -->
<div class="promo-overlay" id="promoOverlay">
  <div class="promo-choices" id="promoChoices"></div>
</div>

<!-- Result -->
<div class="result-overlay" id="resultOverlay">
  <div class="result-card">
    <h2 id="resultTitle">Game Over</h2>
    <p id="resultMsg"></p>
    <div class="row">
      <button class="btn" onclick="hideResult();confirmLeave();">Menu</button>
      <button class="btn primary" id="resultRematch" onclick="rematch()">Rematch</button>
    </div>
  </div>
</div>

<script>
/* ============================================================
   CHESS ARENA – Short room codes with PeerJS
   ============================================================ */

const themeBtn = document.getElementById('themeBtn');
function toggleTheme() {
  const html = document.documentElement;
  const next = html.getAttribute('data-theme') === 'light' ? 'dark' : 'light';
  html.setAttribute('data-theme', next === 'light' ? 'light' : '');
  themeBtn.textContent = next === 'light' ? '☀️' : '🌙';
  localStorage.setItem('chessTheme', next);
}
(function() {
  const t = localStorage.getItem('chessTheme') || 'dark';
  if (t === 'light') { document.documentElement.setAttribute('data-theme', 'light'); themeBtn.textContent = '☀️'; }
})();

function showScreen(id) {
  document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
  document.getElementById('gameScreen').classList.remove('active');
  const el = document.getElementById(id);
  if (el) el.classList.add('active');
}

/* ---------- CHESS ENGINE (same as before) ---------- */
const PIECES = {
  K: '♔', Q: '♕', R: '♖', B: '♗', N: '♘', P: '♙',
  k: '♚', q: '♛', r: '♜', b: '♝', n: '♞', p: '♟'
};
const FILES = 'abcdefgh';

function emptyBoard() { return Array(8).fill(null).map(() => Array(8).fill(null)); }
function cloneBoard(b) { return b.map(r => r.slice()); }
function posToAlg(r, c) { return FILES[c] + (8 - r); }
function inBounds(r, c) { return r >= 0 && r < 8 && c >= 0 && c < 8; }
function isWhite(p) { return p && p === p.toUpperCase(); }
function isBlack(p) { return p && p === p.toLowerCase(); }
function sameColor(a, b) { if (!a || !b) return false; return isWhite(a) === isWhite(b); }

function findKing(board, white) {
  const k = white ? 'K' : 'k';
  for (let r = 0; r < 8; r++)
    for (let c = 0; c < 8; c++)
      if (board[r][c] === k) return [r, c];
  return null;
}

function isAttacked(board, r, c, byWhite) {
  const pr = byWhite ? r + 1 : r - 1;
  for (const cc of [c - 1, c + 1]) {
    if (inBounds(pr, cc)) {
      const p = board[pr][cc];
      if (p && (byWhite ? p === 'P' : p === 'p')) return true;
    }
  }
  const nOff = [[-2,-1],[-2,1],[-1,-2],[-1,2],[1,-2],[1,2],[2,-1],[2,1]];
  for (const [dr, dc] of nOff) {
    const nr = r + dr, nc = c + dc;
    if (inBounds(nr, nc)) {
      const p = board[nr][nc];
      if (p && (byWhite ? p === 'N' : p === 'n')) return true;
    }
  }
  for (let dr = -1; dr <= 1; dr++)
    for (let dc = -1; dc <= 1; dc++) {
      if (!dr && !dc) continue;
      const nr = r + dr, nc = c + dc;
      if (inBounds(nr, nc)) {
        const p = board[nr][nc];
        if (p && (byWhite ? p === 'K' : p === 'k')) return true;
      }
    }
  const rookDir = [[0,1],[0,-1],[1,0],[-1,0]];
  for (const [dr, dc] of rookDir) {
    let nr = r + dr, nc = c + dc;
    while (inBounds(nr, nc)) {
      const p = board[nr][nc];
      if (p) {
        if (byWhite && (p === 'R' || p === 'Q')) return true;
        if (!byWhite && (p === 'r' || p === 'q')) return true;
        break;
      }
      nr += dr; nc += dc;
    }
  }
  const bisDir = [[1,1],[1,-1],[-1,1],[-1,-1]];
  for (const [dr, dc] of bisDir) {
    let nr = r + dr, nc = c + dc;
    while (inBounds(nr, nc)) {
      const p = board[nr][nc];
      if (p) {
        if (byWhite && (p === 'B' || p === 'Q')) return true;
        if (!byWhite && (p === 'b' || p === 'q')) return true;
        break;
      }
      nr += dr; nc += dc;
    }
  }
  return false;
}

function isInCheck(board, white) {
  const k = findKing(board, white);
  if (!k) return false;
  return isAttacked(board, k[0], k[1], !white);
}

function genPseudoMoves(board, r, c, state) {
  const p = board[r][c];
  if (!p) return [];
  const white = isWhite(p);
  const moves = [];
  const add = (tr, tc, promo = null, ep = false, castle = null) => {
    if (!inBounds(tr, tc)) return;
    const t = board[tr][tc];
    if (t && sameColor(p, t)) return;
    moves.push({ from: [r, c], to: [tr, tc], promo, ep, castle, piece: p, capture: t || (ep ? (white ? 'p' : 'P') : null) });
  };
  const type = p.toUpperCase();
  if (type === 'P') {
    const dir = white ? -1 : 1;
    const start = white ? 6 : 1;
    if (!board[r + dir]?.[c]) {
      if (r + dir === (white ? 0 : 7)) {
        ['Q','R','B','N'].forEach(pr => add(r + dir, c, white ? pr : pr.toLowerCase()));
      } else {
        add(r + dir, c);
        if (r === start && !board[r + 2 * dir]?.[c]) add(r + 2 * dir, c);
      }
    }
    for (const dc of [-1, 1]) {
      const tr = r + dir, tc = c + dc;
      if (!inBounds(tr, tc)) continue;
      if (board[tr][tc] && !sameColor(p, board[tr][tc])) {
        if (tr === (white ? 0 : 7)) {
          ['Q','R','B','N'].forEach(pr => add(tr, tc, white ? pr : pr.toLowerCase()));
        } else add(tr, tc);
      }
      if (state.ep && state.ep[0] === tr && state.ep[1] === tc) add(tr, tc, null, true);
    }
  } else if (type === 'N') {
    [[-2,-1],[-2,1],[-1,-2],[-1,2],[1,-2],[1,2],[2,-1],[2,1]].forEach(([dr,dc]) => add(r+dr, c+dc));
  } else if (type === 'B' || type === 'Q' || type === 'R') {
    const dirs = [];
    if (type === 'B' || type === 'Q') dirs.push([1,1],[1,-1],[-1,1],[-1,-1]);
    if (type === 'R' || type === 'Q') dirs.push([0,1],[0,-1],[1,0],[-1,0]);
    for (const [dr, dc] of dirs) {
      let nr = r + dr, nc = c + dc;
      while (inBounds(nr, nc)) {
        if (board[nr][nc]) { add(nr, nc); break; }
        add(nr, nc);
        nr += dr; nc += dc;
      }
    }
  } else if (type === 'K') {
    for (let dr = -1; dr <= 1; dr++)
      for (let dc = -1; dc <= 1; dc++)
        if (dr || dc) add(r + dr, c + dc);
    if (!isInCheck(board, white)) {
      const row = white ? 7 : 0;
      if (r === row && c === 4) {
        if (state.castle[white ? 'K' : 'k'] && !board[row][5] && !board[row][6] &&
            board[row][7] === (white ? 'R' : 'r') &&
            !isAttacked(board, row, 5, !white) && !isAttacked(board, row, 6, !white)) {
          add(row, 6, null, false, 'K');
        }
        if (state.castle[white ? 'Q' : 'q'] && !board[row][3] && !board[row][2] && !board[row][1] &&
            board[row][0] === (white ? 'R' : 'r') &&
            !isAttacked(board, row, 3, !white) && !isAttacked(board, row, 2, !white)) {
          add(row, 2, null, false, 'Q');
        }
      }
    }
  }
  return moves;
}

function makeMove(board, move, state) {
  const nb = cloneBoard(board);
  const [fr, fc] = move.from;
  const [tr, tc] = move.to;
  const p = nb[fr][fc];
  nb[fr][fc] = null;
  if (move.ep) nb[fr][tc] = null;
  if (move.castle) {
    const row = fr;
    if (move.castle === 'K') { nb[row][5] = nb[row][7]; nb[row][7] = null; }
    else { nb[row][3] = nb[row][0]; nb[row][0] = null; }
  }
  nb[tr][tc] = move.promo || p;
  const ns = {
    ep: null,
    castle: { ...state.castle },
    halfmove: (p.toUpperCase() === 'P' || move.capture) ? 0 : state.halfmove + 1,
    fullmove: state.turn === 'b' ? state.fullmove + 1 : state.fullmove,
    turn: state.turn === 'w' ? 'b' : 'w'
  };
  if (p.toUpperCase() === 'P' && Math.abs(fr - tr) === 2) ns.ep = [(fr + tr) / 2, fc];
  if (p === 'K') { ns.castle.K = false; ns.castle.Q = false; }
  if (p === 'k') { ns.castle.k = false; ns.castle.q = false; }
  if (p === 'R' && fr === 7 && fc === 0) ns.castle.Q = false;
  if (p === 'R' && fr === 7 && fc === 7) ns.castle.K = false;
  if (p === 'r' && fr === 0 && fc === 0) ns.castle.q = false;
  if (p === 'r' && fr === 0 && fc === 7) ns.castle.k = false;
  if (move.capture === 'R' && tr === 7 && tc === 0) ns.castle.Q = false;
  if (move.capture === 'R' && tr === 7 && tc === 7) ns.castle.K = false;
  if (move.capture === 'r' && tr === 0 && tc === 0) ns.castle.q = false;
  if (move.capture === 'r' && tr === 0 && tc === 7) ns.castle.k = false;
  return { board: nb, state: ns };
}

function legalMoves(board, r, c, state) {
  const pseudo = genPseudoMoves(board, r, c, state);
  const white = state.turn === 'w';
  return pseudo.filter(m => {
    const { board: nb } = makeMove(board, m, state);
    return !isInCheck(nb, white);
  });
}

function allLegalMoves(board, state) {
  const moves = [];
  const white = state.turn === 'w';
  for (let r = 0; r < 8; r++)
    for (let c = 0; c < 8; c++) {
      const p = board[r][c];
      if (p && isWhite(p) === white) moves.push(...legalMoves(board, r, c, state));
    }
  return moves;
}

function getGameStatus(board, state) {
  const moves = allLegalMoves(board, state);
  const inCheck = isInCheck(board, state.turn === 'w');
  if (moves.length === 0) {
    if (inCheck) return { over: true, result: state.turn === 'w' ? '0-1' : '1-0', reason: 'checkmate' };
    return { over: true, result: '1/2-1/2', reason: 'stalemate' };
  }
  if (state.halfmove >= 100) return { over: true, result: '1/2-1/2', reason: '50-move rule' };
  const pieces = [];
  for (let r = 0; r < 8; r++) for (let c = 0; c < 8; c++) if (board[r][c]) pieces.push(board[r][c].toUpperCase());
  const nonKing = pieces.filter(p => p !== 'K');
  if (nonKing.length === 0) return { over: true, result: '1/2-1/2', reason: 'insufficient material' };
  if (nonKing.length === 1 && (nonKing[0] === 'B' || nonKing[0] === 'N')) return { over: true, result: '1/2-1/2', reason: 'insufficient material' };
  return { over: false, inCheck, moves };
}

function startPosition() {
  const b = emptyBoard();
  const back = ['R','N','B','Q','K','B','N','R'];
  for (let c = 0; c < 8; c++) {
    b[0][c] = back[c].toLowerCase();
    b[1][c] = 'p';
    b[6][c] = 'P';
    b[7][c] = back[c];
  }
  return {
    board: b,
    state: { turn: 'w', castle: { K: true, Q: true, k: true, q: true }, ep: null, halfmove: 0, fullmove: 1 },
    history: [],
    movesSan: []
  };
}

function moveToSan(board, move, state) {
  const p = move.piece.toUpperCase();
  let san = '';
  if (move.castle === 'K') san = 'O-O';
  else if (move.castle === 'Q') san = 'O-O-O';
  else {
    if (p !== 'P') san += p;
    if (p === 'P' && move.capture) san += FILES[move.from[1]];
    if (move.capture) san += 'x';
    san += posToAlg(...move.to);
    if (move.promo) san += '=' + move.promo.toUpperCase();
  }
  const { board: nb, state: ns } = makeMove(board, move, state);
  const st = getGameStatus(nb, ns);
  if (st.reason === 'checkmate') san += '#';
  else if (st.inCheck) san += '+';
  return san;
}

/* ---------- BOT ---------- */
const PIECE_VAL = { P: 100, N: 320, B: 330, R: 500, Q: 900, K: 20000 };
function evalBoard(board, whitePerspective) {
  let score = 0;
  for (let r = 0; r < 8; r++) {
    for (let c = 0; c < 8; c++) {
      const p = board[r][c];
      if (!p) continue;
      const u = p.toUpperCase();
      const val = PIECE_VAL[u] || 0;
      score += isWhite(p) ? val : -val;
    }
  }
  return whitePerspective ? score : -score;
}
function minimax(board, state, depth, alpha, beta, maximizing, whitePerspective) {
  const st = getGameStatus(board, state);
  if (depth === 0 || st.over) {
    if (st.reason === 'checkmate') return maximizing ? -100000 + (4 - depth) : 100000 - (4 - depth);
    if (st.over) return 0;
    return evalBoard(board, whitePerspective);
  }
  const moves = allLegalMoves(board, state);
  moves.sort((a, b) => (b.capture ? PIECE_VAL[b.capture.toUpperCase()] || 0 : 0) - (a.capture ? PIECE_VAL[a.capture.toUpperCase()] || 0 : 0));
  if (maximizing) {
    let maxEval = -Infinity;
    for (const m of moves) {
      const { board: nb, state: ns } = makeMove(board, m, state);
      const ev = minimax(nb, ns, depth - 1, alpha, beta, false, whitePerspective);
      maxEval = Math.max(maxEval, ev);
      alpha = Math.max(alpha, ev);
      if (beta <= alpha) break;
    }
    return maxEval;
  } else {
    let minEval = Infinity;
    for (const m of moves) {
      const { board: nb, state: ns } = makeMove(board, m, state);
      const ev = minimax(nb, ns, depth - 1, alpha, beta, true, whitePerspective);
      minEval = Math.min(minEval, ev);
      beta = Math.min(beta, ev);
      if (beta <= alpha) break;
    }
    return minEval;
  }
}
function botMove(board, state, difficulty) {
  const moves = allLegalMoves(board, state);
  if (!moves.length) return null;
  const white = state.turn === 'w';
  if (difficulty === 'easy') {
    const caps = moves.filter(m => m.capture);
    if (caps.length && Math.random() < 0.6) return caps[Math.floor(Math.random() * caps.length)];
    return moves[Math.floor(Math.random() * moves.length)];
  }
  const depth = difficulty === 'hard' ? 3 : 2;
  let best = null, bestScore = -Infinity;
  moves.sort(() => Math.random() - 0.5);
  for (const m of moves) {
    const { board: nb, state: ns } = makeMove(board, m, state);
    const score = minimax(nb, ns, depth - 1, -Infinity, Infinity, false, white);
    if (score > bestScore) { bestScore = score; best = m; }
  }
  return best || moves[0];
}

/* ---------- GAME STATE ---------- */
let game = null;
let mode = null;
let playerColor = 'w';
let botDiff = 'medium';
let selected = null;
let legalTargets = [];
let lastMove = null;
let orientWhite = true;
let clocks = { w: 0, b: 0 };
let clockInterval = null;
let lastTick = 0;
let gameOver = false;
let myName = 'Player';
let oppName = 'Opponent';
let pendingPromo = null;

/* PeerJS */
let peer = null;
let conn = null;
let isHost = false;
let currentRoomCode = '';
let roomPassword = '';

function resetClocks(seconds) {
  if (clockInterval) clearInterval(clockInterval);
  clocks = { w: seconds * 1000, b: seconds * 1000 };
  lastTick = Date.now();
  if (seconds > 0) clockInterval = setInterval(tickClocks, 100);
  updateClockUI();
}
function tickClocks() {
  if (gameOver || !game) return;
  const now = Date.now();
  const delta = now - lastTick;
  lastTick = now;
  const side = game.state.turn;
  if (clocks[side] > 0) {
    clocks[side] = Math.max(0, clocks[side] - delta);
    if (clocks[side] === 0) endGame(side === 'w' ? '0-1' : '1-0', 'timeout');
  }
  updateClockUI();
}
function updateClockUI() {
  const fmt = ms => {
    if (ms <= 0 && (clocks.w + clocks.b) === 0) return '∞';
    const s = Math.ceil(ms / 1000);
    const m = Math.floor(s / 60);
    const sec = s % 60;
    return `${m}:${sec.toString().padStart(2, '0')}`;
  };
  const topIsWhite = !orientWhite;
  document.getElementById('topClock').textContent = fmt(clocks[topIsWhite ? 'w' : 'b']);
  document.getElementById('botClock').textContent = fmt(clocks[topIsWhite ? 'b' : 'w']);
  document.getElementById('topClock').classList.toggle('low', clocks[topIsWhite ? 'w' : 'b'] > 0 && clocks[topIsWhite ? 'w' : 'b'] < 20000);
  document.getElementById('botClock').classList.toggle('low', clocks[topIsWhite ? 'b' : 'w'] > 0 && clocks[topIsWhite ? 'b' : 'w'] < 20000);
}
function updateTurnBadges() {
  if (!game) return;
  const topIsWhite = !orientWhite;
  const topTurn = (game.state.turn === 'w') === topIsWhite;
  document.getElementById('topTurn').style.display = topTurn && !gameOver ? 'inline-block' : 'none';
  document.getElementById('botTurn').style.display = !topTurn && !gameOver ? 'inline-block' : 'none';
}
function capturedPieces() {
  const start = { P:8,N:2,B:2,R:2,Q:1,p:8,n:2,b:2,r:2,q:1 };
  const now = { P:0,N:0,B:0,R:0,Q:0,p:0,n:0,b:0,r:0,q:0 };
  for (let r = 0; r < 8; r++) for (let c = 0; c < 8; c++) {
    const p = game.board[r][c];
    if (p && now[p] !== undefined) now[p]++;
  }
  const byWhite = [], byBlack = [];
  for (const p of ['p','n','b','r','q']) {
    const d = start[p] - now[p];
    for (let i = 0; i < d; i++) byWhite.push(PIECES[p]);
  }
  for (const p of ['P','N','B','R','Q']) {
    const d = start[p] - now[p];
    for (let i = 0; i < d; i++) byBlack.push(PIECES[p]);
  }
  return { byWhite, byBlack };
}
function updateCapturedUI() {
  const { byWhite, byBlack } = capturedPieces();
  const topIsWhite = !orientWhite;
  document.getElementById('topCaptured').textContent = (topIsWhite ? byWhite : byBlack).join('');
  document.getElementById('botCaptured').textContent = (topIsWhite ? byBlack : byWhite).join('');
}
function updateMovesUI() {
  const el = document.getElementById('movesContent');
  let html = '';
  for (let i = 0; i < game.movesSan.length; i += 2) {
    const n = Math.floor(i / 2) + 1;
    html += `<div>${n}. ${game.movesSan[i] || ''} ${game.movesSan[i+1] || ''}</div>`;
  }
  el.innerHTML = html;
  el.parentElement.scrollTop = el.parentElement.scrollHeight;
}

function renderBoard() {
  const boardEl = document.getElementById('board');
  boardEl.innerHTML = '';
  const checkSq = game && !gameOver ? (() => {
    const st = getGameStatus(game.board, game.state);
    if (st.inCheck) return findKing(game.board, game.state.turn === 'w');
    return null;
  })() : null;

  for (let sr = 0; sr < 8; sr++) {
    for (let sc = 0; sc < 8; sc++) {
      const r = orientWhite ? sr : 7 - sr;
      const c = orientWhite ? sc : 7 - sc;
      const sq = document.createElement('div');
      sq.className = 'sq ' + ((r + c) % 2 === 0 ? 'light' : 'dark');
      if (lastMove && ((lastMove.from[0] === r && lastMove.from[1] === c) || (lastMove.to[0] === r && lastMove.to[1] === c))) sq.classList.add('lastmove');
      if (selected && selected[0] === r && selected[1] === c) sq.classList.add('highlight');
      if (checkSq && checkSq[0] === r && checkSq[1] === c) sq.classList.add('check');

      const isLegal = legalTargets.some(t => t[0] === r && t[1] === c);
      if (isLegal) {
        if (game.board[r][c]) {
          const cap = document.createElement('div');
          cap.className = 'legal-cap';
          sq.appendChild(cap);
        } else {
          const dot = document.createElement('div');
          dot.className = 'legal-dot';
          sq.appendChild(dot);
        }
      }
      const p = game.board[r][c];
      if (p) {
        const span = document.createElement('span');
        span.className = 'piece';
        span.textContent = PIECES[p];
        sq.appendChild(span);
      }
      sq.addEventListener('click', () => onSquareClick(r, c));
      boardEl.appendChild(sq);
    }
  }
  updateTurnBadges();
  updateCapturedUI();
  updateMovesUI();
  updateClockUI();
}

function onSquareClick(r, c) {
  if (gameOver || !game) return;
  if (mode === 'bot' && game.state.turn !== playerColor) return;
  if (mode === 'mp' && game.state.turn !== playerColor) return;

  const p = game.board[r][c];
  if (selected) {
    const target = legalTargets.find(t => t[0] === r && t[1] === c);
    if (target) {
      const move = legalMoves(game.board, selected[0], selected[1], game.state)
        .find(m => m.to[0] === r && m.to[1] === c);
      if (move) {
        if (move.promo) {
          pendingPromo = move;
          showPromotion(isWhite(move.piece));
          return;
        }
        doMove(move);
      }
      selected = null;
      legalTargets = [];
      renderBoard();
      return;
    }
  }
  if (p && ((mode === 'local') || (isWhite(p) === (playerColor === 'w')))) {
    if (mode !== 'local' && isWhite(p) !== (game.state.turn === 'w')) {
      selected = null; legalTargets = [];
    } else if (isWhite(p) === (game.state.turn === 'w')) {
      selected = [r, c];
      legalTargets = legalMoves(game.board, r, c, game.state).map(m => m.to);
    } else {
      selected = null; legalTargets = [];
    }
  } else {
    selected = null; legalTargets = [];
  }
  renderBoard();
}

function showPromotion(white) {
  const overlay = document.getElementById('promoOverlay');
  const choices = document.getElementById('promoChoices');
  const pieces = white ? ['Q','R','B','N'] : ['q','r','b','n'];
  choices.innerHTML = pieces.map(p => `<button onclick="choosePromo('${p}')">${PIECES[p]}</button>`).join('');
  overlay.classList.add('show');
}
function choosePromo(p) {
  document.getElementById('promoOverlay').classList.remove('show');
  if (!pendingPromo) return;
  pendingPromo.promo = p;
  doMove(pendingPromo);
  pendingPromo = null;
  selected = null;
  legalTargets = [];
  renderBoard();
}

function doMove(move, fromRemote = false) {
  if (!game || gameOver) return;
  const san = moveToSan(game.board, move, game.state);
  const { board, state } = makeMove(game.board, move, game.state);
  game.board = board;
  game.state = state;
  game.history.push(move);
  game.movesSan.push(san);
  lastMove = { from: move.from, to: move.to };
  selected = null;
  legalTargets = [];
  renderBoard();

  if (mode === 'mp' && !fromRemote && conn && conn.open) {
    conn.send({ type: 'move', move, clocks });
  }

  const st = getGameStatus(game.board, game.state);
  if (st.over) {
    endGame(st.result, st.reason);
    return;
  }

  if (mode === 'bot' && game.state.turn !== playerColor && !gameOver) {
    setTimeout(() => {
      const bm = botMove(game.board, game.state, botDiff);
      if (bm) doMove(bm);
    }, 300 + Math.random() * 400);
  }
}

function endGame(result, reason) {
  gameOver = true;
  if (clockInterval) clearInterval(clockInterval);
  let title = 'Game Over';
  let msg = reason;
  if (result === '1-0') title = 'White wins!';
  else if (result === '0-1') title = 'Black wins!';
  else title = 'Draw';
  if (reason === 'checkmate') msg = 'Checkmate';
  else if (reason === 'stalemate') msg = 'Stalemate';
  else if (reason === 'timeout') msg = 'Time out';
  else if (reason === 'resign') msg = 'Resignation';
  else if (reason === 'draw') msg = 'Draw agreed';
  document.getElementById('resultTitle').textContent = title;
  document.getElementById('resultMsg').textContent = msg;
  document.getElementById('resultOverlay').classList.add('show');
  document.getElementById('rematchBtn').style.display = 'inline-flex';
  if (mode === 'mp' && conn && conn.open) {
    conn.send({ type: 'gameover', result, reason });
  }
}
function hideResult() { document.getElementById('resultOverlay').classList.remove('show'); }

function startLocal() {
  mode = 'local';
  game = startPosition();
  playerColor = 'w';
  orientWhite = document.getElementById('orientPref')?.value !== 'black';
  myName = 'White';
  oppName = 'Black';
  gameOver = false;
  lastMove = null;
  selected = null;
  legalTargets = [];
  document.getElementById('topName').textContent = orientWhite ? 'Black' : 'White';
  document.getElementById('botNameDisp').textContent = orientWhite ? 'White' : 'Black';
  document.getElementById('chatBox').style.display = 'none';
  document.getElementById('mpStatus').style.display = 'none';
  document.getElementById('rematchBtn').style.display = 'none';
  hideResult();
  showScreen('gameScreen');
  document.getElementById('gameScreen').classList.add('active');
  resetClocks(0);
  renderBoard();
}

function startBotGame() {
  mode = 'bot';
  game = startPosition();
  botDiff = document.getElementById('botDiff').value;
  myName = document.getElementById('botName').value || 'Player';
  oppName = 'Bot (' + botDiff + ')';
  let col = document.getElementById('botColor').value;
  if (col === 'random') col = Math.random() < 0.5 ? 'w' : 'b';
  playerColor = col;
  orientWhite = playerColor === 'w';
  gameOver = false;
  lastMove = null;
  selected = null;
  legalTargets = [];
  document.getElementById('topName').textContent = orientWhite ? oppName : myName;
  document.getElementById('botNameDisp').textContent = orientWhite ? myName : oppName;
  document.getElementById('chatBox').style.display = 'none';
  document.getElementById('mpStatus').style.display = 'none';
  document.getElementById('rematchBtn').style.display = 'none';
  hideResult();
  const t = parseInt(document.getElementById('botTime').value, 10);
  showScreen('gameScreen');
  document.getElementById('gameScreen').classList.add('active');
  resetClocks(t);
  renderBoard();
  if (playerColor === 'b') {
    setTimeout(() => {
      const bm = botMove(game.board, game.state, botDiff);
      if (bm) doMove(bm);
    }, 400);
  }
}

function confirmLeave() {
  if (mode === 'mp' && conn) {
    try { conn.send({ type: 'leave' }); } catch(e){}
  }
  cleanupPeer();
  if (clockInterval) clearInterval(clockInterval);
  showScreen('homeScreen');
  document.getElementById('gameScreen').classList.remove('active');
  game = null;
  mode = null;
}

function resign() {
  if (gameOver || !game) return;
  if (!confirm('Resign the game?')) return;
  let res;
  if (mode === 'local') res = game.state.turn === 'w' ? '0-1' : '1-0';
  else res = playerColor === 'w' ? '0-1' : '1-0';
  endGame(res, 'resign');
}

function offerDraw() {
  if (gameOver) return;
  if (mode === 'mp' && conn && conn.open) {
    conn.send({ type: 'drawOffer' });
    alert('Draw offer sent.');
  } else if (confirm('Agree to a draw?')) {
    endGame('1/2-1/2', 'draw');
  }
}

function rematch() {
  hideResult();
  if (mode === 'bot') startBotGame();
  else if (mode === 'local') startLocal();
  else if (mode === 'mp' && conn && conn.open) {
    if (isHost) {
      game = startPosition();
      gameOver = false;
      lastMove = null;
      selected = null;
      legalTargets = [];
      const t = parseInt(document.getElementById('hostTime')?.value || '300', 10);
      resetClocks(t);
      renderBoard();
      conn.send({ type: 'rematch', game: serializeGame(), clocks });
    } else {
      conn.send({ type: 'rematchRequest' });
    }
  }
}

/* ---------- PEERJS SHORT CODES ---------- */
function generateCode() {
  const chars = 'ABCDEFGHJKLMNPQRSTUVWXYZ23456789';
  let code = '';
  for (let i = 0; i < 6; i++) code += chars[Math.floor(Math.random() * chars.length)];
  return code;
}

function cleanupPeer() {
  if (conn) { try { conn.close(); } catch(e){} conn = null; }
  if (peer) { try { peer.destroy(); } catch(e){} peer = null; }
}

function createRoom() {
  cleanupPeer();
  isHost = true;
  myName = document.getElementById('hostName').value || 'Host';
  roomPassword = document.getElementById('hostPass').value || '';
  currentRoomCode = generateCode();

  peer = new Peer(currentRoomCode, {
    debug: 1
  });

  peer.on('open', id => {
    document.getElementById('roomCodeDisplay').textContent = id;
    document.getElementById('hostCodeArea').style.display = 'block';
    document.getElementById('hostStatus').innerHTML = '<span class="status-dot connecting"></span> Waiting for opponent...';
    document.getElementById('createRoomBtn').disabled = true;
  });

  peer.on('connection', c => {
    conn = c;
    setupConnection();
  });

  peer.on('error', err => {
    console.error(err);
    alert('Error creating room: ' + err.type + '\nTry again.');
    cleanupPeer();
    document.getElementById('createRoomBtn').disabled = false;
  });
}

function joinRoom() {
  cleanupPeer();
  isHost = false;
  myName = document.getElementById('guestName').value || 'Guest';
  const code = (document.getElementById('joinCode').value || '').trim().toUpperCase();
  const pass = document.getElementById('guestPass').value || '';
  if (!code || code.length < 4) return alert('Enter a valid room code');

  document.getElementById('guestStatus').style.display = 'flex';
  document.getElementById('guestStatus').innerHTML = '<span class="status-dot connecting"></span> Connecting...';

  peer = new Peer({ debug: 1 });

  peer.on('open', () => {
    conn = peer.connect(code, { reliable: true });
    conn.on('open', () => {
      // send join info
      conn.send({ type: 'join', name: myName, pass: pass });
      setupConnection();
    });
    conn.on('error', err => {
      alert('Could not connect. Check the code and try again.');
      document.getElementById('guestStatus').innerHTML = '<span class="status-dot offline"></span> Failed';
    });
  });

  peer.on('error', err => {
    console.error(err);
    alert('Connection error: ' + err.type);
    document.getElementById('guestStatus').innerHTML = '<span class="status-dot offline"></span> Failed';
  });
}

function setupConnection() {
  conn.on('data', data => handleSignal(data));
  conn.on('close', () => {
    updateMpStatus(false);
    if (!gameOver && mode === 'mp') alert('Opponent disconnected');
  });
  conn.on('error', e => console.warn(e));

  if (isHost) {
    // wait for join message
  }
}

function startMultiplayerGame(asWhite) {
  mode = 'mp';
  game = startPosition();
  playerColor = asWhite ? 'w' : 'b';
  orientWhite = asWhite;
  gameOver = false;
  lastMove = null;
  selected = null;
  legalTargets = [];
  document.getElementById('topName').textContent = oppName;
  document.getElementById('botNameDisp').textContent = myName;
  document.getElementById('chatBox').style.display = 'block';
  document.getElementById('mpStatus').style.display = 'inline-flex';
  document.getElementById('rematchBtn').style.display = 'none';
  hideResult();
  updateMpStatus(true);
  const t = parseInt(document.getElementById('hostTime')?.value || '300', 10);
  showScreen('gameScreen');
  document.getElementById('gameScreen').classList.add('active');
  resetClocks(t);
  renderBoard();
}

function updateMpStatus(online) {
  const dot = document.querySelector('#mpStatus .status-dot');
  const txt = document.getElementById('mpStatusText');
  if (online) {
    dot.className = 'status-dot online';
    txt.textContent = 'Connected';
  } else {
    dot.className = 'status-dot offline';
    txt.textContent = 'Disconnected';
  }
}

function serializeGame() {
  return { board: game.board, state: game.state, movesSan: game.movesSan, lastMove };
}

function handleSignal(msg) {
  if (msg.type === 'join') {
    if (isHost) {
      if (roomPassword && msg.pass !== roomPassword) {
        conn.send({ type: 'reject', reason: 'Wrong password' });
        conn.close();
        return;
      }
      oppName = msg.name || 'Guest';
      document.getElementById('hostStatus').innerHTML = '<span class="status-dot online"></span> Opponent joined!';
      // Host is White
      startMultiplayerGame(true);
      conn.send({
        type: 'welcome',
        name: myName,
        time: parseInt(document.getElementById('hostTime').value, 10),
        game: serializeGame(),
        clocks
      });
    }
  } else if (msg.type === 'welcome') {
    // Guest receives this
    oppName = msg.name || 'Host';
    startMultiplayerGame(false); // Guest is Black
    if (msg.game) {
      game.board = msg.game.board;
      game.state = msg.game.state;
      game.movesSan = msg.game.movesSan || [];
      lastMove = msg.game.lastMove;
    }
    if (msg.clocks) clocks = msg.clocks;
    renderBoard();
  } else if (msg.type === 'reject') {
    alert(msg.reason || 'Connection rejected');
    cleanupPeer();
    showScreen('joinRoom');
  } else if (msg.type === 'move') {
    if (game && !gameOver) {
      doMove(msg.move, true);
      if (msg.clocks) clocks = msg.clocks;
    }
  } else if (msg.type === 'chat') {
    addChatMsg(msg.name, msg.text);
  } else if (msg.type === 'drawOffer') {
    if (confirm(oppName + ' offers a draw. Accept?')) {
      endGame('1/2-1/2', 'draw');
      conn.send({ type: 'drawAccept' });
    } else {
      conn.send({ type: 'drawDecline' });
    }
  } else if (msg.type === 'drawAccept') {
    endGame('1/2-1/2', 'draw');
  } else if (msg.type === 'gameover') {
    if (!gameOver) endGame(msg.result, msg.reason);
  } else if (msg.type === 'rematch') {
    game = {
      board: msg.game.board,
      state: msg.game.state,
      history: [],
      movesSan: msg.game.movesSan || []
    };
    lastMove = msg.game.lastMove;
    clocks = msg.clocks || clocks;
    gameOver = false;
    selected = null;
    legalTargets = [];
    hideResult();
    renderBoard();
  } else if (msg.type === 'rematchRequest' && isHost) {
    // host starts rematch
    rematch();
  } else if (msg.type === 'leave') {
    alert('Opponent left the game');
    updateMpStatus(false);
  }
}

function sendChat() {
  const input = document.getElementById('chatInput');
  const text = input.value.trim();
  if (!text || !conn || !conn.open) return;
  conn.send({ type: 'chat', name: myName, text });
  addChatMsg(myName, text);
  input.value = '';
}
function addChatMsg(who, text) {
  const el = document.getElementById('chatMessages');
  const div = document.createElement('div');
  div.className = 'chat-msg';
  div.innerHTML = `<span class="who">${who}:</span> ${text.replace(/</g,'&lt;')}`;
  el.appendChild(div);
  el.scrollTop = el.scrollHeight;
}

function copyRoomCode() {
  const code = document.getElementById('roomCodeDisplay').textContent;
  navigator.clipboard.writeText(code).then(() => alert('Code copied: ' + code)).catch(() => {
    prompt('Copy this code:', code);
  });
}

showScreen('homeScreen');
</script>
</body>
</html>
