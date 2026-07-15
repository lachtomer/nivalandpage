# Next steps — Niva landing page

> **Current status:** Phase 2 done — layout, Hebrew copy (איפור תרפי), 3 workshop cards, contact form (not connected).  
> **Phase 3:** ⏭️ **Skipped for now** — placeholders stay (`[שם בעלת העמוד]`, sample photo, placeholder phone).  
> **Stack:** Static HTML/CSS → deploy to Vercel/Netlify free subdomain.

---

## Where you are now

| Done | Pending |
|------|---------|
| Design system (`DESIGN.md`) | Real owner name |
| Content map + page copy | Real photo(s) |
| Hero, dark banner, workshops, form UI | Phone number |
| RTL layout + mobile responsive | Form backend |
| Sample placeholder images | Deploy live URL |
| Local preview | Remove preview banner |

---

## Phase 3 — Real assets ⏭️ SKIPPED (for now)

Placeholders remain until you're ready:

- `[שם בעלת העמוד]` in footer
- Sample Unsplash hero photo
- Phone FAB: `050-0000000`

**When ready later:** say `Phase 3 — name: ___, phone: ___` + drop photo in `assets/images/`.

---

## Phase 4 — Connect the form ← **YOU ARE HERE**

Pick **one** option (simplest first):

### Option A — Formspree (recommended, 5 min)
1. Sign up at [formspree.io](https://formspree.io) (free tier)  
2. Create a form → copy your form ID  
3. Agent updates `<form action="https://formspree.io/f/YOUR_ID" method="POST">`  
4. Submissions arrive by email  

### Option B — Netlify Forms
1. Deploy site to Netlify first  
2. Add `netlify` attribute to form + `name` fields  
3. Submissions in Netlify dashboard  

### Option C — Google Sheet (via Make/Zapier)
- Formspree → Zapier → Google Sheet (if you want a spreadsheet)

**Your job:** choose A or B and create the account.  
**Agent job:** wire the HTML form.

---

## Phase 5 — Deploy (free subdomain)

### Vercel (recommended)

```powershell
cd "c:\Users\TOMERLAC\OneDrive - AMDOCS\Desktop\Niva"
npx vercel
```

- Follow prompts → get URL like `niva-xxx.vercel.app`  
- Or connect GitHub for auto-deploy on every change  

### Netlify (alternative)

- Drag the `Niva` folder onto [app.netlify.com/drop](https://app.netlify.com/drop)  
- Instant URL like `random-name.netlify.app`  

**Your job:** create Vercel/Netlify account (free).  
**Agent job:** add `vercel.json` if needed, remove preview banner, final QA checklist.

---

## Phase 6 — Polish before sharing

- [ ] Test on **your phone** (scroll, form, phone link)  
- [ ] Check all 3 workshop CTAs scroll to contact  
- [ ] Submit test form — confirm email received  
- [ ] Replace Unsplash placeholder with real hero photo  
- [ ] Remove orange "Phase preview" banner at top  
- [ ] Optional: favicon, OG image for WhatsApp/Facebook previews  

---

## Phase 7 — Later (optional)

| Feature | When |
|---------|------|
| Meta Pixel (Facebook ads) | When running ads |
| Custom domain | When ready to buy domain |
| Rav Messer / email list | When CRM chosen |
| Thank-you page (`/thanks`) | After form works |
| Second language (English) | If needed |
| Next.js migration | Only if adding many pages |

---

## Suggested order (this week)

```
Now       → Phase 4: Formspree account + connect form
           → Phase 5: Deploy to Vercel (works with placeholders)

Later     → Phase 3: real name, phone, photo when ready
           → Phase 6: mobile test, remove preview banner, share link
```

---

## How to preview locally

```powershell
cd "c:\Users\TOMERLAC\OneDrive - AMDOCS\Desktop\Niva"
python -m http.server 8080
```

Open: **http://localhost:8080**

---

## Quick prompts for Cursor

| Goal | Say this |
|------|----------|
| Swap real content | `Phase 3 — name: ___, phone: ___` |
| Connect form | `Connect form to Formspree ID: ___` |
| Deploy | `Prepare for Vercel deploy and remove preview banner` |
| Design tweak | `Make workshop cards shorter on mobile` |
| New section | `Add testimonials section below workshops` |

---

## Files to know

| File | Role |
|------|------|
| `index.html` | Page content |
| `css/style.css` | All styling |
| `docs/design/DESIGN.md` | Colors, fonts, layout rules |
| `docs/design/content-map.md` | What text goes where |
| `assets/images/` | Photos |
