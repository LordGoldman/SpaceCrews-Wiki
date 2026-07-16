# SpaceCrews wiki (MkDocs Material)

This folder is a self-contained docs site. To publish it free on GitHub Pages:

1. Create a **public** repo (e.g. `spacecrews-docs`) and push THIS FOLDER'S CONTENTS
   as the repo root (mkdocs.yml at top level).
2. In the repo: Settings → Pages → Source: **GitHub Actions**.
3. Push to `main` — the included workflow builds and deploys automatically.
4. Set `site_url` in `mkdocs.yml` to your real URL (and optionally a custom domain
   under Settings → Pages).

Preview locally:

```
pip install -r requirements.txt
mkdocs serve
```

then open http://127.0.0.1:8000 — live-reloads as you edit the markdown in `docs/`.
