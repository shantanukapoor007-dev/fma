# Field Maintenance Assistant (FMA) — Android

*Diagnose. Maintain. Restore.*

Offline Android app. All data stays on the device. No internet needed.

## Get the APK (no software to install)

1. Create a free account at https://github.com and click **New repository**
   (name it `fma`, click **Create repository**).
2. On the new repository page click **uploading an existing file**.
3. Unzip `FMA-Android-Project.zip`, open the unzipped folder, select
   **everything inside it** and drag it into the GitHub page. Click **Commit changes**.
4. Open the **Actions** tab. If asked, click **I understand my workflows, go ahead and enable them**.
   The *Build FMA APK* job runs automatically (about 4–6 minutes).
5. When it shows a green tick, go to the repository's main page, open **Releases**
   (right side) and download `FMA-Field-Maintenance-Assistant.apk`.
6. Open it on the phone and allow **Install unknown apps** when Android asks.

If the `.github` folder did not upload (it can be hidden on some computers):
**Add file → Create new file**, name it `.github/workflows/build-apk.yml`,
paste the contents of that file from the zip, and commit. The build starts immediately.
If a build was skipped, open **Actions → Build FMA APK → Run workflow**.

## Demo logins (password 1234)

| User ID | Role |
|---|---|
| FMA001 | Field User |
| FMA002 | JCO / Supervisor |
| FMA003 | Technician |

Press and hold the logo on the login screen to reload demo data.

## Build on your own computer (optional)

Open this folder in Android Studio and press **Run**,
or with Gradle 8.7 and JDK 17: `gradle assembleDebug`
→ `app/build/outputs/apk/debug/app-debug.apk`.

## Project layout

- `app/src/main/assets/www/index.html` – the complete FMA application
- `app/src/main/assets/www/fonts/` – bundled fonts and icons (no internet use)
- `app/src/main/java/com/fma/fieldmaintenance/MainActivity.java` – Android host and back button
- `.github/workflows/build-apk.yml` – cloud build that produces the APK

## Notes

- The APK is signed with a development key, suitable for trials and demonstrations.
  For formal distribution, sign a release build with your organisation's key.
- Sample data is generic. Replace it with authorised data before real use
  (`EQ_ROWS`, `TREES`, `REFS` and `seed()` in `index.html`).
