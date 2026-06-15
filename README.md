# World Cup 26 — Live (PWA)

An installable, offline-capable Progressive Web App for the 2026 FIFA World Cup:
live scores, the full 104-match schedule (Eastern Time), auto-computed standings,
key matches, and filters. Built as plain HTML/CSS/JS — no build step, no dependencies.

## Files
- `index.html` — the whole app
- `manifest.json` — PWA manifest (name, icons, theme)
- `sw.js` — service worker (offline caching + installability)
- `icon-192.png`, `icon-512.png`, `icon-512-maskable.png`, `apple-touch-icon.png`

## How the live scores work
- **Online:** scores auto-pull from a free, no-key sports feed (TheSportsDB) every ~75s
  and on launch. Results from June 11–13 are pre-loaded so it's useful immediately.
- **Anytime:** tap any group-stage match to set its score yourself. Edits save on the
  device (localStorage) and feed the standings. Manual edits aren't overwritten by the feed.
- If the feed has no 2026 data yet or you're offline, the schedule + your saved scores
  keep working, and standings still compute.

Knockout matchups show as placeholders (2A, 1C, W73…) and resolve as groups finish.

## Run / deploy (a PWA must be served over HTTPS or localhost — not file://)

### Option A — GitHub Pages (same as before)
1. Create a repo, upload all files in this folder to the root.
2. Settings → Pages → Deploy from branch → `main` / root.
3. Open the published URL on your phone. In Chrome (Android) use the "Install app"
   prompt / ⋮ menu → *Add to Home screen*. On iPhone Safari: Share → *Add to Home Screen*.

### Option B — test locally first
```bash
cd this-folder
python3 -m http.server 8080
# open http://localhost:8080 then install from the browser menu
```

All paths are relative, so it works from a sub-path like `username.github.io/world-cup-26/`.
