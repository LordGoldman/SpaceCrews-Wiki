# SpaceCrews wiki (MkDocs Material)

Published at **https://lordgoldman.github.io/SpaceCrews-Wiki/** from
https://github.com/LordGoldman/SpaceCrews-Wiki — this folder IS the repo clone.

No Jekyll anywhere: the site is built by **MkDocs Material** through the GitHub
Actions workflow in `.github/workflows/deploy.yml`. GitHub Pages must be set to
**Settings → Pages → Source: GitHub Actions** (NOT "Deploy from a branch", which
would run Jekyll on the raw markdown).

## Editing

Edit the markdown in `docs/`, then:

```
git add -A
git commit -m "docs: ..."
git push
```

The workflow rebuilds and deploys automatically on every push to `main`.

## Preview locally

```
pip install -r requirements.txt
python -m mkdocs serve
```

then open http://127.0.0.1:8000 — live-reloads as you edit.
