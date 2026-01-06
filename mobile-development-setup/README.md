📱 Expo Go: Mobile Development Setup

Version: SDK 50+ Compatible

Expo Go is a lightweight sandbox environment that enables developers to preview React Native applications instantly on a physical mobile device. It eliminates the need for heavy platform-specific tools such as Android Studio or Xcode, especially during early-stage development.

🔧 Installation & Launch
1️⃣ Download the Client

Search for “Expo Go” on:

Google Play Store (Android)

Apple App Store (iOS)

2️⃣ Environment Sync

Connect your mobile device and development computer to the same Wi-Fi network.

3️⃣ Initiate Development Server

Run the following command in your project directory:

npx expo start

4️⃣ Bridge the Connection

Android
Open Expo Go → Tap Scan QR Code

iOS
Open the Camera app → Scan QR code → Tap “Open in Expo Go”

⚠️ Common Hurdles & Fixes
Challenge Technical Cause Permanent Solution
Connection Timeout Network isolation or firewall restrictions Ensure both devices are on the same subnet. Use npx expo start --tunnel if Wi-Fi is restricted
App Not Found Expired build or mismatched account Log into the same Expo account on both CLI and Expo Go
Bundling Hangs Large dependency tree or corrupted cache Clear cache with npx expo start -c
QR Scan Fails Camera permission or poor lighting Manually open the exp:// link or use Internal Distribution
✅ Refined Best Practices
🔗 Persistent Connectivity

If operating behind strict firewalls (common in offices or universities), use:

npx expo start --tunnel

This generates a secure URL accessible across different networks.

🔐 System Permissions

Ensure Local Network access is enabled for Expo Go

Especially required on iOS 14+

📦 Dependency Health

If the app crashes on launch:

npx expo install --check

This ensures all libraries match the active Expo SDK version.

🛠️ Automated Recovery

Press r in the terminal to reload the app

Press d to open the developer menu for advanced debugging

📝 Summary

Expo Go offers a fast, cost-effective, and platform-agnostic way to test React Native apps on real devices. Proper network configuration, permission handling, and dependency management are key to a smooth development experience.

🧪 Expo Project Scaffolding & Reset Documentation
📁 Project Setup Overview

This section documents the steps followed to scaffold an Expo project using Expo Router and the behavior observed when resetting the project using the provided reset script.

🚀 Project Scaffolding Steps
1️⃣ Navigate to Project Directory

In the terminal, navigated to the parent project folder:

cd prodev-mobile-setup

2️⃣ Initialize Expo Project

A new Expo project was initialized using the latest Expo Router template:

npx create-expo-app@latest .

This generated the default project structure, including the /app directory required by Expo Router.

🏠 Modify the Home Screen

Open the file:

app/(tabs)/index.tsx

Locate the default text:

Welcome!

Update it to:

First App Created

This confirms successful modification of the main screen.

▶️ Run and Test the Application

Start the Expo development server:

npx expo start

Device Testing

iOS: Scan the QR code using the device’s Camera app

Android: Scan the QR code using the Expo Go app

The application loaded successfully on a physical device, reflecting the updated text.

🔄 Resetting the Application

The project reset command was executed:

npm run reset-project

Prompt Response

When prompted:

Do you want to move existing files to /app-example instead of deleting them? (Y/n): y

The option Yes (y) was selected to preserve existing files.

📌 Observations from reset-project

The reset script performed the following actions:

📁 Created a backup directory: /app-example

📦 Moved existing folders:

/app → /app-example/app

/components → /app-example/components

/hooks → /app-example/hooks

/constants → /app-example/constants

/scripts → /app-example/scripts

🆕 Generated a fresh /app directory

📄 Created new routing files:

app/index.tsx

app/\_layout.tsx

Console Confirmation
✅ Project reset complete.

🧠 Key Takeaways

The reset process does not delete files immediately; instead, it safely archives them in /app-example.

A clean Expo Router structure is recreated automatically.

This command is useful for:

Starting fresh development

Debugging corrupted routing setups

Learning default Expo Router file generation

🔔 The /app-example directory can be safely deleted once it is no longer needed for reference.

✅ Conclusion

The Expo scaffolding and reset workflow provides a safe and efficient way to initialize, modify, and recover a React Native project. Proper documentation of these steps ensures reproducibility and easier troubleshooting during development.
