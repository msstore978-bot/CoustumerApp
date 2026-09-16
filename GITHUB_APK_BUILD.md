# Shipon Store Android App — GitHub APK Build

## Upload
Upload the CONTENTS of this project folder to the ROOT of a GitHub repository.
Do not create an extra `ShiponStoreApp/ShiponStoreApp/` nesting.

The repository root should contain:
- `.github/workflows/build-apk.yml`
- `app/`
- `gradle/`
- `build.gradle.kts`
- `settings.gradle.kts`

## Build
1. Open GitHub repository.
2. Open **Actions**.
3. Select **Build Android APK** / **Build Debug APK** workflow.
4. Click **Run workflow**.
5. Wait for the job to finish.
6. Open the successful run.
7. Under **Artifacts**, download `ShiponStore-debug-apk`.
8. Extract it and install `app-debug.apk` on Android.

## Important
This workflow uses Gradle 8.7 directly, so the repository does not need a working Gradle wrapper JAR.
JDK 17 is used for the Android Gradle Plugin configuration in this project.


## Build-fix note
This version migrates Room annotation processing from KAPT to KSP. Kotlin 1.9.24 is paired with KSP 1.9.24-1.0.20. Room 2.6.1 supports KSP.
