# On Track

Habit tracker for deen, languages and sport. Sign in with Google; everything is saved in Firestore and syncs live between devices.

## Setup

1. **GitHub:** create a repo `on-track`, upload `index.html`, then Settings → Pages → Deploy from branch `main` / root.
   The app will live at `https://athleticconsumer-dotcom.github.io/on-track/`.
2. **Firebase:** create a project `on-track`.
   - Build → Authentication → Get started → Sign-in method → enable **Google**.
   - Authentication → Settings → Authorized domains → add `athleticconsumer-dotcom.github.io`.
   - Build → Firestore Database → Create database (production mode).
   - Firestore → Rules → paste the contents of `firestore.rules` → Publish.
   - Project settings → Your apps → add a **Web app** (`</>`), copy the `firebaseConfig`.
3. Paste the config into `firebaseConfig` at the top of the script in `index.html`, commit, done.

## Data

One document per user: `ontrack/{uid}` with a `state` field (JSON string) holding goals, habits, the daily log, notes and any running timer.
On first sign-in the document is created with the goals and habits baked into `index.html`.
