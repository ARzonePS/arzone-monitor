# ARzonePS — Live Billing Monitor

Website live monitor resmi untuk **ARzonePS (Rental PlayStation)**.
Website ini ringan, responsif (cocok untuk HP pelanggan & kasir), dan langsung terhubung secara realtime ke Firebase Realtime Database.

---

## 🎮 Fitur Utama

1. **Desain Baru & Fresh (Cyberpunk Esports)**:
   - Tema warna neon Red & Blue senada dengan logo resmi **ARzonePS**.
   - Indikator status live: *Tersedia*, *Open Billing*, *Paket Main*, dan *Waktu Habis*.
2. **Murni & Fokus Billing**:
   - Fitur member, self-order, Saweria, dan nomor WhatsApp sudah **dihapus bersih**.
   - Murni hanya menampilkan nama rental, nomor stasiun/PS, status, durasi/countdown, dan tagihan live.
3. **Mendukung Mode Per Unit / Meja (`?unit=...`)**:
   - Bisa discan dari QR Code di meja masing-masing unit:
     - Contoh: `https://username.github.io/arzone-monitor/?unit=STATION 4`
     - Pelanggan di Station 4 hanya akan melihat live timer dan tagihan miliknya.
   - Tanpa parameter `?unit=`:
     - Menampilkan seluruh stasiun dalam bentuk grid dengan ringkasan status stasiun aktif dan kosong.
4. **Perhitungan Tarif Toleransi Presisi (Awal, Tengah, Akhir)**:
   - Jam ticker menghitung detik demi detik secara presisi mengikuti tipe toleransi pembulatan.
   - Angka berjalan di live monitor dijamin **100% SAMA** dengan saat kasir klik Selesai / Checkout.
5. **Dukungan Ganda (Aplikasi PC Lama & Aplikasi HP Android Baru)**:
   - Mendukung node `dashboard_rgans` (dari PC app / Eel).
   - Mendukung node `stations` + `sessions` (dari Android Flutter app `ps_billing_app`).

---

## 🚀 Cara Publish ke GitHub Pages

1. Buat repository baru di GitHub, misalnya bernama `arzone-monitor` (atau `arzone-live`).
2. Upload semua file dari folder ini (`index.html`, `logo.png`, `logo.jpg`) ke repository tersebut.
3. Buka tab **Settings** di repository GitHub Anda.
4. Di menu sebelah kiri, klik **Pages**.
5. Di bagian **Branch**, pilih `main` (atau `master`) dan folder `/ (root)`, lalu klik **Save**.
6. Dalam 1-2 menit, link website Anda sudah aktif di:
   ```
   https://[username-github-anda].github.io/arzone-monitor/
   ```

---

## 📱 Format Link QR Code Meja Pelanggan

Tinggal buatkan QR Code dengan link:
- Meja 1: `https://[username].github.io/arzone-monitor/?unit=STATION 1`
- Meja 2: `https://[username].github.io/arzone-monitor/?unit=STATION 2`
- Meja 3: `https://[username].github.io/arzone-monitor/?unit=STATION 3`
- Meja 4: `https://[username].github.io/arzone-monitor/?unit=STATION 4`
*(Nama stasiun menyesuaikan dengan nama stasiun yang terdaftar di aplikasi kasir).*

---

## ⚙️ Menghubungkan ke Firebase Baru

Website ini secara default sudah terhubung ke database aktif Anda.
Jika Anda nanti membuat project Firebase baru untuk client ini:
1. Anda cukup buka website di browser, klik tombol **Gear (⚙️)** di pojok kanan atas.
2. Masukkan URL Realtime Database yang baru (misal `https://arzone-ps-default-rtdb.asia-southeast1.firebasedatabase.app`).
3. Klik **Simpan & Muat Ulang**.
4. Atau langsung edit baris ke-497 di file `index.html`:
   ```javascript
   const DEFAULT_DB_URL = "https://URL-FIREBASE-BARU-ANDA.firebasedatabase.app";
   ```
