---
title: Report problems with issues
description: What is a GitHub Issue? Learn how to report a bug or request a feature properly, and how the issue workflow (labels, templates, closing) works.
discussions: true
---

# How to Use Issues

An **Issue** is GitHub's built-in ticket system. Anyone can use it to:

- report a **bug**;
- request a **feature**;
- ask a **question**;
- track a **task** (some teams plan their whole project in issues).

An issue is not a private message to the maintainer: it is public, searchable, and becomes part of the repository's history — which is why writing it well matters.

It is also the recommended first step before writing any code for someone else's project: discuss first, then contribute (see [Contribute with a pull request](contribute.md)).

## How to open an issue

1. Open the repository and go to the **Issues** tab, then click **New issue**.
2. If the repository provides **issue templates** (e.g., "Bug report", "Feature request"), choose the matching one — it will guide you through the form.
3. Write a **clear title** that summarizes the problem, e.g., `App crashes when opening a .png file on Windows`.
4. Describe it in detail (see the checklist below) and click **Submit new issue**.

## What a good issue looks like

- **Search first**: your problem may already be reported — comment on the existing issue instead of duplicating it.
- **One issue, one problem**: don't bundle several unrelated problems together.
- **Clear title**: the title alone should tell the maintainer what it is about.
- **Steps to reproduce**: what you did, step by step, and what happened.
- **Expected vs. actual behavior**: what you expected to happen, and what actually happened.
- **Environment**: operating system, software version, programming language version, etc.
- **Evidence**: screenshots, error messages, or log excerpts (wrap logs in a code block).

## How an issue lives

- **Labels**: maintainers tag issues with labels such as `bug`, `enhancement`, `question`, or `good first issue` (beginner-friendly tasks — see [Contribute with a pull request](contribute.md)).
- **Mentioning people**: write `@username` in the issue body to notify a specific person.
- **Closing**: the maintainer closes the issue when it is resolved. If a commit or pull request description contains `fixes #<issue number>`, GitHub closes the issue automatically when that commit or PR is merged.
- **Discussions**: some projects prefer [GitHub Discussions](https://docs.github.com/en/discussions) for Q&A — check whether the repository has a Discussions tab before asking a question in an issue.

!!! tip
    Opening a well-written issue is itself a contribution to open source: it helps maintainers and other users alike. Don't be afraid to report problems — just describe them carefully.

## Practice

1. Open an issue in your own repository (e.g., describe a feature you plan to add) and close it yourself.
2. Go to a repository you often use and find an issue labeled `good first issue` — read it and think about whether you could solve it.
