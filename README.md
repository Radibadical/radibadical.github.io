# radibadical.github.io

Personal landing page and project hub for [radibadical.com](https://radibadical.com).

---

## Projects

| Project | URL | Repo |
|---|---|---|
| Top 200 Movies | [radibadical.com/movies](https://radibadical.com/movies/) | [Radibadical/movies](https://github.com/Radibadical/movies) |
| Music | [radibadical.com/spotify](https://radibadical.com/spotify/) | this repo (`spotify/index.html`) |

---

## Structure

```
index.html              Landing page
spotify/index.html      Spotify playlist embeds
favicon.svg             Global favicon (gold R mark, SVG)
favicon.png             32×32 PNG fallback favicon
apple-touch-icon.png    180×180 iOS home screen icon
CNAME                   Custom domain: radibadical.com
```

All pages across the site link to the favicons in this repo via root-relative paths.

---

## Adding a project

New project repos automatically serve at `radibadical.com/<reponame>` via GitHub Pages
— no DNS changes needed. To add a card on the landing page:

1. Add a CSS rule for the card color in `index.html`
2. Add an `<a class="card card-projectname">` block in the `.cards` div
3. Add `<link rel="icon">` tags in the project repo's HTML pointing to `/favicon.svg` etc.

---

## Deployment

Hosted on GitHub Pages from the `main` branch. Pushes to `main` redeploy within ~1 minute.

Custom domain `radibadical.com` is registered on Porkbun with DNS via Cloudflare.
