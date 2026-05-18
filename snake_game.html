<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>SNAKE</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Press+Start+2P&family=Orbitron:wght@400;700;900&display=swap');

    :root {
      --bg: #0a0a0f;
      --panel: #0f0f1a;
      --border: #1a1a2e;
      --snake-head: #00ff88;
      --snake-body: #00cc66;
      --snake-glow: #00ff8855;
      --food: #ff3366;
      --food-glow: #ff336655;
      --grid: #0d0d1a;
      --text: #e0e0ff;
      --accent: #00ff88;
      --dim: #444466;
      --danger: #ff3366;
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'Press Start 2P', monospace;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      overflow: hidden;
    }

    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background:
        radial-gradient(ellipse 80% 50% at 50% -10%, #00ff8815 0%, transparent 60%),
        radial-gradient(ellipse 60% 40% at 80% 110%, #ff336610 0%, transparent 50%);
      pointer-events: none;
      z-index: 0;
    }

    .container {
      position: relative;
      z-index: 1;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 20px;
    }

    .title {
      font-family: 'Orbitron', sans-serif;
      font-weight: 900;
      font-size: clamp(2rem, 6vw, 3.5rem);
      letter-spacing: 0.3em;
      color: var(--accent);
      text-shadow:
        0 0 10px var(--accent),
        0 0 40px var(--snake-glow),
        0 0 80px var(--snake-glow);
      animation: titlePulse 3s ease-in-out infinite;
    }

    @keyframes titlePulse {
      0%, 100% { text-shadow: 0 0 10px var(--accent), 0 0 40px var(--snake-glow); }
      50% { text-shadow: 0 0 20px var(--accent), 0 0 60px var(--snake-glow), 0 0 100px var(--snake-glow); }
    }

    .scoreboard {
      display: flex;
      gap: 40px;
      font-size: 0.55rem;
      letter-spacing: 0.15em;
    }

    .score-item {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 8px;
    }

    .score-label { color: var(--dim); font-size: 0.45rem; }
    .score-value {
      color: var(--accent);
      font-size: 1.1rem;
      text-shadow: 0 0 12px var(--accent);
      min-width: 3ch;
      text-align: center;
    }

    .game-wrap {
      position: relative;
    }

    canvas {
      display: block;
      border: 1px solid #00ff8833;
      box-shadow:
        0 0 0 1px #00ff8811,
        0 0 30px #00ff8820,
        inset 0 0 60px #00000080;
      image-rendering: pixelated;
    }

    .overlay {
      position: absolute;
      inset: 0;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      background: #0a0a0fcc;
      backdrop-filter: blur(4px);
      gap: 24px;
      transition: opacity 0.3s;
    }

    .overlay.hidden { opacity: 0; pointer-events: none; }

    .overlay-title {
      font-family: 'Orbitron', sans-serif;
      font-weight: 900;
      font-size: clamp(1.2rem, 4vw, 2rem);
      color: var(--danger);
      text-shadow: 0 0 20px var(--danger);
      letter-spacing: 0.2em;
    }

    .overlay-title.start { color: var(--accent); text-shadow: 0 0 20px var(--accent); }

    .overlay-score {
      font-size: 0.55rem;
      color: var(--dim);
      letter-spacing: 0.1em;
      line-height: 2;
      text-align: center;
    }

    .overlay-score span { color: var(--text); }

    .btn {
      font-family: 'Press Start 2P', monospace;
      font-size: 0.6rem;
      letter-spacing: 0.12em;
      padding: 14px 32px;
      background: transparent;
      border: 2px solid var(--accent);
      color: var(--accent);
      cursor: pointer;
      text-transform: uppercase;
      transition: all 0.15s;
      position: relative;
      overflow: hidden;
    }

    .btn::before {
      content: '';
      position: absolute;
      inset: 0;
      background: var(--accent);
      opacity: 0;
      transition: opacity 0.15s;
    }

    .btn:hover::before { opacity: 0.12; }
    .btn:hover {
      box-shadow: 0 0 20px var(--snake-glow);
      text-shadow: 0 0 10px var(--accent);
    }
    .btn:active { transform: scale(0.97); }

    .controls-hint {
      display: flex;
      gap: 12px;
      align-items: center;
      font-size: 0.35rem;
      color: var(--dim);
      letter-spacing: 0.1em;
    }

    .key {
      border: 1px solid var(--dim);
      padding: 4px 8px;
      color: var(--text);
      font-size: 0.45rem;
    }

    .scanlines {
      position: fixed;
      inset: 0;
      pointer-events: none;
      z-index: 100;
      background: repeating-linear-gradient(
        0deg,
        transparent,
        transparent 2px,
        #00000008 2px,
        #00000008 4px
      );
    }
  </style>
</head>
<body>
  <div class="scanlines"></div>
  <div class="container">
    <div class="title">SNAKE</div>

    <div class="scoreboard">
      <div class="score-item">
        <span class="score-label">SCORE</span>
        <span class="score-value" id="scoreDisplay">0</span>
      </div>
      <div class="score-item">
        <span class="score-label">LEVEL</span>
        <span class="score-value" id="levelDisplay">1</span>
      </div>
      <div class="score-item">
        <span class="score-label">BEST</span>
        <span class="score-value" id="bestDisplay">0</span>
      </div>
    </div>

    <div class="game-wrap">
      <canvas id="gameCanvas"></canvas>

      <div class="overlay" id="overlay">
        <div class="overlay-title start" id="overlayTitle">READY?</div>
        <div class="overlay-score" id="overlayScore">
          USE ARROW KEYS OR WASD<br>TO CONTROL THE SNAKE
        </div>
        <button class="btn" id="startBtn" onclick="startGame()">START GAME</button>
      </div>
    </div>

    <div class="controls-hint">
      <span class="key">↑</span>
      <span class="key">↓</span>
      <span class="key">←</span>
      <span class="key">→</span>
      <span style="margin: 0 4px">OR</span>
      <span class="key">W</span>
      <span class="key">A</span>
      <span class="key">S</span>
      <span class="key">D</span>
      <span style="margin-left: 12px">|</span>
      <span class="key">P</span>
      <span style="font-size:0.38rem">PAUSE</span>
    </div>
  </div>

  <script>
    const canvas = document.getElementById('gameCanvas');
    const ctx = canvas.getContext('2d');

    // Responsive sizing
    const CELL = 20;
    const COLS = 25;
    const ROWS = 20;
    canvas.width = COLS * CELL;
    canvas.height = ROWS * CELL;

    let snake, dir, nextDir, food, score, best, level, speed, gameLoop, running, paused;
    let particles = [];
    let flashAlpha = 0;

    function init() {
      snake = [
        { x: 12, y: 10 },
        { x: 11, y: 10 },
        { x: 10, y: 10 },
      ];
      dir = { x: 1, y: 0 };
      nextDir = { x: 1, y: 0 };
      score = 0;
      level = 1;
      speed = 120;
      particles = [];
      flashAlpha = 0;
      best = parseInt(localStorage.getItem('snakeBest') || '0');
      updateUI();
      spawnFood();
    }

    function spawnFood() {
      let pos;
      do {
        pos = { x: Math.floor(Math.random() * COLS), y: Math.floor(Math.random() * ROWS) };
      } while (snake.some(s => s.x === pos.x && s.y === pos.y));
      food = pos;
    }

    function updateUI() {
      document.getElementById('scoreDisplay').textContent = score;
      document.getElementById('levelDisplay').textContent = level;
      document.getElementById('bestDisplay').textContent = best;
    }

    function startGame() {
      init();
      running = true;
      paused = false;
      document.getElementById('overlay').classList.add('hidden');
      clearInterval(gameLoop);
      gameLoop = setInterval(tick, speed);
    }

    function tick() {
      if (paused) return;

      dir = nextDir;
      const head = { x: snake[0].x + dir.x, y: snake[0].y + dir.y };

      // Wall collision
      if (head.x < 0 || head.x >= COLS || head.y < 0 || head.y >= ROWS) {
        return gameOver();
      }
      // Self collision
      if (snake.some(s => s.x === head.x && s.y === head.y)) {
        return gameOver();
      }

      snake.unshift(head);

      // Food eaten
      if (head.x === food.x && head.y === food.y) {
        score += 10 * level;
        if (score > best) { best = score; localStorage.setItem('snakeBest', best); }

        // Level up every 50 pts
        const newLevel = Math.floor(score / 50) + 1;
        if (newLevel > level) {
          level = newLevel;
          speed = Math.max(50, 120 - (level - 1) * 10);
          clearInterval(gameLoop);
          gameLoop = setInterval(tick, speed);
        }

        spawnParticles(food.x, food.y);
        flashAlpha = 0.15;
        spawnFood();
        updateUI();
      } else {
        snake.pop();
      }

      draw();
    }

    function gameOver() {
      clearInterval(gameLoop);
      running = false;

      // Death particles
      snake.forEach(s => spawnParticles(s.x, s.y, '#ff3366'));
      drawDeathAnim();

      setTimeout(() => {
        document.getElementById('overlayTitle').textContent = 'GAME OVER';
        document.getElementById('overlayTitle').className = 'overlay-title';
        document.getElementById('overlayScore').innerHTML =
          `SCORE <span>${score}</span>&nbsp;&nbsp;|&nbsp;&nbsp;BEST <span>${best}</span>`;
        document.getElementById('startBtn').textContent = 'PLAY AGAIN';
        document.getElementById('overlay').classList.remove('hidden');
      }, 600);
    }

    function drawDeathAnim() {
      let frame = 0;
      const anim = setInterval(() => {
        draw(true, frame);
        frame++;
        if (frame > 12) clearInterval(anim);
      }, 50);
    }

    function spawnParticles(gx, gy, color = '#00ff88') {
      for (let i = 0; i < 8; i++) {
        const angle = (Math.PI * 2 * i) / 8 + Math.random() * 0.4;
        particles.push({
          x: gx * CELL + CELL / 2,
          y: gy * CELL + CELL / 2,
          vx: Math.cos(angle) * (1.5 + Math.random() * 2),
          vy: Math.sin(angle) * (1.5 + Math.random() * 2),
          life: 1,
          color,
        });
      }
    }

    function draw(dying = false, deathFrame = 0) {
      // Background
      ctx.fillStyle = '#0a0a0f';
      ctx.fillRect(0, 0, canvas.width, canvas.height);

      // Grid
      ctx.strokeStyle = '#0d0d1a';
      ctx.lineWidth = 0.5;
      for (let x = 0; x <= COLS; x++) {
        ctx.beginPath(); ctx.moveTo(x * CELL, 0); ctx.lineTo(x * CELL, canvas.height); ctx.stroke();
      }
      for (let y = 0; y <= ROWS; y++) {
        ctx.beginPath(); ctx.moveTo(0, y * CELL); ctx.lineTo(canvas.width, y * CELL); ctx.stroke();
      }

      // Flash effect on food eat
      if (flashAlpha > 0) {
        ctx.fillStyle = `rgba(0,255,136,${flashAlpha})`;
        ctx.fillRect(0, 0, canvas.width, canvas.height);
        flashAlpha -= 0.025;
      }

      // Food
      if (!dying) {
        const fx = food.x * CELL, fy = food.y * CELL;
        const pulse = 0.5 + 0.5 * Math.sin(Date.now() / 200);
        ctx.shadowColor = '#ff3366';
        ctx.shadowBlur = 8 + pulse * 8;
        ctx.fillStyle = '#ff3366';
        const pad = 3 + pulse * 1;
        ctx.fillRect(fx + pad, fy + pad, CELL - pad * 2, CELL - pad * 2);

        // Food sparkle
        ctx.fillStyle = '#ffaacc';
        ctx.fillRect(fx + pad + 2, fy + pad + 2, 3, 3);
        ctx.shadowBlur = 0;
      }

      // Snake
      snake.forEach((seg, i) => {
        const isHead = i === 0;
        const t = dying ? Math.max(0, 1 - (deathFrame * 0.08) - i * 0.04) : 1;
        if (t <= 0) return;

        const x = seg.x * CELL, y = seg.y * CELL;
        const pad = isHead ? 1 : 2;
        const alpha = Math.max(0.3, 1 - i / snake.length * 0.6) * t;

        if (dying) {
          ctx.shadowColor = '#ff3366';
          ctx.fillStyle = `rgba(255,51,102,${alpha})`;
        } else {
          ctx.shadowColor = isHead ? '#00ff88' : '#00cc66';
          ctx.fillStyle = isHead
            ? `rgba(0,255,136,${alpha})`
            : `rgba(0,${Math.floor(180 - i * 2)},${Math.floor(80 - i)},${alpha})`;
        }
        ctx.shadowBlur = isHead ? 12 : 4;
        ctx.fillRect(x + pad, y + pad, CELL - pad * 2, CELL - pad * 2);

        // Head eyes
        if (isHead && !dying) {
          ctx.shadowBlur = 0;
          ctx.fillStyle = '#0a0a0f';
          const ex = dir.x === 1 ? 12 : dir.x === -1 ? 4 : 6;
          const ey = dir.y === 1 ? 12 : dir.y === -1 ? 4 : 6;
          const ex2 = dir.y !== 0 ? 12 : ex;
          const ey2 = dir.x !== 0 ? 12 : ey;
          ctx.fillRect(x + ex, y + ey, 3, 3);
          ctx.fillRect(x + ex2, y + ey2, 3, 3);
        }
      });
      ctx.shadowBlur = 0;

      // Particles
      particles = particles.filter(p => p.life > 0);
      particles.forEach(p => {
        p.x += p.vx; p.y += p.vy; p.vy += 0.1; p.life -= 0.06;
        ctx.globalAlpha = p.life;
        ctx.fillStyle = p.color;
        ctx.shadowColor = p.color;
        ctx.shadowBlur = 6;
        ctx.fillRect(p.x - 2, p.y - 2, 4, 4);
        ctx.shadowBlur = 0;
      });
      ctx.globalAlpha = 1;
    }

    // Controls
    const DIRS = {
      ArrowUp: { x: 0, y: -1 }, w: { x: 0, y: -1 }, W: { x: 0, y: -1 },
      ArrowDown: { x: 0, y: 1 }, s: { x: 0, y: 1 }, S: { x: 0, y: 1 },
      ArrowLeft: { x: -1, y: 0 }, a: { x: -1, y: 0 }, A: { x: -1, y: 0 },
      ArrowRight: { x: 1, y: 0 }, d: { x: 1, y: 0 }, D: { x: 1, y: 0 },
    };

    document.addEventListener('keydown', e => {
      if ((e.key === 'p' || e.key === 'P') && running) {
        paused = !paused;
        if (!paused) draw();
        return;
      }
      const d = DIRS[e.key];
      if (!d) return;
      // Prevent reversing
      if (d.x === -dir.x && d.y === -dir.y) return;
      nextDir = d;
      e.preventDefault();
    });

    // Mobile swipe support
    let touchStart = null;
    canvas.addEventListener('touchstart', e => {
      touchStart = { x: e.touches[0].clientX, y: e.touches[0].clientY };
    }, { passive: true });
    canvas.addEventListener('touchend', e => {
      if (!touchStart) return;
      const dx = e.changedTouches[0].clientX - touchStart.x;
      const dy = e.changedTouches[0].clientY - touchStart.y;
      if (Math.abs(dx) > Math.abs(dy)) {
        const nd = dx > 0 ? { x: 1, y: 0 } : { x: -1, y: 0 };
        if (nd.x !== -dir.x) nextDir = nd;
      } else {
        const nd = dy > 0 ? { x: 0, y: 1 } : { x: 0, y: -1 };
        if (nd.y !== -dir.y) nextDir = nd;
      }
      touchStart = null;
    }, { passive: true });

    // Initial draw
    init();
    draw();

    // Idle animation on start screen
    setInterval(() => {
      if (!running) draw();
    }, 80);
  </script>
</body>
</html>
