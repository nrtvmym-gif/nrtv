# Build NRTV APK in the cloud with GitHub Actions

1. Create a GitHub account if you do not already have one.
2. Create a new repository named `NRTVLiveBroadcaster`.
3. Upload the **contents** of this project folder to the repository root (so `settings.gradle`, `build.gradle`, `app/`, and `.github/` are at the repository root).
4. Open the repository's **Actions** tab.
5. Select **Build NRTV APK** and press **Run workflow**. A push to the `main` branch also starts a build.
6. Open the completed workflow run. Under **Artifacts**, download `NRTV-Live-Broadcaster-debug-apk`.
7. Extract the downloaded artifact ZIP. Install `app-debug.apk` on your Android phone. Allow installation from that source if Android asks.

This workflow builds a **debug APK** for testing, not a signed Play Store release. The first build needs internet access to download Android/Gradle dependencies. A successful cloud build does not replace testing on the target phone. The current starter project README also notes that RootEncoder API integration, watermark behavior, and device-specific 4K support must be tested; streaming is stopped when the activity is backgrounded in this starter.
