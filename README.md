# Yuming Jin — personal academic website

Plain HTML + CSS. No build step, no dependencies. Hosted on GitHub Pages at
<https://yuming-jin.github.io>.

## Files

```
index.html             Home — big portrait left, bio and research interests right
research.html          Research — five project blocks
publications.html      Papers, numbered, with HTML/PDF links and Altmetric badges
404.html               Not-found page
assets/css/style.css   All styling. Colors and fonts are CSS variables at the top.
assets/img/            portrait.jpg
assets/img/research/   Figures, animations and originals for the Research page
files/cv.pdf           Downloadable CV
files/papers/          One PDF per paper
_drafts/               Not published: old pages, and blocks parked for later
_to_delete/            Safe to remove
```

## Page layouts

Every page is wrapped in `<div class="page">`, a single centred column (900px).
Two pages widen it: `page-home` (1080px, for the two-column hero) and
`page-research` (990px, so the 400px figure column leaves room for text).
Only the home page carries the portrait and the Scholar / ResearchGate / CV
links. The other pages are nav, title and content.

## Research page

Each project is one `<article class="project">`: a 400px left column holding a
figure, its caption and a "Relevant publications" line, and the description on
the right. Blocks stack to a single column below 780px. There is a how-to
comment above the first block. Conventions:

- Publications are one line, newest first, separated by semicolons, written as
  `Author et al., year, JOURNAL`. Under-review papers come first, say
  `Under review, JOURNAL`, and link to the preprint. One exception, the Morgan
  et al. paper deliberately hides its target journal.
- Figures live in `assets/img/research/`. Keep the original and commit a web
  copy at about 1400px wide (`convert original.png -resize 1400x -strip
  -colors 255 web-copy.png`). PDFs must be converted, browsers will not render
  a PDF in `<img>`.
- Videos use `<video autoplay loop muted playsinline controls>` with explicit
  `width`/`height` and an inline `width:100%`. Muted is required for autoplay.

## Publications page

Both lists are numbered by a CSS counter that counts **down**, so the newest
paper carries the highest number and the numbering runs continuously from the
submitted section into the peer-reviewed one, matching the CV. Never type a
number into an entry. When you add a paper, bump the `counter-reset` value on
that section's `<div class="pub-list">` by one.

Each peer-reviewed paper with a DOI carries an Altmetric donut at its right
edge. The badge stays invisible until the paper has been mentioned somewhere,
so a blank space there is normal, not a bug.

## Writing style

Body prose is justified and avoids dashes, colons and semicolons. Captions,
publication lines and the nav stay ragged-right and may use them.

## Editing

- **Colors / fonts** — the `:root` block at the top of `style.css`, with a
  matching dark-mode block below it. Figures should work in both themes.
- **Adding a publication** — the comment block under "Peer-reviewed
  publications" in `publications.html` has a copy-paste template.
- **Adding the PDF** — drop it into `files/papers/` first, then point the PDF
  link at it. `<year>-<journal>-<topic>.pdf` keeps the folder readable.
- **A new year** — add `<h2 class="pub-year">2027</h2>` above that year's first paper.

## Publishing

Any push to `main` redeploys automatically, usually within a minute. Hard-refresh
afterwards (Cmd+Shift+R), GitHub Pages caches HTML and CSS for about 10 minutes.

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
