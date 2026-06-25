# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

A static, multi-page web app for practising music note recognition and chord lookup. There is **no backend, no build step, no package manager, and no test suite** — every page is plain HTML with inline CSS and JavaScript. The only external dependency is VexFlow, loaded from a CDN at runtime.

## Working in this repo

- There is nothing to build, lint, or test. To preview locally, open an HTML file directly in a browser, or serve the directory (e.g. `python3 -m http.server`) so the chord-image and CDN requests resolve.
- Each page is **self-contained** — styles and logic live inline in the same `.html` file. There is no shared CSS/JS module; changes to one page do not affect others. Match a page's existing inline style when editing it.
- The site is intentionally **not indexed**: every page carries `noindex` meta tags and `robots.txt` disallows all crawlers. Preserve these when adding pages.

## Page map

- `index.html` — home page linking to the tools.
- `Treble-Clef-Sight-reading.html` / `Bass-Clef-Sight-reading.html` — sight-reading trainers. Render a random note on a staff via **VexFlow** (`Vex.Flow`), reveal the name and play the pitch via the **Web Audio API** (oscillator). Each has a Range selector (`#range-start` / `#range-end`) to constrain the practiced notes.
- `chord2.html` — **active** chord-lookup page. Renders piano keyboards as inline **SVG** generated in `renderPiano()`; chord tones are highlighted, every C key gets a green dot. Driven by two data tables: chord types and `CHORD_INTERVALS` (semitone offsets per type). No external assets.
- `chord.html` — **deprecated, pending removal.** Older chord lookup that loads pre-rendered PNGs from `chords/` (84 images, one per root×type) via the `NOTE_PREFIX` map in `imgFor`. Already commented out in `index.html` and `README.md`. When removing it, also delete the `chords/` directory.
- `bookmark.html` + `bookmark_*.html` — static lists of YouTube study links (index page plus per-song subpages).

## Deployment

Pushing to `main` (or `master`) auto-deploys to both GitHub Pages and GitLab Pages. **The two pipelines publish different file sets:**

- **GitHub** (`.github/workflows/deploy.yml`) uploads the entire directory (`path: '.'`) — includes `chords/`.
- **GitLab** (`.gitlab-ci.yml`) copies only `*.html`, `*.svg`, and `readme.txt` into `public/` — it does **not** copy `chords/`. So PNG-based `chord.html` is broken on GitLab; the SVG-based `chord2.html` works everywhere. If you add new asset types or directories that a page needs, update the GitLab `script` block too, or that page will 404 on GitLab Pages.
