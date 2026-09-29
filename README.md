# Note Nailer

A guitar fretboard trainer that ties every fret to its note name, its spot in tab, and where it's written on the treble staff (guitar is written an octave above how it sounds).

## Modes
- **Find it:** a note on the staff; tap a fret that plays it.
- **Read it:** name the note on the staff.
- **Name it:** name the marked fret.
- **Explore:** tap any fret, or pick a note to see every place it lives, colored by octave.

## Options
- Fret range (from / to): the neck zooms to that slice at real fret spacing.
- Strings on/off, with per-string accuracy.
- Views: tab view, over the shoulder (tilted), facing a player (mirrored).
- One spot only: blocks the frets holding other copies of the note, so you have to use the asked-for position.
- Note names on neck, piano-key coloring of the frets, sharps & flats, sound.

Missed spots come back more often. Settings, best streak, and view are saved in the browser (localStorage).

## Files
| File | What it is |
|---|---|
| `index.html` | The whole app: markup, styles, and script in one file. No build step. |
| `sw.js` | Service worker that caches the app so it works offline. |
| `manifest.webmanifest` | Lets it install to a phone home screen and open full screen. |
| `icon-*.png` | Home-screen and browser icons. |

## Run locally
Open `index.html` in a browser. For the offline cache and install prompt, serve it over HTTP instead:

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deploy
It's a static site, so any static host works.

- **GitHub Pages:** push to GitHub, then Settings → Pages → Deploy from a branch → `main`, folder `/ (root)`.
- **Netlify / Cloudflare Pages:** point it at the repo with no build command and the repo root as the publish directory.

On iPhone: open the site in Safari → Share → Add to Home Screen.

## Updating
After changing `index.html`, bump the cache name at the top of `sw.js` (`fts-vN`) so phones that already installed it pick up the new version.
