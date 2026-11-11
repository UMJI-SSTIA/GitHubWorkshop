---
title: Write a README
description: A README is the "first business card" of your project. Learn what a good README contains and the most common Markdown syntax.
discussions: true
---

# How to Write a README

**README.md** is the documentation displayed by default on the homepage after opening the repository, written in **Markdown**. It is the "first business card" for others to understand your project.

A good README usually includes:

- **Project introduction**: One sentence explaining what this project does.
- **Installation method**: Environment dependencies, how to install.
- **Usage method**: How to run, example code.
- **License / Contribution method**: Point to LICENSE or explain how to participate.

## Common Markdown syntax

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

A few more pieces that are commonly used:

```markdown
| Header | Header |
| --- | --- |
| cell | cell |

- [x] done task
- [ ] todo task

> quote
```

How to create: Check "Add a README file" when creating a new repository, or later click **Add file → Create new file** and write the file name as `README.md`.

## A simple README skeleton

You can start from this outline and fill in your own content:

```markdown
# Project name

One sentence: what does this project do?

## Installation

How to install dependencies and set things up.

## Usage

How to run it, with an example command.

## Contributing

How others can participate, and a link to the license.
```

!!! tip "Images and badges"
    - To use images, put them in the repository (e.g., in an `images/` folder) and reference them with relative paths; or drag an image into an issue comment and copy the generated URL.
    - One-line status badges from [shields.io](https://shields.io) (build status, license, downloads, ...) make a README look professional.
