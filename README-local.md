Local quick start (both repos cloned side-by-side)

Prerequisites:
- Docker & Docker Compose installed
- Clone this repo and the Laravel backend next to each other:
  /home/user/projects/farmly-frontend  (this repo)
  /home/user/projects/backend/farmly    (Laravel repo)

Steps:
1. Ensure your `/etc/hosts` contains:
   127.0.0.1 farmway.in

2. Build and start services from frontend folder:

```bash
cd /home/user/projects/farmly-frontend
docker compose up -d --build
```

3. Visit http://farmway.in — Caddy routes `/` to the React app and `/api` or `/healy` to the Laravel app.

Notes:
- The override file `docker-compose.override.yml` expects the Laravel backend at `../backend/farmly`. Adjust `context` if different.
- For local development you may prefer not to use `--build` every time; use `docker compose up -d`.
- If port conflicts exist (Caddy or other services), change host ports in `docker-compose.yml`.
*** End Patch