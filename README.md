# LocalStream ⚡

**LocalStream** is a high-performance, elegant, and secure local area network (LAN) media streaming and file-sharing ecosystem. It consists of a modern Jetpack Compose Android controller app and an authorized Tailwind-styled web dashboard. It allows you to transform your Android device into a powerful local server to stream videos, download files, and manage media across any browser, curl, or wget client on your local Wi-Fi network.

---

## 📸 Key Features

### 📱 Android Administrator App
- **High-Performance HTTP Web Server**: Serve video and media assets with support for content-range streaming (perfect for scrubbing long video/audio files).
- **Comprehensive User Access Control**: Toggle authentication requirements and manage custom authorized users with credentials.
- **Advanced App Lock**: Secure the Android controller interface with a PIN passcode (default `1234` or custom-configured PIN) to block unauthorized administrative actions.
- **Live Active Session Hub**: Real-time overview of active web browser clients including:
  - Username
  - IP Address
  - Browser User-Agent details
  - Login timestamp
  - **Instant Disconnect/Revocation**: Remotely terminate and log out any specific client session with a single tap.

### 🌐 Authorized Web Dashboard (Desktop/Mobile Web)
- **Cinematic Dark Slate & Emerald UI**: Beautifully designed responsive web panel using Tailwind CSS.
- **Media Library**: Live video streaming, file searching, filtering, and media playback control.
- **Dynamic Playlists Manager**: Create playlists, append items in a customized queue, and enjoy sequential media playing.
- **Connected Clients Pane**: Users can view all active sessions currently signed in, highlight their current browser as "You", and log out secondary or old devices securely.
- **Secure Web Authentication**: Fully integrated credential validation page mapped dynamically with the Android User Database.

---

## 🛠️ Architecture & Tech Stack

- **Frontend Core**: Jetpack Compose (Kotlin), Material Design 3 guidelines.
- **Theme & Design**: Custom *Slate & Emerald* high-contrast visual identity.
- **Local Persistence**: SQLite database via Jetpack **Room** to store media information, custom users, settings, and playback state.
- **Web Server Engine**: Optimized Java/Kotlin `HttpServer` supporting chunked requests and partial content ranges.
- **Web Technologies**: Vanilla HTML5, Tailwind CSS, Javascript Fetch API, HTML5 Video Controller, and Session Cookies.

---

## 🚀 How to Run & Use LocalStream

### 1. Launching the Server
1. Open the **LocalStream** app on your Android device.
2. Select your desired server port (Default: `8080`) and toggle **Start Server**.
3. The app will automatically show your device's active local IP address (e.g., `http://192.168.1.50:8080`).

### 2. Setting Up Security & Users
1. By default, **User Authentication** is disabled for quick LAN access. To secure your media, turn on the **Require Web Authentication** switch in the Android settings card.
2. Add custom authorized users by typing a username and password in the **Authorized Users** card.
3. Access the web dashboard on any device connected to the same Wi-Fi network by browsing to the displayed URL.
4. Input the configured credentials to enter the dashboard.

### 3. Securing the Controller (App Lock)
1. Turn on the **Android App Lock** toggle in the App Settings panel.
2. Define a custom PIN code or use the default `1234`.
3. When the app is closed and reopened (or locked manually), administrators must enter this PIN to gain access to port controls, user management, and session logs.

### 4. Managing Active Clients
- Inside the Android app under **Active Connected Web Sessions**, monitor any device connected to your stream.
- Click the red **Block/Disconnect icon** to immediately invalidate their session token, forcing the client browser to sign in again.
- In the Web Dashboard, go to the **🔒 Connected Users** tab to review all active logins on other devices and sign out secondary computers or browsers with ease.

---

## 🧪 Development and Verification

To verify that the application compiles perfectly, runs unit tests, and maintains stable build outputs, execute standard Gradle commands:

- **Check Compilation**:
  ```bash
  gradle compileDebugKotlin
  ```
- **Run JVM Unit Tests**:
  ```bash
  gradle :app:testDebugUnitTest
  ```
- **Generate Debug APK**:
  ```bash
  gradle assembleDebug
  ```

---

*LocalStream • Secure, lightweight, and visual media streaming for your private local network.*
