# Daily Dashboard

A personal daily dashboard that runs entirely in your browser as an installable
app (PWA). All data is stored locally on your device (IndexedDB) — nothing is
sent to a server.

## Publish it (one-time setup)

1. On GitHub, open this repository's **Settings → Pages**.
2. Under **Build and deployment**, set **Source** to "Deploy from a branch",
   choose the `main` branch and the `/ (root)` folder, then **Save**.
3. After a minute or two your dashboard will be live at
   `https://<your-username>.github.io/Daily-Dashboard/`.

## Install it on your phone

**iPhone (Safari):** open the URL above, tap the **Share** button, then
**Add to Home Screen**. The dashboard opens full-screen like a native app.

**Android (Chrome):** open the URL, tap the **⋮** menu, then
**Add to Home screen** (or accept the "Install app" prompt).

Once installed, the app works offline — the service worker (`sw.js`) caches
everything on first load.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The entire app — UI, logic, and bundled libraries in one file |
| `manifest.webmanifest` | App name, colors, and icons for installation |
| `sw.js` | Service worker that makes the app load instantly and work offline |
| `icon-192.png`, `icon-512.png`, `apple-touch-icon.png` | Home-screen icons |

## Updating the dashboard

Replace `index.html` with a new version (keeping the manifest link and
service-worker registration script intact), commit, and push. Installed apps
pick up the new version the next time they're opened with a connection.

Your data lives in your browser's IndexedDB under the `lifeDashboard` database,
so updating the app does not erase it. It is per-device and per-browser,
though — clearing site data will delete it.
