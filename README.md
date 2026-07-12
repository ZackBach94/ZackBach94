# RAMSysz — Website

Companion website for the **RAMSysz YouTube channel**, hosting web pages that explain
**RAMS** concepts: **R**eliability, **A**vailability, **M**aintainability and **S**afety.

> ⚠️ **Note:** this content currently lives on a branch of `ZackBach94/ZackBach94`
> because the session could not create a new repository. See
> [Moving to its own repository](#moving-to-its-own-repository) below for the
> one-time migration steps.

## Site structure

```
.
├── index.html              # Homepage — lists all concept pages
├── assets/
│   ├── css/style.css       # Shared stylesheet (light/dark aware)
│   └── img/                # Diagrams, thumbnails, logos
├── pages/
│   ├── reliability.html    # R — Reliability
│   ├── availability.html   # A — Availability
│   ├── maintainability.html# M — Maintainability
│   ├── safety.html         # S — Safety
│   └── _template.html      # Copy this to start a new concept page
└── .nojekyll               # Serve files as-is on GitHub Pages
```

## Adding a new page (one per video / concept)

1. Copy `pages/_template.html` to `pages/<topic>.html` (e.g. `pages/fmeca.html`).
2. Fill in the title, intro, sections, and paste your YouTube embed code where marked.
3. Add a card for it in `index.html` (copy an existing `<article class="card">` block).

## Publishing with GitHub Pages

Once the content is in its own repository:

1. Go to **Settings → Pages** on GitHub.
2. Under **Build and deployment**, choose **Deploy from a branch**,
   select `main` and the `/ (root)` folder, then save.
3. The site goes live at `https://<user>.github.io/<repo>/` within a minute or two.
   A custom domain can be added on the same settings page later.

## Moving to its own repository

1. On GitHub, create a new empty repository (e.g. `ramsysz`) — no README, no license.
2. Locally:

```bash
git clone --branch claude/ramsysz-youtube-repos-6g86f2 \
    https://github.com/ZackBach94/ZackBach94.git ramsysz
cd ramsysz
git checkout -b main
git remote set-url origin https://github.com/ZackBach94/ramsysz.git
git push -u origin main
```

3. Enable GitHub Pages as described above, and delete the
   `claude/ramsysz-youtube-repos-6g86f2` branch from `ZackBach94/ZackBach94`.
