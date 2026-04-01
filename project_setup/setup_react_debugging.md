# Setup – React Debugging

## Objective
Debug React applications using browser DevTools and VS Code.

---

## 1. Run React app in dev mode

```bash
cd frontend
npm run dev
```

> Dev mode includes source maps, which make debugging much easier.

---

## 2. Open browser DevTools

In Chrome or Edge, press `F12` (or right-click → **Inspect**). In safari, enable DevTools in Preferences → Advanced → "Show Develop menu in menu bar", then press `Option + Command + I`.

Key tabs:
| Tab | Use |
|-----|-----|
| **Console** | See `console.log()` output and errors |
| **Network** | Track all API calls and responses |
| **Components** | Inspect React component state (requires React DevTools) |

---

## 3. Inspect console logs

Add logs in your React code:

```javascript
console.log("data:", data);
console.error("something went wrong:", error);
```

> These appear in the **Console** tab of DevTools.

---

## 4. Debug API calls

1. Open **Network** tab in DevTools
2. Click your API call button in the UI
3. Click the request that appears → check **Response** tab

> If you see a CORS error, refer to `setup_frontend_backend_connection.md`.

---

## 5. Use VS Code debugger (optional)

Create `.vscode/launch.json` inside `frontend/`:

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "type": "pwa-chrome",
      "request": "launch",
      "name": "React App",
      "url": "http://localhost:5173",
      "webRoot": "${workspaceFolder}"
    }
  ]
}
```

Press `F5` — VS Code opens Chrome with the debugger attached. Set breakpoints directly in `.jsx` files.

---

## Validation

- Console logs visible in **Console** tab
- API calls tracked in **Network** tab with correct responses
- Breakpoints pause execution in browser or VS Code
