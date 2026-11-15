# Ford Circles: installable app

This folder is the Ford Circles explorer packaged as a Progressive Web App.
Once it's hosted, your phone can install it like a normal app: its own icon,
full-screen with no browser bar, and it works offline.

## Files

- `index.html`: the explorer itself, plus app tags and service-worker registration
- `manifest.webmanifest`: app name, colours and icons
- `sw.js`: service worker that caches the app for offline use
- `icons/`: app icons (normal, maskable for Android, Apple touch icon)

## Put it online with GitHub Pages (free, about 5 minutes)

1. On GitHub, create a new **public** repository, for example `ford-circles`.
2. Upload everything in this folder to the root of the repo, keeping the `icons/` folder.
   (On the repo page: "Add file" → "Upload files", then drag the files and folder in.)
3. Go to **Settings → Pages**. Under "Build and deployment", set Source to
   **Deploy from a branch**, branch **main**, folder **/ (root)**, and save.
4. After a minute or two the site is live at
   `https://<your-username>.github.io/ford-circles/`

## Install it on your phone

**Android (Chrome, Brave, Edge, Samsung Internet):** open the URL, then use the
browser menu → **Install app** (or **Add to Home screen**). Open it once while online
so it can cache itself. After that it works offline.

**iPhone (Safari):** open the URL → Share → **Add to Home Screen**.

## Updating it later

Edit `index.html`, then open `sw.js` and bump `VERSION` (for example `ford-v1` → `ford-v2`).
Push both. Installed copies pick up the new version the next time they're opened online.

## Notes

- The fonts load from Google Fonts. They're cached after the first online launch.
  Before that, offline, the app falls back to system fonts and works the same.
- GitHub Pages serves over HTTPS, which service workers require. Opening `index.html`
  straight from your phone's files won't install as an app. It needs to be served
  from a web address.
