---
title: Publish with GitHub Pages
description: Turn your repository into a free static website with GitHub Pages, using index.html, Jekyll, or a static site generator like MkDocs.
discussions: true
---

# How to Publish a Website with GitHub Pages

**GitHub Pages** can turn a repository into a free hosted static website.

1. Open the repository → **Settings** → **Pages** on the left.
2. Under **Build and deployment**, select **Deploy from a branch** for **Source**.
3. Select the branch (usually `main`) and directory (root directory `/` or `/docs`), and click **Save**.
4. After a few dozen seconds, the page will give you your URL: `https://your-username.github.io/repository-name/`.

Content sources:

- The simplest approach: Place an `index.html` in the repository root directory; this is the homepage.
- You can also use Jekyll (built into GitHub) to automatically generate blog-style pages by selecting a theme.
- There is also a "user homepage" type: Create a repository named `your-username.github.io`, and the URL will be `https://your-username.github.io/`.

!!! tip
    If you are not satisfied with plain HTML, you can generate a static site from Markdown with tools like **MkDocs** (which builds this very workshop website) or **Hugo**, and publish the result to GitHub Pages in the same way.

**Troubleshooting:**

- The first deployment takes about a minute; you can watch the progress in the **Actions** tab of your repository.
- If the site returns 404, check that **Source** is set to **Deploy from a branch** and that the correct branch and directory are selected.
- After you push new commits to the selected branch, GitHub Pages rebuilds the site automatically.

!!! note "Two things to remember"
    - **Public repositories only**: on a free account, GitHub Pages can only be published from public repositories (private repositories require GitHub Pro).
    - **Custom domain**: in **Settings → Pages**, you can bind your own domain name, and GitHub will issue a free HTTPS certificate for it.
