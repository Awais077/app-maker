# App Maker — apna code, apni cloud build

Ye repo **App Maker app ka apna code** hai (package `com.jack.appmaker`).
Is se App Maker ka APK **GitHub cloud** pe banta hai — bina Muse ke bhi.

## Is mein kya hai

- `www/index.html` — App Maker app ka poora code (AI se code likho, GitHub pe bhejo, build dekho, APK download karo)
- `package.json` + `capacitor.config.json` — app ki pehchan (Capacitor 7.6.9)
- `.github/workflows/build-apk.yml` — cloud build (GitHub Actions)

## Build kaise chalegi

1. **Push karo:** `www/index.html`, `package.json` ya `capacitor.config.json` mein koi change karke `main` branch pe push karo — build khud chal jaye gi.
2. **Ya manual:** GitHub pe repo → **Actions** → **Build APK** → **Run workflow** → branch `main` → **Run workflow**.
3. Build khatam hone pe **Artifacts** mein **App-Maker** mile ga — us ke andar APK hai (ZIP file ke andar). Download karo, phone mein install karo (purane version ke upar — data safe rehta hai).

## Zaroori secrets

Repo → Settings → Secrets and variables → Actions mein ye 4 secrets hone chahiye
(yehi secret names my-apps repo mein bhi hain, lekin values is repo ki apni hain):

- `APK_KEYSTORE_BASE64`
- `APK_KEYSTORE_PASSWORD`
- `APK_KEY_ALIAS` (= `appmaker`)
- `APK_KEY_PASSWORD`

Keystore ki values jack ke paas safe rakhi hain (keystore file + passwords alag se diye gaye hain).
