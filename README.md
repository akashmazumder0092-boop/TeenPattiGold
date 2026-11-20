# Teen Patti Gold — online score-only Android project

This is an original starter project for a friendly, non-wagering multiplayer card game.
It does not include betting, purchasable chips, cash prizes, transfers or withdrawals.

## Project contents
- `app/`: Android app written in Kotlin + Jetpack Compose
- `server/`: Node.js WebSocket room server
- Rooms support up to six players. A deal sends three private cards to each player.

## Run the online server
1. Install Node.js 18 or newer.
2. In a terminal: `cd server`
3. Run `npm install`
4. Run `npm start`
5. Keep TCP port 8080 reachable by the Android devices.

## Connect Android app
- Android emulator: default `ws://10.0.2.2:8080` points to the host computer.
- Physical phones: edit `SERVER_URL` in `MainActivity.kt` to your server's reachable `ws://` or preferably `wss://` address.
- For internet release, deploy the server behind TLS (WSS), add authentication, rate limits, abuse reporting, moderation, persistent room state and secure server-side game validation. Do not expose an unencrypted public WebSocket server.

## Build APK
1. Open this folder in Android Studio (Giraffe or newer).
2. Allow Gradle to sync dependencies.
3. Build > Build Bundle(s) / APK(s) > Build APK(s).
4. The debug APK is normally at `app/build/outputs/apk/debug/app-debug.apk`.

## Current prototype limitations
- This is a runnable starter, not a production-ready Play Store release.
- The server currently deals cards but does not yet implement full hand ranking, turn order, reconnection, accounts, persistence, or anti-cheat.
- Configure a real hosted WSS endpoint before testing over the public internet.
- Use original branding and artwork; do not reuse assets or proprietary code from other games.
