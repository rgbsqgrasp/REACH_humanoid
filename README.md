# REACH — Anonymous Project Page

Static GitHub Pages site for double-anonymous review. Contains no author names, affiliations, emails, or institutional branding.

## Contents

- `index.html` — project page (teaser, abstract, method figure, demos)
- `styles.css` — layout and styling
- `assets/images/` — teaser and architecture figures
- `assets/videos/` — project overview clip and real-world demo clips (~145&nbsp;MB total)

Paper and Code buttons are placeholders until the camera-ready / open-source release.

## Deploy to an anonymous GitHub account

Use a dedicated anonymous GitHub account. Do not link personal identity, email, or other repositories that reveal authorship.

### Option A — repo root (recommended)

1. Create a new public repository on the anonymous account (e.g. `reach`).
2. Copy **the contents** of this `website/` folder into the repository root (so `index.html` is at `/`):

   ```bash
   # from this website/ directory
   git init
   git add .
   git commit -m "Add anonymous REACH project page"
   git branch -M main
   git remote add origin https://github.com/<anonymous-user>/<repo>.git
   git push -u origin main
   ```

3. On GitHub: **Settings → Pages → Build and deployment**
   - Source: **Deploy from a branch**
   - Branch: `main` / folder: `/ (root)`
4. After a minute, open `https://<anonymous-user>.github.io/<repo>/`

### Option B — keep a `website/` subfolder

If the repo root must hold other files, push this folder as `website/` and set Pages source to branch `main` / folder `/website`.

## Local preview

```bash
cd website
python3 -m http.server 8080
```

Open `http://localhost:8080`.

## After acceptance

1. Replace the Paper button with a link to the PDF (or arXiv).
2. Replace the Code button with the public repository URL.
3. Remove or update the double-anonymous footer notice.
4. Optionally remove `noindex` from `index.html` if indexing is desired.

## Size note

Demo videos plus the project overview clip are ~145&nbsp;MB combined. GitHub recommends keeping repositories under ~1&nbsp;GB; individual files under 100&nbsp;MB. Current assets are within those soft limits. For larger future clips, consider Git LFS or external hosting.
