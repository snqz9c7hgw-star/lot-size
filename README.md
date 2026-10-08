# Lot Size (IFX) — install guide

This folder is a complete installable web app (PWA). Once it is hosted on any HTTPS address,
your iPhone and Mac can install it like a normal app: own icon, full screen, works offline.
Your settings are stored only on each device.

## 1. Host it (GitHub Pages, free, ~5 minutes)

1. On github.com create a new repository, e.g. `lot-size`. Free Pages needs it to be **Public**.
   (Nothing personal is in these files; your balances never leave your device.)
2. Click **uploading an existing file** and drag in everything inside this folder
   (`index.html`, `manifest.webmanifest`, `sw.js`, the `icons` folder). Commit.
3. Go to **Settings → Pages**. Under *Build and deployment*, set Source to **Deploy from a branch**,
   branch **main**, folder **/ (root)**. Save.
4. After a minute your app is live at `https://<your-username>.github.io/lot-size/`.

Or from Terminal on your Mac:

```bash
cd ~/Downloads/lot-size-app
git init && git add . && git commit -m "Lot size app"
gh repo create lot-size --public --source=. --push
gh api -X POST repos/{owner}/lot-size/pages -f "source[branch]=main" -f "source[path]=/"
```

## 2. Install on iPhone

1. Open the link in **Safari**.
2. Tap **Share → Add to Home Screen → Add**.
3. Open it once while online. After that it works in flight mode too.

## 3. Install on MacBook

- **Safari:** open the link, then **File → Add to Dock**. It becomes an app in your Dock and Launchpad.
- **Chrome:** open the link, then click the install icon at the right of the address bar.

## Updating the app later

Edit `index.html`, change `VERSION` in `sw.js` (e.g. `lotsize-v2`), and upload both again.
Installed copies update the next time they open with internet.
