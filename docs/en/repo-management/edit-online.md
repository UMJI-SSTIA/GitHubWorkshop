---
title: Edit files on the web
description: 'Make quick changes to a repository directly in the browser: edit, create, upload, and delete files without local Git.'
discussions: true
---

# How to Quickly Edit Content in a Repository

You don't need local Git; you can quickly edit directly on the web page:

1. Open a file in the repository and click the **pencil icon (Edit this file)** in the upper right corner.
2. Modify the content directly in the edit box.
3. Scroll to the bottom of the page, write a short commit message, and choose to commit to the current branch or a new branch.
4. Click **Commit changes** to save.

Other web shortcuts:

- **New file**: Add file → Create new file.
- **Upload file**: Add file → Upload files.
- **Delete file**: Open the file → trash can icon in the upper right corner → Commit.

!!! note
    Web editing is suitable for **small changes** (changing documentation, fixing one line of code). For large changes that require local compilation and testing, the local Git workflow in [Contribute with a pull request](contribute.md) is still more suitable.

!!! tip "Even faster: the web editor"
    On any repository page, press the `.` (period) key to open the repository in **github.dev**, a full VS Code editor running in your browser. It is very handy for browsing or editing code without cloning.

!!! tip "Edit and propose changes in one go"
    When committing a web edit, you can choose **Create a new branch for this commit and start a pull request** — GitHub then opens a pull request for you directly. This is a very common way to contribute small fixes to other people's repositories.
