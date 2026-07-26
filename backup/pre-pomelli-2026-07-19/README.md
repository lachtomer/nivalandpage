# Backup — pre-Pomelli design

**Date:** 2026-07-19  
**Reason:** Before applying Google Pomelli redesign to production `index.html`

## Restore

```powershell
Copy-Item "backup/pre-pomelli-2026-07-19/index.html" "index.html" -Force
Copy-Item "backup/pre-pomelli-2026-07-19/assets/*" "assets/images/" -Recurse -Force
git add index.html assets
git commit -m "Restore pre-Pomelli design"
git push
```

## Pomelli reference

https://labs.google.com/pomelli/website/9PyRH5X6HaD8RXsDxhtOqy

## What was backed up

- Full `index.html` (Tailwind MD3 blush theme)
- `assets/images/` at time of backup
