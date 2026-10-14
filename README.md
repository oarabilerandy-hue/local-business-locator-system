# Local Business Locator System (LBLS)

LBLS is a React Native + Expo MVP for discovering local service providers in Botswana.

## Current working baseline

- The Android release APK has been built successfully with its JavaScript bundle packaged.
- The Git commit used for that verified build is `030153c30b756898b377020a9e00f9b606c617f6`.
- A reference branch, `known-good-android-2026-10-14`, points to that commit.
- The Android app source (`App.js`) is intentionally not changed by the web packaging fix.

## Download builds

Open the [GitHub Actions runs](https://github.com/oarabilerandy-hue/local-business-locator-system/actions) and select the latest successful **Build web and Android** run. Download:

- `local-business-locator-system-android-release-apk` — Android release APK.
- `local-business-locator-system-web-zip` — exported web app ZIP, with `index.html` at the archive root.

Artifacts expire after 14 days, so download important builds promptly. For a permanent release, publish a GitHub Release with the tested APK attached.

## Run the web app

1. Download and extract the web ZIP.
2. Open `index.html` in a modern browser.
3. If your browser blocks local JavaScript, run a local static server from the extracted folder instead (for example, `python -m http.server 8000`) and open `http://localhost:8000`.

The web build workflow checks that the HTML and JavaScript assets exist, rewrites root-relative asset references to relative paths, and checks the ZIP entry point. A successful build does not replace a real browser test.

## Build workflow

The single workflow at `.github/workflows/build-apps.yml` builds both deliverables:
- Web: Expo web export, HTML/asset checks, ZIP packaging.
- Android: Expo native prebuild, Gradle release APK, and embedded JavaScript bundle verification.

It runs on pushes and pull requests to `main` / `master`, and can be started manually from the Actions tab using **Run workflow**.

## Run locally

Requires Node.js 20+.

```bash
npm install --legacy-peer-deps
npm run web
```

## MVP limitations before public launch

The directory currently uses illustrative sample providers, prices, ratings, and areas. Provider listings and demo reviews exist only in memory and reset when the app restarts. Before presenting the service as a live public directory, add persistent storage, verified business profiles, authentication and authorization where needed, privacy and terms pages, reporting/moderation, and a real data backup strategy. Live GPS and embedded maps are not connected; directions open a Google Maps search.

## Open source and release

The repository is public, but a public repository alone does not specify a license. Before describing the project as open source, choose and add a license (for example, MIT if that matches your intended permissions). Before distributing a production APK, test the latest build on real Android devices, check the package name/version, and publish release notes with the exact tested APK.
