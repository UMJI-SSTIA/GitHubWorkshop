---
title: 创建仓库
description: 一步步在 GitHub 上创建一个仓库，并通过网页上传或本地 Git 两种方式把代码放进去，包括初次使用 Git 的配置。
discussions: true
---

# 如何创建一个仓库

**仓库（Repository）** 是项目文件在 GitHub 上的"家"，也是代码托管与协作的基本单位。每个项目都从创建仓库开始。

1. 登录 [github.com](https://github.com)，点击右上角的 **`+`** 图标，选择 **New repository**（新建仓库）。
2. 填写信息：
   - **Repository name**（仓库名）：必填，例如 `my-first-project`。
   - **Description**（描述）：可选，简单说明这个仓库是干什么的。
   - **Public / Private**：公开仓库任何人都能看；私有仓库只有自己和被邀请的人能看。
   - **Add a README file**：建议勾选，自动生成一个 `README.md`。
   - **Add .gitignore**：可选，根据你用的语言（C/C++、Python 等）忽略不需要上传的文件。
   - **Choose a license**：可选，选择开源许可证（见 [选择许可证](license.md)）。
3. 点击 **Create repository** 完成创建。

!!! tip "命名与可见性"
    - 仓库名建议只用小写字母、数字和连字符（例如 `my-first-project`），这样链接更整洁。
    - **Public / Private** 之后可以随时在 **Settings → General** 里修改，现在不必纠结。
    - `.gitignore` 告诉 Git 哪些文件不需要跟踪（编译产物、IDE 配置文件、密钥等），创建仓库时可以直接套用 GitHub 提供的语言模板。

!!! note "改名与默认分支"
    - 之后可以在 **Settings → General** 里给仓库改名，但改名后旧链接对所有人都会失效（GitHub 会自动跳转，但别人书签里的链接会受影响），所以尽量在有人引用之前确定好名字。
    - 从 2020 年 10 月起，新仓库的默认分支名是 `main`（一些老教程里可能还写着 `master`）。

## 把代码放进仓库

创建之后，你有两种方式往仓库里放代码：

- **网页操作**：点 **Add file → Upload files** 直接拖拽上传。
- **本地 Git**：复制仓库地址，在终端执行：

```bash
git clone https://github.com/你的用户名/仓库名.git
# 放入文件后
git add .
git commit -m "first commit"
git push
```

!!! note "初次使用 Git 的配置"
    如果你的电脑还没有配置过用户名和邮箱，就无法提交（commit）。请按下面配置（如果你不想全局配置、只想配置这一个仓库，去掉 `--global`）：

    ```bash
    git config --global user.name <你的名字，自己想一个>
    git config --global user.email <邮箱>
    git config --list # 用于确认你的配置状态
    ```
