# Mandagres — Aplikasi Android

Isi folder ini:
- `www/` → website Mandagres (sudah PWA: manifest, service worker, ikon)
- `capacitor.config.json`, `package.json` → pembungkus Android (Capacitor)
- `.github/workflows/build-apk.yml` → build APK otomatis di GitHub (tanpa Android Studio)

## Cara 1 — Tanpa install apa pun (GitHub Actions)
1. Buat repo GitHub baru, upload semua isi folder ini (termasuk folder `.github`).
2. Buka tab **Actions → Build APK → Run workflow**.
3. Tunggu ±5 menit, unduh **Mandagres-APK** dari bagian Artifacts → ekstrak → `app-debug.apk`.
4. Kirim ke HP, install (izinkan "install dari sumber tidak dikenal").

## Cara 2 — Di komputer (butuh Node 18+, JDK 17, Android Studio/SDK)
```
npm install
npx cap add android
npx capacitor-assets generate --android
npx cap sync android
npx cap open android      # lalu Build > Build APK(s)
```
Setiap mengubah `www/index.html`, jalankan `npx cap sync android` lagi.

## Cara 3 — Paling cepat (tanpa APK): Install dari Chrome
Hosting `www/` di HTTPS (GitHub Pages / Netlify), buka di Chrome Android → menu ⋮ → **Install app**.

Catatan: peta, font, dan pencarian buku butuh internet. Data (keuangan, tema, dll.) tersimpan di localStorage perangkat.
