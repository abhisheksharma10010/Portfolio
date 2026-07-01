# CAD/CAM Design Portfolio

A single-page portfolio site (`index.html`) styled around engineering-drawing conventions — title blocks, dimension lines, and a technical mono/display type pairing — built for CAD/CAM, mechanical design, or manufacturing engineering work.

Everything (HTML, CSS, JS) lives in **one file**, so there's nothing to build or install. You can preview it by just double-clicking `index.html`, and you can host it for free on **GitHub Pages** in about five minutes.

---

## 1. Preview it locally

Just open `index.html` in any browser — no server or build step needed.

## 2. Put it on GitHub

If you don't already have a GitHub account, create one at [github.com](https://github.com).

### Option A — using the GitHub website (no command line)

1. Go to [github.com/new](https://github.com/new) and create a new **public** repository.
   - Name it `portfolio` (or anything you like) — **or** name it exactly `yourusername.github.io` if you want the site at the root of your GitHub domain (see step 4).
2. On the new repo page, click **"uploading an existing file"**.
3. Drag in `index.html` (and `README.md` if you want it in the repo too).
4. Commit the changes.

### Option B — using git from the command line

```bash
cd path/to/this/folder
git init
git add index.html README.md
git commit -m "Add portfolio site"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/portfolio.git
git push -u origin main
```

## 3. Turn on GitHub Pages

1. In your repository on GitHub, go to **Settings → Pages**.
2. Under **Build and deployment → Source**, choose **"Deploy from a branch"**.
3. Under **Branch**, select **`main`** and folder **`/ (root)`**, then **Save**.
4. Wait 1–2 minutes. GitHub will show a green banner with your live URL.

## 4. Your live URL

- If your repo is named `portfolio`: `https://YOUR-USERNAME.github.io/portfolio/`
- If your repo is named `YOUR-USERNAME.github.io`: `https://YOUR-USERNAME.github.io/` (no extra path — this is the "root" personal-site convention GitHub supports)

You can also attach a custom domain later under **Settings → Pages → Custom domain**.

## 5. Customize the content

Everything is in `index.html`. Places to edit, top to bottom:

| What | Where to look |
|---|---|
| Your name / title | `<title>` tag and the `.logo` + hero `<h1>` |
| Hero intro text | `.lede` paragraph in the hero section |
| Stats (years, parts, tolerance) | `.hero-meta` block |
| Project cards | Each `<div class="card">` in the `#work` section — swap title, description, tags, and title-block fields (DWG NO, SCALE, MATERIAL, REV) |
| Process steps | `#process` section, six `.step` blocks |
| Tools / software list | `.spec-table` rows in `#skills` |
| About text + stats | `#about` section |
| Contact links | `footer#contact` — update the `mailto:`, LinkedIn, and GitHub links |
| Colors | CSS custom properties at the very top of the `<style>` block (`--paper`, `--ink`, `--blueprint`, `--accent`, etc.) |
| Fonts | The Google Fonts `<link>` tags in `<head>`, and the `font-family` values in CSS |

### Adding real project images

Each project card currently uses a small placeholder SVG icon inside `.card-art`. To use real photos or renders:

1. Create an `assets/` folder next to `index.html` and add your images there.
2. Replace the `<svg>...</svg>` inside a `.card-art` div with:
   ```html
   <img src="assets/your-project.jpg" alt="Project name" style="width:100%; height:100%; object-fit:cover;">
   ```
3. Commit and push — GitHub Pages picks up the new files automatically.

---

Built as a static site — no framework, no build step, so it stays easy to edit and free to host.
