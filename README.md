# Local Business Locator System (LBLS)

Cross-platform MVP concept for the Botho University project brief. Built with Expo and React Native for Android and web.

## Features
- Search providers by name, category, service, or area
- Filter and sort by category, price, rating, and distance
- Provider details with call and Google Maps search actions
- Demo provider listing and review interactions
- Responsive web layout and mobile navigation

## Run locally
Requirements: Node.js 20+

```bash
npm install
npm run web
```

For Android, install Android Studio/SDK and run `npm run android` on a connected device or emulator.

## GitHub Actions
The workflow in `.github/workflows/build-apps.yml` exports the web build and creates an Android debug APK. Open the repository's **Actions** tab after pushing to inspect build results and download artifacts.

## Prototype limitations
Seeded provider information, prices, ratings and distances are demo data, not verified businesses. Listings and reviews are in-memory only and reset on restart. No persistent database, authentication, live GPS, review moderation, or signed production APK is included yet.