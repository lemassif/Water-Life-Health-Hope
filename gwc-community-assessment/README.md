# GWC Community Assessment

Author: Rick Sebastian

Offline-ready field app for running community water assessments. Version 1.5.0.

## Files

| File | Purpose |
|---|---|
| `index.html` | The app: screens, questions, local storage, export, and sync |
| `i18n.js` | Translations for Español, Kiswahili, and नेपाली. English text lives in `index.html`. Answers are always stored in English. |
| `sw.js` | Service worker that caches the app so it works with no signal |
| `manifest.webmanifest` | Lets the app install to a phone home screen |
| `icon.svg`, `icon-192.png`, `icon-512.png` | App icons |

## Running it

Serve the folder from any static web host (GitHub Pages works). The service worker needs `http` or `https`, so opening `index.html` straight from disk will run the app but will not cache it for offline use.

## Database sync

Records save on the device first and sync to Supabase when a connection is available. The connection is blank by default. Enter the project URL, anon public key, and table name on the Settings screen, or fill in `SUPABASE_URL` and `SUPABASE_ANON_KEY` near the top of the script in `index.html`. The default table is `gwc_assessments`.

Do not commit a filled-in key to this repo.
