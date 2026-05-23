# CLAUDE.md — Project Guide for Claude Code

This file tells Claude Code how this website is built so it can make accurate,
consistent edits from a single prompt. Read it before changing anything.

## What this is
A single-page academic personal website for **Vishavdeep Sharma**, PhD candidate
in Agricultural, Environmental, and Development Economics at The Ohio State
University. It is a static site — no build step, no framework, no dependencies.

## File structure
```
vishavdeep-website/
├── index.html        ← the entire website (HTML + CSS + JS in one file)
├── assets/
│   ├── cv.pdf        ← the CV linked by the "Download CV" buttons
│   └── photo.jpg     ← (optional) profile photo — see "Adding a photo" below
├── README.md         ← human-facing setup & deploy instructions
└── CLAUDE.md         ← this file
```

## How index.html is organized
The file is divided by clearly-labelled HTML comment banners, in this order:
1. `DESIGN TOKENS` — CSS `:root` variables (colors, fonts, max width)
2. `NAVIGATION` — the top nav bar and its links
3. `HERO` — name, title, tagline, CV button, photo slot
4. `ABOUT` — bio, education list, honors, skills, languages
5. `RESEARCH INTERESTS` — four topic cards
6. `PUBLICATIONS` — "Peer-Reviewed" and "Working Papers" subsections
7. `TEACHING` — OSU teaching rows + a note on prior Delhi teaching
8. `OUTREACH, TALKS & MEDIA` — conferences, outreach, "In the News"
9. `CONTACT` — email, office, profile links, CV
10. `<script>` — scroll-reveal animation + active-nav highlighting

Each section has `<!-- ============ SECTION NAME ============ -->` so you can
find it by searching. To edit content, locate the banner and edit the text in
place. Keep the surrounding HTML structure intact.

## Editing conventions
- **Add a publication:** inside the PUBLICATIONS section, copy one full
  `<div class="pub"> … </div>` block and edit the year, title, authors, venue.
  Optional `<span class="badge">…</span>` shows a status (e.g. "Forthcoming").
  Optional `<div class="tags"><a href="…">PDF</a></div>` adds link buttons.
- **Add a talk / teaching item:** copy one `<div class="row"> … </div>` block.
- **Add a research interest:** copy one `<div class="card"> … </div>` block.
- **Restyle the whole site:** change the variables under `DESIGN TOKENS` only.
  `--accent` is the oxblood highlight; `--paper` / `--ink` are background / text.
- **Fonts** are loaded from Google Fonts in `<head>`: Fraunces (headings) and
  Hanken Grotesk (body). Swap the `<link>` and the `font-family` rules to change.

## Adding a photo
1. Save the image as `assets/photo.jpg`.
2. In the HERO section, replace the `<div class="ph"> … </div>` placeholder with:
   `<img src="assets/photo.jpg" alt="Vishavdeep Sharma">`

## Updating the CV
Replace `assets/cv.pdf` with the new file (keep the same name) — every
"Download CV" link already points to it.

## Hard rules — accuracy
- This is a real person's academic record. **Never invent publications, venues,
  awards, dates, or coauthors.** Only add or change facts the user explicitly
  provides. If a detail is unknown, leave a clear placeholder (e.g. "Add link").
- Keep author name styling consistent: `Sharma, V.` Bold the user's own name
  only if that convention is already used in a list.

## Style/quality
- Keep the refined, minimal academic aesthetic. Avoid clutter and heavy effects.
- Maintain responsive behavior (the `@media(max-width:860px)` block).
- After edits, the page must still open correctly by double-clicking index.html.

## Deploy
Static hosting only. GitHub Pages or Netlify both work with zero configuration —
see README.md for steps.
