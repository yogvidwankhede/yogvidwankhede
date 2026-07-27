# ⌨️ Command-line integration — YOGVID.OS profile

Everything below runs on your machine. Total time: ~3 minutes.

> Your GitHub **profile README** lives in a **public repo named exactly `yogvidwankhede`**
> (same as your username). That's the magic — GitHub renders its README on your profile page.

---

## 1. Get the files

Unzip the package I sent, then `cd` into it:

```bash
unzip yogvid-os.zip -d yogvid-os && cd yogvid-os
# folder now contains: README.md  index.html  assets/  .github/  SETUP.md
```

---

## 2. Push to your profile repo

### ▸ Fastest — with the GitHub CLI (`gh`)

```bash
git init -b main
git add .
git commit -m "YOGVID.OS — cinematic profile"
gh repo create yogvidwankhede --public --source=. --remote=origin --push
```

That creates `github.com/yogvidwankhede/yogvidwankhede` and pushes in one shot.
(Run `gh auth login` first if you haven't authenticated.)

### ▸ Or — plain git (create the repo on github.com first)

1. On github.com: **New repository** → name it **`yogvidwankhede`** → **Public** →
   **do NOT** add a README/.gitignore → **Create**.
2. Then:

```bash
git init -b main
git add .
git commit -m "YOGVID.OS — cinematic profile"
git remote add origin https://github.com/yogvidwankhede/yogvidwankhede.git
git push -u origin main
```

Open **github.com/yogvidwankhede** — your animated profile is live. 🎉

---

## 3. Turn on the contribution snake

```bash
# allow the Action to write the generated SVG back to the repo
gh api -X PUT repos/yogvidwankhede/yogvidwankhede/actions/permissions/workflow \
  -f default_workflow_permissions=write

# run it once now (it re-runs automatically twice a day after this)
gh workflow run "Generate contribution snake"
```

No `gh`? Do it in the browser: **Settings → Actions → General → Workflow permissions →
Read and write → Save**, then **Actions tab → "Generate contribution snake" → Run workflow**.

---

## 4. (Optional) Light up the interactive experience — same repo, no website

The README's "▸ ENTER THE INTERACTIVE EXPERIENCE" button points at this repo's free
GitHub Pages URL. One toggle makes `index.html` go live there:

```bash
gh api -X POST repos/yogvidwankhede/yogvidwankhede/pages \
  -f "source[branch]=main" -f "source[path]=/"
```

…or in the browser: **Settings → Pages → Source: Deploy from branch → `main` / root → Save**.

Live in ~1 min at **https://yogvidwankhede.github.io/yogvidwankhede/** — the full boot
sequence, AI terminal, 3D gallery, and mini-game, served from the very same repo as your
README. If you'd rather NOT enable this, just delete the two "EXPERIENCE"/"TALK TO AI"
buttons near the top of `README.md`.

---

## 5. Add your 6 photos anytime

Drop them into `assets/` with these names, then commit + push:

```
assets/avatar.jpg          # hero portrait
assets/project-sign.jpg    # Sign Language Interpreter
assets/project-health.jpg  # HealthMate-AI
assets/project-caption.jpg # Image Captioning + TTS
assets/project-emmi.jpg    # EMMI research
```

```bash
git add assets && git commit -m "add photos" && git push
```

Until then, on-brand fallbacks keep everything looking complete.

---

### Quick sanity checklist
- [ ] repo is **public** and named exactly **`yogvidwankhede`**
- [ ] `README.md` + `assets/hero-banner.svg` are at the repo **root**
- [ ] Actions have **read/write** permission (for the snake)
- [ ] profile page at **github.com/yogvidwankhede** shows the animated banner

Stuck on any step? Paste the error and I'll fix it.
