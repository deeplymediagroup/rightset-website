# Rightset website — working notes

Static marketing site — plain HTML/CSS/JS, **no build step**. Page variants:
- `index.html` — v222 (globe hero), the canonical homepage
- `home2.html` — dashboard hero
- `home3.html` — globe hero + Bill Gates split-screen deepfake demo
- `home4.html` — dashboard hero + deepfake demo

Routed via `vercel.json` rewrites (`/home2`, `/home3`, `/home4`). Shared assets in
`videos/`, `thumbs/`, `images/`. Dark theme; colors are CSS custom props in `:root`
(`--bg:#0f1418`, `--accent:#4de5c4`, `--danger-bright:#ff8e8e`). Brand logo:
`/images/rightset-logo.png`; favicons + `site.webmanifest` at repo root.

The four pages share most markup (nav, footer, most sections) — when changing a
shared element, apply the same edit to all four.

## Deploy / going live
- Dev branch: `claude/zealous-wright-Em5z2` — commit work here.
- Production = Vercel project **rightset-v222** (`rightset-v222.vercel.app`), which
  auto-deploys from **`main`**.
- To ship: fast-forward `main` to the branch tip —
  `git push origin claude/zealous-wright-Em5z2:main` — Vercel builds prod in ~1 min.
- Prefer this fast-forward flow over opening PRs (don't open PRs unless asked).

## Working agreement
- **Auto-push straightforward changes live without asking** — copy/content, assets
  (logos, favicons, images), styling, section tweaks, small bug fixes. Commit to the
  dev branch, then fast-forward `main` so it deploys to production. Report the live
  URL when done.
- **Pause and confirm first** for: large refactors, deletions / destructive changes,
  anything outward-facing beyond a normal site update, or when genuinely unsure.
