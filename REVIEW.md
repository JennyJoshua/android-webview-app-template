# Project Review and Quality Checklist

## 1. Current Status

Status: Documentation and planning in progress.

No Android build or installation tests are claimed as passed
until the corresponding tests have actually been performed.

## 2. Repository Structure

- [ ] All required Android source files are present.
- [ ] Root Gradle configuration is present.
- [ ] settings.gradle.kts is present.
- [ ] App-level Gradle configuration is present.
- [ ] gradlew and gradlew.bat are present.
- [ ] Gradle wrapper properties are present.
- [ ] Gradle wrapper JAR is present.
- [ ] AndroidManifest.xml is present.
- [ ] Required resources and assets are present.

## 3. WebView Functionality

- [ ] Remote HTTPS website mode works.
- [ ] Bundled website mode works.
- [ ] Hybrid frontend and backend mode is documented and tested.
- [ ] Loading progress is displayed appropriately.
- [ ] Android back navigation works.
- [ ] Network errors are handled.
- [ ] Navigation restrictions work as documented.
- [ ] Login and redirect behaviour is checked.
- [ ] Cookies and storage work where required.
- [ ] File uploads and downloads are tested where supported.
- [ ] External links are handled appropriately.

## 4. Security Review

- [ ] HTTPS is the default.
- [ ] TLS certificate errors are not bypassed.
- [ ] Cleartext HTTP is disabled by default.
- [ ] Unsafe local-file access is avoided.
- [ ] JavaScript bridges are not unnecessarily exposed.
- [ ] Allowed-host restrictions are reviewed.
- [ ] Secrets are not committed to the repository.
- [ ] Third-party licences are reviewed.

## 5. GitHub Actions

- [ ] Project validation workflow passes.
- [ ] Automated tests pass.
- [ ] Debug APK builds successfully.
- [ ] Build failures are reported clearly.
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

- [ ] README.md is complete.
- [ ] PROJECT_REQUIREMENTS.md matches the implementation.
- [ ] DECISIONS.md reflects approved decisions.
- [ ] CHANGELOG.md records notable changes.
- [ ] Setup instructions are tested.
- [ ] Website import instructions are tested.
- [ ] Troubleshooting instructions are useful.
- [ ] Known limitations are documented.

## 8. Review Results

Date:
Reviewer:
Build workflow URL:
Build result: Not yet tested.
Automated test result: Not yet tested.
Android installation result: Not yet tested.

Issues found:
Pending.

Required fixes:
Pending.

## 9. Release Decision

- [ ] All required acceptance criteria are satisfied.
- [ ] Critical security issues are resolved.
- [ ] Documentation is complete.
- [ ] A successful debug APK is available.

Release status: Not yet approved.
