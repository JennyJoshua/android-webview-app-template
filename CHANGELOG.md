# Changelog

All notable changes to this project will be documented here.

## [Unreleased]

### Added

- `PROJECT_REQUIREMENTS.md` — project requirements and acceptance criteria.
- `DECISIONS.md` — approved initial project decisions (D001-D007) plus implementation choices (D008-D014).
- Complete Android project: Gradle build (AGP 8.5.2, Gradle 8.9), manifest, resources, Java sources.
- Gradle wrapper: `gradlew`, `gradlew.bat`, `gradle-wrapper.properties`, real `gradle-wrapper.jar`.
- `app-config.properties` — app name, application ID, load mode, start URL, allowed hosts,
  external link handling, theme colour, JavaScript/storage/cookie/upload/download switches.
- Three modes: REMOTE, BUNDLED (WebViewAssetLoader) and HYBRID.
- WebView: progress bar, back navigation, network and TLS error screen with retry,
  navigation allow-list (`UrlPolicy`), external link handling, file upload, downloads,
  splash screen, renderer-crash recovery.
- Security defaults: HTTPS only, TLS errors never bypassed, cleartext disabled, no JavaScript
  bridge, file access disabled, mixed content blocked, backups disabled.
- Sample bundled site in `app/src/main/assets/www/`.
- Unit tests for `UrlPolicy`.
- GitHub Actions workflow `android-build.yml`: validate, unit tests, debug APK, artifact upload.
- `scripts/validate-project.sh`.
- Documentation: README, docs/SETUP.md, docs/WEBVIEW_CONFIGURATION.md,
  docs/WEBSITE_IMPORT_GUIDE.md, docs/TROUBLESHOOTING.md.

### Not yet verified

- A real Gradle build, the GitHub Actions run, and installation on an Android device.
  See REVIEW.md for the recorded results.
