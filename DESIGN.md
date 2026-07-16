# DESIGN.md — איפור תרפי • Makeup Therapy

> Brand contract for **Niva** landing page.  
> Compatible with [Open Design](https://github.com/nexu-io/open-design) 9-section schema.  
> **Production site:** `index.html` → GitHub → Vercel.  
> **Copy source of truth:** `docs/design/content-map.md`

---

## 1. Color

Warm rose / blush MD3 palette — wellness, femininity, therapy (not corporate red).

| Token | Hex | Role |
|-------|-----|------|
| `surface` | `#fff7fa` | Page background |
| `surface-container-low` | `#ffeffb` | About section |
| `surface-container-highest` | `#f7daf4` | Contact section |
| `primary` | `#7c5454` | Headlines, primary buttons |
| `secondary` | `#8c4b55` | Subheads, secondary CTAs |
| `primary-container` | `#d4a3a3` | Icon backgrounds |
| `secondary-container` | `#feaab6` | Accents |
| `on-surface` | `#271528` | Primary text |
| `on-surface-variant` | `#504444` | Body text |
| `on-primary` | `#ffffff` | Text on primary buttons |
| `outline-variant` | `#d4c2c2` | Borders, dividers |

**Glass card:** `rgba(255,255,255,0.75)` + blur 12px + border `rgba(140,75,85,0.12)`  
**Shadow soft:** `0 10px 30px -5px rgba(212,163,163,0.2)`

Do not introduce high-contrast red `#D32F2F` (legacy Ravpage theme — deprecated).

---

## 2. Typography

| Role | Font | Weight | Size (desktop) |
|------|------|--------|----------------|
| Display / H1 | Hanken Grotesk | 600–700 | 2rem–2.5rem |
| Headline / H2–H3 | Hanken Grotesk | 500–600 | 1.25rem–1.875rem |
| Body | Manrope | 400 | 1rem–1.125rem |
| Labels / CTAs | Manrope or Hanken | 600 | 0.875rem–1rem |

- **Direction:** RTL always (`dir="rtl"`, `lang="he"`)
- **Line height:** 1.65–1.75 for body Hebrew
- **Load:** Google Fonts — Hanken Grotesk + Manrope

---

## 3. Spacing

| Token | Value |
|-------|-------|
| Section padding (mobile) | `py-16` (64px) |
| Section padding (desktop) | `py-20` / `py-24` (80–96px) |
| Container max width | `1200px` |
| Horizontal margin mobile | `20px` |
| Horizontal margin desktop | `64px` |
| Card padding | `p-7` / `p-8` (28–32px) |
| Grid gap (workshops) | `gap-6` / `gap-8` |

Mobile-first. Never clip Hebrew descenders with tight line-height.

---

## 4. Layout

**Page structure (production):**

1. Sticky header — logo, nav, mobile contact icon  
2. Hero `#about` — glass panel over full-width photo  
3. About — 2-col text + image  
4. Workshops `#workshops` — 3 glass cards (1 → 2 → 3 cols)  
5. Contact `#contact` — split form + image  
6. Footer  

**Breakpoints:** Tailwind `md:` (768px) for 2–3 column grids.

**RTL rules:** Use logical properties; nav uses `flex-row-reverse` where needed; form inputs `dir="rtl"`.

---

## 5. Components

### Header
- Sticky, `bg-surface/85`, backdrop blur
- Brand: 💄 + **איפור תרפי • Makeup Therapy** + tagline
- Nav: אודות · סדנאות · יצירת קשר

### Hero
- Background: `assets/images/hero-brushes.jpg`
- Glass panel: H1 question, subheadline, P1, CTA → `#workshops`

### About block
- P2 + P3 (method + invitation)
- Image: `assets/images/intro-mirror.jpg`

### Workshop card
- Emoji + Material icon circle
- Title: אפשרות N + name + tagline in parentheses
- Hook paragraph
- `<dl>`: מה מחכה / למי / התהליך / התוצאה
- CTA button → `#contact`
- Hover: slight lift (`-translate-y-1`)

### Contact form
- Intro copy (2 paragraphs from content-map)
- Fields: שם מלא, טלפון, select (3 workshops)
- Submit: **שלחי לי פרטים ונתאם!**
- Side image: `assets/images/contact-workshop.jpg`

### Buttons
- Primary: `bg-primary text-on-primary`, rounded-lg, shadow-soft
- Secondary: `bg-secondary` or outline `border-primary`

---

## 6. Motion

- Card hover: `transition-all duration-300`, `-translate-y-1`
- Button active: `active:scale-95`
- Scroll reveal (optional): workshop cards fade up via IntersectionObserver
- No aggressive animations — calm, therapeutic feel

---

## 7. Voice & tone

- **Language:** Hebrew first; brand name bilingual (איפור תרפי • Makeup Therapy)
- **Audience:** Women — personal groups, HR/wellness, mothers & daughters
- **Tone:** Warm, inviting, professional-therapeutic — not salesy or clinical
- **Person:** First person singular from facilitator ("פיתחתי", "אני מזמינה")
- **You:** Feminine singular ("את", "בחרי", "השאירי") — do not change without approval

Full marketing copy: **`docs/design/content-map.md`** — do not paraphrase in production.

---

## 8. Brand

| Field | Value |
|-------|-------|
| Name | איפור תרפי • Makeup Therapy |
| Tagline | המקום שבו המברשת פוגשת את הנפש |
| Category | Makeup therapy workshops / wellness |
| Visual mood | Soft blush, glass, beauty tools, mirror, group warmth |
| Icons | Material Symbols Outlined + emoji (🥂 🏢 👩‍👧 🔮 💄) |

**Imagery:** Local assets in `assets/images/` — makeup brushes, mirror, workshop circle. No stock that feels cold or corporate.

---

## 9. Anti-patterns

- ❌ English-only UI copy (except brand subtitle "Makeup Therapy")
- ❌ LTR layout or left-aligned body paragraphs
- ❌ Legacy red Ravpage palette (`#D32F2F`, charcoal banners)
- ❌ Invented workshop copy — use content-map verbatim
- ❌ Adding npm/React/Next to production repo without explicit request
- ❌ Merging [open-design](https://github.com/nexu-io/open-design) monorepo into this repo
- ❌ Generic AI-slop phrases ("unlock your potential", "game-changer")
- ❌ Cluttered hero — keep one clear H1 + one CTA
- ❌ More than 3 workshop cards without client approval

---

## Open Design prompt seed

```
Hebrew RTL landing page for "איפור תרפי • Makeup Therapy".
Use DESIGN.md from nivalandpage repo: blush MD3 palette, Hanken Grotesk + Manrope,
glass cards, warm wellness photography.
Copy MUST match docs/design/content-map.md exactly.
Sections: header, hero, about, 3 workshops, contact form, footer.
Static HTML + Tailwind CDN. dir="rtl" lang="he".
```

---

## Implementation reference

| Artifact | Path |
|----------|------|
| Live page | `index.html` |
| Content map | `docs/design/content-map.md` |
| Open Design workflow | `docs/OPEN-DESIGN-WORKFLOW.md` |
| Deploy | `docs/DEPLOY.md` |
