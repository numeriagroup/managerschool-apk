# Manager School — Android app (WebView)

A native Android wrapper that opens **https://app.managerschool.online/login.php**
full-screen, with back-button navigation, pull-to-refresh, and persistent login
(cookies / local storage). Package id: `online.managerschool.app`.

This folder is a complete, ready-to-build Android Studio / Gradle project.
It is **not** a pre-compiled APK — building the APK requires the Android SDK,
which could not be installed in the environment that generated these files.
Any of the three options below produces an installable `app-debug.apk`.

## Option A — GitHub Actions (no tools to install) ✅ easiest
1. Create a new GitHub repository and upload the contents of this `android/` folder.
2. GitHub runs `.github/workflows/build-apk.yml` automatically on push.
3. Open the run → **Artifacts** → download **ManagerSchool-apk** → unzip →
   you get `app-debug.apk`. Copy it to an Android phone and install
   (allow "install from unknown sources").

## Option B — Android Studio
1. Open this folder in Android Studio (it will download the SDK if needed).
2. **Build ▸ Build Bundle(s) / APK(s) ▸ Build APK(s)**.
3. The APK is at `app/build/outputs/apk/debug/app-debug.apk`.

## Option C — command line
Requires JDK 17 and the Android SDK (set `sdk.dir` in `local.properties`,
see `local.properties.example`).
```
./gradlew assembleDebug
```
APK: `app/build/outputs/apk/debug/app-debug.apk`

## Notes
- `assembleDebug` is signed with the debug key and installs directly on any phone.
- For Google Play you need a **release** build signed with your own keystore.
- iОS cannot be built from this project — see the separate `ios/` folder.
