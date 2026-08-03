# Al-folio Setup Guide — Keerti Yadav

I cloned the real al-folio repo and checked its exact file structure to make sure everything below matches. Follow these steps in order.

## Step 1: Fork the template
1. Go to https://github.com/alshedivat/al-folio
2. Click **Fork** (top right)
3. Rename the forked repo to `YOUR-GITHUB-USERNAME.github.io` (Settings → repository name) — this makes it live at the root domain instead of a subpath

## Step 2: Enable GitHub Pages
1. In your forked repo → **Settings** → **Pages**
2. Under "Build and deployment," source should already be set to **GitHub Actions** (al-folio ships with a workflow that builds automatically)
3. Push any change (even just editing `_config.yml`) to trigger the first build

## Step 3: Replace these 4 files with the ones I've prepared
| File in this folder | Goes to this path in your repo |
|---|---|
| `about.md` | `_pages/about.md` |
| `cv.yml` | `_data/cv.yml` |
| `papers.bib` | `_bibliography/papers.bib` |
| `config_fields_to_change.yml` | **Don't replace the whole file** — open your repo's `_config.yml` and manually update just the fields listed (see that file for exact lines) |

You can edit directly in GitHub's web UI (click the file → pencil icon → paste content → commit) — no local setup needed.

## Step 4: Add a profile photo (optional but recommended)
- Upload a photo named `prof_pic.jpg` to `assets/img/` in your repo
- If skipped, the about page will show a placeholder

## Step 5: Update your GitHub username in two places
- `cv.yml` → `social_networks` → replace `your-github-username` with your real one
- `config_fields_to_change.yml` → replace `YOUR-GITHUB-USERNAME` in the `url` field

## Step 6: Wait ~2 minutes, then visit
```
https://YOUR-GITHUB-USERNAME.github.io
```

---

## Notes
- **Publications page**: pulls automatically from `_bibliography/papers.bib` — I've marked your top 2 papers as `selected: true` so they also show on your About page.
- **CV page**: pulls from `_data/cv.yml` — already filled in with your Education, Experience, Awards, Publications, Skills, and Languages.
- **If you get a build error**: check the "Actions" tab in your repo — al-folio's GitHub Action will show exactly which file/line has a YAML formatting issue (usually a missing space after a colon, or a wrongly-indented line).
- **Later, if you want the visualcinnamon-inspired design instead**: I already built that as a complete standalone HTML file — happy to hand that back over any time.
