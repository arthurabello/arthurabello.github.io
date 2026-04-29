# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal portfolio website for Arthur Rabello Oliveira. Single-file static site — everything lives in `index.html` with no build step, no framework, and no external dependencies (not even Google Fonts).

## Running / Previewing

```bash
python3 -m http.server 8080
# then visit http://localhost:8080
```

Deployment is via GitHub Pages (pushing to `main` publishes automatically).

## Architecture

456-line `index.html` with three blocks: `<style>`, HTML body, `<script>`.

**CSS** — plain, no custom properties. Single breakpoint at 640px. Key rules organized with `/* ── SECTION ── */` comments.

**HTML body** — fixed `<nav>`, a `<div class="bg">` (the Erwin background), `<main>` containing five `<section>` elements (`#about`, `#projects`, `#experience`, `#stack`, `#contact`), and `<footer>`.

**JS** — ~20 lines at the bottom:
- Music toggle: `<audio id="bgm" src="coolsong.mp3" loop>`. `setPlaying(bool)` plays/pauses and updates the button label. First click anywhere on the page auto-starts the song; the bottom-right "♪ Sound on / ■ Sound off" button toggles independently.
- No i18n, no scroll animations, no localStorage.

## Assets

| File | Purpose |
|---|---|
| `erwin.jpg` | Erwin Smith (Attack on Titan) fanart — used as fixed full-page background at 13% opacity |
| `coolsong.mp3` | Background music, loops, starts on first page interaction |
| `artu.jpeg` | Photo of Arthur — not currently used on the site |

## Design

Intentionally minimal — modelled after academic personal sites (adrianobarbosa.xyz / HTML5 UP "Read Only" aesthetic).

- **Background:** `#f5f4f0` warm off-white. `erwin.jpg` overlaid at `opacity: 0.13` via `.bg` fixed div.
- **Text:** `#1a1a1a` primary, `#555` secondary, `#333` card body.
- **Links:** `#2a5d8f` (muted slate blue), underlined.
- **Headings:** `Georgia, serif`. Body: `system-ui, sans-serif`. No web fonts loaded.
- **Layout:** centered single column, `max-width: 720px`.
- **No:** dark theme, gold accents, CSS animations, i18n, stats/counters, language switcher.

## Content Notes

- English only.
- About: 2 paragraphs + 1 quiet location line. No stats, no bragging.
- Languages spoken mentioned as one inline sentence only: "I speak Portuguese, English, French, Spanish, and Russian."
- Projects: 8 cards in a 2-col grid. SGEngine and Stone Co. cards link to the GitHub profile root (no dedicated repo found at time of writing — update when available).
- Experience: 8 entries, newest first, no "currently active" badges.
