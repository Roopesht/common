# macOS Development Environment Setup

A step-by-step guide to set up a clean development environment on macOS using Homebrew.

**This guide installs:**

| Tool | Purpose |
|------|---------|
| Homebrew | Package manager |
| Git | Version control |
| Node.js | JavaScript runtime |
| Python | Programming language |
| VS Code | Code editor |

Each step includes what you are installing, why it is needed, and validation before and after installation.

---

## Prerequisites

- macOS (latest recommended)
- Admin access (you may be prompted for your password)
- Stable internet connection

---

## Step 1 — Install Homebrew

**What is Homebrew?**
Homebrew is a package manager for macOS. It lets you install software via simple terminal commands instead of downloading installers manually.

**Check if already installed:**
```bash
brew -v
```

- If you see `Homebrew 4.x.x` → continue to the next step
- If not found → install it:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

**Add to PATH** (required on Apple Silicon Macs):
```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

**Validate:**
```bash
brew -v
```
Expected: Homebrew version is displayed.

---

## Step 2 — Update & Verify Homebrew

**Why?** Ensures you have the latest package definitions and checks system readiness.

```bash
brew update
brew doctor
```

**Validate:**
- `brew update` completes without errors
- `brew doctor` warnings are acceptable — only fix `Error` messages

---

## Step 3 — Install Git

**What is Git?**
Git is a version control system for tracking code changes and collaborating via GitHub, GitLab, etc.

**Check if already installed:**
```bash
git --version
```

- If you see `git version 2.x.x` → continue
- If not found → install it:

```bash
brew install git
```

**Validate:**
```bash
git --version
```
Expected: Git version is displayed.

---

## Step 4 — Install Node.js

**What is Node.js?**
Node.js runs JavaScript outside the browser. Used for backend development, frontend tooling (React, Angular, etc.), and package management via `npm`.

**Check if already installed:**
```bash
node -v
npm -v
```

- If you see `v18.x.x` or higher → continue
- If not found → install it:

```bash
brew install node
```

**Validate:**
```bash
node -v
npm -v
```
Expected: Node and npm versions are displayed.

---

## Step 5 — Install Python

**What is Python?**
Python is a versatile language used for backend development, data science & AI/ML, and automation/scripting.

**Check if already installed:**
```bash
python3 --version
pip3 --version
```

- If you see `Python 3.x.x` → continue
- If not found → install it:

```bash
brew install python
```

**Validate:**
```bash
python3 --version
pip3 --version
```
Expected: Python and pip versions are displayed.

---

## Step 6 — Install VS Code

**What is VS Code?**
Visual Studio Code is a lightweight, powerful code editor with support for multiple programming languages.

**Check if already installed:**
```bash
code --version
```

- If a version is displayed → continue
- If not found → install it:

```bash
brew install --cask visual-studio-code
```

**Validate:**
```bash
code --version
```

> **`code` command not found after install?**
> 1. Open VS Code
> 2. Press `Cmd + Shift + P`
> 3. Search: `Shell Command: Install 'code' command in PATH`
> 4. Restart your terminal

---

## Step 7 — Final Verification

Run all commands to confirm everything is installed:

```bash
brew -v
git --version
node -v
npm -v
python3 --version
pip3 --version
code --version
```

All commands should return version numbers with no errors.

---

## Done

Your Mac is now ready for development. You can:

- Clone repositories using Git
- Run Node.js applications
- Write and execute Python programs
- Use VS Code for development
