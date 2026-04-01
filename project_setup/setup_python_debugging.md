# Setup – Python Debugging in VS Code

## Objective
Enable debugging for Python projects so you can pause execution and inspect values.

---

## 1. Open project in VS Code

Open the `backend/` folder (not the root):

```
File → Open Folder → select backend/
```

---

## 2. Install the Python extension

1. Click the **Extensions** icon in the left sidebar (or press `CTRL+SHIFT+X`)
2. Search for **Python** (by Microsoft)
3. Click **Install**

---

## 3. Create `launch.json`

1. Click **Run & Debug** in the left sidebar (or press `CTRL+SHIFT+D`)
2. Click **create a launch.json file**
3. Select **Python** when prompted

Replace the file contents with:

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "FastAPI",
      "type": "python",
      "request": "launch",
      "module": "uvicorn",
      "args": ["main:app", "--reload"],
      "jinja": true
    }
  ]
}
```

> This tells VS Code how to start your FastAPI server with the debugger attached.

---

## 4. Add a breakpoint

Click the **red dot** that appears to the left of any line number in `main.py`.

> A breakpoint tells the debugger to pause execution at that line.

---

## 5. Start the debugger

Press `F5` (or click the green play button in the Run & Debug panel).

---

## Validation

1. Visit [http://127.0.0.1:8000](http://127.0.0.1:8000) in your browser
2. Execution pauses at your breakpoint
3. Inspect variable values in the **Variables** panel on the left
4. Press `F5` again to continue, or `F10` to step line by line
