# Setup – React

## Objective
Create and run a React application with API integration.

---

## 1. Create app using Vite

Run this from your project root (not inside `backend/`):

```bash
npm create vite@latest frontend
```

When prompted:
- Select **React**
- Select **JavaScript** (or TypeScript if preferred)

---

## 2. Install dependencies

```bash
cd frontend
npm install
```

---

## 3. Folder structure overview

```
frontend/
  src/
    App.jsx       ← main component, edit this
    main.jsx      ← entry point, don't touch
  index.html
  package.json
  vite.config.js
```

> Start by editing `src/App.jsx`.

---

## 4. Run the dev server

```bash
npm run dev
```

**Stop the server:** Press `CTRL + C`

---

## 5. Call your backend API

Add this inside a component in `App.jsx`:

```javascript
fetch("http://127.0.0.1:8000")
  .then(res => res.json())
  .then(data => console.log(data));
```

> Make sure the FastAPI backend is running before making this call.

---

## Validation

- App runs at [http://localhost:5173](http://localhost:5173)
- Open DevTools (`F12`) → Console tab → API response visible after the fetch runs
