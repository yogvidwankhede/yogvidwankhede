# 🚀 YOGVID.OS — Setup & Deploy Guide

You have two things:

1. **`index.html`** — your full interactive experience site (the main event).
2. **`README.md` + `assets/hero-banner.svg` + `.github/workflows/snake.yml`** — your animated GitHub profile that acts as the cinematic "trailer" and links into the site.

Everything is self-contained and works **without any build step**.

---

## 🖼️ Step 0 — Drop in your 6 images (optional but recommended)

The site + README look complete already (they use generated fallbacks), but your real photos make it *yours*. Create an `assets/` folder next to `index.html` and add:

| Filename | Where it appears | Suggested content |
|---|---|---|
| `assets/avatar.jpg` | Hero portrait card (site) | A strong photo of you / headshot |
| `assets/project-sign.jpg` | Sign Language project card | Screenshot / demo frame |
| `assets/project-health.jpg` | HealthMate-AI card | Screenshot / diagram |
| `assets/project-caption.jpg` | Image Captioning card | Screenshot / sample output |
| `assets/project-emmi.jpg` | EMMI research card | A figure / render |
| `assets/og-cover.jpg` *(optional)* | Social share preview | 1200×630 banner |

**No image? No problem.** Every slot has an automatic on-brand fallback, so nothing looks broken while a slot is empty. Just match the filenames above and the images appear instantly.

> Tell me which of your 6 images is which, and I'll wire them to the exact right slots for you.

---

## 🌐 Step 1 — Deploy the experience site

Pick the easiest path for you:

### Option A — Vercel (fastest, recommended)
1. Put `index.html` (and your `assets/` folder) in a folder / repo.
2. Go to **vercel.com → New Project → Import** the repo (or drag-drop the folder).
3. Framework preset: **Other**. Deploy. Done — you get a live URL in ~20s.
4. Add your custom domain `yogvidwankhede.com` in **Project → Settings → Domains**.

### Option B — GitHub Pages (free, no signup)
1. Create a repo, e.g. `yogvidwankhede/experience`.
2. Add `index.html` + `assets/` and push.
3. **Settings → Pages → Source: Deploy from branch → `main` / root.**
4. Live at `https://yogvidwankhede.github.io/experience/`.

### Option C — Your own site
`index.html` is a single file — drop it at the root of `yogvidwankhede.com` and it just works.

> After deploying, update the CTA links in `README.md` if your URL differs from `yogvidwankhede.com`.

---

## 🎬 Step 2 — Set up the animated GitHub profile

Your profile README lives in a **special repo named exactly after your username**.

1. Create a **public** repo named **`yogvidwankhede`** (same as your username).
   GitHub shows a "✨ special repository" hint when you name it right.
2. Add these files to it:
   ```
   README.md
   assets/hero-banner.svg
   .github/workflows/snake.yml
   ```
   (plus your project images in `assets/` if you added them)
3. Commit to `main`. Your profile page updates immediately.

---

## 🐍 Step 3 — Turn on the contribution snake

1. In the `yogvidwankhede` repo: **Settings → Actions → General →**
   set *Workflow permissions* to **Read and write**.
2. Go to the **Actions** tab → select **"Generate contribution snake"** → **Run workflow**.
3. It creates an `output` branch with `snake.svg` / `snake-dark.svg`. The README already points there. It re-runs automatically twice a day.

---

## ✅ What's already handled for you

- **Performance** — one HTML file, no frameworks, canvas animations throttle correctly.
- **Accessibility** — respects `prefers-reduced-motion` (animations auto-simplify), keyboard-navigable terminal + game, focus outlines, ARIA labels.
- **Mobile** — fully responsive; the game supports touch.
- **GitHub compatibility** — the README uses only GitHub-safe HTML (no `<script>`/`<style>`); all motion lives inside the SVG banner and external stat cards.

---

## 🎮 The secrets (so you can show them off)

- **Konami code** anywhere on the site: `↑ ↑ ↓ ↓ ← → ← → B A` → launches the mini-game.
- Terminal commands: `help`, `hire me`, `sudo hire-yogvid`, `matrix`, `game`, `secret`, `whoami`, `ls`.
- Find all 5 secrets → a special message appears.

---

## 🔧 Easy tweaks

- **Change colors** — edit the `:root { --cyan / --indigo / --mint ... }` block at the top of `index.html`.
- **Edit the AI's answers** — search `RESP = {` in `index.html`; each command is a short function.
- **Add a project** — copy one object inside `DATA.projects` in `index.html` and add a matching card row to `README.md`.
- **Change roles** — edit `roles:[ ... ]` in `DATA` (site) and the SVG `CYCLING ROLES` block (banner).

Questions or want me to wire your images / add sections? Just ask.
