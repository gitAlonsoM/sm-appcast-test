# Sleeman Appcast Feed Manager

This repository hosts the remote XML appcast feeds for the **Sleeman Fridge** mobile application. These files are used to trigger proactive update notifications for both Android and iOS platforms.

## Core Functionality
The application utilizes the `upgrader` package in Flutter to fetch these XML files. By comparing the installed version of the app with the `sparkle:version` defined in these feeds, the app decides whether to prompt the user for an update.

---

## How to Update App Versions

To release a new update notification, follow these steps:

### 1. Locate the Target File
* **Android:** `appcast_android.xml`
* **iOS:** `appcast_ios.xml`

### 2. Edit Metadata
Open the file and modify the following key fields:
* **`<title>`**: Update the text to reflect the new version (e.g., `Version 41.0.0`).
* **`sparkle:version`**: This is the most critical field. The app uses this string for version comparison (e.g., `"41.0.0"`).
* **`enclosure url`**: Ensure this link points to the correct Store URL (Google Play Store or Apple App Store).
* **`<description>`**: (Optional) Add brief release notes that will appear in the update modal if enabled.

### 3. Commit Changes
Once edited, commit the changes directly to the `main` branch.

---

## Generating the Public Link (The "Raw" Method)

The Flutter application is configured to consult a specific permanent URL. If you ever need to retrieve or verify the public link for the appcast feed, use the following procedure:

1.  Navigate to the desired file (`.xml`) in the GitHub web interface.
2.  Click on the **"Raw"** button located at the top-right of the file editor/viewer.
3.  The browser will redirect to a plain-text version of the file on the `raw.githubusercontent.com` domain.
4.  **Copy the URL** from your browser's address bar. 

**Current Production Links:**
* **Android:** `https://raw.githubusercontent.com/gitAlonsoM/sm-appcast-test/refs/heads/main/appcast_android.xml`
* **iOS:** `https://raw.githubusercontent.com/gitAlonsoM/sm-appcast-test/refs/heads/main/appcast_ios.xml`

---

## Environment & References
* **Platform:** Flutter (Android & iOS)
* **Dependency:** `upgrader` package
* **Hosting:** GitHub Public Repository
