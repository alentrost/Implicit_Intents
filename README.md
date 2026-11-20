# Implicit Intents

An Android application developed in Java demonstrating how to handle implicit intents for performing external system actions such as launching web pages, viewing geographic locations on a map, sharing text to other applications, and launching the phone dialer.

## Overview

This project was built following the Android Developer Fundamentals guidelines for working with implicit intents. It provides an intuitive user interface with entry fields and action buttons to trigger various implicit intent actions.

## Features

- **Open Website**: Parses a web URL and launches the device default browser using `Intent.ACTION_VIEW`.
- **Open Location**: Takes a geographic query string and opens a map application using the `geo:0,0?q=` URI format and `Intent.ACTION_VIEW`.
- **Share Text**: Uses `ShareCompat.IntentBuilder` to open the system share sheet with `text/plain` content.
- **Dial Phone Number**: Takes a phone number and opens the system dialer with `Intent.ACTION_DIAL` and a `tel:` URI.

## Requirements

- Android Studio Jellyfish or newer
- JDK 11 or higher
- Android SDK (Compile SDK 37, Min SDK 24, Target SDK 37)

## Project Structure

```
app/
├── src/
│   └── main/
│       ├── java/com/example/implicit_intents/
│       │   └── MainActivity.java       # Activity with intent handling logic
│       ├── res/
│       │   ├── layout/activity_main.xml # Vertical LinearLayout with fields and buttons
│       │   └── values/strings.xml      # String resources for labels and defaults
│       └── AndroidManifest.xml          # Includes <queries> for API 30+ intent resolution
└── build.gradle.kts                     # Module build configuration
```

## How to Build

### Debug Build

To assemble the debug APK, run the following command in the project root:

```bash
./gradlew assembleDebug
```

The output APK will be generated at:
`app/build/outputs/apk/debug/app-debug.apk`

### Release Build

To assemble an unsigned release APK, run:

```bash
./gradlew assembleRelease
```

The output APK will be generated at:
`app/build/outputs/apk/release/app-release-unsigned.apk`

## APK Release and Installation

To install the build onto a connected device or emulator via ADB:

```bash
adb install app/build/outputs/apk/debug/app-debug.apk
```

For production deployment, sign the unsigned release APK using `apksigner` or configure signing details inside `app/build.gradle.kts`.
