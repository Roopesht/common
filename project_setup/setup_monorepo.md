# Setup – Monorepo Structure

## Objective
Organize frontend and backend in a single repository so everything is in one place.

---

## 1. Folder structure

```
project-root/
  backend/
    main.py
    db.py
    .env
    requirements.txt
    venv/
  frontend/
    src/
    package.json
  .gitignore
  README.md
```

> Keep `backend/` and `frontend/` completely separate — they have their own dependencies and run independently.

---

## 2. Initialize Git at the root

Run this once from `project-root/`:

```bash
git init
```

---

## 3. Add a `.gitignore` file

Create `.gitignore` in `project-root/`:

```
# Python
backend/venv/
backend/__pycache__/
backend/*.db
backend/.env

# Node
frontend/node_modules/
frontend/dist/
```

> This prevents large or sensitive files from being committed.

---

## 4. Manage separate dependencies

- **Backend:** activate `venv`, use `pip install`
- **Frontend:** use `npm install` inside `frontend/`

They do not share dependencies.

---

## 5. Run both projects

Open **two terminals**:

```bash
# Terminal 1 — Backend
cd backend
source venv/bin/activate   # Mac/Linux
uvicorn main:app --reload
```

```bash
# Terminal 2 — Frontend
cd frontend
npm run dev
```

---

## Optional: root `package.json` shortcuts

Create `package.json` in `project-root/`:

```json
{
  "scripts": {
    "backend": "cd backend && uvicorn main:app --reload",
    "frontend": "cd frontend && npm run dev"
  }
}
```

Then use:
```bash
npm run backend   # Terminal 1
npm run frontend  # Terminal 2
```

---

## Validation

- Backend runs at [http://127.0.0.1:8000](http://127.0.0.1:8000)
- Frontend runs at [http://localhost:5173](http://localhost:5173)
- Both run at the same time without conflict
