---
title: Format Templates
description: README, CONTRIBUTING, LICENSE, Issue, Pull Request, and index.html templates from the workshop script, plus a CHANGELOG template and the full mini-game source.
discussions: true
---

# Format Templates

This page follows chapters 3–6 of the workshop script and collects the templates used when creating and maintaining a repository, with an additional CHANGELOG template. Copy each block to the indicated path and replace the `<...>` placeholders.

## Recommended repository structure

The script's appendix C recommends this demo repository:

```text
github-workshop-demo/
├── README.md
├── LICENSE                   # MIT
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── contributors.md           # practice table
└── .github/
    ├── ISSUE_TEMPLATE/
    │   └── bug_report.md
    └── PULL_REQUEST_TEMPLATE.md
```

The `.github/` directory can also contain `feature_request.md` and `workflows/` for CI.

## README.md

A good README answers four questions: what is this, what can it do, how do I install it, and how do I use it.

````markdown
# Project name

> One sentence explaining what problem this project solves.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## Features

- Feature one
- Feature two

## Installation

```bash
git clone https://github.com/<username>/<repository>.git
cd <repository>
npm install
```

## Quick start

```bash
npm start
```

## Usage example

```python
from mylib import hello
hello()
```

## Contributing

Issues and pull requests are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) first.

## License

This project is licensed under the [MIT](LICENSE) license.
````

## CONTRIBUTING.md

`LICENSE` answers "may I change this?"; `CONTRIBUTING.md` answers "how should I change it?".

````markdown
# Contributing

Thank you for contributing!

## Development environment

- Node.js >= 20
- Install dependencies: `npm install`
- Run tests: `npm test`

## Branches and commits

- Branch names: `feat/xxx`, `fix/xxx`, `docs/xxx`
- Follow Conventional Commits, e.g. `fix: fix login timeout`
- Make sure `npm test` passes before committing

## Submitting a pull request

1. Fork this repository and clone it locally
2. Create a branch from the latest `main`
3. Make your changes and commit them
4. Push the branch, open a pull request, and link the related issue

## Code of conduct

By participating in this project, you agree to follow [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md).
````

## LICENSE

Do not hand-write the license text; use GitHub's license template. Choosing a license:

| License | Characteristics | Best for |
| --- | --- | --- |
| MIT | Shortest and most permissive; keep the copyright notice | Personal projects, libraries, broad reuse |
| Apache-2.0 | MIT plus an explicit patent grant | Company projects with patent risk |
| GPL-3.0 | Derivative works must stay open source (copyleft) | Projects that must remain open source |
| BSD-3-Clause | Like MIT, plus a clause forbidding endorsement | Academia, infrastructure |
| CC0 / Unlicense | Waive copyright and release into the public domain | Example code, datasets |

Adding a license to an existing repository:

1. Repository page → **Add file** → **Create new file**
2. Enter `LICENSE` as the file name
3. On the right, choose **Choose a license template**
4. Select MIT → fill in the year and author → **Review and submit**

Add a line to the README: "This project uses the MIT license", and link to the `LICENSE` file. Changing the license after others have contributed requires all contributors' agreement.

## index.html

`index.html` is the default entry point for a web project; with GitHub Pages enabled, the repository becomes a website. Minimal example:

````html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <title>My GitHub Page</title>
</head>
<body>
  <h1>Hello GitHub Pages</h1>
</body>
</html>
````

## .github/ISSUE_TEMPLATE/bug_report.md

````markdown
---
name: Bug report
about: Report a problem
title: "[Bug] "
labels: bug
---

## Description

## Steps to reproduce

1.
2.
3.

## Expected behavior

## Actual behavior

## Environment

- OS:
- Version:
- Browser/runtime:

## Logs / screenshots
````

## .github/PULL_REQUEST_TEMPLATE.md

````markdown
## What does this PR do?

## Related issue

Closes #

## How was it tested?

## Checklist

- [ ] Tested locally
- [ ] Documentation updated
- [ ] Commit messages follow the convention
- [ ] No unrelated changes included
````

## contributors.md

````markdown
# Contributors

| Name | GitHub | One-line note |
|------|--------|---------------|
| Instructor | @<instructor-username> | Example row |
````

## Markdown quick reference

- Headings: `# Level 1`, `## Level 2`
- Bold / italic: `**bold**`, `*italic*`
- List: `- item`
- Link: `[text](https://...)`
- Image: `![description](docs/screenshot.png)`
- Inline code: `` `code` ``
- Code block: three backticks + language name
- Quote: `> quote`
- Table: `| A | B |`
- Task list: `- [x] done`

## CHANGELOG.md

````markdown
# Changelog

All notable changes to this project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

- New features.

### Changed

- Changes to existing functionality.

### Fixed

- Bug fixes.

## [1.0.0] - YYYY-MM-DD

### Added

- First release.
````

## Mini-game source: `index.html`

The `index.html` below is a complete, runnable mini-game (Commit Catcher). Save it and open it in a browser, or publish it with the steps in [Publish with GitHub Pages](github-pages.md).

````html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Commit Catcher · GitHub Workshop</title>
<style>
:root{--bg:#010409;--panel:#0d1117;--line:#30363d;--text:#e6edf3;--muted:#8b949e;--green:#2ea44f;--gold:#d29922;--red:#cf222e}
*{box-sizing:border-box}
body{margin:0;min-height:100vh;display:grid;place-items:center;background:radial-gradient(circle at 50% 0,#161b22 0,var(--bg) 55%);color:var(--text);font:16px/1.5 system-ui,-apple-system,"Segoe UI","Noto Sans SC",sans-serif}
main{width:min(960px,100%);padding:20px}
header{display:flex;align-items:center;justify-content:space-between;gap:12px;flex-wrap:wrap;margin-bottom:12px}
.brand{display:flex;align-items:baseline;gap:8px}
.brand b{font-size:20px}
.brand span{color:var(--muted);font-size:13px}
.hud{display:flex;align-items:center;gap:16px;font-size:14px;color:var(--muted)}
.hud b{color:var(--text);font-variant-numeric:tabular-nums}
#lives{letter-spacing:2px;color:var(--red)}
#mute{border:1px solid var(--line);background:var(--panel);color:var(--text);border-radius:8px;padding:3px 8px;cursor:pointer}
.stage{position:relative;border:1px solid var(--line);border-radius:14px;overflow:hidden;background:var(--panel);box-shadow:0 20px 60px rgba(0,0,0,.45)}
canvas{display:block;width:100%;height:auto;aspect-ratio:900/540;touch-action:none;cursor:crosshair}
#overlay{position:absolute;inset:0;display:grid;place-items:center;background:rgba(1,4,9,.72);backdrop-filter:blur(4px);opacity:0;pointer-events:none;transition:opacity .2s}
#overlay.show{opacity:1;pointer-events:auto}
.panel{width:min(440px,86%);padding:26px;text-align:center;background:rgba(13,17,23,.94);border:1px solid var(--line);border-radius:16px;box-shadow:0 12px 40px rgba(0,0,0,.5)}
.panel h1{margin:0 0 10px;font-size:30px;letter-spacing:.5px}
.panel p{margin:0 0 18px;color:var(--muted);font-size:14px}
kbd{border:1px solid var(--line);border-bottom-width:2px;border-radius:5px;padding:1px 6px;background:#161b22;color:var(--text);font:inherit;font-size:12px}
button.play{border:0;border-radius:10px;padding:11px 30px;background:var(--green);color:#fff;font:inherit;font-weight:700;cursor:pointer}
button.play:hover{filter:brightness(1.12)}
button.play:focus-visible{outline:2px solid #58a6ff;outline-offset:2px}
footer{display:flex;justify-content:space-between;gap:10px;flex-wrap:wrap;margin-top:10px;color:var(--muted);font-size:12px}
.legend{display:flex;gap:12px}
.legend .c{color:var(--green)}.legend .s{color:var(--gold)}.legend .b{color:var(--red)}
@media(max-width:560px){.brand span{display:none}.hud{gap:10px;font-size:13px}}
</style>
</head>
<body>
<main>
  <header>
    <div class="brand"><b>Commit Catcher</b><span>GitHub Workshop · 提交捕手</span></div>
    <div class="hud">
      <span>得分 <b id="score">0</b></span>
      <span>最佳 <b id="best">0</b></span>
      <span id="lives" aria-label="剩余生命">❤❤❤</span>
      <button id="mute" type="button" aria-label="开关音效">🔊</button>
    </div>
  </header>
  <div class="stage">
    <canvas id="game" width="900" height="540" aria-label="Commit Catcher 游戏画面"></canvas>
    <div id="overlay" class="show">
      <div class="panel">
        <h1 id="ovTitle">提交捕手</h1>
        <p id="ovText">用 <kbd>←</kbd> <kbd>→</kbd> 或 <kbd>A</kbd> <kbd>D</kbd> 移动 Octocat，也可以直接用鼠标或手指。<br>接住 <b style="color:#2ea44f">commit</b> 和 <b style="color:#d29922">star</b>，躲开 <b style="color:#cf222e">bug</b>；你有 3 条命。</p>
        <button class="play" id="startBtn" type="button">开始游戏</button>
      </div>
    </div>
  </div>
  <footer>
    <div class="legend"><span class="c">● commit +10</span><span class="s">★ star +30</span><span class="b">✗ bug −1 命</span></div>
    <div><kbd>P</kbd> / <kbd>Esc</kbd> 暂停 · 最高分保存在本地</div>
  </footer>
</main>
<script>
const cv = document.getElementById('game');
const g = cv.getContext('2d');
const W = 900, H = 540;
const scoreEl = document.getElementById('score');
const bestEl = document.getElementById('best');
const livesEl = document.getElementById('lives');
const overlay = document.getElementById('overlay');
const ovTitle = document.getElementById('ovTitle');
const ovText = document.getElementById('ovText');
const btn = document.getElementById('startBtn');
const mute = document.getElementById('mute');
const KINDS = {
  commit: { pts: 10, color: '#2ea44f', label: '+', r: 17 },
  star:   { pts: 30, color: '#d29922', label: '★', r: 18 },
  bug:    { pts: 0,  color: '#cf222e', label: '✗', r: 19 }
};
const player = { x: W / 2, y: H - 58, tx: W / 2 };
const items = [], parts = [], keys = new Set();
let state = 'ready', score = 0, lives = 3, t = 0, spawn = 0, shake = 0, soundOn = true, ac = null;
let best = 0;
try { best = +localStorage.getItem('commit-catcher-best') || 0; } catch (e) {}
bestEl.textContent = best;
function beep(freq, dur = .07, type = 'sine', vol = .045) {
  if (!soundOn) return;
  try {
    ac = ac || new (window.AudioContext || window.webkitAudioContext)();
    const o = ac.createOscillator(), gn = ac.createGain();
    o.type = type; o.frequency.value = freq; gn.gain.value = vol;
    o.connect(gn).connect(ac.destination);
    gn.gain.exponentialRampToValueAtTime(.0001, ac.currentTime + dur);
    o.start(); o.stop(ac.currentTime + dur);
  } catch (e) {}
}
function setOverlay(title, text, label) {
  ovTitle.textContent = title;
  ovText.innerHTML = text;
  btn.textContent = label;
  overlay.classList.add('show');
}
function syncHud() {
  scoreEl.textContent = score;
  livesEl.textContent = '❤'.repeat(lives) + '♡'.repeat(3 - lives);
}
function start() {
  score = 0; lives = 3; t = 0; spawn = 0; shake = 0;
  items.length = 0; parts.length = 0; player.x = player.tx = W / 2;
  state = 'playing';
  overlay.classList.remove('show');
  syncHud();
}
function gameOver() {
  state = 'over';
  if (score > best) {
    best = score;
    try { localStorage.setItem('commit-catcher-best', best); } catch (e) {}
  }
  bestEl.textContent = best;
  setOverlay('游戏结束', '得分 <b>' + score + '</b> · 最佳 <b>' + best + '</b><br>再来一局？', '再来一局');
  beep(110, .3, 'sawtooth', .06);
}
function togglePause() {
  if (state === 'playing') {
    state = 'paused';
    setOverlay('已暂停', '按 <kbd>P</kbd> 或点击按钮继续', '继续游戏');
  } else if (state === 'paused') {
    state = 'playing';
    overlay.classList.remove('show');
  }
}
function spawnItem() {
  const r = Math.random();
  const kind = r < .08 ? 'star' : r < .35 ? 'bug' : 'commit';
  const diff = Math.min(1, score / 350);
  items.push({
    kind, x: 40 + Math.random() * (W - 80), y: -30,
    vy: 100 + diff * 150 + Math.random() * 45,
    rot: 0, vr: (Math.random() - .5) * 2, r: KINDS[kind].r
  });
}
function burst(x, y, color, n = 10) {
  for (let i = 0; i < n; i++) {
    const a = Math.random() * Math.PI * 2, s = 60 + Math.random() * 180;
    parts.push({ x, y, vx: Math.cos(a) * s, vy: Math.sin(a) * s, life: .55, color });
  }
}
function update(dt) {
  t += dt; spawn -= dt;
  const diff = Math.min(1, score / 350);
  if (spawn <= 0) { spawnItem(); spawn = .62 - diff * .32; }
  let dir = 0;
  if (keys.has('ArrowLeft') || keys.has('a') || keys.has('A')) dir--;
  if (keys.has('ArrowRight') || keys.has('d') || keys.has('D')) dir++;
  if (dir) {
    player.x += dir * 520 * dt;
    player.tx = player.x;
  } else {
    player.x += (player.tx - player.x) * Math.min(1, dt * 12);
  }
  player.x = Math.max(38, Math.min(W - 38, player.x));
  for (let i = items.length - 1; i >= 0; i--) {
    const it = items[i];
    it.y += it.vy * dt; it.rot += it.vr * dt;
    if (it.y > H + 40) { items.splice(i, 1); continue; }
    if (it.y > H - 92 && Math.hypot(it.x - player.x, it.y - player.y) < it.r + 25) {
      items.splice(i, 1);
      if (it.kind === 'bug') {
        lives--; shake = .35; burst(it.x, it.y, it.color, 14);
        beep(120, .18, 'sawtooth', .06); syncHud();
        if (lives <= 0) { gameOver(); return; }
      } else {
        score += KINDS[it.kind].pts;
        burst(it.x, it.y, it.color);
        beep(it.kind === 'star' ? 880 : 660, .06, 'triangle', .04);
        syncHud();
      }
    }
  }
  for (let i = parts.length - 1; i >= 0; i--) {
    const p = parts[i];
    p.life -= dt; p.x += p.vx * dt; p.y += p.vy * dt; p.vy += 300 * dt;
    if (p.life <= 0) parts.splice(i, 1);
  }
  if (shake > 0) shake -= dt;
}
function drawBg() {
  const grd = g.createLinearGradient(0, 0, 0, H);
  grd.addColorStop(0, '#0b1220'); grd.addColorStop(1, '#010409');
  g.fillStyle = grd; g.fillRect(0, 0, W, H);
  g.strokeStyle = 'rgba(48,54,61,.5)'; g.lineWidth = 1;
  for (let y = 0; y < H; y += 45) { g.beginPath(); g.moveTo(0, y + .5); g.lineTo(W, y + .5); g.stroke(); }
  for (let x = 0; x < W; x += 45) { g.beginPath(); g.moveTo(x + .5, 0); g.lineTo(x + .5, H); g.stroke(); }
  const colors = ['#2ea44f', '#8957e5', '#d29922'];
  g.globalAlpha = .12;
  for (let i = 0; i < 3; i++) {
    g.strokeStyle = colors[i]; g.lineWidth = 3;
    g.beginPath(); g.moveTo(0, 120 + i * 150);
    g.bezierCurveTo(300, 40 + i * 150, 600, 260 + i * 140, W, 90 + i * 160);
    g.stroke();
  }
  g.globalAlpha = 1;
}
function drawCat() {
  const bob = state === 'playing' ? Math.sin(t * 7) * 2 : 0;
  g.save(); g.translate(player.x, player.y + bob);
  g.fillStyle = 'rgba(0,0,0,.35)';
  g.beginPath(); g.ellipse(0, 36, 30, 7, 0, 0, 7); g.fill();
  g.fillStyle = '#e6edf3'; g.strokeStyle = '#8b949e'; g.lineWidth = 2;
  g.beginPath(); g.moveTo(-26, -14); g.lineTo(-19, -36); g.lineTo(-6, -20); g.closePath(); g.fill(); g.stroke();
  g.beginPath(); g.moveTo(26, -14); g.lineTo(19, -36); g.lineTo(6, -20); g.closePath(); g.fill(); g.stroke();
  g.beginPath(); g.arc(0, 0, 28, 0, 7); g.fill(); g.stroke();
  g.fillStyle = '#0d1117';
  g.beginPath(); g.arc(-10, -3, 4, 0, 7); g.fill();
  g.beginPath(); g.arc(10, -3, 4, 0, 7); g.fill();
  g.fillStyle = '#f9826c';
  g.beginPath(); g.moveTo(0, 6); g.lineTo(-5, 10); g.lineTo(5, 10); g.closePath(); g.fill();
  g.strokeStyle = '#57606a'; g.lineWidth = 1.5;
  [-1, 1].forEach(s => {
    g.beginPath(); g.moveTo(s * 6, 10); g.lineTo(s * 20, 10);
    g.moveTo(s * 6, 13); g.lineTo(s * 20, 16); g.stroke();
  });
  g.strokeStyle = '#2ea44f'; g.lineWidth = 5;
  g.beginPath(); g.arc(0, 0, 28, Math.PI * 1.18, Math.PI * 1.82); g.stroke();
  g.restore();
}
function drawItem(it) {
  const k = KINDS[it.kind];
  g.save(); g.translate(it.x, it.y); g.rotate(it.rot);
  g.shadowColor = k.color; g.shadowBlur = 16;
  g.fillStyle = k.color; g.beginPath(); g.arc(0, 0, it.r, 0, 7); g.fill();
  g.shadowBlur = 0; g.strokeStyle = 'rgba(255,255,255,.65)'; g.lineWidth = 1.5; g.stroke();
  g.fillStyle = '#fff'; g.font = '700 ' + it.r + 'px system-ui,sans-serif';
  g.textAlign = 'center'; g.textBaseline = 'middle'; g.fillText(k.label, 0, 1);
  g.restore();
}
function draw() {
  g.save();
  if (shake > 0) g.translate((Math.random() - .5) * 12 * shake, (Math.random() - .5) * 12 * shake);
  drawBg();
  items.forEach(drawItem);
  parts.forEach(p => {
    g.globalAlpha = Math.max(0, p.life / .55);
    g.fillStyle = p.color; g.beginPath(); g.arc(p.x, p.y, 3, 0, 7); g.fill();
  });
  g.globalAlpha = 1;
  drawCat();
  g.restore();
}
let last = performance.now();
function frame(now) {
  const dt = Math.min(.033, (now - last) / 1000);
  last = now;
  if (state === 'playing') update(dt);
  draw();
  requestAnimationFrame(frame);
}
requestAnimationFrame(frame);
btn.addEventListener('click', () => {
  if (state === 'paused') { state = 'playing'; overlay.classList.remove('show'); }
  else start();
});
mute.addEventListener('click', () => {
  soundOn = !soundOn;
  mute.textContent = soundOn ? '🔊' : '🔇';
  mute.setAttribute('aria-pressed', String(!soundOn));
});
addEventListener('keydown', e => {
  const k = e.key;
  if (['ArrowLeft', 'ArrowRight', ' '].includes(k)) e.preventDefault();
  if (k === 'p' || k === 'P' || k === 'Escape') { togglePause(); return; }
  if (k === ' ' || k === 'Enter') {
    if (state === 'ready' || state === 'over') start();
    return;
  }
  keys.add(k);
});
addEventListener('keyup', e => keys.delete(e.key));
addEventListener('blur', () => keys.clear());
cv.addEventListener('pointermove', e => {
  const r = cv.getBoundingClientRect();
  player.tx = Math.max(38, Math.min(W - 38, (e.clientX - r.left) * W / r.width));
});
cv.addEventListener('pointerdown', e => {
  const r = cv.getBoundingClientRect();
  player.tx = Math.max(38, Math.min(W - 38, (e.clientX - r.left) * W / r.width));
  if (state === 'ready' || state === 'over') start();
});
document.addEventListener('visibilitychange', () => {
  if (document.hidden && state === 'playing') togglePause();
});
syncHud();
</script>
</body>
</html>
````
