---
title: 在网页上快速编辑
description: 不用本地 Git，直接在浏览器里快速修改仓库内容：编辑、新建、上传、删除文件。
discussions: true
---

# 如何快速编辑一个仓库里的内容

不需要本地 Git，直接在网页上就能快速改：

1. 打开仓库里的某个文件，点击右上角的**铅笔图标（Edit this file）**。
2. 在编辑框里直接修改内容。
3. 滚动到页面底部，写一句简短的提交说明（Commit message），选择提交到当前分支或新分支。
4. 点 **Commit changes** 保存。

其他网页快捷操作：

- **新建文件**：Add file → Create new file。
- **上传文件**：Add file → Upload files。
- **删除文件**：打开文件 → 右上角垃圾桶图标 → Commit。

!!! note
    网页编辑适合**小改动**（改个文档、修一行代码）。如果是大改动、需要本地编译测试，还是用 [通过 Pull Request 参与贡献](contribute.md)里的本地 Git 流程更合适。

!!! tip "更快的办法：网页版编辑器"
    在任意仓库页面按下键盘上的 `.`（英文句号），就会在浏览器中打开 **github.dev**——一个运行在浏览器里的完整 VS Code 编辑器，不用克隆就能浏览、编辑代码，非常方便。

!!! tip "编辑的同时直接发起 PR"
    网页编辑提交时，可以选择 **Create a new branch for this commit and start a pull request**——GitHub 会直接帮你创建分支并打开一个 Pull Request。给别人仓库提小修复时，这是非常常用的方式。
