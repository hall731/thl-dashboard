# THL P&L Dashboard

Real-time P&L dashboard for Tele-Help-Ing. Reads directly from Google Drive.

## Deploy

```bash
# 1. Create GitHub repo and push
git init
git add .
git commit -m "init"
git remote add origin https://github.com/hall731/thl-dashboard.git
git push -u origin main

# 2. Connect to Netlify
# netlify.app → Add new site → Import from GitHub → pick repo → Deploy
```

## After deploy

1. Copy your Netlify URL (e.g. `https://thl-dashboard.netlify.app`)
2. Go to Google Cloud Console → APIs & Services → Credentials
3. Edit your OAuth 2.0 Client ID
4. Add to "Authorized JavaScript origins":
   - `https://thl-dashboard.netlify.app`
5. Save — takes ~5 min to propagate

## How it works

- No backend. Pure client-side.
- Google OAuth (implicit flow) — token lives in memory only, never stored.
- Reads the folder named `Tele-help-Ing PnLs 2026` from your Drive.
- Downloads each `.xlsx`, parses the `High Level` sheet with SheetJS.
- Renders KPIs, charts, P&L table, and client roster.

## Refresh

Click ↻ Refresh in the top bar to re-pull from Drive at any time.
