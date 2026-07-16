# Open Design + Niva — side-by-side workflow

> **Rule:** Open Design is the **design lab**. `nivalandpage` is the **production site**.  
> Never merge [nexu-io/open-design](https://github.com/nexu-io/open-design) into this repo.

```
┌──────────────────────────┐     copy winners      ┌─────────────────────────┐
│  Open Design (optional)  │  ──────────────────►  │  Niva / nivalandpage    │
│  explore · mock · decks  │                       │  index.html → Vercel    │
└──────────────────────────┘                       └─────────────────────────┘
```

---

## What lives where

| Item | Location |
|------|----------|
| Brand contract | **`DESIGN.md`** (repo root) |
| Hebrew copy | **`docs/design/content-map.md`** |
| Production HTML | **`index.html`** |
| Images | **`assets/images/`** |
| Deploy | Git push → Vercel (see `docs/DEPLOY.md`) |

---

## Setup (one time)

### Option A — Desktop app (easiest)

1. Download from [open-design.ai](https://open-design.ai) (Windows/macOS)
2. Open app → pick skill **saas-landing** or **web-prototype**
3. Load or paste **`DESIGN.md`** from this repo as the design system
4. Paste brief + point to **`content-map.md`** for copy

### Option B — Cursor MCP

```powershell
# After installing Open Design desktop or CLI:
od mcp install cursor
```

In Cursor, reload window. Then prompt:

```
Use open-design with DESIGN.md from this repo.
Generate a Hebrew RTL variant of the Makeup Therapy landing page.
Copy must match docs/design/content-map.md exactly.
```

**Windows note:** If `od` fails, use the MCP snippet from Open Design desktop → Settings → MCP server.

---

## Typical workflow

### 1. Explore a new look (in Open Design)

- Skill: `saas-landing` or `web-prototype`
- Design system: this repo's **`DESIGN.md`**
- Brief example:

```
Hebrew RTL landing page for makeup therapy workshops.
3 workshop cards + contact form. Soft blush MD3 palette.
Use exact copy from content-map.md. dir=rtl lang=he.
```

- Review in sandbox iframe
- Iterate until direction is approved

### 2. Port to production (in Niva / Cursor)

- Copy **layout/CSS patterns** — not the whole Open Design project
- Update **`index.html`** only
- Keep **`content-map.md`** text verbatim
- Verify RTL on mobile (375px)
- Test locally: `python -m http.server 8080`

### 3. Ship

```powershell
git add index.html assets/images DESIGN.md
git commit -m "Design update: hero glass panel tweak"
git push
```

Vercel redeploys in ~30 seconds.

---

## When to use Open Design vs Cursor-only

| Task | Tool |
|------|------|
| Fix typo, form, phone number | **Cursor** on `index.html` |
| New hero layout / color exploration | **Open Design** → port to Niva |
| Connect Formspree | **Cursor** |
| Workshop pitch deck (PPTX/PDF) | **Open Design** deck skill |
| Promo video | **Open Design** HyperFrames |
| Deploy | **Git + Vercel** |

---

## Copy-paste brief for Open Design

Attach or paste **`docs/design/content-map.md`** and add:

```
Project: Niva / nivalandpage
Brand: איפור תרפי • Makeup Therapy
Design system: ./DESIGN.md
Output: single static HTML file, Tailwind CDN, RTL Hebrew
Do NOT use English placeholder copy.
Workshop section: exactly 3 cards with full process/result text from content-map.
```

---

## RTL checklist after porting from Open Design

- [ ] `<html dir="rtl" lang="he">`
- [ ] Hebrew fonts load (Hanken Grotesk + Manrope)
- [ ] Form labels and inputs align right
- [ ] Workshop `<dl>` labels readable on mobile
- [ ] CTA buttons full-width on mobile
- [ ] No English lorem ipsum

---

## What NOT to do

- ❌ Clone open-design into `nivalandpage`
- ❌ Replace Vercel deploy with Open Design Docker
- ❌ Let Open Design rewrite marketing copy — only `content-map.md` is authoritative
- ❌ Commit Open Design daemon data or `.od` project folders into Niva

---

## Links

- Open Design repo: https://github.com/nexu-io/open-design
- Your repo: https://github.com/lachtomer/nivalandpage
- Production deploy: Vercel (import from GitHub)
