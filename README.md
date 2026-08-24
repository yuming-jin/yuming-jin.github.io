# yumingjin — personal academic website

Plain HTML + CSS. No build step, no dependencies. Hosted on GitHub Pages.

## Files

```
index.html          Home — bio, research interests, news
research.html       Research themes, software & data
publications.html   Papers, preprints, talks
teaching.html       Courses, mentoring, outreach
cv.html             Web CV
assets/css/style.css   All styling. Colors and fonts are CSS variables at the top.
assets/img/            portrait.jpg and any figures
files/cv.pdf           Downloadable CV
404.html            Not-found page
```

## Editing

- **Colors / fonts** — change the variables in the `:root` block at the top of `style.css`. There is a matching dark-mode block below it.
- **Sidebar** (name, title, contact, profile links) — duplicated in the `<aside class="sidebar">` block of all five HTML pages. Change one, change all five.
- **Adding a publication** — copy an existing `<div class="pub">` block and edit it.
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
