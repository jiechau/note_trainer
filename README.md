# Music Note Trainer

A static web app for practising music note recognition and chord lookup — no backend, no build step, runs entirely in the browser.

**Live demo:** https://jiechau.github.io/note_trainer/

---

## Features

### Sight-reading Trainers

Both trainers display a random note on a staff rendered with [VexFlow](https://www.vexflow.com/). Press **Show Answer & Play Sound** to reveal the note name and hear the pitch via the Web Audio API. Press **Next Question** for a new note.

| Page | Clef | Range |
|------|------|-------|
| `sight_reading/Treble-Clef-Sight-reading.html` | Treble clef | C3 – A6 (natural notes) |
| `sight_reading/Bass-Clef-Sight-reading.html` | Bass clef | Lower range natural notes |

Both trainers include a **Range** selector at the top so you can narrow practice to a comfortable set of notes.

### Piano Chord Lookup (`chord_lookup/`)

A keyboard-based chord reference. The page shows a column of rows, each independently configurable, where every row renders its own piano keyboard with the chord tones highlighted.

Each row provides:
- A **root note** dropdown — 17 options including enharmonic spellings (C, C#, Db, D, D#, Eb, E, F, F#, Gb, G, G#, Ab, A, A#, Bb, B)
- A **chord-type** dropdown — 7 types: maj7 △, m7 -7, 7, 6, m6, dim7 °, m7b5 ø
- A **piano keyboard** spanning two octaves (C4–B5)

The keyboard is drawn live as an inline **SVG** rather than loaded from PNG images, so any root/type combination is generated instantly and no image library is needed. Rendering details:
- Chord tones are highlighted in red on both white and black keys.
- A green dot marks every C key as a positional reference for reading the keyboard.
- Black keys use realistic horizontal offsets so they sit naturally within their 2- and 3-key groups instead of centered on the white-key boundaries.

The page opens with 8 rows pre-filled (C, D, E, F, G, A, B, C#) as a starting point.

### Bookmark (`bookmark/`)

A curated list of YouTube links for jazz / piano learning resources (Fly Me to the Moon, Jazz for Beginners, Jimbo beginner series, etc.).

---

## Project Structure

```
.
├── index.html                          # Home — links to all tools
├── sight_reading/
│   ├── index.html                      # Sight-reading index (links to both trainers)
│   ├── Treble-Clef-Sight-reading.html  # Treble clef sight-reading trainer
│   └── Bass-Clef-Sight-reading.html    # Bass clef sight-reading trainer
├── chord_lookup/
│   └── index.html                      # Piano chord lookup (live SVG keyboard)
├── bookmark/
│   ├── index.html                      # YouTube bookmarks index
│   └── *.html                          # Per-song bookmark pages
├── favicon.svg
├── robots.txt
├── .github/workflows/deploy.yml        # GitHub Pages auto-deploy
└── .gitlab-ci.yml                      # GitLab Pages auto-deploy
```

---

## Tech Stack

- Pure HTML / CSS / JavaScript — no framework, no build tool
- [VexFlow 4.2.2](https://www.vexflow.com/) (CDN) — music notation rendering
- Web Audio API — in-browser note playback

---

## Deployment

Both platforms deploy automatically on every push to `main` / `master`.

| Platform | Config | URL |
|----------|--------|-----|
| GitHub Pages | `.github/workflows/deploy.yml` | https://jiechau.github.io/note_trainer/ |
| GitLab Pages | `.gitlab-ci.yml` | https://jiechau.gitlab.io/note_trainer/ |



