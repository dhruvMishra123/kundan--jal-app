# Kundan Jal — Android APK kaise banayein

This folder is a complete Android app project. GitHub builds the APK for you in the cloud, for free, in about 5 minutes. You don't need to install Android Studio.

## One-time setup (10 minutes, a laptop/computer is easiest)

1. Create a free account at https://github.com
2. Click **+** (top right) → **New repository**
   - Name: `kundan-jal-app`
   - Choose **Private** (recommended)
   - Click **Create repository**
3. On the new repository page click **"uploading an existing file"**.
4. Unzip `kundan-jal-app.zip` on your computer. Open the unzipped folder, select **everything inside it**
   (including the `.github` folder) and drag it into the GitHub upload page.
   - `.github` is a hidden folder. On Mac press `Cmd + Shift + .` to show it; on Windows turn on
     View → Hidden items.
   - If the upload page skips the `.github` folder, see "If the build doesn't start" below.
5. Click **Commit changes**.

## Get the APK

6. Open the **Actions** tab of your repository. A job called **Build Android APK** starts on its own.
   Wait for the green ✓ (about 4–6 minutes).
7. Go to the repository's main page → **Releases** (right side) → latest **Kundan Jal v1.0.x** →
   tap **KundanJal.apk** to download. (You can do this directly from your phone's browser while logged in to GitHub.)

## Install on the phone

8. Open the downloaded **KundanJal.apk**.
9. Android will ask to allow "Install unknown apps" for Chrome/Files → **Allow** → **Install**.
   If Play Protect warns you, tap **More details → Install anyway** (it warns because the app isn't from the Play Store).
10. Open **Kundan Jal** from the home screen and set your 4-digit PIN.

## Updating the app later

Change files (for example `www/index.html`) on GitHub → a new APK builds automatically → install it over the old one.
Your orders are **kept**, because every build is signed with the same key in the `keystore` folder.
Don't delete or change that folder, or updates will require uninstalling (which erases the orders).

## Important: data and backups

- Orders are saved **on the phone**, and the app works without internet.
- Go to **Daily Record → 💾 Backup** regularly and send the file to yourself on WhatsApp/Drive/email.
  If the phone is lost or the app is uninstalled, use **♻ Restore** to bring the orders back.
- **⬇ Excel (CSV)** shares a spreadsheet of all orders that opens in Excel or Google Sheets.

## If the build doesn't start

GitHub's web upload sometimes skips the hidden `.github` folder. To fix it:
Repository → **Add file → Create new file** → name it `.github/workflows/build-apk.yml` →
paste in the contents of that file from the zip → **Commit changes**. The build starts right away.

## Building on your own computer instead (optional)

Install Node.js 22, Java 21 and Android Studio, then in this folder:

```
npm install
npx cap add android
npx @capacitor/assets generate --android
npx cap sync android
npx cap open android      # then Build → Build APK(s) in Android Studio
```
(Add the location permissions from the workflow file to `android/app/src/main/AndroidManifest.xml`.)

## Play Store

This APK is for installing directly on your phones. Publishing on the Google Play Store needs a Google Play developer
account ($25 one-time) and a release-signed AAB file. Ask if you want that set up.
