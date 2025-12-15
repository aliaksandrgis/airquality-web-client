# AirQuality Web Client

Single-page HTML/JS app (OpenLayers + Chart.js). It loads `/api/*` endpoints, so the hosting layer must proxy `/api` to the Geo API domain.

## Local preview

1. Clone the repo.
2. Serve `index.html` via any static server, for example `python -m http.server 8081`.
3. Configure a proxy `/api` → `http://localhost:8000` (running Geo API).

## Deployment

- **Cloudflare Pages / static hosting**: upload `index.html` (and assets) and add a rule proxying `/api/*` to `https://api.naviodev.com/*`.
- **Docker**: use the provided `Dockerfile` + `nginx.conf` to serve the app and proxy `/api`.

## Files

- `index.html` — main UI.
- `nginx.conf` — nginx config (static + `/api` proxy).
- `Dockerfile` — container image based on nginx.

## Domain setup (`air.naviodev.com`)

1. Host the static files (Cloudflare Pages or Docker).
2. Ensure `/api` requests are forwarded to `https://api.naviodev.com`.
3. Update Geo API CORS (`ALLOWED_ORIGINS=https://air.naviodev.com`).
