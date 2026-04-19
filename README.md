# larrywirsing.com

Source for [larrywirsing.com](https://larrywirsing.com) — a static, two-page portfolio site for Larry Wirsing.

## Stack

Hand-authored static HTML + a single CSS file. No build step, no frameworks, no bundlers. System font stack only (zero web-font network cost). Fully responsive, dark-mode aware via `prefers-color-scheme`, a11y-baseline with skip-link, `aria-current`, and semantic landmarks, and print-friendly.

## Layout

```
.
├── index.html              # About / landing
├── resume.html             # Résumé walkthrough
├── 404.html                # Branded not-found page
├── styles.css              # Single stylesheet (design tokens, fluid type, print)
├── favicon.svg             # LW monogram favicon
├── robots.txt
├── sitemap.xml
├── CNAME                   # Custom apex domain
├── assets/
│   └── Larry_Wirsing_Resume_2026.pdf
└── .github/workflows/
    └── deploy.yml          # GitHub Pages via Actions
```

## Local preview

```bash
python3 -m http.server 4000
# then open http://localhost:4000
```

## Deployment

Pushes to `main` trigger a GitHub Actions workflow that lints the HTML, packages the repository root as a Pages artifact, and deploys to `larrywirsing.com`. DNS is an apex `A`-record set at the registrar pointed at GitHub Pages IPs, plus a `CNAME` file in the repo root pinning the custom domain.

## Editing

Each page is self-contained; most edits are plain-HTML text changes. Design tokens (colors, spacing, type scale) live at the top of `styles.css` as CSS custom properties.
