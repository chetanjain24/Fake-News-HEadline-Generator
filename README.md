# Fake News Headline Generator (Flask Web)

A Flask web app with user registration/login and a modern UI to generate fun, fake headlines. Protected routes require login. Includes animated transitions (glassmorphism + gradients).

## Quick start

1) Create and activate a virtual environment (Windows PowerShell):

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

2) Install dependencies:

```powershell
pip install -r requirements.txt
```

3) Run the app (creates SQLite DB automatically):

```powershell
python run.py
```

4) Open in your browser:

- http://127.0.0.1:5000/auth/register – create an account
- http://127.0.0.1:5000/auth/login – log in
- http://127.0.0.1:5000/ – headline generator (requires login)

## Project structure

```
app/
  __init__.py         # app factory, db and login manager
  models.py           # User model
  auth/routes.py      # register/login/logout
  generator/routes.py # index + /api/headline
  services/headline.py# headline generation logic
static/
  app.js              # UI interactions and fetch
  styles.css          # custom animations and styles
templates/
  base.html           # layout + nav + flash messages
  auth/login.html
  auth/register.html
  index.html          # generator UI with transitions
run.py                # dev entrypoint
```

## Notes
- Uses SQLite in `instance/app.db` (auto-created).
- Secret key is development-only. Change `SECRET_KEY` in `app/__init__.py` for production.
- Tailwind via CDN for utility classes; custom CSS handles shine/springy transitions.



