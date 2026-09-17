# Budget 2026

A personal budget planner that installs on your iPhone. You get a monthly overview, income, debts, savings and plans, in RON, EUR, USD and GBP.

The app has no build step: it's plain files you upload. Your data is stored only on your device. Nothing is uploaded anywhere.

## Files

| File | What it does |
|---|---|
| `index.html` | The whole app |
| `manifest.json` | Makes it installable as a home-screen app |
| `sw.js` | Keeps it working offline |
| `icon-192.png`, `icon-512.png`, `apple-touch-icon.png` | App icons |

**Keep `my-budget.json` off GitHub.** That file holds your real names and amounts. The repo is public, so if the file is uploaded, anyone can read it.

## Publish on GitHub Pages

1. Create a new public repo named `ES-budget` and upload the files in this folder (the files themselves, not the folder).
2. Go to **Settings → Pages**, set Source to **Deploy from a branch**, then choose `main` and `/ (root)`, and save.
3. After a minute the app is live at `https://esthyu.github.io/ES-budget/`.

The old `budget-planner-2026` repo still shows personal data in its code. Once this one works, set the old repo to private (Settings → General → Danger Zone → Change visibility).

## Install on iPhone

1. Open the link in **Safari**.
2. Tap **Share**, then **Add to Home Screen**.
3. Open **Budget 2026** from the home screen.
4. Go to **Settings → Import JSON** and pick `my-budget.json`. You can do this from Files, iCloud Drive, or an email to yourself.

The home-screen app keeps its own storage, separate from Safari. Import your file inside the installed app.

## Updating the app later

1. Upload the new `index.html`.
2. In `sw.js`, bump `VERSION` (for example `budget2026-v2`) so phones pick up the change.
3. Your data isn't touched by updates.

## Backups

Go to **Settings → Export JSON**. On iPhone this opens the share sheet, so you can save the file to Files or iCloud. Export a backup every few weeks.

## How the numbers work

- **Net balance** = income − expenses − debts due that month − savings. You can turn off subtracting savings in Settings.
- **Marking a debt paid** moves it to "Debt paid" for that month. The net balance doesn't change.
- **The current month** follows today's date automatically. In Settings you can set a fixed month instead.
- **Exchange rates** come from the European Central Bank reference rates, via frankfurter.app, when you're online. Typing a rate switches the app to manual rates.
- **Future debts** aren't counted anywhere else.
