# Setup – Python Project

## Objective
Set up a Python project with a clean structure and a runnable entry point.

---

## 1. Create project folder
This will be the root directory for your project files. You can name it anything you like. for the purpose of this guide, we'll call it `my-project`.

```bash
mkdir my-project
cd my-project
```

---

## 2. Create virtual environment

A virtual environment keeps your project's packages separate from the rest of your system.

**Mac/Linux:**
```bash
python3 -m venv venv
```

**Windows:**
```bash
python -m venv venv
```

---

## 3. Activate the environment

You must activate the environment every time you open a new terminal.

**Mac/Linux:**
```bash
source venv/bin/activate
```

**Windows:**
```bash
venv\Scripts\activate
```

> Your terminal prompt will show `(venv)` when active.

---

## 4. Create `main.py`

This is the entry point — the file that runs when you start your app.

```python
def main():
    print("Project is running!")

if __name__ == "__main__":
    main()
```

---

## 5. Install dependencies via `requirements.txt`

List your packages in `requirements.txt`:

```
requests
```

Install them all at once:

```bash
pip install -r requirements.txt
```

> Always run this after activating your virtual environment.

---

## Validation

```bash
python main.py
```

Expected output:
```
Project is running!
```
