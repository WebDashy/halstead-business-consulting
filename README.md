# Halstead Business Consulting — WebDashy Template

A multi-page, SEO-structured marketing site template for a business
consulting firm, built for use as a live preview template in
[WebDashy](https://github.com/WebDashy/webdashy).

This is the **Business-category reskin of Layout 1** (originally built as
Ironpeak Construction) — same page structure and CSS component system,
with new colors (navy + deep teal), fonts (Spectral + Source Sans 3),
stock photography, and all-new copy for a business consulting business.
See "Reskinning for a different category" below for exactly what changed
and what stayed the same.

Ships with real stock photography (sourced from Pexels, free for
commercial use, no attribution required) in `assets/img/`.

Built with [Jekyll](https://jekyllrb.com/) using only the plugins GitHub
Pages runs natively (`jekyll-seo-tag`, `jekyll-sitemap`) — no local build
step required to deploy: push to `main` and GitHub Pages builds it for you.

## Structure

Same convention as every WebDashy layout:

```
_config.yml           site-wide settings + business info
_layouts/default.html shared page shell — head/SEO tags, header, footer
_includes/             header.html, footer.html
assets/css/styles.css  all styling — CSS custom properties at the top are
                       what change when this layout gets reskinned for a
                       different WebDashy category
assets/js/script.js    mobile nav toggle
assets/img/            stock photography — hero and case-study imagery
index.html             home
services/index.html    services hub
services/<slug>/       one folder per service
about/                 company story + testimonials
projects/               case study gallery
contact/                contact form + info
robots.txt              points at the auto-generated sitemap.xml
```

## Reskinning for a different category

This is itself a reskin of Layout 1 (Ironpeak Construction) — the CSS
custom property *names* in `assets/css/styles.css` still say `--amber`
etc. from the original Construction version, but hold new teal values.
That's intentional: renaming the tokens risks breaking references across
the stylesheet for no visible benefit. When reskinning this file again:

- Change the `:root` custom property *values* (not necessarily the
  names) in `assets/css/styles.css`
- Also update the hardcoded `rgba(...)` values in `.hero-overlay` and
  `--shadow` — those aren't tokenized and were hand-matched to this
  version's ink color
- Swap the Google Fonts `<link>` in `_layouts/default.html`
- Swap the photography in `assets/img/`
- Rewrite all business content — `_config.yml`'s `business:` block plus
  every page's text

## Local preview

```bash
bundle install
bundle exec jekyll serve
```

Then open `http://localhost:4000/halstead-business-consulting/`.

## Deploying

**GitHub Pages** (this repo): Settings → Pages → Deploy from branch →
`main` / `/ (root)`. GitHub builds the Jekyll site automatically on every
push.
