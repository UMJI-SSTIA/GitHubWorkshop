---
title: 用 Issue 反馈问题
description: Issue 是什么？学习如何正确地报告 bug、提出功能请求，以及 Issue 的标签、模板和关闭流程。
discussions: true
---

# Issue 怎么用

**Issue** 是 GitHub 内置的"工单系统"。任何人都可以用它来：

- 报告 **bug**；
- 提出**功能请求**；
- 提问；
- 记录**任务**（有些团队甚至用 Issue 规划整个项目）。

Issue 不是给维护者发的私信：它是公开的、可被搜索的，并且会成为仓库历史的一部分——所以认真写好它很重要。

给别人项目写代码之前，也推荐先开一个 Issue：先沟通，再动手（见 [通过 Pull Request 参与贡献](contribute.md)）。

## 如何新建一个 Issue

1. 打开仓库，进入 **Issues** 标签页，点击 **New issue**。
2. 如果仓库提供了 **Issue 模板**（例如 "Bug report"、"Feature request"），选择对应的模板——它会引导你填写。
3. 写一个**清晰的标题**，概括问题，例如 `在 Windows 上打开 .png 文件时应用崩溃`。
4. 详细描述问题（见下面的清单），然后点击 **Submit new issue**。

## 一份好的 Issue 长什么样

- **先搜索**：你的问题可能已经有人报告过——在已有的 Issue 下补充评论，而不是重复发一个新的。
- **一个问题一个 Issue**：不要把几个不相关的问题混在一起。
- **标题清晰**：只看标题，维护者就应该知道这大概是什么问题。
- **复现步骤**：一步步说明你做了什么，发生了什么。
- **预期与实际行为**：你期望发生什么，实际发生了什么。
- **环境信息**：操作系统、软件版本、语言版本等。
- **证据**：截图、报错信息或日志片段（日志用代码块包裹）。

## 一个 Issue 的一生

- **标签（Labels）**：维护者会用 `bug`、`enhancement`、`question`、`good first issue`（适合新手的任务，见 [通过 Pull Request 参与贡献](contribute.md)）等标签标记 Issue。
- **@ 提醒**：在 Issue 正文里写 `@用户名` 可以提醒特定的人。
- **关闭（Close）**：问题解决后由维护者关闭。如果提交或 PR 的描述里包含 `fixes #<Issue 编号>`，合并后 GitHub 会自动关闭对应的 Issue。
- **讨论区（Discussions）**：有些项目更喜欢用 [GitHub Discussions](https://docs.github.com/en/discussions) 进行问答——提问前先看看仓库有没有 Discussions 标签页。

!!! tip
    写一份高质量的 Issue 本身就是对开源的贡献：它同时帮助了维护者和其他使用者。不要害怕报告问题——只要认真描述清楚就好。

## 实践环节

1. 在自己的仓库里开一个 Issue（比如描述一个你打算加的功能），再自己把它关掉。
2. 去一个你常用的仓库，找一个带 `good first issue` 标签的 Issue 读一读，想想自己能不能解决。
