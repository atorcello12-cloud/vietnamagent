# Vietnam Family Trip

A phone-friendly trip app for our family trip to Vietnam (31 Oct – 15 Nov 2026): route and day ideas, flights, where locals eat, things to do, and a travel toolkit.

## Live site

Hosted with GitHub Pages: **Settings → Pages → Build and deployment → Deploy from a branch → `main` / `(root)` → Save**.
The site appears at `https://atorcello12-cloud.github.io/vietnamagent/` a minute or two later.

On Android, open it in Chrome, tap **⋮ → Add to Home screen** (or **Install app**) to get it as an app with its own lantern icon.

## Files

| File | What it is |
|---|---|
| `index.html` | The whole app: content, styles and scripts in one file |
| `sw.js` | Offline support: caches the app so it opens without signal once it has been loaded online |
| `manifest.webmanifest` | App name, colours and icons for "Add to Home screen" |
| `icon-192.png`, `icon-512.png` | App icons |

## Editing

Everything lives in `index.html`. The trip data is near the top of the main `<script>`:

- `TRIP.stages` – route, hotels and day ideas
- `TRIP.flights` – boarding passes
- `TRIP.food` – Eat tab (breakfast / lunch / dinner)
- `TRIP.activities` – Do tab picks
- `COST` – rough prices
- `RAFFY_KIT`, `PHRASES` – Toolkit cards

After pushing a change, phones pick it up the next time the app is opened online. If an old version sticks, bump `VERSION` in `sw.js`.

## Notes

- **Live exchange rate:** the converter fetches AUD→VND from open.er-api.com (falls back to the free currency-api feed), refreshing every 6 hours or when you tap ↻.
- **Directions:** each place has a Directions button that opens Google Maps from your current location (it uses downloaded offline areas when there's no signal), plus an "Offline maps app" button that opens the place in any installed maps app such as Organic Maps.
- **Translator:** live translation only works inside Claude (claude.ai). On GitHub Pages it offers Google Translate instead. Listen uses the phone's built-in voices.
