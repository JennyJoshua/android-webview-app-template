# Implementation Handover — Android WebView App Template

## 1. Project Identity

Repository:
JennyJoshua/android-webview-app-template

Project type:
Reusable Android WebView application template.

Primary development environment:
GitHub, GitHub Actions, and an Android phone.

Implementation assistant:
Claude or another capable coding assistant.

## 2. Mission

Implement a complete, reusable Android application template for
packaging websites and web frontends into installable Android APKs.

The project must be reusable for future applications without
rewriting the Android infrastructure for every new project.

Read these documents before implementing:

- PROJECT_REQUIREMENTS.md
- DECISIONS.md
- CHANGELOG.md
- REVIEW.md

These documents define the requirements, approved decisions,
change history, and verification checklist.

## 3. Required Website Modes

### Mode A — Remote Website

Load a configurable HTTPS website inside Android WebView.

### Mode B — Bundled Website

Package HTML, CSS, JavaScript, images, and other frontend assets
inside the APK.

Use AndroidX WebKit WebViewAssetLoader where appropriate.

### Mode C — Hybrid Website

Bundle the frontend inside the APK while connecting to an online
backend, API, authentication service, or database.

Explain that bundling the frontend does not bundle the backend.

Implement these modes with a clear, documented configuration
mechanism.

## 4. Implementation Status (added 2026-10-20)

Implemented: Android project, Gradle build and wrapper, three modes configured through
`app-config.properties`, WebView behaviour and security defaults, sample bundled site,
unit tests, `Android CI` workflow, and all documents listed in PROJECT_REQUIREMENTS.md section 8.

Verified so far (authoring sandbox only): required-file validation, XML well-formedness, workflow YAML
parses, and `UrlPolicyTest` (11/11) run on a plain JVM with JUnit stand-ins.

NOT yet verified: Gradle build, GitHub Actions run, APK install on a device. The sandbox had no Android SDK and
could not reach Gradle or Google Maven. `MainActivity.java`, `AppConfig.java`, the Gradle scripts and the
resources have never been compiled.

Next steps for whoever continues:
1. Upload the project, run **Android CI**, and read REVIEW.md section 8.
2. If a job fails, fix the first error in the log; do not rewrite completed files.
3. Install the APK on a device and tick the REVIEW.md checklists with real results.
4. Delete the old extension-less `PROJECT_REQUIREMENTS` file.
