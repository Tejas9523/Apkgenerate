# Build an installable Android APK (cloud build)

This is an Android WebView wrapper around the OptionPilot paper-trading app.

## Build APK with GitHub Actions
1. Create a new empty GitHub repository.
2. Upload all files/folders from this project to the repository root.
3. Open the repository's **Actions** tab and allow workflows if GitHub asks.
4. Select **Build OptionPilot APK** → **Run workflow**.
5. When the run completes, open it and download the artifact named **OptionPilot-India-debug-apk**.
6. Extract the artifact ZIP on your Android phone and install `app-debug.apk`. If Android asks, allow installation from that source.

This creates a debug APK for personal testing, not a Play Store release. A release APK should be signed with your own private signing key.

## Important live data note
The app calls the Upstox Option Chain REST endpoint from its WebView. Upstox API access and a valid personal access token are required. Browser/WebView cross-origin restrictions may block direct calls; if that occurs, a secure backend proxy/OAuth flow is required. Do not hardcode a permanent broker token in the APK. No real orders are placed; wallet and trades are simulated locally.
