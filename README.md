# Niva

Hebrew RTL welcome landing page — **איפור תרפי · Makeup Therapy** (Makeup Therapy workshops).

## Status

**New design live** — Tailwind MD3 pink theme + your full Hebrew copy.

**Stack:** `index.html` + Tailwind CDN + `assets/images/`  
(Legacy `css/style.css` = old red theme, unused.)

**Next:** Formspree → deploy. See **[docs/NEXT-STEPS.md](docs/NEXT-STEPS.md)**.

### Preview locally

```powershell
cd "c:\Users\TOMERLAC\OneDrive - AMDOCS\Desktop\Niva"
python -m http.server 8080
```

Open: http://localhost:8080

## Documentation

| File | Purpose |
|------|---------|
| [**docs/NEXT-STEPS.md**](docs/NEXT-STEPS.md) | **Start here** — phased roadmap |
| [`docs/design/content-map.md`](docs/design/content-map.md) | Text → section mapping |
| [`docs/design/DESIGN.md`](docs/design/DESIGN.md) | Colors, typography, components |
| [`docs/design/reference/hero-and-top-sections.png`](docs/design/reference/hero-and-top-sections.png) | Visual reference |
| [`.cursor/rules/hebrew-rtl-landing.mdc`](.cursor/rules/hebrew-rtl-landing.mdc) | Cursor rules for this project |

## Project structure

```
Niva/
├── index.html          ← page
├── css/style.css       ← styles
├── assets/images/      ← photos
└── docs/               ← brief, design, next steps
```
