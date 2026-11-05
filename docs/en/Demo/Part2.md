---
title: The usage of GitHub Repository
description: Using a GitHub Repository
---

# Using a GitHub Repository

> **Author:** Zhang Junming  

---

## 1. How to Create a Repository

1. Log in to [github.com](https://github.com), click the **`+`** icon in the upper right corner, and select **New repository**.
2. Fill in the information:
   - **Repository name**: Required, e.g., `my-first-project`.
   - **Description**: Optional, a brief explanation of what the repository is for.
   - **Public / Private**: A public repository can be viewed by anyone; a private repository can only be viewed by you and invited people.
   - **Add a README file**: Recommended, automatically generates a `README.md`.
   - **Add .gitignore**: Optional, ignores files that don't need to be uploaded based on your language (C/C++, Python, etc.).
   - **Choose a license**: Optional, select an open-source license (see Section 2).
3. Click **Create repository** to finish creating.

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

Of course, if your computer has not been configured with a username and email, you cannot commit, so you need to (if you don't want a global configuration and only want to configure this one repository, remove --global):

```bash
git config --global user.name <your name, come up with one yourself>
git config --global user.email <email>
git config --list # used to confirm your configuration status
```

---

## 2. What Is a License

A **License** is a legal statement that specifies how others may use your code. It is an important part of open-source projects:

| License | Features | Applicable Scenarios |
| --- | --- | --- |
| **MIT** | The most permissive; others can use, modify, and commercialize freely, only needing to retain the copyright notice | Most personal projects |
| **Apache 2.0** | Permissive + explicit patent grant | Enterprises, needing patent protection |
| **GPL** | Strong "infectiousness"; if you use it, you must also open-source | Want derivative projects to be open-source too |
| **BSD** | Similar to MIT, with slightly more clauses | Academic projects |

Key points:
- **No license** means "all rights reserved" by default; others **cannot legally** copy or modify your code.
- How to add: Select it directly when creating the repository, or later click **Add file → Create new file**, write the file name as `LICENSE.txt`, and GitHub will automatically provide template options.

---

## 3. How to Fork a Repository

**Fork** means completely copying someone else's repository to your own account, after which you can modify it freely without affecting the original repository.

1. Open the repository page you want to fork.
2. Click the **Fork** button in the upper right corner (usually next to Star).
3. Select the target account (usually yourself) and click **Create fork**.
4. After completion, a repository with the same name will appear under your account, marked "forked from original author/original repository".

After getting the fork, clone it locally:
```bash
git clone https://github.com/your-username/repository-name.git
```
Uses: wanting to do secondary development based on someone else's project, learn the source code, or prepare to submit a Pull Request to the original project (see Section 4).

---

## 4. How to Contribute to a Repository

The core process of contributing is **Fork → Modify → Pull Request (PR)**:

1. **Fork** the target repository (Section 3).
2. Clone your fork locally:
```bash
git clone https://github.com/your-username/repository-name.git
cd repository-name
```
3. Create a new branch to avoid modifying main directly:
```bash
git checkout -b <branch name>
```
4. Modify the code or documentation, then commit: (I believe you are already very familiar with these from 151 or 101)
```bash
git add .
git commit -m "Describe your changes"
git push origin my-feature
```

**[!]** Note that, suppose your .gitignore ignores .o files, but you still do:
```bash
git add -f main.o
```
This will force the addition and treat main.o as a tracked file, so try not to write -f.

5. Go back to your fork page on GitHub and click **Contribute → Open pull request**.
6. Clearly describe what you changed and why (be detailed), then click **Create pull request**.
7. Wait for the original repository maintainer to review; they may give feedback, and you can continue to modify and push to update the same PR.

Supplement:
- If you just find a bug or want to make a suggestion, you can directly submit a **New issue** on the repository's **Issues** page. This is also a way to contribute. At the same time, your **Issue** should not be just one or two lines; instead, it should explain your suggestion, bug description, and your version, environment, etc. as detailed as possible.
- If the original repository gives you write permission, you can skip the fork and directly create a branch, make changes, and submit a PR.

---

## 5. How to Quickly Edit Content in a Repository

You don't need local Git; you can quickly edit directly on the web page:

1. Open a file in the repository and click the **pencil icon (Edit this file)** in the upper right corner.
2. Modify the content directly in the edit box.
3. Scroll to the bottom of the page, write a short commit message, and choose to commit to the current branch or a new branch.
4. Click **Commit changes** to save.

Other web shortcuts:
- **New file**: Add file → Create new file.
- **Upload file**: Add file → Upload files.
- **Delete file**: Open the file → trash can icon in the upper right corner → Commit.

Note: Web editing is suitable for **small changes** (changing documentation, fixing one line of code). For large changes that require local compilation and testing, the local Git workflow in Section 4 is still more suitable.

---

## 6. How to Use README

**README.md** is the documentation displayed by default on the homepage after opening the repository, written in **Markdown**. It is the "first business card" for others to understand your project.

A good README usually includes:
- **Project introduction**: One sentence explaining what this project does.
- **Installation method**: Environment dependencies, how to install.
- **Usage method**: How to run, example code.
- **License / Contribution method**: Point to LICENSE or explain how to participate.

Common Markdown syntax:
````markdown
# Level 1 heading
## Level 2 heading
- List item
**Bold**, *italic*
`inline code`
[link text](URL)
![image description](image URL)
```
code block
```
````

How to create: Check "Add a README file" when creating a new repository, or later click **Add file → Create new file** and write the file name as `README.md`.

---

## 7. How to Build a Web Page Corresponding to the Repository (GitHub Pages)

**GitHub Pages** can turn a repository into a free hosted static website.

1. Open the repository → **Settings** → **Pages** on the left.
2. Under **Build and deployment**, select **Deploy from a branch** for **Source**.
3. Select the branch (usually `main`) and directory (root directory `/` or `/docs`), and click **Save**.
4. After a few dozen seconds, the page will give you your URL: `https://your-username.github.io/repository-name/`.

Content sources:
- The simplest approach: Place an `index.html` in the repository root directory; this is the homepage.
- You can also use Jekyll (built into GitHub) to automatically generate blog-style pages by selecting a theme.
- There is also a "user homepage" type: Create a repository named `your-username.github.io`, and the URL will be `https://your-username.github.io/`.

---

## 8. The Practical Process Corresponding to the Above Steps

**First use Step 1 to create a repository → use Steps 2 and 6 to clarify the project → use Step 3 to Fork when you need someone else's code → follow Step 4's PR when participating in collaboration → use Step 5 for small daily changes → once the project matures, you can use Step 7 to build a web page for display**.