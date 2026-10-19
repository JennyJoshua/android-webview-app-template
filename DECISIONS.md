# Project Decisions — Android WebView App Template

## Status
Initial decisions approved for implementation.

## D001 — Reusable Android Template
Build a general-purpose Android WebView template that can be
reused for multiple website-to-Android app projects.

Do not build the template around one specific website.

## D002 — Three Website Modes
Support these application modes:

1. Remote website loaded from an HTTPS URL.
2. Website frontend bundled inside the APK.
3. Bundled frontend connected to an online backend or API.

Document the differences and limitations of each mode.

## D003 — Phone-First Development
The owner primarily manages the project using an Android phone,
GitHub, and GitHub Actions.

Do not require Android Studio for routine template configuration,
building, or APK downloading.

## D004 — GitHub Actions Builds
Use GitHub Actions to validate, test, and build the Android APK.

The basic debug-build workflow must not require paid services,
private API keys, or signing secrets.

## D005 — Complete Gradle Wrapper
Commit every required Gradle wrapper file, including:

- gradlew
- gradlew.bat
- gradle/wrapper/gradle-wrapper.properties
- gradle/wrapper/gradle-wrapper.jar

Never assume that phone uploads preserve hidden or nested files.

## D006 — Secure WebView Defaults
Use HTTPS by default.

Do not bypass TLS errors or enable cleartext HTTP by default.
Avoid unsafe file access and unrestricted JavaScript bridges.
Use AndroidX WebKit WebViewAssetLoader for bundled content
where appropriate.

## D007 — Configuration Must Be Documented
Make common customizations straightforward:

- App name
- Application ID
- App icon
- Splash screen
- Website
