# VSCode Setup Guide

## Git Configuration

Git requires your name and email to associate commits with an author. These values are embedded in every commit you make and are visible in the repository history. Without them, Git will either refuse to commit or use system defaults that may not identify you correctly.

Configure your global Git identity:

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

Validate that the values were saved correctly:

```bash
git config --global --list
```

