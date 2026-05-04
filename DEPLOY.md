# Contact Us — Vercel Deployment Guide

## Folder Structure

```
vercel-contact/
├── index.html              ← Single-file landing page (inline CSS + JS)
├── vercel.json             ← { "cleanUrls": true } only
├── DEPLOY.md               ← This file
├── download                ← Blank placeholder (required)
└── images/
    └── doctors/
        ├── angela-kifer-thomas.jpg
        ├── dr-patel.jpg
        ├── dr-akler.jpg
        ├── brett-whaley.jpg
        ├── dr-ahmed.jpg
        └── dr-chandler.jpg
```

---

## Deployment Steps

1. **Initialize Git & push to GitHub**
   ```bash
   cd vercel-contact
   git init
   git add .
   git commit -m "initial commit — Contact Us landing page"
   git branch -M main
   git remote add origin https://github.com/YOUR-ORG/contact-landing.git
   git push -u origin main
   ```

2. **Import into Vercel**
   - Go to [https://vercel.com/new](https://vercel.com/new)
   - Click **Import Git Repository**
   - Select the `contact-landing` repo
   - **Framework Preset**: Other
   - **Root Directory**: `vercel-contact`
   - **Build Command**: *(leave blank)*
   - **Output Directory**: *(leave blank)*
   - **Install Command**: *(leave blank)*
   - Click **Deploy**

3. Vercel will serve `index.html` directly. No build step needed.

---

## ⚠️ Do NOT

- Add a `build` script or `package.json`
- Add rewrites to `vercel.json`
- Use absolute image paths (e.g., `/images/...`) — always use relative (`images/...`)
- Use `vh`, `dvh`, or `svh` units for any section heights
- Add a `.gitignore`, `node_modules/`, or `public/` folder

---

## CTA URLs

| Link | URL |
|---|---|
| Privacy Policy | `https://precisiontelemed.com/privacy-policy/` |
| Terms of Service | `https://precisiontelemed.com/terms-of-service/` |
| Trustpilot | `https://www.trustpilot.com/review/precisiontelemed.com` |

---

## Conventions Compliance Checklist

- [x] No `vh`, `dvh`, or `svh` units anywhere
- [x] Section uses `min-height: clamp(560px, 60vw, 860px)` (iframe-safe)
- [x] All image paths are relative (`images/...`)
- [x] `vercel.json` contains only `{ "cleanUrls": true }`
- [x] Blank `download` placeholder present
- [x] No `../` cross-folder references
- [x] Brand tokens match conventions (`--color-bg: #fdfbf7`, `--color-primary: #788C75`, etc.)
- [x] `--section-gap: clamp(3rem, 6vw, 5rem)`
- [x] `overflow-x: hidden` on `#page-wrap`
- [x] All doctor images non-zero bytes
- [x] iframe-safe — no circular viewport sizing

---

*Last updated: May 2026*
