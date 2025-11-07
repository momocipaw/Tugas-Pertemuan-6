# Laporan Praktikum PBW - Pertemuan 6

Nama  : Reno Fatullah  
NPM   : 4522210021  
Mata Kuliah : Pemrograman Berbasis Web (PBW)  
Pertemuan : 6  
Tanggal : (isi tanggal praktikum)

## Tujuan
1. Memahami dan menerapkan paket Filament pada proyek Laravel.
2. Membuat resource admin sederhana (model, migration, resource Filament).
3. Menguji antarmuka admin untuk operasi CRUD pada entitas contoh.

## Alat dan Bahan
- Sistem operasi: Windows / Linux / macOS
- PHP >= 8.x
- Composer
- Laravel (versi proyek)
- Paket Filament (dalam folder proyek: filament)
- Basis data (MySQL / SQLite)
- Editor kode (VSCode / lainnya)
- Browser untuk mengakses panel admin

## Dasar Teori Singkat
Filament adalah toolkit admin panel untuk Laravel yang mempermudah pembuatan antarmuka CRUD berbasis resource. Dengan Filament, developer dapat membuat Resource, Form, dan Table untuk manajemen data model Laravel.

## Langkah Kerja (berdasarkan isi folder filament)
1. Persiapan proyek
   - Pastikan dependensi terpasang: jalankan `composer install` dan `npm install` bila diperlukan.
   - Salin file .env.example ke .env dan sesuaikan konfigurasi basis data.
   - Jalankan `php artisan key:generate`.

2. Migrasi dan pembuatan model
   - Jalankan migrasi: `php artisan migrate`.
   - Jika ada migration di folder proyek yang sesuai, periksa tabel yang dibuat (contoh: users, posts, dsb.).

3. Instalasi dan konfigurasi Filament (jika belum terpasang)
   - Biasanya: `composer require filament/filament`
   - Publikasikan resource config dan jalankan `php artisan filament:install` bila perlu.

4. Meninjau folder filament
   - Buka folder app/Filament atau resources/filament (tergantung struktur proyek).
   - Identifikasi Resource class (mis. PostResource), Form dan Table yang mengatur field, kolom, dan actions.
   - Periksa policy atau gate yang mengatur akses.

5. Menjalankan server dan menguji
   - Jalankan `php artisan serve`.
   - Akses panel admin Filament (misal: /admin).
   - Lakukan operasi CRUD pada resource yang tersedia (create, read, update, delete) dan catat hasilnya.

6. Dokumentasikan hasil percobaan
   - Ambil screenshot halaman list, form create/edit, dan detail (jika diperlukan).
   - Catat error dan cara penyelesaiannya (mis. perbaikan migration, tambahan field di model, dsb.).

## Hasil Praktikum (Contoh pelaporan)
- Resource yang diuji: PostResource (contoh)
- Field pada form: title (string), content (text), published_at (datetime)
- Operasi yang diuji:
  - Create: Berhasil menambah data baru dengan field lengkap.
  - Read: Data tampil pada tabel dengan kolom title dan published_at.
  - Update: Berhasil mengubah title dan content.
  - Delete: Berhasil menghapus data.
- Catatan error/penyesuaian:
  - Jika terjadi error mass assignment, tambahkan `$fillable` pada model.
  - Jika form tidak menampilkan field, periksa definisi form di Resource.
  ![WhatsApp Image 2025-11-07 at 19 28 38](https://github.com/user-attachments/assets/2f68532b-356f-451c-8d8b-e0c6590361ff)
![WhatsApp Image 2025-11-07 at 19 28 39](https://github.com/user-attachments/assets/1e545267-9a96-4f16-a18e-a16f7c7e1216)
![WhatsApp Image 2025-11-07 at 19 30 56](https://github.com/user-attachments/assets/6f99acc6-1d83-4e35-a1e6-c59259da543b)


## Analisis
- Filament mempercepat pembuatan panel admin berkat abstraksi Resource/Form/Table.
- Konfigurasi yang umum menyebabkan masalah: fillable/guarded pada Model, tipe kolom migration yang tidak sesuai, serta autentikasi admin.
- Pengujian CRUD menunjukkan alur data dari form -> controller/resource -> model -> database bekerja sesuai desain Filament.

## Kesimpulan
- Praktikum ini menunjukkan bahwa Filament memudahkan pembuatan antarmuka admin di Laravel.
- Dengan sedikit konfigurasi pada model dan migration, resource Filament dapat langsung digunakan untuk operasi CRUD.
- Disarankan untuk memperhatikan keamanan (akses admin) dan validasi data saat menerapkan di proyek nyata.

## Tindak Lanjut / Saran
- Implementasikan validasi more robust pada Form Filament.
- Buat Role & Permission untuk membatasi akses di panel admin.
- Tambahkan fitur upload file dan preview pada resource yang membutuhkan.

## Daftar Pustaka
- Dokumentasi Laravel: https://laravel.com/docs  
- Dokumentasi Filament: https://filamentphp.com/docs

## Cara Menghapus Remote di Git

Langkah singkat:
1. Periksa daftar remote:
   ```
   git remote -v
   ```
2. Hapus remote (misal `origin`):
   ```
   git remote remove origin
   ```
   atau
   ```
   git remote rm origin
   ```
3. Verifikasi penghapusan:
   ```
   git remote -v
   ```
Catatan tambahan:
- Untuk menghapus branch di remote (server): `git push <remote> --delete <branch>`
- Alternatif manual: buka file `.git/config` dan hapus blok `[remote "<nama>"]` lalu simpan.
