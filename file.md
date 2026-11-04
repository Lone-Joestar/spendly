# Spendly

A personal expense tracker built with Flask. Users register, log in, record what they spend, and see where their money goes. Amounts are shown in rupees (₹).

This is an early scaffold of a step-by-step teaching project: the code comments mark the parts students are meant to implement.

Repo: https://github.com/Lone-Joestar/spendly

## Tech stack

**Backend**
- Python 3.14
- Flask 3.1.3 and Werkzeug 3.1.6
- Jinja2 templates (bundled with Flask)
- SQLite via the built-in `sqlite3` module (planned, not written yet)

**Frontend**
- Server-rendered Jinja2 templates
- Hand-written CSS (`static/css/style.css`, ~530 lines)
- Google Fonts: DM Serif Display and DM Sans
- JavaScript: essentially unused so far

**Testing**
- pytest 8.3.5 and pytest-flask 1.3.0 (installed, no tests yet)

## Project structure

```
expense-tracker/
├── app.py                 # Flask app: creates the app, defines all routes
├── requirements.txt       # Pinned dependencies
├── .gitignore             # Excludes venv/, expense_tracker.db, __pycache__/, .env, etc.
│
├── database/              # Data layer (SQLite)
│   ├── __init__.py        # Makes `database` an importable package
│   └── db.py              # Comments only: get_db(), init_db(), seed_db() to be written
│
├── templates/             # Jinja2 HTML templates
│   ├── base.html          # Shared layout: navbar, footer, fonts, CSS/JS includes
│   ├── landing.html       # Home page
│   ├── login.html         # Sign-in form
│   └── register.html      # Sign-up form
│
└── static/
    ├── css/style.css      # All styling
    └── js/main.js         # Empty placeholder
```

Every page template extends `base.html`, so the navbar and footer live in one place.

## Status

**Working**
- Landing page at `/`
- `/login` and `/register` pages render (forms don't submit yet)

**Not built yet**
- SQLite database layer (Step 1)
- Registration, login, sessions (Steps 2-3)
- Profile page (Step 4)
- Add / edit / delete expenses (Steps 7-9); these routes currently return placeholder text
- Tests

## Running locally

```
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python app.py
```

Then open http://127.0.0.1:5001.
