# Niva

Hebrew RTL landing page — **איפור תרפי • Makeup Therapy** (Makeup Therapy workshops).

**Live repo:** [github.com/lachtomer/nivalandpage](https://github.com/lachtomer/nivalandpage) → Vercel

## Status

Tailwind MD3 blush theme + full Hebrew copy. Form (Formspree) pending.

## Manage & deploy

```powershell
git add .
git commit -m "Describe your change"
git push    # Vercel auto-redeploys
```

Local preview: `python -m http.server 8080` → http://localhost:8080

## Documentation

| File | Purpose |
|------|---------|
| **[`DESIGN.md`](DESIGN.md)** | Brand contract (Open Design 9-section schema) |
| **[`docs/OPEN-DESIGN-WORKFLOW.md`](docs/OPEN-DESIGN-WORKFLOW.md)** | Use Open Design *beside* this repo |
| [`docs/design/content-map.md`](docs/design/content-map.md) | Hebrew copy → sections |
| [`docs/DEPLOY.md`](docs/DEPLOY.md) | Vercel + Formspree |
| [`docs/NEXT-STEPS.md`](docs/NEXT-STEPS.md) | Roadmap |
| [`.cursor/rules/audience-brand-fit-review.mdc`](.cursor/rules/audience-brand-fit-review.mdc) | Audience review agent (beauty × psychology) |

## Design tools

| Tool | Role |
|------|------|
| **This repo + Cursor** | Production edits & deploy |
| **[Open Design](https://github.com/nexu-io/open-design)** | Optional — explore layouts, decks, video |
| Google Stitch | Optional — quick mockups |

Open Design does **not** live in this repo. See `docs/OPEN-DESIGN-WORKFLOW.md`.

## Structure

```
Niva/
├── DESIGN.md           ← brand contract (agents read this first)
├── index.html          ← production page
├── assets/images/
├── docs/
└── vercel.json
```
