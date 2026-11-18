# OPSC Tracker – Android project

This repository contains the Android Studio project and the web-based tracker bundled in the Android app.

## Build an installable APK

1. Open this repository on GitHub.
2. Select **Actions** → **Build OPSC Tracker APK** → **Run workflow** (or push a commit to trigger a build).
3. Open the completed workflow run and download the **OPSC-Tracker-Android-APK** artifact.
4. Extract `app-debug.apk` on your Android phone and install it. Android may ask you to allow installation from that source.

Alternatively, open the `android/` folder in Android Studio and build the `app` debug APK.

## Data safety

- The existing Philosophy optional syllabus and all supplied syllabus topics are retained unchanged.
- WebView DOM storage is enabled, so the existing tracker data remains in the app's local storage across app updates using the same application ID.
- The Progress tab includes **Export backup** and **Import backup**. Export a JSON backup before uninstalling the old app or changing devices. Uninstalling an app can erase its local data.

## Focus / Do Not Disturb

The native focus bridge requests Android Notification Policy Access only when the user starts focus. During focus it sets Priority DND to allow alarms and calls from starred contacts, and restores the previous interruption filter and priority policy when focus ends. If the app is force-stopped or the process is killed during focus, the saved prior DND state is restored on the next launch.

Android does not expose selective per-app notification blocking through DND alone. This build does **not** claim to silence only selected apps; that requires an additional notification-listener feature and a separate user-granted permission. Emergency calling behavior and OEM-specific DND behavior should be tested on the target phone.

## Package

Application ID: `com.opsc.tracker`  
Version: `2.0`  
Minimum Android: 8.0 (API 26)
