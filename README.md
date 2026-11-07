# NRTV Live Broadcaster

Android Studio project for an RTMP/RTMPS mobile camera broadcaster.

## Features in this starter project
- Minimum Android 8.0 (API 26)
- RTMP and RTMPS destination URL + stream key
- Camera preview and front/rear camera switch
- 4K / 1080p / 720p resolution selection (hardware-dependent)
- Adjustable video bitrate (0.5–25 Mbps)
- Custom logo picker and outgoing GL watermark filter
- Camera and microphone runtime permissions
- Connection status callbacks

## Build APK
1. Install Android Studio (recent stable release) and Android SDK Platform 35.
2. Open this folder (`NRTVLiveBroadcaster`) in Android Studio.
3. Allow Gradle sync. Internet is needed on the first sync to download Android Gradle Plugin and RootEncoder 2.8.1 from JitPack.
4. Select **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
5. Debug APK output: `app/build/outputs/apk/debug/app-debug.apk`.

Command line from this folder (after installing Android SDK and Gradle):

```bash
gradle assembleDebug
```

## RTMP destination format
For a server that expects an application path and key, enter the base URL in **RTMP/RTMPS URL** and the stream key separately. Example:
- URL: `rtmp://YOUR-FLUSSONIC-HOST:1935/live`
- Key: `camera01`

The app joins them as `rtmp://YOUR-FLUSSONIC-HOST:1935/live/camera01`. Follow the exact publish URL format configured on your media server.

## Important device notes
- A 4K menu option does not guarantee 4K capture. The phone must expose a 3840x2160 camera stream and have a compatible hardware encoder. If preparation fails, choose 1080p or 720p.
- Sustained 4K streaming can overheat phones and requires substantial, stable upload bandwidth.
- RTMPS requires a server with a valid TLS certificate. Cleartext RTMP is permitted in this starter so local/private RTMP servers can be tested; use RTMPS on public networks.
- The stream is stopped when the activity is backgrounded in this starter. A production release should add a foreground service with persistent notification for reliable background operation.
- Test the exact RootEncoder 2.8.1 API integration and logo filter on your target handset before production deployment.

## Dependencies and license
RootEncoder 2.8.1 is an external Apache-2.0 library: https://github.com/pedroSG94/RootEncoder
Keep its license notice when distributing the app.
