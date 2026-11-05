# Dynamic QR Apps Script backend

This is the independent backend for the Dynamic QR Platform. It is not the Customer Connect Desk backend.

1. Open the `Dynamic_QR_DB` spreadsheet and choose **Extensions → Apps Script**, or create a standalone Apps Script project.
2. Add the contents of `Code.gs` to the project. Enable the manifest editor and apply `appsscript.json`.
3. Confirm `APP.DB_ID` in `Code.gs` is the intended Dynamic QR spreadsheet ID before running anything.
4. Save, select `setupDatabase_`, and run it once. It adds required sheets/headers and never clears existing rows. Back up the spreadsheet first.
5. Add the Script Properties `OWNER_EMAIL`, `GOOGLE_CLIENT_ID`, `SUPPORT_EMAIL`, `PUBLIC_BASE_URL` and `SCAN_BASE_URL`. Set `SCAN_BASE_URL` after deploying the Web App.
6. Deploy as a Web App, execute as the deploying user, access Anyone. Copy the `/exec` URL.
7. Put that same `/exec` URL into Cloudflare Pages as the `DQR_APPS_SCRIPT_URL` environment variable.

Do not commit this backend source, the database ID, tokens, owner email or PINs into the public static frontend folder. Read the package `DEPLOYMENT_GUIDE.md` for the full coordinated deployment steps.
# MPlus---QR-Dynamic