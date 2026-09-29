# Colaberry School website

The Colaberry School marketing site (AI Architect Accelerator and related pages), exported from the Claude Design project `098454b7-2472-4c4d-8ab7-2ed3ae605522`.

This repo holds only the website and the shared assets it loads. The full Colaberry design system lives separately.

## Layout

| Path | What it is |
|---|---|
| `Colaberry School/` | Site pages (`accelerator.html` is the home page) plus their `.jsx`, `.css` and `.js` |
| `styles.css`, `tokens/` | Design tokens and base styles, loaded by every page |
| `_ds_bundle.js`, `motion.js` | Design-system component bundle and motion helpers |
| `assets/` | Fonts, vendor scripts (React, Babel, GSAP, Lucide), logos, photos |
| `index.html` | Redirects to `Colaberry School/accelerator.html` |

Pages reference shared files with `../` paths, so keep the folder structure as is.

## Run locally

Pages compile JSX in the browser with Babel, so they need to be served over HTTP (opening the files directly with `file://` won't work):

```sh
npx serve .
# or
python -m http.server 8000
```

Then open http://localhost:8000/.

## Deploy

Pushing to `main` runs `.github/workflows/deploy.yml`. It stamps `?v=<hash>` cache-busters onto local CSS/JS references (`node _stamp-versions.mjs`) and publishes the repo root to GitHub Pages.

## Updating from Claude Design

Re-pull the files under `Colaberry School/` (and any changed shared assets) from the Claude Design project, replace them here, and push.
