# TuffClient — Base44 dev notes

## What this is
A **pure static site** (no build step, no backend, no package manager). It's the
TuffClient Eaglercraft client distribution page: `index.html` + `files.css` at the
repo root, game builds under `files/<version>/{WASM,JS}/`, a service worker `sw.js`,
and `js/eags-servers.js` injected into game pages by the service worker.

## Running it
`docker compose -f docker-compose.base44.yml up -d` — nginx:alpine serves the repo
root on host port 3000. No dependencies to install, no build, no migrations, no
secrets. Edits to HTML/CSS/JS are live on refresh (nginx serves files directly).

## Verifying
`curl -s http://localhost:3000/ | grep -i tuff` should return the page title.
The preview shows the TuffClient landing page with Latest / Archive / Support tabs.
