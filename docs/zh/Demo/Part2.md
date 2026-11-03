---
title: Part2
description: GitHub仓库的使用
---

# Github 仓库的使用
> **作者：** 张峻铭  
> **日期：** 2026.11.01    
> **状态：** 草稿
---

## 1. 如何创建一个仓库

1. 登录 [github.com](https://github.com)，点击右上角的 **`+`** 图标，选择 **New repository**（新建仓库）。
2. 填写信息：
   - **Repository name**（仓库名）：必填，例如 `my-first-project`。
   - **Description**（描述）：可选，简单说明这个仓库是干什么的。
   - **Public / Private**：公开仓库任何人都能看；私有仓库只有自己和被邀请的人能看。
   - **Add a README file**：建议勾选，自动生成一个 `README.md`。
   - **Add .gitignore**：可选，根据你用的语言（C/C++、Python 等）忽略不需要上传的文件。
   - **Choose a license**：可选，选择开源许可证（见第 2 节）。
3. 点击 **Create repository** 完成创建。

创建之后，你有两种方式往仓库里放代码：
- **网页操作**：点 **Add file → Upload files** 直接拖拽上传。
- **本地 Git**：复制仓库地址，在终端执行：

```bash
git clone https://github.com/你的用户名/仓库名.git
# 放入文件后
git add .
git commit -m "first commit"
git push
```

当然如果你的电脑没有配置过 username 和 email， 你无法 commit， 所以你需要 ( 如果你不想全局配置，只想配置这一个仓库，删掉 --global)：
```bash
git config --global user.name <你的名字，自己想一个>
git config --global user.email <邮箱>
git config --list #用于确认你的配置状态
```

---

## 2. License 是什么

**License（许可证）** 是一份法律声明，规定别人可以怎样使用你的代码。它是开源项目里很重要的一部分：

| 许可证 | 特点 | 适用场景 |
| --- | --- | --- |
| **MIT** | 最宽松，别人可以随便用、改、商用，只需保留版权声明 | 大多数个人项目 |
| **Apache 2.0** | 宽松 + 明确专利授权 | 企业、需要专利保护 |
| **GPL** | “传染性”强，用了它就必须同样开源 | 希望衍生项目也开源 |
| **BSD** | 类似 MIT，条款略多 | 学院派项目 |

要点：
- **没有 license** 是默认“保留所有权利”，别人**不能合法地**复制或修改你的代码。
- 添加方法：创建仓库时直接选择，或之后点 **Add file → Create new file**，把文件名写成 `LICENSE.txt`，GitHub 会自动提供模板选择。

---

## 3. 如何 Fork 一个仓库

**Fork（分叉）** 就是把别人的仓库完整复制一份到你自己的账号下，之后你可以自由修改，而不会影响原仓库。

1. 打开你想 fork 的仓库页面。
2. 点击右上角的 **Fork** 按钮（一般在 Star 旁边）。
3. 选择目标账号（通常就是你自己），点击 **Create fork**。
4. 完成后，你账号下就会出现一份同名仓库，标注了 “forked from 原作者/原仓库”。

拿到 fork 后，把它克隆到本地：

```bash
git clone https://github.com/你的用户名/仓库名.git
```

用途：想在别人项目基础上二次开发、学习源码、或者准备给原项目提 Pull Request（见第 4 节）。

---

## 4. 如何 Contribute 一个仓库

贡献的核心流程是 **Fork → 修改 → Pull Request（PR）**：

1. **Fork** 目标仓库（第 3 节）。
2. 克隆自己的 fork 到本地：

```bash
git clone https://github.com/你的用户名/仓库名.git
cd 仓库名
```

3. 新建一个分支，避免直接在 main 上改：

```bash
git checkout -b my-feature
```

4. 修改代码或文档，然后提交：（相信这些在 151 or 101 已经很熟练了）

```bash
git add .
git commit -m "描述你的改动"
git push origin my-feature
```
**[!]** 需要注意的是, 假设你的.gitignore里屏蔽了.o文件，但是仍然：
```bash
git add -f main.o
```
会导致强制添加，并把main.o当成已追踪文件，所以尽量不要写 ```-f```

5. 回到 GitHub 上你的 fork 页面，点击 **Contribute → Open pull request**。
6. 写清楚你改了什么、为什么改 (详细一点)，然后点 **Create pull request**。
7. 等待原仓库维护者 review（审查）；他们可能会提意见，你继续修改并 push 即可更新同一个 PR。

补充：
- 如果只是发现 bug 或提建议，可以直接在仓库的 **Issues** 页面提交 **New issue**，这也是贡献的一种方式,同时，你的 **Issue** 不要一两行带过，而是应该尽可能详细地阐明你的建议，bug的描述，和你的版本，环境等。
- 如果原仓库给了你写权限，可以跳过 fork，直接建分支改完提 PR。

---

## 5. 如何快速编辑一个仓库里的内容

不需要本地 Git，直接在网页上就能快速改：

1. 打开仓库里的某个文件，点击右上角的**铅笔图标（Edit this file）**。
2. 在编辑框里直接修改内容。
3. 滚动到页面底部，写一句简短的提交说明（Commit message），选择提交到当前分支或新分支。
4. 点 **Commit changes** 保存。

其他网页快捷操作：
- **新建文件**：Add file → Create new file。
- **上传文件**：Add file → Upload files。
- **删除文件**：打开文件 → 右上角垃圾桶图标 → Commit。

注意：网页编辑适合**小改动**（改个文档、修一行代码）。如果是大改动、需要本地编译测试，还是用第 4 节里的本地 Git 流程更合适。

---

## 6. README 怎么使用

**README.md** 是仓库打开后默认展示在首页的说明文档，用 **Markdown** 编写。它是别人了解你项目的“第一张名片”。

一份好的 README 通常包含：
- **项目简介**：一句话说明这个项目是做什么的。
- **安装方法**：环境依赖、如何安装。
- **使用方法**：怎么运行、示例代码。
- **许可证 / 贡献方式**：指向 LICENSE 或说明如何参与。

常用 Markdown 语法：

```markdown
# 一级标题
## 二级标题
- 列表项
**加粗**、*斜体*
`行内代码`
[链接文字](网址)
![图片描述](图片地址)

```代码块```
```

创建方法：新建仓库时勾选 “Add a README file”，或之后点 **Add file → Create new file**，文件名写 `README.md`。

---

## 7. 怎么建立仓库对应的网页（GitHub Pages）

**GitHub Pages** 可以把仓库变成一个免费托管的静态网站。

1. 打开仓库 → **Settings** → 左侧 **Pages**。
2. 在 **Build and deployment** 下，**Source** 选择 **Deploy from a branch**。
3. 选择分支（通常选 `main`）和目录（根目录 `/` 或 `/docs`），点 **Save**。
4. 等几十秒，页面会给出你的网址：`https://你的用户名.github.io/仓库名/`。

内容来源：
- 最简单的做法：在仓库根目录放一个 `index.html`，这就是首页。
- 也可以使用 Jekyll（GitHub 内置支持）来自动生成博客风格的页面，选一个主题即可。
- 还有一种“用户主页”型：创建名为 `你的用户名.github.io` 的仓库，网址就是 `https://你的用户名.github.io/`。

---

## 8. 以上步骤对应的实践过程

**先用第 1 步建仓库 → 用第 2、6 步把项目弄清楚 → 需要别人代码时用第 3 步 Fork → 参与协作时走第 4 步 PR → 平时小改动用第 5 步 → 项目成熟后可以用第 7 步搭个网页展示**。

---
