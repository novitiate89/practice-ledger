# Practice ledger — deployment guide

A private, offline-capable practice tracker. All data lives in your phone's
local storage; the hosted files contain no personal information — they are
only the empty app shell.

## Files

- `index.html` — the entire app (self-contained, no dependencies)
- `manifest.json` — makes it installable as an app
- `sw.js` — service worker; makes it work offline
- `icon-192.png`, `icon-512.png` — home-screen icons

## Deploy to GitHub Pages (one-time, ~5 minutes)

1. Go to github.com and sign in. Click the **+** (top right) → **New repository**.
2. Name it something unmemorable to others if you like (e.g. `ledger-4a67`).
   Set it to **Public** (required for free Pages). Click **Create repository**.
3. On the new repo page, click **uploading an existing file**, drag in all
   five files from this folder, and click **Commit changes**.
4. Go to the repo's **Settings** → **Pages** (left sidebar).
   Under "Branch", select **main** and folder **/ (root)**, then **Save**.
5. Wait a minute, refresh the Pages settings page, and copy your URL:
   `https://<your-username>.github.io/<repo-name>/`

## Install on Android (~1 minute)

1. Open that URL in **Chrome** on your phone.
2. Chrome will usually show an **Install app** banner or prompt. If not:
   tap the **⋮** menu → **Add to Home screen** (or **Install app**).
3. Confirm. The icon appears on your home screen; it launches full-screen
   like a native app and works with no connection.

## Daily use

- The app opens on **Today**: everything currently due across all cycles,
  with weekly/monthly/quarterly items surfacing until checked for their period.
- **Events** logs the trigger-driven drills; **Journal** holds every entry.
- No streaks or scores anywhere — by design.

## Backups

Phone browser storage is durable but not sacred (clearing Chrome's site data
would erase it). Once a month or so, tap **Export backup** at the bottom —
it downloads a JSON file. **Import backup** restores it on any device,
which is also how you'd move to a new phone.

## Updating the app later

Replace `index.html` in the GitHub repo (Edit or re-upload → Commit).
If you change `sw.js`, bump the cache name (`practice-ledger-v1` → `-v2`)
so phones fetch the new version. Open the app once online and it refreshes.

## A note on the design

There are deliberately no notifications, streaks, or completion percentages.
The Today view on open is the reminder. If the ledger ever starts feeling
like a scorecard — the capture check will ask, every fifth day — that
noticing is the practice working.
