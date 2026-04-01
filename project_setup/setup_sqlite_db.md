# Setup – SQLite Database

## Objective
Set up a SQLite database for your backend with tables and sample data.

---

## 1. What is SQLite?

SQLite is a lightweight database that stores everything in a single file (`test.db`). It comes built into Python — no installation needed.

---

## 2. Install SQLAlchemy

SQLAlchemy lets you work with the database using Python instead of raw SQL.

```bash
pip install sqlalchemy
```

---

## 3. Create `db.py` — database connection

```python
from sqlalchemy import create_engine
from sqlalchemy.orm import sessionmaker, declarative_base

DATABASE_URL = "sqlite:///./test.db"

engine = create_engine(DATABASE_URL, connect_args={"check_same_thread": False})
SessionLocal = sessionmaker(bind=engine)
Base = declarative_base()

def get_db():
    db = SessionLocal()
    try:
        yield db
    finally:
        db.close()
```

> `get_db()` opens a database session for each request and closes it when done.

---

## 4. Create a table (model)

Add this to `db.py` or a separate `models.py`:

```python
from sqlalchemy import Column, Integer, String

class User(Base):
    __tablename__ = "users"

    id = Column(Integer, primary_key=True, index=True)
    name = Column(String)
    email = Column(String)
```

---

## 5. Create the table and insert sample data

Create `init_db.py`:

```python
from db import engine, SessionLocal, Base
from db import User  # or wherever you defined your model

# Create tables
Base.metadata.create_all(bind=engine)

# Insert sample data
db = SessionLocal()
db.add(User(name="Alice", email="alice@example.com"))
db.commit()
db.close()

print("Database initialized!")
```

Run it once:

```bash
python init_db.py
```

---

## Validation

- A `test.db` file appears in your project folder
- Output: `Database initialized!`
- To inspect: install **SQLite Viewer** extension in VS Code, then click `test.db`
