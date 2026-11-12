---
title: 注册 GitHub 账号
description: 一步步创建自己的 GitHub 账号，并配置 SSH 密钥，方便之后用 Git 克隆仓库。
discussions: true
---

# 实践：注册 GitHub 账号

目标：拥有一个自己的 GitHub 账号，能登录、能创建仓库。

**步骤：**

1. 打开浏览器，访问 **https://github.com**。
2. 点击右上角 **Sign up**（注册）。
3. 按提示依次填写：
   - **邮箱**：建议用常用、可长期使用的邮箱；
   - **密码**：至少 8 位，建议包含大小写字母、数字和符号；
   - **用户名（Username）**：会出现在你的主页地址 `https://github.com/<用户名>` 中，建议用简短、易识别、专业的名字（如姓名拼音或常用昵称）；
4. 点击 **Create account**，GitHub 会向你填写的邮箱发送一封验证邮件。
5. 登录邮箱，点击邮件中的 **Verify email address** 完成验证。
6. 回到 GitHub，即可进入你的个人主页。

## 完成注册后的建议

- **用户名要慎重选择**：它会出现在你的主页地址里，之后并不容易修改。
- **开启两步验证（2FA）**：在 **Settings → Password and authentication** 中开启，保护账号安全。
- 开启 2FA 时，GitHub 会给你一串**恢复代码（Recovery codes）**——请妥善保存（比如放进密码管理器），手机丢失时它们是找回账号的唯一途径。

**配置 SSH**，便于之后使用 Git 克隆 GitHub 上的仓库：

1. 在电脑上打开终端，生成一对 SSH 密钥（可以直接使用默认保存位置，密码口令可留空）：

    ```bash
    ssh-keygen -t ed25519 -C "your_email@example.com"
    ```

2. 查看公钥内容：

    ```bash
    cat ~/.ssh/id_ed25519.pub
    ```

3. 复制输出的内容，进入 GitHub **Settings → SSH and GPG keys → New SSH key**，粘贴后点击 **Add SSH key**。

配置完成后，就可以使用 SSH 地址（`git@github.com:...`）克隆仓库，速度更快、更适合频繁推送。HTTPS 与 SSH 的区别见 [下载源代码](download-code.md)。

!!! tip "学生福利"
    注册完账号，还可以用学校邮箱申请 [GitHub Student Developer Pack](https://education.github.com/pack)，免费获得 GitHub Pro、GitHub Copilot 等权益。
