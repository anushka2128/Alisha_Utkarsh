Alisha & Utkarsh Wedding Invitation
====================================

1. Open index.html in Chrome / Safari / Edge (internet connection is needed for Google Fonts, Firebase, and SheetJS).
2. Keep Sajiri-Gojiri.mp3 in the same folder as index.html.
3. To host online, upload the folder to Netlify, GitHub Pages, Vercel, or Firebase Hosting.

-------------------------------------------------------------
SHARED BLESSINGS & UKHANE WALL (Firebase Firestore)
-------------------------------------------------------------
1. Visible on every phone:
   The blessings wall is powered by Firebase Firestore, a cloud database that keeps all guest devices synchronized in real time.

2. Stack of 10:
   The wall displays only the newest 10 posts, newest on top. When an 11th post arrives, the oldest automatically drops off the wall. The wall updates live across all phones without needing a page refresh.

3. Author-Only Delete:
   A "✕ Delete" button appears ONLY on the guest's own posts. Deletion is enforced on the server via Firebase Firestore Security Rules (firestore.rules) using Anonymous Authentication, so nobody can delete or tamper with someone else's blessing.

4. Export to Excel:
   - On the website: Click the "Export All to Excel (.xlsx)" button directly below the Blessings Wall to download the full spreadsheet of all blessings and ukhane.
   - Via CLI: Run `node export-blessings.mjs` in terminal.

-------------------------------------------------------------
QUICK 2-MINUTE FIREBASE SETUP
-------------------------------------------------------------
To connect all phones to the live shared database:
1. Go to https://console.firebase.google.com and click "Add project" (e.g. "alisha-utkarsh-wedding").
2. In your project overview, click the Web icon (</>) to register a web app.
3. Copy the `firebaseConfig` object and paste it into `firebase-config.js`.
4. In the left sidebar:
   - Go to "Build" -> "Firestore Database" -> Click "Create database" (choose test mode or production).
   - Go to the "Rules" tab in Firestore and paste the contents of `firestore.rules`.
   - Go to "Build" -> "Authentication" -> "Sign-in method" -> Enable "Anonymous".
5. That's it! Every guest will now see the live wall, post blessings/ukhane, delete their own notes, and export to Excel.
