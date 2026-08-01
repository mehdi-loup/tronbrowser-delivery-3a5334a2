# Native iOS/Android App Delivery — app 3a5334a2
Evidence repo for the ugig application `3a5334a2` on gig `dbe8e98a` ("I need native ios and/or a native android app builder").

## Surveyed source repo
- https://github.com/profullstack/tronbrowser.dev
- Relevant paths: `apps/mobile`, `apps/android-engine`, `packages/sdk`, `packages/shared`, `docs/mobile-architecture.md`

## Current state
- `apps/mobile`: Expo/React Native scaffold (`App.tsx`, `app.json`, `metro.config.js`, etc.).
- `apps/android-engine`: README stub; no populated Chromium subtree.
- No Swift/Kotlin native iOS/Android apps present in the repo.

## Deliverable
A build plan for native iOS/Android wrappers around the existing browser core:
1. **iOS**: SwiftUI shell with a local engine bridge to `browser-core` via WebView/FFI or local HTTP.
2. **Android**: Kotlin/Jetpack Compose shell reusing `apps/android-engine`, sharing `packages/sdk` APIs.
3. **Shared**: typed clients from `packages/sdk` and `packages/shared` for both shells.
4. **CI**: GitHub Actions matrix for iOS/Android build verification.

## Suggested first PRs
- `ios/` scaffold with Swift Package template and bridge client.
- `android/` scaffold under `apps/android-engine` with Gradle module and `MainActivity`.
- README steps to build from a clean checkout.
