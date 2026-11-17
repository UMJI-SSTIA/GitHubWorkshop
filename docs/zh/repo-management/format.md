---
title: 格式模板
description: 按 workshop 讲稿整理的 README、CONTRIBUTING、LICENSE、Issue、Pull Request 与 index.html 模板，另附 CHANGELOG 模板和小游戏完整源码。
discussions: true
---

# 格式模板

本页按照 workshop 讲稿第 3–6 章整理，收录创建和维护仓库时最常用的模板，并补充一个通用的 CHANGELOG 模板。把代码块复制到对应路径，替换 `<...>` 占位符即可使用。

## 推荐仓库结构

讲稿附录 C 建议的演示仓库如下：

```text
github-workshop-demo/
├── README.md
├── LICENSE                   # MIT
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── contributors.md           # 练习用表格
└── .github/
    ├── ISSUE_TEMPLATE/
    │   └── bug_report.md
    └── PULL_REQUEST_TEMPLATE.md
```

`.github/` 目录还可以放 `feature_request.md` 和 `workflows/`（CI 配置）。

## README.md

一个好的 README 回答四个问题：这是什么、能干什么、怎么装、怎么用。

````markdown
# 项目名

> 一句话说明这个项目解决什么问题。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## 特性

- 特性一
- 特性二

## 安装

```bash
git clone https://github.com/<用户名>/<仓库名>.git
cd <仓库名>
npm install
```

## 快速开始

```bash
npm start
```

## 使用示例

```python
from mylib import hello
hello()
```

## 贡献

欢迎提交 Issue 和 Pull Request，请先阅读 [CONTRIBUTING.md](CONTRIBUTING.md)。

## 许可证

本项目采用 [MIT](LICENSE) 许可证。
````

## CONTRIBUTING.md

`LICENSE` 回答“你能不能改”，`CONTRIBUTING.md` 回答“你该怎么改”。

````markdown
# 贡献指南

感谢你愿意贡献！

## 开发环境

- Node.js >= 20
- 安装依赖：`npm install`
- 运行测试：`npm test`

## 分支与提交

- 分支命名：`feat/xxx`、`fix/xxx`、`docs/xxx`
- 提交信息遵循 Conventional Commits，例如 `fix: 修复登录超时`
- 提交前请确保 `npm test` 通过

## 提交 PR

1. Fork 本仓库并 clone 到本地
2. 从最新的 `main` 新建分支
3. 修改代码并提交
4. 推送分支，创建 PR，并关联相关 Issue

## 行为准则

参与本项目即表示同意遵守 [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md)。
````

## LICENSE

不要手写许可证正文，用 GitHub 的模板。常见许可证怎么选：

| 许可证 | 特点 | 适合 |
| --- | --- | --- |
| MIT | 最短最宽松，保留版权声明即可 | 个人项目、库、希望被广泛使用 |
| Apache-2.0 | MIT + 明确的专利授权 | 企业项目、涉及专利风险 |
| GPL-3.0 | 衍生作品必须同样开源（传染性） | 希望强制开源 |
| BSD-3-Clause | 类似 MIT，多一条禁止用作者名义背书 | 学术、基础设施 |
| CC0 / Unlicense | 放弃版权，进入公共领域 | 示例代码、数据集 |

给已有仓库添加 license：

1. 仓库页 → **Add file** → **Create new file**
2. 文件名输入 `LICENSE`
3. 右侧会出现 **Choose a license template**
4. 选 MIT → 填年份和作者 → **Review and submit**

在 README 里写一句“本项目采用 MIT 许可证”，并链接到 `LICENSE` 文件。多人贡献后再换 license，理论上需要所有贡献者同意。

## index.html

`index.html` 是网页项目的默认入口文件；开启 GitHub Pages 后，仓库会变成一个可访问的网站。最小示例：

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
about: 报告一个问题
title: "[Bug] "
labels: bug
---

## 描述

## 复现步骤

1.
2.
3.

## 期望结果

## 实际结果

## 环境

- OS:
- 版本:
- 浏览器/运行时:

## 日志 / 截图
````

## .github/PULL_REQUEST_TEMPLATE.md

````markdown
## 这个 PR 做了什么

## 关联 Issue

Closes #

## 测试方式

## 检查清单

- [ ] 已本地测试
- [ ] 已更新文档
- [ ] 提交信息符合规范
- [ ] 没有夹带无关改动
````

## contributors.md

````markdown
# 贡献者

| 姓名 | GitHub | 一句话 |
|------|--------|--------|
| 讲师 | @<讲师用户名> | 示例行 |
````

## Markdown 速查

- 标题：`# 一级`、`## 二级`
- 粗体 / 斜体：`**粗体**`、`*斜体*`
- 列表：`- 项目`
- 链接：`[文字](https://...)`
- 图片：`![说明](docs/screenshot.png)`
- 行内代码：`` `code` ``
- 代码块：三个反引号 + 语言名
- 引用：`> 引用`
- 表格：`| A | B |`
- 任务列表：`- [x] 已完成`

## CHANGELOG.md

````markdown
# 更新日志

所有值得记录的改动都写在这里。

格式参考 [Keep a Changelog](https://keepachangelog.com/zh-CN/1.1.0/)，版本号遵循 [Semantic Versioning](https://semver.org/lang/zh-CN/)。

## [Unreleased]

### Added

- 新增的功能。

### Changed

- 对现有功能的调整。

### Fixed

- 修复的问题。

## [1.0.0] - YYYY-MM-DD

### Added

- 第一个正式版本。
````

## 小游戏完整源码：`index.html`

下面的 `index.html` 是一个可直接运行的完整小游戏（Commit Catcher）。保存后双击打开，或按[用 GitHub Pages 发布网页](github-pages.md)中的步骤发布。

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
