# Project Review and Quality Checklist

## 1. Current Status

Status: Implementation written. Partially verified in a sandbox that could NOT run Gradle
(no Android SDK; services.gradle.org and Google Maven were unreachable).

Nothing below is ticked unless it was actually checked. The Gradle build, the GitHub Actions
run and the device tests have NOT been performed yet.

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

- [ ] Project validation workflow passes. (script passes locally; workflow not run)
- [ ] Automated tests pass. (see section 8)
- [ ] Debug APK builds successfully.
- [ ] Build failures are reported clearly. (step summaries and test-report artifact are configured; not exercised)
- [ ] APK artifact is uploaded successfully.
- [ ] APK can be downloaded from the workflow run.

## 6. Android Device Testing

- [ ] APK installs on a compatible Android device.
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
Reviewer: Claude (sandbox checks only; no human or device review yet)
Build workflow URL: none recorded
Build result: Run 1 (2026-10-19) FAILED at :app:checkDebugDuplicateClasses (Kotlin stdlib version conflict). Fix applied (kotlin-bom 1.8.22); re-run pending. In that run gradle/actions confirmed the Gradle wrapper JAR is a known, valid one (SHA-256 498495120a03...4f17). Java compilation was not reached.
Automated test result: UrlPolicyTest, 11 of 11 tests passed when compiled with javac 21 against
minimal JUnit stand-ins and run directly on a JVM. This is NOT a Gradle/JUnit run.
Other local checks: validate-project.sh passed; all XML files are well-formed; workflow YAML parses.
Android installation result: NOT TESTED.

Not compiled anywhere yet: MainActivity.java, AppConfig.java, the Gradle scripts and the
resources (they need the Android SDK and AndroidX libraries).

Issues found:
- Pending the first real GitHub Actions run.

Required fixes:
- Pending. Expect that the first CI run may reveal compile or Gradle errors; paste the log to get them fixed.

## 9. Release Decision

- [ ] All required acceptance criteria are satisfied.
- [ ] Critical security issues are resolved.
- [ ] Documentation is complete.
- [ ] A successful debug APK is available.

Release status: Not yet approved.
