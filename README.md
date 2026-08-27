# Yuming Jin — personal academic website

Plain HTML + CSS. No build step, no dependencies. Hosted on GitHub Pages.

## Files

```
index.html          Home — bio, research interests, news
research.html       Research — currently an empty placeholder
publications.html   Papers (each with a thumbnail) + other publications
cv.html             Web CV — education, positions, awards, teaching, service
assets/img/pubs/    One thumbnail per paper, named <year>-<journal>-<topic>.jpg
_drafts/            Not published: the old research.html and teaching.html
assets/css/style.css   All styling. Colors and fonts are CSS variables at the top.
assets/img/            portrait.jpg and any figures
files/cv.pdf           Downloadable CV
404.html            Not-found page
```

## Editing

- **Colors / fonts** — change the variables in the `:root` block at the top of `style.css`. There is a matching dark-mode block below it.
- **Sidebar** (name, title, contact, profile links) — duplicated in the `<aside class="sidebar">` block of all five HTML pages. Change one, change all five.
- **Adding a publication** — copy an existing `<div class="pub">` block and edit it. Drop a matching 4:3 image into `assets/img/pubs/` and point the `<img src>` at it.
- **Replacing a paper thumbnail** — overwrite the file in `assets/img/pubs/` keeping the same name; no HTML change needed. Any aspect ratio works, it's center-cropped to 4:3.
- **Adding a news item** — copy an `<li>` inside `<ul class="news">` on `index.html`. Newest first.

## Publishing

Any push to `main` redeploys automatically, usually within a minute.

```bash
git add -A
git commit -m "Update publications"
git push
```

## Local preview

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```
