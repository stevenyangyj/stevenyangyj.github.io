# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Build & Development Commands

```bash
bundle install                    # Install Ruby dependencies (delete Gemfile.lock if errors)
jekyll serve -l -H localhost      # Serve locally at localhost:4000 (live-reload enabled)
npm run build:js                  # Minify JS into assets/js/main.min.js
```

Note: `_config.yml` changes require restarting the Jekyll server — they are not picked up by live-reload.

Prerequisites: Ruby, Bundler, Node.js (`brew install ruby node && gem install bundler` on macOS).

## Architecture

This is a Jekyll-based academic personal website deployed via GitHub Pages. It is forked (then detached) from the **academicpages** template, which itself derives from **Minimal Mistakes** by Michael Rose.

### Key Configuration

- **`_config.yml`** — Site metadata, author profile, collections, plugin list, SASS settings, defaults for each content type. This is the central config file.
- **`_data/navigation.yml`** — Top navigation bar links.
- **`_data/ui-text.yml`** — Internationalized UI strings (English + Chinese variants).

### Content & Collections

| Path | Purpose |
|---|---|
| `_pages/about.md` | Homepage (permalink `/`), contains biography, news section, and selected papers |
| `_pages/` | Static pages: CV, publications archive, talks, teaching, portfolio |
| `_publications/` | Individual paper entries (title, venue, date, paperurl, citation) |
| `_talks/` | Presentations (venue, location, type, talk_url) |
| `_teaching/` | Course entries |
| `_posts/` | Blog posts (standard Jekyll `YYYY-MM-DD-title.md` naming) |

### Layouts & Includes

- **`_layouts/`** — `default.html` → `single.html` (main content), `talk.html` (venue/location display), `archive.html`, `splash.html`
- **`_includes/`** — Partials: `author-profile.html` (sidebar), `archive-single.html` (listing items with citation/paper/slides links), `head/custom.html` (fonts, favicons, MathJax, custom CSS)

### Styling

- **`_sass/_variables.scss`** — Font family (Inter + system fallbacks), color scheme, responsive breakpoints. Primary customization point for visual changes.
- **`_sass/_base.scss`** — Base element styles including heading sizes (h1: 1.75em, h2: 1.375em).
- **`assets/css/collapse.css`** — Accordion/expand-collapse widget styles.
- **`_includes/head/custom.html`** — Inline `<style>` blocks for component-specific CSS (e.g., `.news-scroll`).
- Vendor SASS: `_sass/vendor/` contains breakpoint, font-awesome, magnific-popup, susy grid.

### JavaScript

- **`assets/js/_main.js`** — Sticky footer, FitVids, sticky sidebar, smooth scroll, MagnificPopup lightbox.
- **`assets/js/collapse.js`** — jQuery accordion for expandable content.
- **`assets/js/plugins/`** — jQuery plugins (fitvids, greedy-navigation, magnific-popup, smooth-scroll, stickyfill).
- All JS is bundled via `npm run build:js` into `assets/js/main.min.js`.

### External Dependencies Loaded via CDN

- **MathJax** (math rendering) — configured in `_includes/head/custom.html`
- **Inter font** (Google Fonts) — loaded in `_includes/head/custom.html`

### Content Generation Tools

`markdown_generator/` contains Python scripts and Jupyter notebooks to generate markdown files from TSV/BibTeX data for publications and talks. See `markdown_generator/readme.md`.

## Deployment

Push to `master` branch triggers automatic GitHub Pages build and deployment to `https://stevenyangyj.github.io`. No CI workflow files — uses GitHub's built-in Pages deployment.

## Conventions

- The homepage (`_pages/about.md`) mixes markdown and raw HTML. Section headings use either markdown (`=======` for h1) or HTML tags (`<h1>`). Keep these consistent — both should produce `<h1>` elements.
- Custom per-component CSS goes in `_includes/head/custom.html` inside `<style>` blocks, not in separate CSS files.
- PDFs (CVs, papers) are stored directly in `assets/`.
- Images and favicons go in `images/`.
