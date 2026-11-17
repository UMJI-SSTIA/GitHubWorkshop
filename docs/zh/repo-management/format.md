---
title: 格式模板
description: 可直接复制的 README、CONTRIBUTING、CHANGELOG、SECURITY 格式模板，以及 Commit Catcher 小游戏的完整源码。
discussions: true
---

# 格式模板

本页收集了本 workshop 使用的仓库级 Markdown 模板，以及 **Commit Catcher（提交捕手）** 小游戏的完整源码。可以把下面的代码块直接复制到自己的仓库中，再按项目情况修改。

!!! tip "使用说明"
    发布前请把项目名和占位符替换成自己的内容。GitHub 会自动在仓库首页展示根目录下的 `README.md`，并在对应位置展示 `CONTRIBUTING.md`、`CHANGELOG.md` 和 `SECURITY.md`。下面的模板正文为英文，可以按需翻译。

## README.md 模板

````markdown
# GitHub Workshop

<div markdown="1" style="text-align: center; margin: 2rem 0;">

![GitHub logo](/docs/assets/images/GitHub_Lockup_Black.svg)

</div>

![Static Badge](https://img.shields.io/badge/SJTU_SSTIA-blue)
![Static Badge](https://img.shields.io/badge/GitHub_Workshop-purple?logo=github)
![Static Badge](https://img.shields.io/badge/license-MIT-green)

## A great way to get into GitHub

This beginner-friendly GitHub workshop was created by SSTIA. It has two parts: first, you will explore GitHub and the open-source community while learning how to find, evaluate, and download repositories; then, you will create and maintain a repository and experience the complete open-source collaboration workflow.

By the end of the workshop, you will be able to:

- Find open-source projects and decide whether they are suitable for use;
- Create repositories and use Git to commit and push code;
- Collaborate through forks, issues, and pull requests;
- Write a README, choose an open-source license, and publish a website with GitHub Pages.

## How this repository helps you understand the workshop

- The worksheet is published on the workshop website, so you can read it when you cannot catch up with the lecture or want to work ahead.
- Each part of the worksheet has a discussion board, so you can ask questions there and we will be glad to answer them.
- The repository includes links and pictures that help you understand GitHub.
- Other unexpected surprises are waiting for you to explore. :)

## Get started

```text
Open the deployed website and follow the instructions there, or follow the lecture.
```

## The worksheet link

```text
https://umji-sstia.github.io/GitHubWorkshop/
```

## License

```text
This repository uses the MIT license, so you can use it for commercial purposes (though we don't think you will).
```

## Thanks

```text
SJTU GC College SSTIA
Everyone who contributed to or attended this workshop
```

<div markdown="1" style="text-align: center; margin: 2rem 0;">

![SSTIA logo](/docs/assets/favicon.svg)

</div>
````

## CONTRIBUTING.md 模板

````markdown
# Contributing

The repository is a documentation template, so most contributions are content or configuration changes. All contributions are welcome: bug reports, new teaching pages, translations, and configuration improvements.

## Getting started

1. Open an issue first to describe the change. This avoids work on a design the maintainers would not accept.
2. Fork the repository and create a feature branch from `main`.
3. Set up a local preview:

    ```bash
    python3 -m venv .venv
    source .venv/bin/activate        # Windows: .venv\Scripts\activate
    pip install -r requirements.txt
    mkdocs serve
    ```

4. Make the change, then verify the build:

    ```bash
    mkdocs build --strict
    ```

The health check workflow runs the same command on every pull request; broken links or unresolved files fail CI.

## Content conventions

- **Bilingual pages**: every page exists twice — `docs/en/<path>.md` (default language) and `docs/zh/<path>.md` (translation) — with the same relative path. If the Chinese file is missing, the site falls back to the English content; merged changes are expected to include both versions.
- **Navigation**: new pages are registered in `nav` in `mkdocs.yml`, and their Chinese titles are added to `nav_translations` under the `zh` language entry. Pages not listed in `nav` are not built.
- **Assets**: shared files go in `docs/assets/` — images in `docs/assets/images/`, videos in `docs/assets/videos/`. Everything under `docs/` is published, so do not commit private files there.
- **Frontmatter**: each page carries a `title` and a `description`. Pages with a comment thread add `discussions: true`.
- **Style**: the documentation is written in a neutral, official tone. Avoid decorative emoji and casual phrasing.

## Commit messages

Follow the convention used in the repository history:

- `feat:` — new functionality or pages
- `fix:` — bug fixes
- `chore:` — maintenance and configuration
- `deploy:` — site deployments (generated)

## Pull requests

- Target the `main` branch.
- Describe the change and, for content changes, confirm that both language versions were updated.
- Keep the strict build warning-free: the build log should not contain warnings about unresolved links or missing translations.
````

## CHANGELOG.md 模板

````markdown
# Changelog

All notable changes to this project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Changed

- Split the workshop drafts (`Demo/Part1.md`, `Demo/Part2.md`) into per-topic pages under `github-introduction/` and `repo-management/` in both English and Chinese (including a new guide on GitHub Issues), and reorganized the navigation accordingly.

## [0.1.1] - 2026-10-29

### Changed

- Bump `mkdocs-material` from `9.7.0` to `9.8.0`.

### Security

- Update `mkdocs-material` to 9.8.0 to include fixes for known vulnerabilities, including the `search.suggest` DOM XSS issue (CVE-2026-73295) and dependency-level CVEs in Jinja2, Markdown, Pygments, PyMdown Extensions, Requests, Pillow, CairoSVG, and GitPython.

## [0.1.0] - 2026-10-28

Initial release.

### Added

- MkDocs and Material for MkDocs setup with pinned Python dependencies (`requirements.txt`)
- GitHub Actions automation: build and deployment to GitHub Pages on every push to `main` (`publish_site.yaml`), and a `mkdocs build --strict` health check on pull requests (`health_check.yaml`)
- Bilingual site structure (English / 简体中文) via mkdocs-static-i18n: per-language navigation translations (`nav_translations`), header language switcher, Chinese UI strings, and fallback to the default language for untranslated pages
- Per-page discussion board powered by giscus and GitHub Discussions, enabled by frontmatter and synchronized with the site's light/dark theme
- Media support: image embedding with sizing and captions, video embedding via the mkdocs-video plugin, with bundled demo assets (`image_demo.png`, `video_demo.mp4`)
- Markdown extensions: tables, task lists, content tabs, admonitions, emoji, LaTeX math, Mermaid diagrams, and raw HTML
- Theme configuration: light/dark color palettes, Material color schemes, logo and favicon
- Build hooks: `sitemap.xml` copied into language subdirectories after each build
- Complete bilingual documentation: introduction, deployment, repository structure, page authoring, Markdown reference, theming, media, internationalization, discussion board, and customization
- Embedded Snake game demo illustrating interactive HTML/CSS/JS widgets
- Project files: README, CONTRIBUTING, SECURITY
- MIT license

[Unreleased]: https://github.com/CedricHaskell/WorkshopTemplate/compare/v0.1.0...HEAD
[0.1.0]: https://github.com/CedricHaskell/WorkshopTemplate/releases/tag/v0.1.0
````

## SECURITY.md 模板

````markdown
# Security

## Reporting a vulnerability

To report a security issue in this template, use the GitHub **Report a vulnerability** flow (Security tab → Advisories) on this repository. DON'T open an issue and make it visible to everyone.

Include a description of the issue, the affected files, and — if possible — a minimal reproduction. Do not include sensitive data in public reports.

## Scope

The template consists of static configuration and content; it contains no server-side code. In scope:

- `mkdocs.yml` and the build configuration
- `docs/scripts/hooks.py` and the templates under `docs/overrides/`
- `.github/workflows/`
- Markdown content that embeds executable JavaScript (e.g. the game demo)

Out of scope: GitHub Pages infrastructure, GitHub Actions runners, and third-party projects (MkDocs, Material for MkDocs, giscus, MathJax, Mermaid, and the plugins listed in `requirements.txt`). Vulnerabilities in those projects should be reported to their maintainers.

## Guidance for adopters

Sites built from this template inherit the following properties:

- The published site is static HTML/CSS/JS and exposes no server-side attack surface.
- Comments are served by a third-party iframe from giscus.app and stored as GitHub Discussions in the configured repository.
- Embedded widgets execute in visitors' browsers. Do not embed secrets, API keys, or other credentials in Markdown pages or in `docs/assets/` — everything under `docs/` is published.
- Python dependencies are pinned in `requirements.txt`. Enabling Dependabot version updates is recommended to receive security fixes.
- The deploy workflow uses the built-in `GITHUB_TOKEN`, scoped to the repository by `permissions: contents: write`. Keep the repository's Actions setting at read/write as documented in the deployment guide.
- The discussion board (giscus) requires a public repository. Do not enable it for private or internal-only workshops.

## Supported versions

Only the latest commit on the `main` branch is supported. There is no backporting or long-term support policy.
````

## 小游戏源码：`index.html`

小游戏是一个单文件 HTML，CSS 和 JavaScript 都内联在文件中。把下面的代码保存为 `index.html`，用浏览器打开即可运行；也可以按[用 GitHub Pages 发布网页](github-pages.md)中的步骤发布。

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
