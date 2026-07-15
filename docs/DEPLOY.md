# Deploy & manage — Niva on Vercel

## Your workflow (many changes)

```
Edit index.html / images in Cursor
    → git commit
    → git push (once GitHub connected)
    → Vercel auto-redeploys (~30 sec)
    → Share same URL with customer
```

---

## Option A — Vercel + GitHub (recommended for you)

Best when you’ll keep changing the site.

### One-time setup

1. **Create a GitHub repo** (private is fine)
   - [github.com/new](https://github.com/new) → name e.g. `niva-makeup-therapy`
   - Do **not** add README (you already have one)

2. **Push this project** (PowerShell):
```powershell
cd "c:\Users\TOMERLAC\OneDrive - AMDOCS\Desktop\Niva"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/niva-makeup-therapy.git
git push -u origin main
```

3. **Connect Vercel**
   - [vercel.com/new](https://vercel.com/new) → Import Git Repository
   - Select your repo
   - Framework: **Other** (static)
   - Root Directory: `./`
   - Build Command: leave empty
   - Output Directory: leave empty (or `.`)
   - Deploy

4. **You get a URL** like `https://niva-makeup-therapy.vercel.app`

### Every change after that

```powershell
git add .
git commit -m "Update workshop copy"
git push
```

Vercel redeploys automatically. Same link — send to customer anytime.

---

## Option B — Vercel CLI (from this folder)

```powershell
cd "c:\Users\TOMERLAC\OneDrive - AMDOCS\Desktop\Niva"
npx vercel          # preview URL
npx vercel --prod   # production URL
```

**Note:** On Amdocs/corporate network, CLI may fail with SSL certificate errors. Use **Option A** (dashboard + GitHub) or run CLI from home network / phone hotspot.

---

## Option C — Quick share (no Git)

1. [app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag the `Niva` folder
3. Instant URL — good for one-off preview, not ideal for ongoing edits

---

## Project files

| File | Purpose |
|------|---------|
| `vercel.json` | Static site config for Vercel |
| `.gitignore` | Ignores `.vercel` local cache |
| `index.html` | The live page |

---

## Connect form later (Formspree)

1. [formspree.io](https://formspree.io) → new form → copy ID `f/xxxxx`
2. In `index.html`, set:
```html
<form action="https://formspree.io/f/xxxxx" method="POST">
```
3. Remove the `onsubmit="event.preventDefault()..."` handler
4. `git commit` + `git push` → live

---

## Custom domain (later)

Vercel project → **Settings → Domains** → add e.g. `makeuptherapy.co.il`

---

## Share with customer

Send the Vercel URL. Example message:

> היי, הנה דף הנחיתה לתצוגה:  
> https://YOUR-PROJECT.vercel.app  
>  
> אפשר לגלול, לבדוק במobile, ולשלוח הערות. הטופס יחובר בשלב הבא.
