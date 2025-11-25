# DrRockyJagpal.com (static site)

This is a static HTML/CSS site (Tailwind via CDN) deployed on Vercel. There is no build step.

## Structure
- `index.html` (home)
- `before-after.html` (client transformations)
- `blueprint.html` (free blueprint form)
- `before-after-clients/` (original client images used when requested)
- `before-after-clients-blurred/` (server-side blurred copies used for privacy)
- `vercel.json` (asset caching headers)

## Update flow (Vercel + GitHub)
1. Make your edits locally.
2. Commit and push to the connected branch (usually `main`).
   ```bash
   git add -A
   git commit -m "Update: content, gallery, mobile menu, smooth scroll, CTAs, Instagram footer"
   git push origin main
   ```
3. Vercel auto-deploys on push. Check Deployments in the Vercel dashboard.
4. Visit the live site (e.g., https://drrockyjagpal.vercel.app) and hard-refresh if needed (Cmd+Shift+R).

## Manual deploy (CLI)
```bash
npm i -g vercel
vercel        # preview
vercel --prod # production
```
When prompted:
- Framework preset: Other
- Build command: (leave empty)
- Output directory: `.`

## Images and privacy
- Faces are blurred in `before-after-clients-blurred/`. Originals remain in `before-after-clients/`.
- If you add new client images, either place them directly in `before-after-clients` and regenerate blurred copies, or add blurred copies to `before-after-clients-blurred` and reference them directly in `before-after.html`.
- Avoid spaces in folder names. We've renamed `before after clients` to `before-after-clients` for deployment safety.

## Troubleshooting
- If a button doesn’t navigate, ensure it links to `blueprint.html` (not `#cta`).
- If a page shows blank, force refresh or verify that file names match (all screenshots are sanitized to `Screenshot-YYYY-MM-DD-h.mm.ss-PM.png`).
- Vercel Pages config: Framework = Other, Build Command = empty, Output Directory = `.`.

## Future improvements
- Optional clean URLs (e.g., `/before-after` instead of `/before-after.html`)
- Image compression for faster mobile loads
- Width/height attributes on images to reduce CLS
