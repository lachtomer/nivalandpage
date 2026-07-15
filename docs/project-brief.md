# Niva — Keren Elyakim Welcome Landing Page

> Project brief captured from planning session. Use with `docs/design/DESIGN.md` when speccing or building.

## Goal (v1)

Single Hebrew RTL welcome landing page introducing **Keren Elyakim**, a therapist who facilitates workshops (סדנאות). Ravpage-style layout; static HTML deployable to a free subdomain.

## Scope — in

- Hero + intro + workshop positioning
- Sections visible in reference mockup (header through features grid)
- Mobile-first, RTL
- Simple lead CTA (form backend TBD)

## Scope — out (later)

- CRM / email list integration (Rav Messer, Mailchimp, etc.)
- Meta Pixel / paid ads tracking
- Custom domain
- Booking / payments
- Additional pages beyond welcome landing

## Decisions

| Topic | Choice |
|-------|--------|
| Language | Hebrew, RTL |
| Purpose | Introduce therapist + workshops |
| Hosting | Free subdomain (Vercel / Netlify) |
| Stack | Static HTML/CSS (match Ravpage example) |
| Leads | Not decided — use placeholder form handler for v1 |

## Reference

- Live inspiration: `https://kerenelyakim.ravpage.co.il/welcome`
- Design system: [`docs/design/DESIGN.md`](design/DESIGN.md)
- Screenshot: [`docs/design/reference/hero-and-top-sections.png`](design/reference/hero-and-top-sections.png)
- Content extract from mockup: [`docs/design/content-from-reference.md`](design/content-from-reference.md)

## Next steps (when ready)

1. `specify init --here --integration cursor-agent --integration-options="--skills" --script ps --ignore-agent-tools`
2. `speckit-specify` using this brief + DESIGN.md
3. `speckit-plan` → static site + Formspree/Netlify Forms placeholder
4. Build sections top-to-bottom per DESIGN.md
