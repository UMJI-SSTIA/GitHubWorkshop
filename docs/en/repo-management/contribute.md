---
title: Contribute with a pull request
description: 'The core flow of contributing to open source: Fork → Modify → Pull Request (PR). Also learn how to report a bug with a good issue.'
discussions: true
---

# How to Contribute to a Repository

The core process of contributing is **Issue → Fork → Modify → Pull Request (PR)**.

Start with an **issue** and only write code after you reach agreement with the maintainer: this avoids duplicated work (someone may already be fixing it) and misunderstandings (the maintainer may not want that feature at all).

1. **Open an issue** to report the bug or propose the feature, and discuss it with the maintainer (see [Report problems with issues](issues.md)). If someone else already reported it, join that discussion — and mention that you would like to fix it.
2. **Fork** the target repository (see [Fork a repository](fork.md)) and clone your fork locally:

    ```bash
    git clone https://github.com/your-username/repository-name.git
    cd repository-name
    ```

3. Create a new branch to avoid modifying `main` directly:

    ```bash
    git checkout -b <branch name>
    ```

4. Modify the code or documentation, then commit (I believe you are already very familiar with these from 151 or 101):

    ```bash
    git add .
    git commit -m "Describe your changes"
    git push origin <branch name>
    ```

    !!! warning "Don't force-add ignored files"
        Suppose your `.gitignore` ignores `.o` files, but you still run:

        ```bash
        git add -f main.o
        ```

        This will force the addition and treat `main.o` as a tracked file, so try not to write `-f`.

5. Go back to your fork page on GitHub and click **Contribute → Open pull request**.
6. Clearly describe what you changed and why (be detailed) — a good description explains what problem you solve, how you solve it, and how the change can be tested. Mention the related issue (e.g., `fixes #12`) to link them together, then click **Create pull request**.
7. Wait for the original repository maintainer to review; they may give feedback, and you can continue to modify and push to update the same PR.

**Supplements:**

- If you just find a bug or want to make a suggestion, you can directly submit a **New issue** on the repository's **Issues** page. This is also a way to contribute — see [Report problems with issues](issues.md) for how to write a good one.
- If the original repository gives you write permission, you can skip the fork and directly create a branch, make changes, and submit a PR.
- New to open source? Search for issues labeled `good first issue` — maintainers use this label to mark beginner-friendly tasks.
- Keep a pull request **small and focused** — one PR solves one problem; it is much easier to review and merge.
- Work in progress? Open a **draft pull request** so the maintainer knows not to review it yet.
- After your PR is merged, you can safely delete your feature branch.
- If the original repository keeps updating, sync your fork from time to time:

    ```bash
    git remote add upstream https://github.com/original-owner/repository-name.git
    git fetch upstream
    git merge upstream/main
    ```
