---
title: Fork 一个仓库
description: Fork 是什么？把任意公开仓库完整复制到自己的账号下，再克隆到本地，用于学习源码或二次开发。
discussions: true
---

# 如何 Fork 一个仓库

**Fork（分叉）** 就是把别人的仓库完整复制一份到你自己的账号下，之后你可以自由修改，而不会影响原仓库。

1. 打开你想 fork 的仓库页面。
2. 点击右上角的 **Fork** 按钮（一般在 Star 旁边）。
3. 选择目标账号（通常就是你自己），点击 **Create fork**。
4. 完成后，你账号下就会出现一份同名仓库，标注了 "forked from 原作者/原仓库"。

拿到 fork 后，把它克隆到本地：

```bash
git clone https://github.com/你的用户名/仓库名.git
```

!!! note "Fork 与 clone 的区别"
    **Fork** 发生在 GitHub 上：整个仓库被复制到你自己的账号下，成为一个新的远端仓库；而 `git clone` 是把仓库下载到你的本地电脑。要在一个 fork 上开发，通常是两者都做：先 fork，再克隆*你自己的 fork*。

每个仓库页面上三个按钮的快速对比：

| 按钮 | 作用 | 典型用途 |
| --- | --- | --- |
| **Star** ⭐ | 把仓库收藏到自己的列表 | 标记"以后再看"，也是对作者的肯定 |
| **Watch** 👁 | 订阅仓库的动态通知 | 关注项目的新版本和讨论 |
| **Fork** | 把仓库复制到自己账号下 | 修改代码或准备提 Pull Request |

用途：想在别人项目基础上二次开发、学习源码、或者准备给原项目提 Pull Request（见 [通过 Pull Request 参与贡献](contribute.md)）。如果打算给原项目提交修复，建议先开 Issue 沟通——见 [用 Issue 反馈问题](issues.md)。

!!! tip "Fork 不会自动跟随原仓库更新"
    你的 fork 只是 fork 那一刻的快照。原仓库更新后，你的 fork **不会**自动同步——如何通过 `upstream` 同步见 [通过 Pull Request 参与贡献](contribute.md)。另外，公开仓库任何人都可以随意 fork，而私有仓库不能被别人 fork。
