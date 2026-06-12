# Bara Indah Sinergi Group - Workflow Approval Web App

Aplikasi workflow approval ini siap di-host di GitHub dan di-deploy ke Vercel dengan database backend menggunakan Google Sheets (via Google Apps Script).

## Struktur File Distribusi
- index.html: File frontend gabungan (HTML + CSS + JS) untuk di-deploy ke Vercel atau GitHub Pages.
- Code.js: Kode backend Google Apps Script.
- SetupSheets.js: Kode inisialisasi tabel basis data Google Sheets.

## Langkah-Langkah Deploy ke GitHub & Vercel

### 1. Set Up Backend Google Apps Script (GAS)
1. Buat Spreadsheet Google baru.
2. Buka menu **Ekstensi** > **Apps Script**.
3. Hapus kode default, lalu buat dua file script di Apps Script editor:
   - Code.gs (salin konten dari Code.js)
   - SetupSheets.gs (salin konten dari SetupSheets.js)
4. Klik **Deploy** > **New Deployment**.
5. Pilih tipe deployment **Web App**.
6. Konfigurasikan:
   - *Execute as*: **Me (akun email Anda)**
   - *Who has access*: **Anyone**
7. Klik **Deploy** dan salin **URL Web App** yang diberikan (formatnya: https://script.google.com/macros/s/.../exec).

### 2. Deploy Frontend ke Vercel
1. Unggah isi folder dist/ ke repositori GitHub baru Anda.
2. Masuk ke dashboard **Vercel** (ercel.com) dan hubungkan dengan akun GitHub Anda.
3. Klik **Add New** > **Project** dan pilih repositori Anda.
4. Klik **Deploy**. Vercel akan otomatis menyajikan aplikasi Anda sebagai situs web statis yang sangat cepat.
5. Setelah dideploy, buka tautan situs web Vercel Anda.

### 3. Hubungkan Frontend Vercel dengan GAS Backend
1. Saat pertama kali membuka web Vercel, sistem akan mendeteksi bahwa URL API belum dikonfigurasi dan akan memunculkan popup modal **API Connection Settings**.
2. Masukkan **URL Web App** Google Apps Script yang telah Anda salin di Langkah 1 ke kolom input, lalu klik **Simpan Koneksi**.
3. Halaman akan dimuat ulang dan aplikasi Anda siap digunakan secara penuh jangka panjang!
4. Anda juga dapat mengubah URL ini kapan saja dengan mengklik ikon **Settings (sliders)** di bar kanan atas.
