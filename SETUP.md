# How to publish this profile

GitHub shows the README of a repo **named exactly like your username** on your profile Overview page.
Your username is `tayyabtestai`, so the repo must be named `tayyabtestai`.

## 1. Create the repo

On GitHub: **New repository** → name it `tayyabtestai` → **Public** → do **not** add a README.
(GitHub will show a "✨ special repository" hint when the name matches your username — that confirms it's right.)

## 2. Push this folder

From inside this folder:

```bash
git init -b main && git add -A && git commit -m "Add profile README" && git remote add origin https://github.com/tayyabtestai/tayyabtestai.git && git push -u origin main
```

Then open <https://github.com/tayyabtestai> — the Overview tab will show the new profile.

## 3. Optional: the contribution-graph snake

`.github/workflows/snake.yml` renders your contribution graph as an animated snake in the brand lime.

1. After the first push, go to the repo's **Actions** tab and enable workflows if prompted.
2. Run **Generate snake** manually once (Actions → Generate snake → *Run workflow*).
3. It creates an `output` branch with `snake.svg`.
4. In `README.md`, find the block that starts `<!-- Contribution-graph snake` in the **GitHub** section and remove the `<!--` and `-->` around the `<img>` tag.

After that it regenerates itself every day at 03:00 UTC.

## What's in here

| File | Purpose |
|:--|:--|
| `README.md` | The profile Overview page |
| `assets/banner.svg` | Hero banner — name, tagline, stat strip, terminal card |
| `assets/skills.svg` | The skill-set graphic (5 categories, colour-coded) |
| `.github/workflows/snake.yml` | Optional daily contribution-snake generator |

## Editing later

Both SVGs are plain text — open them in any editor and change the numbers or labels directly.
For example, in `assets/banner.svg` the stat strip lives under `<!-- stat strip -->`; change `30+` to whatever
the real number is today. In `assets/skills.svg`, each skill is a `<g>` block containing a `<rect>`, a `<circle>`
(the coloured dot) and a `<text>` — editing the text alone will make the pill the wrong width, so if you add or
rename skills it's easier to ask Claude to regenerate the file.

## Notes

- The stats cards in the **GitHub** section come from `github-readme-stats.vercel.app`, a free third-party
  service. If it's ever slow or down, those two images won't load — the rest of the page is unaffected.
- Everything else (banner, skills graphic, badges) is served from this repo or shields.io.
