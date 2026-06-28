# radibadical.github.io — Claude Context

## Overview

Root site for `radibadical.com`. Serves the landing page and any subpages that
don't warrant their own repo. Deployed via GitHub Pages from `main`.

**Live URL:** https://radibadical.com/
**Repo:** `Radibadical/radibadical.github.io`

## File structure

| File | Serves at | Purpose |
|---|---|---|
| `index.html` | `radibadical.com/` | Landing page with project cards |
| `spotify/index.html` | `radibadical.com/spotify/` | Spotify playlist embeds |
| `CNAME` | — | Custom domain declaration (`radibadical.com`) |

## Landing page (`index.html`)

Dark theme (`#0d1117`) matching the movies site. Two-card grid linking to:
- `/movies/` — movie list
- `/spotify/` — playlist page

Cards use coloured top borders: gold for Movies (`#d4a017`), Spotify green for
Music (`#1db954`). Additional project cards can be added to the `.cards` grid.

## Spotify page (`spotify/index.html`)

18 Spotify embed iframes in a responsive grid (`minmax(320px, 1fr)`).
Playlist IDs are hardcoded — no API keys or auth in the page. Embeds load
live from Spotify; adding songs to a playlist is reflected automatically.
Users play via their own Spotify session; non-logged-in users get 30s previews.

Header matches the landing page style: "RADIBADICAL" with "Playlists" byline
below, blue rule lines, and a "← radibadical" back link.

## Updating

```bash
cd /tmp/radibadical.github.io   # or wherever cloned
# edit files
git add . && git commit -m "..." && git push
```

GitHub Pages redeploys automatically within ~1 minute.

## Domain and hosting

Custom domain: `radibadical.com` — registered on Porkbun, DNS via Cloudflare.
HTTPS enforced. See `Radibadical/movies` CLAUDE.md for full DNS record details.

Project repos (`movies`, etc.) automatically serve at `radibadical.com/<reponame>`
— no DNS changes needed when adding new projects.
