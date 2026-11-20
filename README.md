# Vánoční losování z klobouku

Secret Santa draw for Eva, Katka, Děda, Babička, Martin, Hanka. Live name locking via Firebase Realtime Database, hosted on GitHub Pages.

The database stores only *who has already drawn* and *which papers are left in the hat*, never who drew whom.

## Setup
1. Firebase console → your project → **Build → Realtime Database → Create database** (any location, start in *locked mode*).
2. **Rules** tab → paste the contents of `database.rules.json` → **Publish**.
3. **Project settings → General → Your apps → Web (`</>`)** → register app (no hosting) → copy the `firebaseConfig` object.
4. Put it into `index.html` as `firebaseConfig` (done for project christmas-hat-b7f87).
5. GitHub repo → **Settings → Pages** → Source: *Deploy from a branch*, branch with `index.html`, folder `/ (root)`. Share the resulting link in Signal.

## Reset / new draw
Delete the `draws/vanoce2026` node in the Realtime Database console, or change `DRAW_ID` in `index.html`.

## Test mode
Open the link with `#zkouska` at the end: it draws from a separate practice hat (`draws/zkouska`). Delete that node in the console afterwards.

## Deploy to Firebase Hosting (from your own computer)
```
npm install -g firebase-tools
firebase login
firebase deploy
```
App: https://christmas-hat-b7f87.web.app — `firebase deploy` also uploads `database.rules.json`.
