# iOS 27-style Launcher for Pixel 7a

An Android Studio starter project for Android 16. It is an original launcher implementation inspired by the visual language of recent iOS versions; it is not Apple's iOS and does not include Apple's proprietary assets.

## Included
- Home screen with a 4-column app grid
- Dock with detected Phone, Messages, Chrome and Camera apps
- App drawer and app search
- Original installed Android app icons and labels (loaded from PackageManager)
- Soft gradient background and translucent dock
- HOME intent so Android can offer it as the default launcher

## Build
1. Install Android Studio with Android SDK Platform 36 and JDK 17.
2. Open this folder in Android Studio.
3. Let Gradle sync.
4. Choose **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
5. Install the generated debug APK on the Pixel 7a.
6. Press Home and choose **iOS 27 Launcher**, then select **Always** if you want it as default.

Alternatively, from a terminal with Android SDK configured:
```bash
./gradlew assembleDebug
```
The APK is generated at `app/build/outputs/apk/debug/app-debug.apk`.

## Notes and limitations
- This is a starter implementation, not a complete iOS clone.
- Android's system navigation, notifications, quick settings, lock screen, permission dialogs and recent-apps screen remain controlled by Android. A normal third-party launcher cannot replace all of these.
- The status/navigation bars are left to Android's system UI. This project does not request sensitive permissions.
- The app list is limited to launcher activities visible through Android package visibility.
- The sample uses a generated gradient background and does not change the device wallpaper.
- Before publishing, update the application ID, app icon, screenshots, accessibility labels and test on-device.


## Build APK using only an Android phone (GitHub Actions)
1. In your phone browser, sign in to GitHub and create a **new public or private repository**.
2. Upload the contents of this project ZIP to the repository. Make sure the `.github/workflows/android.yml` file is included (some mobile file pickers hide dot-folders; if so, create that file in GitHub using **Add file > Create new file** and paste its contents from this project).
3. Open the repository's **Actions** tab. If GitHub asks, enable Actions.
4. Select **Build Android APK** and tap **Run workflow** (or push/upload the files to the `main` branch to trigger it).
5. When the run finishes with a green check, open that run, scroll to **Artifacts**, and download `iOS27PixelLauncher-debug`.
6. Extract the downloaded artifact ZIP on your phone. Tap `app-debug.apk` and approve Android's install prompt if asked.

The APK is a debug build for testing. It is not signed for Play Store release.
