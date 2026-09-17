# Jammat Journey

Private, offline-first Jammat daily tracker by **Sufiyan Ahmed S A**. It is a dependency-free static PWA: daily data lives in IndexedDB, lightweight preferences live in localStorage, and the service worker caches the app for offline use.

## Run and deploy

Serve the folder with any static web server (for example `npx serve .`) or deploy the root to GitHub Pages. Open it once online so the service worker can cache assets; then install it from the browser menu.

## Data and privacy

No account or server is required. Export produces a versioned JSON backup; import validates its basic schema. Location is requested only after the user presses **Use current location** and is saved only in that date's local record.

## Architecture

- `data/questions.json` — data-driven conditional questionnaire
- `js/app.js` — routing, IndexedDB, onboarding, daily engine, history, export/import and UI
- `service-worker.js` / `manifest.json` — installability and offline cache
- `css/app.css` — responsive premium light/dark interface

Browser notifications are best-effort: browsers cannot guarantee reminders while the app is fully closed.
