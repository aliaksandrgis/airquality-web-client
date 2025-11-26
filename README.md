# AirQuality Web Client

Static web client (Cloudflare Pages) that consumes the Geo API.

## Quick start
```bash
npm install
cp .env.example .env  # set API base URL
npm run build
npm run preview
```

## Environment (.env)
- `VITE_API_BASE_URL` — e.g., `https://api.air.naviodev.com`.

## Deployment
- Configure Cloudflare Pages with the same build commands and env vars.
- No secrets on the client; only public API URLs.

## CI (template)
- `npm ci`, `npm run lint` (if configured), `npm run build`.
