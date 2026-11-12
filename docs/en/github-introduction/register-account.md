---
title: Register a GitHub account
description: Create your own GitHub account step by step, and configure an SSH key so you can clone repositories with Git conveniently.
discussions: true
---

# Practice: Register a GitHub Account

Goal: Have your own GitHub account and be able to sign in and create repositories.

**Steps:**

1. Open a browser and visit **https://github.com**.
2. Click **Sign up** in the upper-right corner.
3. Follow the prompts and enter:
   - **Email**: Use an email address that you check regularly and can keep using long-term;
   - **Password**: Use at least 8 characters; a combination of uppercase and lowercase letters, numbers, and symbols is recommended;
   - **Username**: This will appear in your profile URL, `https://github.com/<username>`. Choose a short, recognizable, and professional name, such as the pinyin spelling of your name or a commonly used nickname;
4. Click **Create account**. GitHub will send a verification email to the address you provided.
5. Open your email and click **Verify email address** to complete verification.
6. Return to GitHub to access your profile page.

## Recommendations after registration

- Choose your username carefully: it appears in your profile URL, and it is not easy to change later.
- Enable **two-factor authentication (2FA)** in **Settings → Password and authentication** to protect your account.
- When you enable 2FA, GitHub gives you **recovery codes** — save them somewhere safe (e.g., a password manager); they are the only way back in if you lose your phone.

**Configure SSH** so that you can clone GitHub repositories with Git conveniently:

1. Open a terminal on your computer and generate an SSH key pair (you can accept the default location; a passphrase is optional):

    ```bash
    ssh-keygen -t ed25519 -C "your_email@example.com"
    ```

2. Display the public key:

    ```bash
    cat ~/.ssh/id_ed25519.pub
    ```

3. Copy the output, go to GitHub **Settings → SSH and GPG keys → New SSH key**, paste it, and click **Add SSH key**.

After that, you can clone repositories using the SSH address (`git@github.com:...`), which is faster and better for frequent pushes. See [Download source code](download-code.md) for the difference between HTTPS and SSH.

!!! tip "Student benefits"
    Registering is also the first step to the [GitHub Student Developer Pack](https://education.github.com/pack) — apply with your school email to get GitHub Pro, GitHub Copilot, and dozens of other tools for free.
