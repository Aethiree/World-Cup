# World Cup 26 — Live (PWA)

Installable, offline-capable PWA for the 2026 FIFA World Cup: live scores, full
104-match schedule (your local time), standings, key matches, a follow list, and
a live bracket org chart from the Round of 32 to the Final.

## Files
- `index.html` — the whole app
- `manifest.json` — PWA manifest
- `sw.js` — service worker (offline + install)
- icons (192 / 512 / maskable / apple-touch)

## Live data & knockout
- Online: scores auto-pull from a free no-key feed (TheSportsDB) on launch and every ~75s.
- Knockout slots (2A, 1C, W73…) fill automatically from the group standings the app
  computes, and winners advance through the bracket on their own.
- Tap any match (including bracket nodes) to set teams / score / who advances yourself.
  Saved on-device; the feed won't overwrite your manual edits.

## Deploy (HTTPS or localhost — not file://)
GitHub Pages: upload all files to the repo root, Settings → Pages → Deploy from branch →
main / root. Open the URL, Add to Home Screen.
Re-uploading an update: replace all files (especially index.html and sw.js — the cache
version is bumped each release), then fully close and reopen the installed app once.
