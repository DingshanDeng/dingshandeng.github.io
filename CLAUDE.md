# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a personal academic website for Dingshan Deng (PhD candidate at the University of Arizona), built with Jekyll and deployed to GitHub Pages at https://dingshandeng.github.io. It uses the [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) theme (`mint` skin).

## Local Development

```bash
# Install dependencies (first time)
bundle install

# Serve locally with live reload
bundle exec jekyll serve --livereload

# Build without serving
bundle exec jekyll build
```

The site auto-deploys to GitHub Pages on every push to `main` via `.github/workflows/jekyll.yml`.

## Site Architecture

**Theme**: `mmistakes/minimal-mistakes@4.26.2` (pulled via `remote_theme`). The site overrides specific theme components rather than maintaining a full local copy.

**Key files**:
- `_config.yml` — all site-wide settings: theme, author profile, navigation, plugins, pagination
- `index.html` — home page (uses `splash` layout with custom HTML/CSS inline)
- `_data/navigation.yml` — top nav bar links
- `_includes/head/custom.html` — injects Academicons CSS (for ADS/ORCID icons)
- `assets/css/custom.css` — all custom component styles (paper cards, intro grid, tile grid)
- `assets/css/main.scss` — imports the Minimal Mistakes base; leave as-is

**Content**:
- `_pages/` — static pages (research, software, posts, photos); each has YAML front matter with `permalink`, `layout`, and `classes: wide`
- `_posts/` — blog posts in `YYYY-MM-DD-title.md` format, auto-listed at `/posts/`
- `assets/images/` — all images referenced in pages and the CV PDF

## Custom CSS Components

All custom styles live in `assets/css/custom.css`. Current components:

- `.paper-card` / `.paper-card__inner` — two-column grid card used in `_pages/research.md` to display papers (image left, body right; stacks to single column below 800px)
- `.intro-grid` — flex layout on the home page for photo + bio side-by-side
- `.tile-grid` / `.tile-card` — two-column card grid on the home page for Research/Software tiles

When adding new layout components, add styles to `custom.css` rather than inline `<style>` blocks (the home page has some inline styles as legacy; prefer the CSS file for new work).

## Adding Content

**New research paper** — add a `<section class="paper-card">` block in `_pages/research.md` following the existing pattern.

**New blog post** — create `_posts/YYYY-MM-DD-slug.md` with front matter:
```yaml
---
title: "Post Title"
date: YYYY-MM-DD
layout: single
author_profile: true
classes: wide
---
```

**New nav page** — add a `.md` file to `_pages/` with a unique `permalink`, then add an entry to `_data/navigation.yml` under `main`.

**CV** — replace `assets/cv.pdf` directly; the home page links to it at `/assets/cv.pdf`.

## Icons

Author sidebar and footer use Font Awesome (`fas`, `fab` prefixes) and Academicons (`ai` prefix, loaded via CDN in `_includes/head/custom.html`). Icon keys like `ai ai-ads`, `ai ai-orcid`, `ai ai-google-scholar` are Academicons classes.
