A step-by-step guide to set up a clean development environment on macOS using Homebrew.

This guide installs:
- Homebrew (package manager)
- Git (version control)
- Node.js (JavaScript runtime)
- Python (programming language)
- VS Code (code editor)

Each step includes:
- What you are installing
- Why it is needed
- Validation before and after installation

---

## 0. Pre-requisites

- macOS (latest recommended)
- Admin access (you may be prompted for password)
- Stable internet connection

---

## 1. Install Homebrew

### What is Homebrew?
Homebrew is a package manager for macOS. It allows you to install software using simple commands instead of downloading installers manually.

---

### Check if already installed
```bash
brew -v

If installed
	•	You will see a version like: Homebrew 4.x.x
	•	✅ Continue to next step

⸻

If NOT installed

Install Homebrew

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

Add to PATH (important for Apple Silicon Macs)

echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"


⸻

Validate

brew -v

Expected: Displays Homebrew version

⸻

2. Update & Verify Homebrew

Why this step?

Ensures you are using the latest package definitions and checks system readiness.

⸻

Run

brew update
brew doctor


⸻

Validate
	•	brew update completes without errors
	•	brew doctor may show warnings → acceptable
	•	❌ Fix only if it shows “Error”

⸻

3. Install Git

What is Git?

Git is a version control system used to track code changes and collaborate with others (GitHub, GitLab, etc.).

⸻

Check if already installed

git --version

If installed
	•	Example: git version 2.x.x
	•	✅ Continue

⸻

If NOT installed

Install Git

brew install git


⸻

Validate

git --version

Expected: Git version displayed

⸻

4. Install Node.js

What is Node.js?

Node.js allows you to run JavaScript outside the browser. It is used for:
	•	Backend development
	•	Frontend tooling (React, Angular, etc.)
	•	Package management via npm

⸻

Check if already installed

node -v
npm -v

If installed
	•	Example: v18.x.x or higher
	•	✅ Continue

⸻

If NOT installed

Install Node.js (LTS)

brew install node


⸻

Validate

node -v
npm -v

Expected:
	•	Node version
	•	npm version

⸻

5. Install Python

What is Python?

Python is a versatile programming language used in:
	•	Backend development
	•	Data science & AI/ML
	•	Automation and scripting

⸻

Check if already installed

python3 --version
pip3 --version

If installed
	•	Example: Python 3.x.x
	•	✅ Continue

⸻

If NOT installed

Install Python

brew install python


⸻

Validate

python3 --version
pip3 --version

Expected:
	•	Python version
	•	pip version (package installer)

⸻

6. Install VS Code

What is VS Code?

Visual Studio Code is a lightweight but powerful code editor with support for multiple programming languages.

⸻

Check if already installed

code --version

If installed
	•	Version displayed
	•	✅ Continue

⸻

If NOT installed

Install VS Code

brew install --cask visual-studio-code


⸻

Validate

code --version


⸻

If code command not found
	1.	Open VS Code
	2.	Press Cmd + Shift + P
	3.	Search: Shell Command: Install 'code' command in PATH
	4.	Restart terminal

⸻

7. Final Verification

Run all commands:

brew -v
git --version
node -v
npm -v
python3 --version
pip3 --version
code --version


⸻

Expected Result

All commands should:
	•	Return version numbers
	•	Not show errors

⸻

8. Done ✅

Your Mac is now ready for development.

You can now:
	•	Clone repositories using Git
	•	Run Node.js applications
	•	Write and execute Python programs
	•	Use VS Code for development
