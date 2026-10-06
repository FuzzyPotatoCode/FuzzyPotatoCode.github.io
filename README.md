# FuzzyPotatoCode.github.io

The public web pages behind the Budget app (`budget-app` repo, plan Phase 12, stage C).
Served by GitHub Pages at https://fuzzypotatocode.github.io.

- `budget/callback/` - BankSync's return address. BankSync only sends people back to an https
  page, so this page hands the one-time code on to the app (`budgetapp://callback?...`), with
  a button if the browser doesn't open the app by itself. The code is single-use, expires in a
  minute and needs a secret only the app holds (PKCE).
- `.well-known/assetlinks.json` - lets Android open the app for this site's links (Android App
  Links): the app id `app.budget.budget_app` with the release key's and the debug key's
  SHA-256 fingerprints (public; they are in every APK).
- `budget/privacy/` - the privacy policy (BankSync's app review and the Play Store ask for one).
- `index.html` - a short page about the app.
- `.nojekyll` - so GitHub Pages serves the `.well-known` folder.

Plain HTML, no build step. A change here is live once pushed.
