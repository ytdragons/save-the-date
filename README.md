# Chantelle & Nicholas - save the date

Build: `save-the-date-final-2026-10-30` (in a `<meta name="build">` tag in index.html).
If that string isn't in index.html, this is the wrong copy.

One page. A plane crosses with the two of us in the doorway, Chantelle
drops a letter on a parachute, the guest opens it, and a card slides out
with the date. Nothing else.

```
index.html          the whole thing
fonts/              Bodoni Moda + Jost, self-hosted (OFL licence)
images/og.jpg       the preview image when the link is shared
.nojekyll           tells GitHub Pages to serve files as-is
```

No photos, no build step, no external requests.

## Deploy to GitHub Pages

1. Create a **public** repo, e.g. `save-the-date`. Leave it empty.
2. Push these files to `main`.
3. **Settings -> Pages**: Deploy from a branch, `main`, `/ (root)`.
4. Live at `https://YOUR-USERNAME.github.io/save-the-date/`

## Before sharing

`index.html` contains `https://REPLACE-ME.github.io/save-the-date/` four
times, all in the `<head>` (canonical, og:url, og:image, twitter:image).
Replace it with the real URL. The page works without this; link previews
in Messages and WhatsApp won't.

Check by texting yourself the link - you should see the card.

The page is marked `noindex`, so it won't turn up in Google.

## Editing the card

All in `index.html`, inside `<article class="iv-final__card">`:

| What | Where |
|---|---|
| Names | `<h1 class="iv-final__names">` |
| Date | the three `<div class="fw">` blocks - the `<i>` is the value each window lands on; the `<b>` values before it are what it flicks through on the way |
| Day of week | `<p class="iv-final__dow">` |
| The note | `<p class="iv-final__note">` |
