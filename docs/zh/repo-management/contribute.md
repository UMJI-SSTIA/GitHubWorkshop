---
title: 通过 Pull Request 参与贡献
description: 开源贡献的核心流程：Fork → 修改 → Pull Request（PR）。也了解如何提交一份高质量的 Issue。
discussions: true
---

# 如何参与贡献

贡献的核心流程是 **Issue → Fork → 修改 → Pull Request（PR）**。

先开 **Issue** 沟通、达成一致后再动手写代码：这样既不会重复劳动（别人可能已经在修了），也不会白费力气（维护者可能根本不想要这个功能）。

1. **先开 Issue** 报告 bug 或提出功能设想，并和维护者讨论（见 [用 Issue 反馈问题](issues.md)）。如果已经有人提过，就在那个 Issue 下参与讨论——并说明你想来修它。
2. **Fork** 目标仓库（见 [Fork 一个仓库](fork.md)），并克隆自己的 fork 到本地：

    ```bash
    git clone https://github.com/你的用户名/仓库名.git
    cd 仓库名
    ```

3. 新建一个分支，避免直接在 `main` 上改：

    ```bash
    git checkout -b <分支名>
    ```

4. 修改代码或文档，然后提交（相信这些在 151 or 101 已经很熟练了）：

    ```bash
    git add .
    git commit -m "描述你的改动"
    git push origin <分支名>
    ```

    !!! warning "尽量不要强制添加被忽略的文件"
        假设你的 `.gitignore` 里屏蔽了 `.o` 文件，但是仍然执行：

        ```bash
        git add -f main.o
        ```

        会导致强制添加，并把 `main.o` 当成已追踪文件，所以尽量不要写 `-f`。

5. 回到 GitHub 上你的 fork 页面，点击 **Contribute → Open pull request**。
6. 写清楚你改了什么、为什么改（详细一点）——一份好的描述会说明：解决了什么问题、怎么解决的、如何测试。记得关联对应的 Issue（比如在描述里写 `fixes #12`），然后点 **Create pull request**。
7. 等待原仓库维护者 review（审查）；他们可能会提意见，你继续修改并 push 即可更新同一个 PR。

**补充：**

- 如果只是发现 bug 或提建议，可以直接在仓库的 **Issues** 页面提交 **New issue**，这也是贡献的一种方式——怎么写好一份 Issue 见 [用 Issue 反馈问题](issues.md)。
- 如果原仓库给了你写权限，可以跳过 fork，直接建分支改完提 PR。
- 刚开始接触开源？可以搜索带有 `good first issue` 标签的 Issue——维护者用它来标记适合新手入门的任务。
- Pull Request 尽量**小而聚焦**——一个 PR 解决一个问题，这样更容易被 review 和合并。
- 还没做完？可以先开 **Draft PR（草稿 PR）**，让维护者知道暂时不要 review。
- PR 合并之后，你的功能分支就可以放心删除了。
- 如果原仓库一直在更新，记得不时同步你的 fork：

    ```bash
    git remote add upstream https://github.com/原作者/仓库名.git
    git fetch upstream
    git merge upstream/main
    ```
