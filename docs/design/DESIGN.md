# Design System — Keren Elyakim Welcome Page

> Extracted from reference mockup (`image_4dd106.jpg` / `hero-and-top-sections.png`).  
> Use for Google Stitch, `gstack-design-html`, and implementation. RTL Hebrew throughout.

## Reference assets

| Asset | Path |
|-------|------|
| Top-of-page screenshot | `docs/design/reference/hero-and-top-sections.png` |
| Source label | `image_4dd106.jpg` |

---

## Color palette

| Token | Hex | Usage |
|-------|-----|--------|
| `--color-primary` | `#D32F2F` | Buttons, list icons, logo accent, CTA bars |
| `--color-dark` | `#1A1A1A` | Dark information banner background |
| `--color-white` | `#FFFFFF` | Cards, hero overlay, inverted text backgrounds |
| `--color-text-primary` | `#000000` | H1, section titles on light backgrounds |
| `--color-text-body` | `#444444` | Body paragraphs |
| `--color-text-inverted` | `#FFFFFF` | Text on dark / red backgrounds |

Light backgrounds: white and semi-transparent white overlays on photography.

---

## Typography

| Property | Value |
|----------|--------|
| Direction | **RTL** (`dir="rtl"`, `direction: rtl`) |
| Font family | Modern Hebrew sans-serif — **Heebo** or **Assistant** (Google Fonts) |
| H1 (hero) | Bold, largest size, block format |
| H2 (sections) | Bold, centered |
| Body | Regular weight, generous line-height (~1.6–1.8) |
| Nav | Sans-serif, moderate size |

---

## Layout & spacing

- Mobile-first; sections stack naturally on narrow viewports.
- Generous vertical padding between major sections.
- Hero: asymmetrical split — subject photo on **right** (RTL visual anchor), content overlay on **left**.
- Features grid: 4 columns desktop → 2 tablet → 1 mobile.
- Dark banner: 2-column bullet grid desktop → 1 column mobile.

---

## Components

### Global header

- Centered primary logo beneath top bar area.
- Horizontal navigation menu directly under logo.
- Standalone **red circular icon button** on the **far left** (phone / contact — floating feel).

### Hero section

- Full-width background image (portrait + environment).
- **Right:** primary subject (therapist photo).
- **Left:** white overlay panel containing:
  - H1 headline
  - Descriptive paragraph
  - 3-item list with **red circular checkmark** icons
  - Primary CTA — full-width red button, rounded corners, white label text

### Dark information banner

- Full-width `--color-dark` background.
- Centered white introductory paragraph.
- **2-column grid** of bullet points with small red dash/dot icons.
- Bottom: **full-width red CTA bar** with centered white bold text (anchor statement).

### Features grid (4 columns)

- Section background: very light gray with **faded landscape watermark** (East Asian ink-wash style).
- Centered H2 + gray subtitle.
- Row of **4 uniform white cards**:
  - Soft drop shadow
  - Top-centered red icon
  - Bold centered title
  - 2–3 lines centered gray description

---

## Visual motifs

- Blend of professional business layout with subtle Eastern / philosophical imagery (dolls in hero, mountain painting in features section).
- Red used consistently for action and emphasis — not decorative noise.

---

## Section order (top → bottom, as in reference)

1. Global header (logo, nav, phone FAB)
2. Hero (split layout + primary CTA)
3. Dark information banner (intro + 2-col bullets + red bottom bar)
4. Features grid (4 cards)
5. *(Additional sections below fold — to be captured when more reference assets arrive)*

---

## Implementation notes

```css
/* Suggested CSS custom properties */
:root {
  --color-primary: #D32F2F;
  --color-dark: #1A1A1A;
  --color-white: #FFFFFF;
  --color-text-primary: #000000;
  --color-text-body: #444444;
  --color-text-inverted: #FFFFFF;
  --font-family: 'Heebo', 'Assistant', sans-serif;
  --shadow-card: 0 4px 20px rgba(0, 0, 0, 0.08);
  --radius-button: 8px;
}
```

- Set `html { dir: rtl; lang: he; }`.
- Hero overlay: semi-opaque white (`rgba(255,255,255,0.92)` or similar).
- Primary button: `--color-primary` background, white text, hover darken ~10%.
- Card icons: SVG or icon font, `--color-primary` fill.

---

## Stitch / AI prompt seed

> Hebrew RTL landing page for therapist Keren Elyakim. Colors: red #D32F2F, charcoal #1A1A1A, white. Hero with photo right, white text panel left, red CTA. Dark section with 2-column bullets and red bottom bar. Four feature cards on faded mountain watermark background. Clean Ravpage-style, mobile-first, Heebo font.
