# JobMaster AI Android (WebView shell)

Package `com.jobmaster.ai` · Version 3.0.0 · minSdk 26 · targetSdk 35

## CI Build (recommended)

The root workflow `.github/workflows/android.yml` builds the debug APK on every push that touches `android/` and on manual dispatch.

**Part XXV proof artifacts produced by CI:**
1. Full Gradle build log ending in success
2. SHA-256 of the APK (printed in the job log)
3. Downloadable APK artifact (`jobmaster-ai-debug-apk`)
4. After download: `adb install app-debug.apk` (exit 0) + cold-start screenshot

## Local build (requires Android SDK)

```bash
cd android
# ensure local.properties has sdk.dir=...
gradle wrapper --gradle-version 8.9   # if gradlew missing
./gradlew assembleDebug
# APK → app/build/outputs/apk/debug/app-debug.apk
```

## Configuration
Edit `MainActivity.kt` → `BASE_URL` to point at the deployed clean `index.html` (Vercel or GitHub Pages).
