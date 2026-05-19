# Music Note Trainer

A static web app for practising music note recognition and chord lookup — no backend, no build step, runs entirely in the browser.

**Live demo:** https://jiechau.github.io/note_trainer/

---

## Features

### Sight-reading Trainers

Both trainers display a random note on a staff rendered with [VexFlow](https://www.vexflow.com/). Press **Show Answer & Play Sound** to reveal the note name and hear the pitch via the Web Audio API. Press **Next Question** for a new note.

| Page | Clef | Range |
|------|------|-------|
| `Treble-Clef-Sight-reading.html` | Treble clef | C3 – A6 (natural notes) |
| `Bass-Clef-Sight-reading.html` | Bass clef | Lower range natural notes |

Both trainers include a **Range** selector at the top so you can narrow practice to a comfortable set of notes.

### Piano Chord Lookup (`chord.html`)

Displays multiple rows, each with:
- A root note dropdown (C, C#, Db, D … B)
- A chord-type dropdown (maj7 △, m7 -7, 7, 6, m6, dim7 °, m7b5 ø)
- A piano keyboard diagram loaded from the `chords/` image library

All 7 chord types across all 12 chromatic roots are covered (84 chord images total).

### Bookmark (`bookmark.html`)

A curated list of YouTube links for jazz / piano learning resources (Fly Me to the Moon, Jazz for Beginners, Jimbo beginner series, etc.).

---

## Project Structure

```
.
├── index.html                      # Home — links to all tools
├── Treble-Clef-Sight-reading.html  # Treble clef sight-reading trainer
├── Bass-Clef-Sight-reading.html    # Bass clef sight-reading trainer
├── chord.html                      # Piano chord lookup
├── bookmark.html                   # YouTube bookmarks
├── chords/                         # Piano chord diagram images (PNG)
├── favicon.svg
├── robots.txt
├── .github/workflows/deploy.yml    # GitHub Pages auto-deploy
└── .gitlab-ci.yml                  # GitLab Pages auto-deploy
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



