# blink-ipad-build

Membangun **Blink Shell** (termasuk perintah `code`) dari kode sumbernya yang terbuka
([blinksh/blink](https://github.com/blinksh/blink), lisensi GPL-3.0) untuk dipakai pribadi di iPad,
tanpa membeli lewat App Store. Ini jalur "bangun sendiri" yang dijelaskan README Blink sendiri.

Repo ini hanya berisi satu workflow GitHub Actions. Ia mengambil kode Blink terbaru, membangunnya
di Mac milik GitHub, dan menghasilkan berkas `.ipa` **belum bertanda tangan**.

## Cara pakai

1. Buka tab **Actions** → **Build Blink IPA** → **Run workflow** (atau cukup push ke `main`).
2. Tunggu sampai hijau (±30–60 menit). Buka run itu → bagian **Artifacts** → unduh **Blink-ipa**.
3. Di dalamnya ada dua berkas:
   - `Blink-noext-unsigned.ipa` ← **pakai ini dengan Apple ID gratis**
   - `Blink-full-unsigned.ipa` ← lengkap dengan ekstensi File Provider (butuh akun developer berbayar)
4. Pasang ke iPad dari Windows dengan **Sideloadly**:
   - pasang iTunes versi apple.com (bukan Microsoft Store) dan Sideloadly,
   - iPad: Settings → Privacy & Security → **Developer Mode** → On (iPad restart),
   - sambungkan iPad lewat USB dan pilih "Trust",
   - buka Sideloadly, seret `.ipa`, isi Apple ID, klik **Start**,
   - di iPad: Settings → General → **VPN & Device Management** → percayai profil Apple ID-mu.
5. Dengan Apple ID gratis, aplikasi **kedaluwarsa tiap 7 hari**: pasang ulang dari Sideloadly
   (atau aktifkan auto-refresh Sideloadly selama PC dan iPad ada di Wi-Fi yang sama).

## Yang tidak ikut (karena Apple ID gratis)

iCloud sync, push notification, keychain sharing, associated domains, dan ekstensi File Provider.
Kunci SSH dan pengaturan disimpan lokal di iPad.

## Catatan

- Build ini tidak resmi dan tidak didukung pembuat Blink. Jika berguna, pertimbangkan membeli versi
  App Store untuk mendukung pengembangnya.
- Kode sumber ada di repo upstream; workflow ini tidak mengubahnya selain pengaturan tanda tangan.
