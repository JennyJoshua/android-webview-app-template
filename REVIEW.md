# Project Review and Quality Checklist

## 1. Current Status

Status: Builds in GitHub Actions and installs on the owner's Android phone. WebView behaviour
(page loading, back button, error screen, bundled mode) has not been checked item by item yet.

Nothing below is ticked unless it was actually checked or reported by the owner.

## 2. Repository Structure

- [x] All required Android source files are present. (scripts/validate-project.sh)
- [x] Root Gradle configuration is present.
- [x] settings.gradle.kts is present.
- [x] App-level Gradle configuration is present.
- [x] gradlew and gradlew.bat are present.
- [x] Gradle wrapper properties are present.
- [x] Gradle wrapper JAR is present (43,504-byte genuine JAR from the Gradle 8.9.0 source tag, valid ZIP).
- [x] AndroidManifest.xml is present.
- [x] Required resources and assets are present.

## 3. WebView Functionality

- [ ] Remote HTTPS website mode works.
- [ ] Bundled website mode works.
- [ ] Hybrid frontend and backend mode is documented and tested. (documented; not tested)
- [ ] Loading progress is displayed appropriately.
- [ ] Android back navigation works.
- [ ] Network errors are handled.
- [ ] Navigation restrictions work as documented. (policy logic unit-tested on a JVM only; not on a device)
- [ ] Login and redirect behaviour is checked.
- [ ] Cookies and storage work where required.
- [ ] File uploads and downloads are tested where supported.
- [ ] External links are handled appropriately.

## 4. Security Review

- [x] HTTPS is the default (build fails for non-https START_URL in REMOTE mode).
- [x] TLS certificate errors are not bypassed (code review: handler.cancel()).
- [x] Cleartext HTTP is disabled by default (manifest + network security config).
- [x] Unsafe local-file access is avoided (code review).
- [x] JavaScript bridges are not unnecessarily exposed (none registered).
- [ ] Allowed-host restrictions are reviewed by the owner.
- [x] Secrets are not committed to the repository (validate script scan).
- [ ] Third-party licences are reviewed. (Dependencies are AndroidX, Apache-2.0; gradle-wrapper.jar is Apache-2.0. Owner review pending.)

## 5. GitHub Actions

- [x] Project validation workflow passes. (Android CI green on 2026-10-20 after the Kotlin BOM fix)
- [x] Automated tests pass. (the unit-test job is a prerequisite of the build job, which succeeded)
- [x] Debug APK builds successfully. (Android CI run after the fix)
- [x] Build failures are reported clearly. (observed on run 1: failing Gradle task and error text visible, failure summary step ran)
- [x] APK artifact is uploaded successfully. (upload step fails the run if no APK exists)
- [x] APK can be downloaded from the workflow run. (owner downloaded and installed it)

## 6. Android Device Testing

- [x] APK installs on a compatible Android device. (owner's phone; device model and Android version not recorded)
- [ ] App launches successfully.
- [ ] Website loading is verified.
- [ ] Navigation is verified.
- [ ] Error handling is verified.
- [ ] No critical crashes are observed.

## 7. Documentation

- [x] README.md is complete.
- [x] PROJECT_REQUIREMENTS.md matches the implementation.
- [x] DECISIONS.md reflects approved decisions.
- [x] CHANGELOG.md records notable changes.
- [ ] Setup instructions are tested.
- [ ] Website import instructions are tested.
- [x] Troubleshooting instructions are written.
- [x] Known limitations are documented.

## 8. Review Results

Date: 2026-10-20
Reviewer: Claude (sandbox checks and CI logs) plus owner device report
Build workflow URL: not recorded
Build result:
- Run 1 (2026-10-19) FAILED at :app:checkDebugDuplicateClasses (Kotlin stdlib 1.8.22 vs 1.6.21 conflict).
  Fixed by adding the kotlin-bom 1.8.22 platform dependency.
- Run after the fix: SUCCESS (reported by owner): validate, unit tests, debug APK build and artifact upload.
- gradle/actions confirmed the wrapper JAR is a known valid one (SHA-256 498495120a03...4f17).
Automated test result: unit-test job passed in CI (11 UrlPolicyTest cases; also run on a plain JVM during authoring).
Android installation result: APK installed on the owner's phone and was reported as working.

Not yet verified on a device: website loading in REMOTE mode, back navigation, network error screen,
bundled mode, file upload/download, login redirects, external link handling.

Issues found:
- Kotlin stdlib duplicate-class conflict (fixed).

Required fixes:
- None known. Complete the device checks in sections 3 and 6, then decide on release.

## 9. Release Decision

- [ ] All required acceptance criteria are satisfied.
- [ ] Critical security issues are resolved.
- [ ] Documentation is complete.
- [ ] A successful debug APK is available.

Release status: Not yet approved.
