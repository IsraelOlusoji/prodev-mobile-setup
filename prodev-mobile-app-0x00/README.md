---

## 🚀 Project 1: Creating the First App

This section documents the process of scaffolding, running, and resetting the initial React Native application using the Expo Router template.

### 1. Scaffolding and Modification

1.  **Navigated to Directory:** I opened my terminal in the `prodev-mobile-setup` directory.
2.  **Initialized Project:** I ran `npx create-expo-app@latest .` to set up the project with the latest Expo Router template in the current directory.
3.  **Modified Home Screen:** I opened the project in VS Code and navigated to `app/(tabs)/index.tsx`. I located the default text and changed it to `** First App Created**`.

### 2. Running the Application

1.  **Started Server:** I ran `npx expo start` in the terminal.
2.  **Tested on Device:** I used the **Expo Go app** on my Android device to scan the QR code.
3.  **Result:** The application loaded successfully on my phone, and the home screen displayed my "First App Created" text.

### 3. Observations from `npm run reset-project`

After testing the initial application, I ran the `npm run reset-project` command as instructed.

#### Attempt 1: (Error)

My first attempt to run the script failed.

```bash
$ npm run reset-project
> ...
Do you want to move existing files to /app-example instead of deleting them? (Y/n): y
📁 /app-example directory created.
❌ Error during script execution: EPERM: operation not permitted, rename '...app' -> '...app-example\app'
Observation: The script failed with an EPERM: operation not permitted error. This is a common Windows error that usually means a file or directory is "locked" or in use by another program (e.g., VS Code still had the app directory open, or the Expo development server was still running).

Attempt 2: (Success)
I stopped the npx expo start server, closed VS Code, and ran the command again in my terminal.

Bash

$ npm run reset-project
> ...
Do you want to move existing files to /app-example instead of deleting them? (Y/n): y
📁 /app-example directory created.
➡️ /hooks moved to /app-example/hooks.
➡️ /constants moved to /app-example/constants.
➡️ /scripts moved to /app-example/scripts.
...
📁 New /app directory created.
📄 app/index.tsx created.
📄 app/_layout.tsx created.

✅ Project reset complete.
Observation: The second attempt was successful. The script performed the following actions:

It prompted me to save the existing files, and I selected y (yes).

It created a new directory named /app-example.

It moved the original template's folders (like /app, /hooks, /constants, etc.) into the /app-example directory to serve as a backup.

It then created a new, minimal /app directory.

It populated this new directory with only two files: app/index.tsx (a new, blank home screen) and app/_layout.tsx (the root layout file).

Conclusion: The reset-project script is a utility to clean the project of the default template's boilerplate (like the tab navigation) and provide a minimal, single-page starting point for a new application.