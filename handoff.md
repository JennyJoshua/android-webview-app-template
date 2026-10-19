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
