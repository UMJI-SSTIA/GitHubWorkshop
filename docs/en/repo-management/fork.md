---
title: Fork a repository
description: What is a fork? Copy any public repository to your own account, clone it locally, and use it for learning or secondary development.
discussions: true
---

# How to Fork a Repository

**Fork** means completely copying someone else's repository to your own account, after which you can modify it freely without affecting the original repository.

1. Open the repository page you want to fork.
2. Click the **Fork** button in the upper right corner (usually next to Star).
3. Select the target account (usually yourself) and click **Create fork**.
4. After completion, a repository with the same name will appear under your account, marked "forked from original author/original repository".

After getting the fork, clone it locally:

```bash
git clone https://github.com/your-username/repository-name.git
```

!!! note "Fork vs. clone"
    A **fork** happens on GitHub: the entire repository is copied to your own account as a new remote repository. `git clone` downloads a repository to your local computer. To work on a fork, you usually do both: fork first, then clone *your fork*.

A quick comparison of the three buttons you see on every repository page:

| Action | What it does | Typical use |
| --- | --- | --- |
| **Star** ⭐ | Bookmarks the repository for you | Save it for later; also a sign of appreciation |
| **Watch** 👁 | Subscribes to notifications | Follow a project's new releases and discussions |
| **Fork** | Copies the repository into your account | Modify the code or prepare a pull request |

Uses: wanting to do secondary development based on someone else's project, learn the source code, or prepare to submit a Pull Request to the original project (see [Contribute with a pull request](contribute.md)). If you plan to contribute a fix, discuss it in an issue first — see [Report problems with issues](issues.md).

!!! tip "A fork does not sync itself"
    Your fork is a snapshot of the repository at the moment you forked it. When the original repository updates, your fork does **not** follow automatically — see [Contribute with a pull request](contribute.md) for how to sync it via `upstream`. Also note that anyone can fork a public repository freely, while private repositories cannot be forked by others.
