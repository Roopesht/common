# Windows Development Environment Setup

A step-by-step guide to set up a clean development environment on Windows using Winget (Windows Package Manager).

**This guide installs:**

| Tool | Purpose |
|------|---------|
| Winget | Package manager (built into Windows 11) |
| Git | Version control |
| Node.js | JavaScript runtime |
| Python | Programming language |
| VS Code | Code editor |

Each step includes what you are installing, why it is needed, and validation before and after installation.

---

## Prerequisites

- Windows 10 (version 1809 or later) or Windows 11
- Admin access (you may be prompted by User Account Control)
- Stable internet connection
- PowerShell 5.1 or later (pre-installed on Windows 10/11)

> All commands in this guide are run in **PowerShell** (not Command Prompt). Search for `PowerShell` in the Start menu to open it.

---

## Step 1 — Verify Winget

**What is Winget?**
Winget is the Windows Package Manager, built into Windows 11 and available on Windows 10. It lets you install software via simple terminal commands.

**Check if already installed:**
```powershell
winget --version
```

- If you see `v1.x.x` → continue to the next step
- If not found → install the [App Installer from the Microsoft Store](https://apps.microsoft.com/store/detail/app-installer/9NBLGGH4NNS1), which includes Winget

**Validate:**
```powershell
winget --version
```
Expected: Winget version is displayed.

---

## Step 2 — Update Winget Sources

**Why?** Ensures you have the latest package definitions before installing anything.

```powershell
winget source update
```

**Validate:**
- Command completes without errors

---

## Step 3 — Install Git

**What is Git?**
Git is a version control system for tracking code changes and collaborating via GitHub, GitLab, etc.

**Check if already installed:**
```powershell
git --version
```

- If you see `git version 2.x.x` → continue
- If not found → install it:

```powershell
winget install --id Git.Git -e --source winget
```

After installation, **close and reopen PowerShell** to reload your PATH.

**Validate:**
```powershell
git --version
```
Expected: Git version is displayed.

**Configure Git** (first-time setup):
```powershell
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

---

## Step 4 — Install Node.js

**What is Node.js?**
Node.js runs JavaScript outside the browser. Used for backend development, frontend tooling (React, Angular, etc.), and package management via `npm`.

**Check if already installed:**
```powershell
node -v
npm -v
```

- If you see `v18.x.x` or higher → continue
- If not found → install it:

```powershell
winget install --id OpenJS.NodeJS.LTS -e --source winget
```

After installation, **close and reopen PowerShell** to reload your PATH.

**Validate:**
```powershell
node -v
npm -v
```
Expected: Node and npm versions are displayed.

---

## Step 5 — Install Python

**What is Python?**
Python is a versatile language used for backend development, data science & AI/ML, and automation/scripting.

**Check if already installed:**
```powershell
python --version
pip --version
```

- If you see `Python 3.x.x` → continue
- If not found → install it:

```powershell
winget install --id Python.Python.3 -e --source winget
```

After installation, **close and reopen PowerShell** to reload your PATH.

**Validate:**
```powershell
python --version
pip --version
```
Expected: Python and pip versions are displayed.

> **Tip:** If `python` opens the Microsoft Store instead of running, disable the app execution alias:
> Settings → Apps → Advanced app settings → App execution aliases → turn off **python.exe** and **python3.exe**

---

## Step 6 — Install VS Code

**What is VS Code?**
Visual Studio Code is a lightweight, powerful code editor with support for multiple programming languages.

**Check if already installed:**
```powershell
code --version
```

- If a version is displayed → continue
- If not found → install it:

```powershell
winget install --id Microsoft.VisualStudioCode -e --source winget
```

After installation, **close and reopen PowerShell** to reload your PATH.

**Validate:**
```powershell
code --version
```

> **`code` command not found after install?**
> 1. Open VS Code
> 2. Press `Ctrl + Shift + P`
> 3. Search: `Shell Command: Install 'code' command in PATH`
> 4. Restart PowerShell

---

## Step 7 — Final Verification

Run all commands to confirm everything is installed:

```powershell
winget --version
git --version
node -v
npm -v
python --version
pip --version
code --version
```

All commands should return version numbers with no errors.

---

## Done

Your Windows machine is now ready for development. You can:

- Clone repositories using Git
- Run Node.js applications
- Write and execute Python programs
- Use VS Code for development
