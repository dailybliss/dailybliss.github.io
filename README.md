# DailyBliss Website

Jekyll-based static site for DailyBliss, hosted on GitHub Pages.

## Structure

```
.
├── _config.yml                    # Site config, nav definitions
├── _includes/
│   ├── header.html                # Shared top nav
│   └── footer.html                # Shared footer
├── _layouts/
│   └── default.html               # Shared layout (CSS, chrome)
├── assets/
│   ├── serenerise.jpg             # SereneRise app icon
│   └── vedicwisdom.jpg            # Vedic Wisdom app icon
├── index.html                     # Homepage
├── apps/
│   ├── index.html                 # Apps listing
│   ├── serenerise/
│   │   ├── index.html             # Marketing page + FAQ
│   │   └── privacy.html           # Privacy policy (link to this from Play Store)
│   └── vedicwisdom/
│       ├── index.html
│       └── privacy.html
├── tools/
│   ├── index.html                 # Tools listing
│   └── brahma-muhurta/
│       └── index.html             # Interactive calculator
└── blog/
    ├── index.html
    └── what-is-brahma-muhurta.html
```

## URLs

GitHub Pages will serve clean URLs (because `permalink: pretty` is set in `_config.yml`):

- `/` — homepage
- `/apps/serenerise/` — SereneRise page
- `/apps/serenerise/privacy/` — SereneRise privacy policy (use this URL in your Play Store listing)
- `/apps/vedicwisdom/` — Vedic Wisdom page
- `/apps/vedicwisdom/privacy/` — Vedic Wisdom privacy policy
- `/tools/brahma-muhurta/` — Brahma Muhurta calculator
- `/blog/` — blog index
- `/blog/what-is-brahma-muhurta/` — first article

## Deployment

Jekyll runs automatically on GitHub Pages. Just push to the branch you've configured for Pages (typically `main` or `gh-pages`) and it'll build and deploy within a minute or two.

## Editing

### Adding a new page

Create the HTML file with Jekyll front matter at the top:

```
---
layout: default
title: Page Title
description: Meta description for search engines.
---

<article class="page">
  <h1>Page content here</h1>
  ...
</article>
```

### Adding a new app

1. Create `apps/<appname>/index.html` — copy from an existing app as template.
2. Create `apps/<appname>/privacy.html` — copy + edit.
3. Add an icon to `assets/<appname>.jpg` (512×512 recommended).
4. Add a card to the homepage (`index.html`) and the apps listing (`apps/index.html`).

### Adding a blog post

1. Create `blog/<slug>.html` with front matter.
2. Add an entry to the list in `blog/index.html`.

### Adding a nav item

Edit the `nav:` list in `_config.yml`.

### Updating privacy policies

Both privacy policies live at `apps/<appname>/privacy.html`. The "Last updated" date in the page body should be updated whenever you change anything substantive.

## Local preview (optional)

If you have Ruby installed:

```bash
bundle install
bundle exec jekyll serve
```

Then visit `http://localhost:4000`.
