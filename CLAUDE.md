# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Purpose

This is Nicola Lorenzon's **personal portfolio and research showcase** — a site meant to stand out visually from typical GitHub Pages academic sites. Primary content areas are **projects** (`_portfolio/`) and **research** (`_publications/`). Design and layout choices should support a strong visual identity.

## Overview

Built with Jekyll, based on the [academicpages](https://github.com/academicpages/academicpages.github.io) template. Hosted via GitHub Pages at https://onlynicoo.github.io.

## Commands

```bash
# Install dependencies
bundle install

# Serve locally with live reload
bundle exec jekyll serve -l -H localhost

# Build the site
bundle exec jekyll build
```

> Note: `_config.yml` is NOT hot-reloaded during `jekyll serve`. Restart the server after any config changes.

## Site Architecture

Content is organized into Jekyll **collections** (in `_config.yml`):
- `_portfolio/` — project showcase entries
- `_publications/` — academic papers (categorized by `category:` front matter: `books`, `manuscripts`, `conferences`)
- `_talks/` — talk/presentation entries (use `talk` layout)
- `_teaching/` — teaching experience entries
- `_pages/` — standalone pages (included via `include: [_pages]` in config)
- `_posts/` — blog posts (currently unused/minimal)

**Layouts** (in `_layouts/`): `single`, `archive`, `archive-taxonomy`, `splash`, `talk`, `compress`

**Sidebar** is the author profile (`_includes/author-profile.html`). Author info comes from `author:` block in `_config.yml`.

**Navigation** is configured in `_data/navigation.yml`. Header nav items are defined there; currently only Portfolio is uncommented/active. To add a nav item, uncomment or add an entry under the `main:` key.

**Home page** is `_pages/about.md` (front matter: `permalink: /`).

## Key Configuration

- Author bio, social links, avatar: edit `author:` section in `_config.yml`
- CV: PDF file at `/files/CV_Nicola_Lorenzon.pdf`, embedded in `_pages/cv.md`
- Publication categories: defined under `publication_category:` in `_config.yml`
- The `_pages/publications.html` page renders publications grouped by category using Liquid

## Content Front Matter

Publications use `category:` to match `publication_category` keys (`books`, `manuscripts`, `conferences`).

Portfolio entries use the `single` layout with `author_profile: true` by default. The portfolio grid (`_pages/portfolio.html`) uses a Bootstrap-style card layout. The `excerpt:` field in a portfolio entry's front matter supports HTML, enabling rich card previews (e.g., badges, links, formatted descriptions).

## Git Workflow

Make **small, atomic, standalone commits** — one logical change per commit. Each commit message should clearly describe what changed and why. Commit after each meaningful change rather than batching unrelated edits.

## Code Comments

Add inline comments only where logic is non-obvious — particularly in Liquid templates, SCSS, and JavaScript. Do not add comments to self-explanatory code.
