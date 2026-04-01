# Setup – Alembic Database Migrations

## Objective
Set up database migrations using Alembic so schema changes are tracked and repeatable.

---

## What is Alembic?

Alembic is a migration tool for SQLAlchemy. It tracks changes to your database schema over time — like version control for your tables. Instead of manually editing the database, you create migration scripts that can be applied or rolled back.

---

## 1. Install Alembic

Make sure your virtual environment is active, then:

```bash
pip install alembic
```

---

## 2. Initialize Alembic

Run this once from inside `backend/`:

```bash
alembic init alembic
```

This creates:
```
backend/
  alembic/
    versions/       ← migration files go here
    env.py          ← Alembic config
  alembic.ini       ← main config file
```

---

## 3. Configure `alembic.ini`

Open `alembic.ini` and update the database URL:

```ini
sqlalchemy.url = sqlite:///./test.db
```

---

## 4. Connect to SQLite DB

Open `alembic/env.py` and point Alembic to your models:

```python
from db import Base  # import your Base from db.py
target_metadata = Base.metadata
```

> This tells Alembic what tables to watch for changes.

---

## 5. Create your first migration

```bash
alembic revision --autogenerate -m "init"
```

> Alembic compares your models to the database and generates a migration script in `alembic/versions/`.

---

## 6. Apply the migration

```bash
alembic upgrade head
```

> `head` means "apply all pending migrations up to the latest."

---

## Common commands

| Command | Purpose |
|---------|---------|
| `alembic upgrade head` | Apply all pending migrations |
| `alembic downgrade -1` | Undo the last migration |
| `alembic history` | See all migrations |
| `alembic current` | See which migration is applied |

---

## Validation

- `test.db` file is created (or updated)
- Open with **SQLite Viewer** extension in VS Code → tables match your models
- Run `alembic current` → shows the latest applied migration ID
