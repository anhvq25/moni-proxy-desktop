# moni-proxy-desktop

Distribution channel for **Moni Proxy** macOS auto-update (Sparkle).

- **`appcast.xml`** — the Sparkle feed the app polls.
  Live: https://anhvq25.github.io/moni-proxy-desktop/appcast.xml
- **Releases** — host the signed `.dmg` files here (tag `vX.Y.Z`); the
  `<enclosure url>` in each appcast item points at the Release asset.

The app source lives in the main repo. Each release:
1. `macos/packaging/sign_and_notarize.sh` (build + Developer ID sign + notarize)
2. `macos/packaging/sparkle_release.sh X.Y.Z <dmg> <release-download-url>`
   (Sparkle-signs the DMG, appends an item to `appcast.xml`)
3. Upload the DMG to a GitHub Release here, commit/push the updated `appcast.xml`.

GitHub Pages must be enabled (Settings → Pages → Deploy from branch → `main` / root).
