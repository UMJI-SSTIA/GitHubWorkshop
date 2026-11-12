---
title: Create a repository
description: Create a GitHub repository step by step, then put code into it via web upload or local Git, including the initial Git configuration.
discussions: true
---

# How to Create a Repository

A **repository** (repo for short) is where a project's files live on GitHub, and the basic unit of code hosting and collaboration. Every project starts with creating one.

1. Log in to [github.com](https://github.com), click the **`+`** icon in the upper right corner, and select **New repository**.
2. Fill in the information:
   - **Repository name**: Required, e.g., `my-first-project`.
   - **Description**: Optional, a brief explanation of what the repository is for.
   - **Public / Private**: A public repository can be viewed by anyone; a private repository can only be viewed by you and invited people.
   - **Add a README file**: Recommended, automatically generates a `README.md`.
   - **Add .gitignore**: Optional, ignores files that don't need to be uploaded based on your language (C/C++, Python, etc.).
   - **Choose a license**: Optional, select an open-source license (see [Choose a license](license.md)).
3. Click **Create repository** to finish creating.

!!! tip "Naming and visibility"
    - Name your repository with lowercase letters, numbers, and hyphens (e.g., `my-first-project`), so the URL stays clean.
    - You can change **Public / Private** later in **Settings → General**, so don't stress about it now.
    - The `.gitignore` file tells Git which files not to track (build outputs, IDE files, secrets); you can start from the language template GitHub provides.

!!! note "Renaming and the default branch"
    - You can rename a repository later in **Settings → General**, but the old URL stops working for everyone (GitHub redirects visitors, so try not to rename once people link to it).
    - Since October 2020, new repositories use `main` as the default branch name (some older tutorials may still say `master`).

## Put code into the repository

After creating it, you have two ways to put code into the repository:

- **Web operations**: Click **Add file → Upload files** to drag and drop directly.
- **Local Git**: Copy the repository address and run in the terminal:

```bash
git clone https://github.com/your-username/repository-name.git
# After placing files inside
git add .
git commit -m "first commit"
git push
```

!!! note "First-time Git configuration"
    If your computer has not been configured with a username and email, you cannot commit. Configure them as follows (if you don't want a global configuration and only want to configure this one repository, remove `--global`):

    ```bash
    git config --global user.name <your name, come up with one yourself>
    git config --global user.email <email>
    git config --list # used to confirm your configuration status
    ```
