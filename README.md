# Local Business Locator System (LBLS)

Cross-platform MVP concept for the Botho University project brief. Built with Expo and React Native for Android and web.

## Features
- Search providers by name, category, service, or area
- Filter and sort by category, price, rating, and distance
- Provider details with call and Google Maps search actions
- Demo provider listing and review interactions
- Responsive web layout and mobile navigation

## Download the app

This project is set up to generate a downloadable Android APK.

### Option 1: GitHub Actions APK artifact
1. Push the project to the `main` branch.
2. Open the repository's Actions tab.
3. Run the `Build web and Android` workflow.
4. Download the artifact named `local-business-locator-system-android-debug-apk`.
5. Install the APK on an Android device.

### Option 2: Local Expo build
```bash
npm install
npx expo prebuild --platform android --non-interactive
cd android
./gradlew assembleDebug
```

The APK will be generated under:
```bash
android/app/build/outputs/apk/debug/app-debug.apk
```

## Run locally
Requirements: Node.js 20+

```bash
npm install
npm run web
```

For Android, install Android Studio/SDK and run `npm run android` on a connected device or emulator.

## GitHub Actions
The workflow in `.github/workflows/build-apps.yml` exports the web build and creates an Android debug APK. Open the repository's Actions tab after pushing to inspect build results and download the APK artifact.

## Prototype limitations
Seeded provider information, prices, ratings and distances are demo data, not verified businesses. Listings and reviews are in-memory only and reset on restart. No persistent database, authenticat...
