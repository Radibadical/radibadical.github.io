# radibadical.github.io — Claude Context

## Overview

Root site for `radibadical.com`. Serves the landing page and any subpages that
don't warrant their own repo. Deployed via GitHub Pages from `main`.

**Live URL:** https://radibadical.com/
**Repo:** `Radibadical/radibadical.github.io`
**Local path:** `/home/jakedog/ghq/github.com/Radibadical/radibadical.github.io`

## File structure

| File | Serves at | Purpose |
|---|---|---|
| `index.html` | `radibadical.com/` | Landing page with project cards |
| `spotify/index.html` | `radibadical.com/spotify/` | Spotify playlist embeds |
| `favicon.svg` | `radibadical.com/favicon.svg` | SVG favicon (global — all subprojects reference `/favicon.svg`) |
| `favicon.png` | `radibadical.com/favicon.png` | 32×32 PNG fallback favicon |
| `apple-touch-icon.png` | `radibadical.com/apple-touch-icon.png` | 180×180 PNG for iOS home screen |
| `CNAME` | — | Custom domain declaration (`radibadical.com`) |

## Favicon

Three formats for broad coverage:
- `favicon.svg` — modern browsers (Chrome, Firefox, Safari 15+). Gold serif "R" on dark `#0d1117` background.
- `favicon.png` — 32×32 PNG fallback for older browsers. Generated from the SVG via Inkscape.
- `apple-touch-icon.png` — 180×180 PNG for iOS "Add to Home Screen".

All pages across the site link to these via root-relative paths:
```html
<link rel="icon" type="image/svg+xml" href="/favicon.svg">
<link rel="icon" type="image/png" sizes="32x32" href="/favicon.png">
<link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png">
```

To update the favicon: edit `favicon.svg`, regenerate PNGs with Inkscape, commit all three files.

```bash
inkscape favicon.svg --export-type=png --export-filename=favicon.png --export-width=32 --export-height=32
inkscape favicon.svg --export-type=png --export-filename=apple-touch-icon.png --export-width=180 --export-height=180
```

## Landing page (`index.html`)

Dark theme (`#0d1117`) matching the movies site. Card grid linking to projects:

| Card class | Color | Links to |
|---|---|---|
| `.card-movies` | Gold `#d4a017` | `/movies/` |
| `.card-music` | Spotify green `#1db954` | `/spotify/` |
| `.card-twitch` | Twitch purple `#9146ff` | (CSS defined, no card in HTML yet) |

To add a new project card, add a new `<a class="card card-X">` block in the `.cards` div and a
corresponding `.card-X` / `.card-X:hover` rule in the CSS.

## Spotify page (`spotify/index.html`)

18 Spotify embed iframes in a responsive grid (`minmax(320px, 1fr)`).
Playlist IDs are hardcoded — no API keys or auth in the page. Embeds load
live from Spotify; adding songs to a playlist is reflected automatically.
Users play via their own Spotify session; non-logged-in users get 30s previews.

Header matches the landing page style: "RADIBADICAL" with "Playlists" byline
below, blue rule lines, and a "← radibadical" back link.

## Updating

```bash
cd /home/jakedog/ghq/github.com/Radibadical/radibadical.github.io
# edit files
git add <files> && git commit -m "..." && git push
```

GitHub Pages redeploys automatically within ~1 minute.

## Domain and hosting

Custom domain: `radibadical.com` — registered on Porkbun, DNS via Cloudflare.
HTTPS enforced. See `Radibadical/movies` CLAUDE.md for full DNS record details.

Project repos (`movies`, etc.) automatically serve at `radibadical.com/<reponame>`
— no DNS changes needed when adding new projects.
