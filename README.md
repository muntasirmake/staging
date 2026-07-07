# Banglalink · Horizon Entry Point

Hybrid sliced-PNG layout: the original Banglalink mockup is cut into static full-width
image strips, with the three interactive Horizon embeds placed **between** them as real
document-flow blocks — so each embed takes its own height and the next banner always
starts after it (no overlap, mobile or desktop). No full-page background PNG.

Flow: `section-1` (demo bar + header + hero + 150GB card + bKash title) → `HORIZON_ENTRY_1`
(`#377585`, `cs`) → `section-2` (Daraz promo + title) → `HORIZON_ENTRY_2` (`#985860`, `rs`)
→ `section-3` (Samsung promo + title) → `HORIZON_ENTRY_3` (`#143783`, `b4`) →
`section-nav` (bottom nav). Single embed script loads once.

390px frame, centered on desktop, 100% width on smaller screens.

No build step — plain static HTML. Vercel serves it as-is.

## Files
- `index.html` — the page
- `img/` — the four static PNG slices (section-1/2/3 + section-nav)

## Deploy to Vercel

**Option A — GitHub + Vercel dashboard**
1. Create a new GitHub repo and push the contents of this `deploy/` folder to its root.
2. In Vercel: **Add New → Project → Import** the repo.
3. Framework Preset: **Other**. Build Command: *(leave empty)*. Output Directory: *(leave empty / `.`)*.
4. Deploy. Copy the resulting `*.vercel.app` domain.

**Option B — Vercel CLI**
```bash
cd deploy
npx vercel        # preview deploy
npx vercel --prod # production deploy
```

## Whitelist the domain in Horizon Console
After the first deploy, add your live domain (e.g. `your-app.vercel.app`, and any
custom domain) to the allowed-origins / whitelist for ref `69359e05b62bd32a6d2ec964`
in Horizon Console. Until the domain is whitelisted, `HORIZON_ENTRY_1` renders its
container but the circular video rail stays empty — this is expected.
