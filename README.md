ContactManagerApp

A React Native Contact Manager App that allows users to create, view, favorite, and manage contacts.
This project was developed as part of CPAN-213 (Cross-Platform Mobile App Development).

🚀 Features

Add new contacts with name, phone number, email, and company

Mark/unmark contacts as favorites

Search contacts by name, company, or email

View detailed contact information

Call or send SMS directly from the app

Accessibility labels for screen readers

Loading spinner and pull-to-refresh support

🛠️ Tech Stack

React Native 0.82.0

React Navigation (stack navigation)

Context API for global state management

react-native-vector-icons for icons

Xcode / iOS Simulator for development and testing

⚡ Challenges Faced & Solutions

Android Build Error

Initial development targeted Android Emulator.

Faced persistent error:

> Task :app:configureCMakeDebug[arm64-v8a] FAILED


Tried multiple clean builds, fresh installs, and professor’s help — error persisted.

✅ Solution: Restarted the project from scratch using Xcode and focused on iOS. This approach worked smoothly.

iOS Pod Issues

After copying ios/ folder from a temporary project (TempApp), pod install failed because the Podfile target name didn’t match.

✅ Solution: Updated Podfile target to match the project name (ContactManagerApp) and re-ran:

cd ios
pod install --repo-update
cd ..

📂 Project Structure
ContactManagerApp/
 ├── android/                  # Android project (not functional due to build error)
 ├── ios/                      # iOS project (functional)
 │   ├── ContactManagerApp.xcworkspace
 │   ├── Podfile
 │   └── Pods/
 ├── src/
 │   ├── components/           # Reusable UI components
 │   ├── screens/              # App screens (ContactList, AddContact, etc.)
 │   ├── styles/               # Global styles
 │   ├── data/                 # Dummy contacts & helpers
 │   └── utils/                # Context API, hooks
 ├── App.js / App.tsx          # Entry point
 ├── package.json
 └── README.md

▶️ How to Run
1. Clone the Repository
git clone https://github.com/<your-username>/ContactManagerApp.git
cd ContactManagerApp

2. Install Dependencies
npm install

3. iOS Setup (Preferred)
cd ios
pod install --repo-update
cd ..
npx react-native run-ios

4. Android Setup (Not functional due to CMake issue)

If you want to try:

npx react-native run-android


⚠️ May fail with configureCMakeDebug[arm64-v8a] error.