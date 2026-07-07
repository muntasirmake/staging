# Banglalink · Horizon Entry Point

Static prototype: the Banglalink app screen (`bl-empty.png`) as a fixed 430px mobile
canvas, with three interactive Horizon entry points overlaid into their reserved rails:

- `HORIZON_ENTRY_1` — under **bKash Deal Room** (ep `#377585`, `cs`)
- `HORIZON_ENTRY_2` — under **Daraz Discount Festival** (ep `#985860`, `rs`)
- `HORIZON_ENTRY_3` — under **Samsung Stories** (ep `#143783`, `b4`)

The PNG is the only visible app shell; a single embed script loads once for all three.

No build step — plain static HTML. Vercel serves it as-is.

## Files
- `index.html` — the page (background + Horizon overlays + embed script)
- `bl-empty.png` — the app-shell background image

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
