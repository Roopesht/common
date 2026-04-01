# Setup – Frontend ↔ Backend Connection

## Objective
Connect the React frontend with the FastAPI backend so they can communicate.

---

## 1. Enable CORS in FastAPI

By default, browsers block requests from one origin (React at port 5173) to another (FastAPI at port 8000). CORS removes that block.

Add this to `main.py`:

```python
from fastapi import FastAPI
from fastapi.middleware.cors import CORSMiddleware

app = FastAPI()

app.add_middleware(
    CORSMiddleware,
    allow_origins=["http://localhost:5173"],  # React dev server
    allow_methods=["*"],
    allow_headers=["*"],
)
```

---

## 2. Create a test API endpoint

```python
@app.get("/hello")
def hello():
    return {"message": "Hello from FastAPI!"}
```

---

## 3. Call the API from React

In `src/App.jsx`:

```javascript
import { useState } from "react";

function App() {
  const [message, setMessage] = useState("");

  async function fetchData() {
    const res = await fetch("http://127.0.0.1:8000/hello");
    const data = await res.json();
    setMessage(data.message);
  }

  return (
    <div>
      <button onClick={fetchData}>Call API</button>
      <p>{message}</p>
    </div>
  );
}

export default App;
```

---

## 4. Handle JSON response

> `res.json()` parses the response from FastAPI into a JavaScript object you can display or use.

---

## Validation

1. Start backend: `uvicorn main:app --reload`
2. Start frontend: `npm run dev`
3. Open [http://localhost:5173](http://localhost:5173)
4. Click **Call API** → `Hello from FastAPI!` appears on the page
