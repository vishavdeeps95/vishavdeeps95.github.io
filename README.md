# Vishavdeep Sharma — Academic Website

A single-page academic website. It's a plain static site (one HTML file, no
build step, no dependencies), designed to be easy to revise — by hand or with
**Claude Code** using simple prompts.

---

## Quick start

**Preview it:** double-click `index.html` — it opens in your browser. That's it.

For a more accurate local preview (so links resolve the way they will online),
run a tiny local server from inside this folder:

```bash
python3 -m http.server 8000
# then open http://localhost:8000 in your browser
```

---

## Editing by hand
Open `index.html` in any text editor. Each section is marked with a banner like
`<!-- ============ PUBLICATIONS ============ -->`. Find the section, change the
text, save, and refresh the browser. To restyle colors or fonts, edit the
`DESIGN TOKENS` block near the top.

- **Add your photo:** save it as `assets/photo.jpg`, then follow the note in the
  HERO section of `index.html`.
- **Update your CV:** replace `assets/cv.pdf` with your new file (same name).
- **Google Scholar link:** in the CONTACT section, paste your Scholar URL into
  the `href="#"` marked "Add your Google Scholar URL".

---

## Editing with Claude Code (the easy way)

This project includes a `CLAUDE.md` file that tells Claude Code exactly how the
site is structured, so it can make precise edits from a single instruction.

**One-time setup**
1. Install Claude Code (see Anthropic's docs — it runs in your terminal).
2. Open a terminal and `cd` into this folder:
   ```bash
   cd path/to/vishavdeep-website
   ```
3. Start it:
   ```bash
   claude
   ```

**Then just describe the change.** Example prompts:

- "Add my new working paper: 'Title here', sole-authored, 2026, to the working
  papers list."
- "My Manchester School paper is now published, vol. 93, pp. 120–145 — update it
  and remove the Forthcoming label."
- "Add a Google Scholar link in Contact: <paste URL>."
- "Add a talk: invited seminar at Iowa State, April 2026."
- "Change the accent color from oxblood to a deep navy."
- "Add a new section called 'Awards' after Teaching."
- "Add my photo — I just saved it as assets/photo.jpg."

Claude Code edits `index.html` for you. Refresh your browser to see the result.
Because everything lives in one file with clear markers, changes are quick and
low-risk. Tip: keep this folder in Git (below) so you can undo anything.

---

## Version control (recommended)
Track changes so you can always roll back:

```bash
git init
git add .
git commit -m "Initial website"
```

After each round of edits: `git add . && git commit -m "what changed"`.

---

## Publishing it online (free)

**Option A — GitHub Pages**
1. Create a GitHub repo and push this folder to it.
2. Repo → Settings → Pages → Source: `main` branch, `/root`.
3. Your site goes live at `https://<username>.github.io/<repo>/`.

**Option B — Netlify (drag & drop)**
1. Go to app.netlify.com → "Add new site" → "Deploy manually".
2. Drag this entire folder onto the page. Done — you get a live URL instantly.

Either way you can later connect a custom domain (e.g. yourname.com).

---

## Files
| File | Purpose |
|------|---------|
| `index.html` | The whole website (HTML + CSS + JS) |
| `assets/cv.pdf` | Your CV, linked by the Download buttons |
| `CLAUDE.md` | Instructions Claude Code reads automatically |
| `README.md` | This file |
