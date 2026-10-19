# Daymark — installable PWA

A standalone task dashboard for iPhone and iPad. Work and Personal workspaces, custom categories, task notes, priority, due dates, filters, search, editing, completion, JSON backup/restore. No external libraries or account.

## Deploy using GitHub Pages
1. Sign in at https://github.com and create a **public** repository named `daymark` (or another name).
2. Upload **the contents of the `daymark` folder**, not the ZIP itself: `index.html`, `app.js`, `styles.css`, `manifest.webmanifest`, `sw.js`, and the `icons` folder with all three PNG files. On GitHub use **Add file → Upload files** and commit. Keep the file/folder structure.
3. Go to **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, and Save.
4. Wait for Pages to publish. Your address will be `https://YOUR-USERNAME.github.io/daymark/` if the repository is called `daymark`. Use the actual URL GitHub displays.
5. Open the HTTPS URL in Safari on your iPhone or iPad. Tap **Share → Add to Home Screen** and turn on **Open as Web App** if shown. Tap Add. Launch Daymark from its icon.

## Deploy using Cloudflare Pages (direct upload)
1. Sign in at https://dash.cloudflare.com and open **Workers & Pages**.
2. Create a Pages project using **Direct Upload** (interface wording may vary).
3. Upload the **daymark folder or the ZIP** when prompted, ensuring `index.html` ends up at the site's root (not inside a nested folder).
4. Deploy and open the HTTPS `*.pages.dev` address Cloudflare gives you.
5. In Safari use **Share → Add to Home Screen** and choose **Open as Web App** if available.

## Important limitations
- Tasks persist in **localStorage** in this browser/app installation. This is not cloud storage. Clearing website data, removing the app, or some browser storage cleanup can remove tasks.
- iPhone and iPad **do not sync**. Use **Export JSON** and **Import backup** to transfer data manually. Import **replaces** the current dataset.
- Offline support starts after the app has been opened online once and its service worker has installed and cached assets. To test, load once, then switch on Airplane Mode and relaunch.
- App updates: after editing files, increase `CACHE` in `sw.js` (for example `daymark-v1.0.1`) so the new assets are cached. Refresh online, then reopen the app.
- This version does not connect to Apple Calendar, Reminders or ChatGPT automatically; those require additional integration work.
- Hosting is free on typical starter tiers subject to provider terms; GitHub Pages public repositories are publicly viewable. Do not store confidential client details in the app without appropriate security controls.
