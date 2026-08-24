# Chantelle & Nicholas - save the date

Static site. No build step, no dependencies. Three files and a folder of images.

```
index.html
images/hero.jpg     hero background
images/aisle.jpg    full-width plate
images/og.jpg       link preview when the URL is shared
```

---

## Deploying to GitHub Pages

**1. Create the repository**

Sign in at github.com, click **New repository**. Name it `save-the-date`.
Set it to **Public** - Pages needs public on a free account. Don't tick
"Add a README", the repo should start empty.

**2. Upload the files**

On the empty repo page, click **uploading an existing file**. Drag in
`index.html`, `README.md`, `.nojekyll`, and the whole `images` folder.
Click **Commit changes**.

**3. Turn Pages on**

**Settings** -> **Pages** in the left sidebar. Under *Build and deployment*
set Source to **Deploy from a branch**, branch **main**, folder **/ (root)**.
Click **Save**.

Give it about a minute. The URL appears at the top of that same page and
looks like:

```
https://YOUR-USERNAME.github.io/save-the-date/
```

**4. Fix the six placeholder URLs**

`index.html` contains `https://REPLACE-ME.github.io/save-the-date/` in six
places - the canonical tag, the Open Graph tags, the structured data, and the
calendar file. These only affect link previews and search results, not whether
the page works.

In GitHub, open `index.html`, click the pencil icon, use **Ctrl/Cmd + F**,
and replace `REPLACE-ME` with your actual username. Commit.

**5. Check the link preview**

Paste the URL into a message to yourself. You should get the photograph and
"Chantelle & Nicholas - 13 May 2027". If it shows nothing, the og:image URL is
still wrong - recheck step 4.

---

## Using your own domain

Buy the domain, then:

1. Add a file named `CNAME` to the repo containing one line, e.g.
   `chantelleandnicholas.com` - no `https://`, no trailing slash.
2. At your registrar, create four `A` records for `@` pointing at
   `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`,
   and a `CNAME` record for `www` pointing at `YOUR-USERNAME.github.io`.
3. **Settings** -> **Pages** -> Custom domain, enter it, then tick
   **Enforce HTTPS** once the certificate is issued (can take an hour).
4. Redo step 4 above with the real domain.

---

## A faster alternative

If GitHub feels like a lot: go to app.netlify.com/drop and drag this whole
folder onto the page. You get a live URL in about ten seconds with no account.
Same result, and you can attach a custom domain later.

---

## Editing later

Everything is in `index.html`. The things most likely to change:

| What | Where to look |
|---|---|
| Names, date, venue | the `<h1>` and the date apertures near the top of `<body>` |
| The two-day plan | the `<ol class="days">` block |
| Travel and rooms | the three `<article class="card">` blocks |
| Contact email | search for `hello@chantelleandnicholas.com` |
| Colours | the `:root` block at the top of `<style>` |
| Calendar event | the `EV` object in the script at the bottom |

The intro animation is self-contained. Everything belonging to it is prefixed
`iv-` and sits between the `INTRO LAYER` comments. Deleting that block and its
`<style id="iv-style">` removes the animation without touching the site.
