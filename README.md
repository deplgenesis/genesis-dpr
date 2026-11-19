# Genesis DPR - home-screen app wrapper

A tiny static site on GitHub Pages. `index.html` is a full-screen frame that opens your Apps Script form. The form itself always loads live from Apps Script and is never cached.

## Files (all go in the repo root)
- index.html
- manifest.webmanifest
- sw.js
- icon-192.png
- icon-512.png
- icon-maskable-512.png
- apple-touch-icon.png
- README.md

## Publish on GitHub (no command line)
1. Sign in at github.com with the right account.
2. Click the + at the top right > New repository.
3. Repository name: genesis-dpr. Choose Public. Click Create repository.
4. On the new empty repo page click "uploading an existing file".
5. Drag all 8 files in at once. Wait until all are listed.
6. Click Commit changes.
7. Click Settings > Pages (left menu).
8. Under Build and deployment > Source choose "Deploy from a branch".
9. Branch: main, folder: / (root). Click Save.
10. Wait 1-2 minutes, refresh the Pages screen. Your link is https://YOUR-USERNAME.github.io/genesis-dpr/
11. Dashboard link: add ?page=dashboard to the end of that link.

## Install on a phone
- Android Chrome: open the link, menu (three dots) > Install app, or Add to Home screen.
- iPhone Safari: open the link, Share > Add to Home Screen.

## Test list
1. Opens full screen with no browser bar.
2. The form loads after the white cover.
3. Camera and location prompts appear when you add a photo.
4. Airplane mode shows "No internet" with a Try again button.
5. The icon looks right and is not cropped.
6. iPhone only: take a photo with the camera and check the location shows. If the camera or location keeps failing inside the home-screen app, open the form link in Safari instead.

## When the app changes later
1. Code.gs or Index.html changed: in Apps Script click Deploy > New deployment (never Manage deployments > New version).
2. Copy the new link ending in /exec.
3. On GitHub open index.html, click the pencil icon, replace ONLY the APP_URL line, click Commit changes.
4. Nothing else changes. Wait a minute, then close and reopen the app.

## If the form stays blank
- The Apps Script doGet must return the page with `.setXFrameOptionsMode(HtmlService.XFrameOptionsMode.ALLOWALL)`. Your current Code.gs already does this.
- Deploy settings: Execute as: Me, Who has access: Anyone.
