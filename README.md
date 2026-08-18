# Personal website — Aqila Putri

Plain HTML and CSS. No Jekyll, no build step, no dependencies. Edit the `.html`
files directly and the changes are live as soon as you push.

## Files

```
index.html        Home — about, research interests, education
research.html     Publications, working papers, works in progress
cv.html           Link to CV PDF
assets/style.css  All styling (colors, fonts, layout in one place)
assets/photo.jpg  Your portrait — REPLACE THIS
```

## Before you publish

1. **Swap the photo.** Replace `assets/photo.jpg` with a real headshot. Square
   crop, roughly 600×600px or larger. Keep the filename `photo.jpg` and nothing
   else needs to change.

2. **Check the abstracts** in `research.html`. I paraphrased them from your
   Google Site — replace the text between the `<p class="abstract">` tags with
   your actual abstracts. Look for the `<!-- TODO -->` comments.

3. **Optional: host your CV on the site.** Right now `cv.html` links to your
   Dropbox copy. To serve it from the site instead, drop the PDF at
   `assets/cv.pdf` and change the `href` in `cv.html` to `assets/cv.pdf`.

## Publishing to GitHub Pages

1. Go to <https://github.com/new>.
2. Name the repository **exactly** `aqilalistyaputri.github.io` — matching your
   GitHub username, all lowercase. The name is what determines the URL.
3. Set it to **Public**. Don't add a README (this folder has one).
4. Click **Create repository**.
5. On the empty repo page, click **uploading an existing file**.
6. Drag in `index.html`, `research.html`, `cv.html`, `README.md`, and the whole
   `assets` folder. Commit.
7. Go to **Settings → Pages**. Under "Build and deployment", set Source to
   **Deploy from a branch**, branch **main**, folder **/ (root)**. Save.
8. Wait 1–2 minutes. Your site is live at <https://aqilalistyaputri.github.io>.

## Making edits later

Easiest path: open the file on GitHub, click the pencil icon, edit, commit.
The site rebuilds in under a minute.

If you'd rather work locally:

```bash
git clone https://github.com/aqilalistyaputri/aqilalistyaputri.github.io.git
cd aqilalistyaputri.github.io
# edit files, then:
git add . && git commit -m "Update research page" && git push
```

To preview locally before pushing, just open `index.html` in a browser — no
server needed.

## Adding a section (e.g. Teaching)

1. Copy `cv.html` to `teaching.html`.
2. Replace the content inside `<main class="content">`.
3. In the `<nav>` block of **all four** pages, add:
   `<li><a href="teaching.html">Teaching</a></li>`
4. On `teaching.html` itself, move `class="here"` to the Teaching link.

## Changing the look

Everything visual lives in `assets/style.css`, in the `:root` block at the top:

```css
--accent: #7a1f2b;   /* link color and accents — currently a muted maroon */
--ink:    #1a1a1a;   /* body text */
--serif:  Georgia;   /* headings and paper titles */
--sans:   Helvetica; /* body text */
```

Change those four values and the whole site follows.

## Custom domain (optional)

If you buy `aqilaputri.com` later, add a file named `CNAME` (no extension)
containing just `aqilaputri.com`, then point the domain's DNS at GitHub Pages
per <https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site>.
