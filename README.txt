SH HOST - Setup
================
1) pip install -r requirements.txt
2) python app.py            (http://localhost:5000)
   Admin panel: http://localhost:5000/admin

Environment variables (recommended):
   ADMIN_USER   admin username   (default: admin)
   ADMIN_PASS   admin password   (default: admin123  -> CHANGE IT)
   SECRET_KEY   long random string
   BASE_DOMAIN  your main domain, e.g. shhost.com -> sites open as name.shhost.com
                (also editable later in Admin > Settings; needs wildcard DNS *.shhost.com)
   DATA_DIR     where DB + sites are stored (use a persistent disk on Render)

Render / production start command:
   gunicorn app:app --workers 1 --threads 4 --timeout 120

GitHub import:
   Users can host a public GitHub repo (static site with index.html). Optional env GITHUB_TOKEN
   lets the server also import private repos you own and avoids GitHub rate limits.
