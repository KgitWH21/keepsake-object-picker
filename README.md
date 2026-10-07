# Keepsake

A writer’s object picker: 240 objects, eight collections, relationship prompts, evolving callbacks, and independent rerolls.

This is the complete standalone app. It doesn't need npm, a build step, API keys, or a ChatGPT login.

## Publish as its own GitHub Pages app

1. Extract this ZIP and open the `keepsake-github` folder in VS Code.
2. Put the folder’s contents in your GitHub repository, with `index.html` at the repository root. Push your files to `main`.
3. In the repository, open **Settings > Pages**.
4. Choose **Deploy from a branch**, select **main** and **/(root)**, then save.
5. Open the published address shown by GitHub Pages. Publication can take a few minutes.

Official guide: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## Add to an existing writing-tools site

Copy the app files into a `keepsake/` folder inside the existing site's publishing directory. Link to `./keepsake/` from your tools page. Keep the app files together. Use a URL with the trailing slash.

All asset paths, the install manifest, and the service worker are relative, so the app supports both repository hosting and a nested folder. The offline cache is scoped to this app’s address.

## Install on your phone

Open the published app URL on your phone, then tap **Add to phone** for instructions.

- iPhone/iPad: use Safari’s Share menu, then Add to Home Screen.
- Android: use the browser’s Install app or Add to Home screen option.

The package includes 192px and 512px app icons and a standalone manifest. After a successful first online visit and cache setup, the app can work offline. Browser storage clearing can remove that cache.

## Preview locally

Open the folder using VS Code’s Live Server extension, or run `python -m http.server 8000` from this folder and visit http://localhost:8000. Basic picking also works when opening `index.html` directly, but installation and offline support need HTTPS hosting or localhost.

## Edit

- `data.js`: objects, associations, relationships, and prompts.
- `style.css`: layout and colors.
- `app.js`: picker behavior.
- `index.html`: page text and layout.
- `manifest.webmanifest`: app name, launch path, and icons.
- `sw.js`: offline cache. Increment the version suffix when releasing changed assets.

No personal story text is sent to a server. The display-mode preference stays in this browser. Copy prompt uses the clipboard.
