---
title: Choose a license
description: What is an open-source license? Compare MIT, Apache 2.0, GPL, and BSD, and learn how to add a license to your repository.
discussions: true
---

# What Is a License?

A **License** is a legal statement that specifies how others may use your code. It is an important part of open-source projects:

| License | Features | Applicable Scenarios |
| --- | --- | --- |
| **MIT** | The most permissive; others can use, modify, and commercialize freely, only needing to retain the copyright notice | Most personal projects |
| **Apache 2.0** | Permissive + explicit patent grant | Enterprises, needing patent protection |
| **GPL** | Strong "infectiousness"; if you use it, you must also open-source | Want derivative projects to be open-source too |
| **BSD** | Similar to MIT, with slightly more clauses | Academic projects |
| **Unlicense** | Waives all rights; the code enters the public domain | Want zero restrictions at all |

Key points:

- **No license** means "all rights reserved" by default; others **cannot legally** copy or modify your code.
- How to add: Select it directly when creating the repository, or later click **Add file → Create new file**, write the file name as `LICENSE.txt`, and GitHub will automatically provide template options.
- When GitHub generates the license file from a template, it inserts a placeholder copyright line (`[year] [fullname]`) — remember to replace it with your own name and the current year.

!!! tip
    Not sure which license to choose? [choosealicense.com](https://choosealicense.com) is maintained by GitHub — answer a few simple questions and it will recommend a suitable license for your project.

!!! note "Which one should I pick?"
    If in doubt: **MIT** for personal and course projects, **Apache 2.0** if you care about patents, **GPL** if you want derivatives to stay open. You can also change the license later by replacing the `LICENSE` file (for serious projects with many contributors, everyone should agree first).
