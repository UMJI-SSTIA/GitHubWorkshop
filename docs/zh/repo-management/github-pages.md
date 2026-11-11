---
title: 用 GitHub Pages 发布网页
description: 用 GitHub Pages 把仓库变成免费托管的静态网站：可以放 index.html、用 Jekyll，或使用 MkDocs 等静态站点生成器。
discussions: true
---

# 怎么用 GitHub Pages 发布网页

**GitHub Pages** 可以把仓库变成一个免费托管的静态网站。

1. 打开仓库 → **Settings** → 左侧 **Pages**。
2. 在 **Build and deployment** 下，**Source** 选择 **Deploy from a branch**。
3. 选择分支（通常选 `main`）和目录（根目录 `/` 或 `/docs`），点 **Save**。
4. 等几十秒，页面会给出你的网址：`https://你的用户名.github.io/仓库名/`。

内容来源：

- 最简单的做法：在仓库根目录放一个 `index.html`，这就是首页。
- 也可以使用 Jekyll（GitHub 内置支持）来自动生成博客风格的页面，选一个主题即可。
- 还有一种"用户主页"型：创建名为 `你的用户名.github.io` 的仓库，网址就是 `https://你的用户名.github.io/`。

!!! tip
    如果你不想纯手写 HTML，还可以用 **MkDocs**（本 workshop 网站就是用 MkDocs 搭建的）或 **Hugo** 等工具从 Markdown 生成静态网站，再同样发布到 GitHub Pages 上。

**常见问题：**

- 第一次部署大约需要一分钟，可以在仓库的 **Actions** 标签页查看进度。
- 如果网站返回 404，检查 **Source** 是否选了 **Deploy from a branch**，以及所选分支和目录是否正确。
- 之后向所选分支推送新提交，GitHub Pages 会自动重新构建网站。

!!! note "两个要知道的点"
    - **只能用于公开仓库**：免费账号只能从公开仓库发布 Pages（私有仓库需要 GitHub Pro）。
    - **自定义域名**：在 **Settings → Pages** 里可以绑定你自己的域名，GitHub 还会自动签发免费的 HTTPS 证书。
