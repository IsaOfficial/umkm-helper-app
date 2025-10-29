# Software Requirements Specification (SRS) — UMKM Helper (MVP)

## 1. Pendahuluan
### 1.1 Tujuan Dokumen
Menjabarkan kebutuhan fungsional dan non-fungsional dari UMKM Helper versi MVP.

### 1.2 Ruang Lingkup
Aplikasi mobile (Flutter) untuk manajemen produk, pemrosesan pesanan, dashboard ringkas, dan laporan penjualan dasar.

## 2. Deskripsi Umum
Pengguna utama: pemilik UMKM.

## 3. Kebutuhan Fungsional (Functional Requirements)
FR1: Registrasi & Login
- FR1.1: Pengguna dapat mendaftar dengan email & password.
- FR1.2: Pengguna dapat login via email & Google Sign-In.
- FR1.3: Pengguna dapat mengatur profil dan info toko.

FR2: Manajemen Produk
- FR2.1: Pengguna dapat menambahkan produk (nama, deskripsi, harga, stok, foto).
- FR2.2: Pengguna dapat mengedit/hapus produk.
- FR2.3: Pengguna dapat melihat daftar produk dan mencari berdasarkan nama.

FR3: Manajemen Pesanan
- FR3.1: Pelanggan dapat membuat pesanan (MVP: pesanan dibuat oleh owner/mock customer).
- FR3.2: Owner dapat melihat daftar pesanan dan mengubah status.
- FR3.3: Sistem menghitung total pesanan dan memperbarui stok saat pesanan selesai.

FR4: Dashboard & Laporan
- FR4.1: Tampilkan ringkasan pendapatan harian/mingguan.
- FR4.2: Ekspor laporan penjualan ke CSV.

FR5: Notifikasi
- FR5.1: Notifikasi lokal muncul saat pesanan baru tiba.

## 4. Kebutuhan Non-Fungsional (Non-Functional Requirements)
NFR1: Performa
- Aplikasi harus memuat daftar produk < 2s pada koneksi 4G.

NFR2: Keamanan
- Password disimpan secara hashed.
- Komunikasi menggunakan HTTPS.

NFR3: Skalabilitas
- Arsitektur harus mendukung skala ke beberapa merchant (future).

NFR4: Ketersediaan Offline
- Data produk dan pesanan terbaru disimpan lokal (SQLite / Hive) untuk akses offline.

NFR5: Kompatibilitas
- Mendukung Android 8.0+ dan iOS 13+ (pengembangan di Android fokus dulu).

## 5. Use Cases (Ringkas)
- UC1: Owner menambah produk.
- UC2: Owner mengubah status pesanan menjadi 'dikirim'.
- UC3: Owner mengekspor laporan penjualan bulanan.

## 6. Acceptance Criteria (Contoh)
- Akun baru dapat mendaftar dan login.
- Produk dapat ditambahkan dan muncul di daftar produk.
- Pesanan dapat dibuat dan status berubah; stok berkurang setelah status 'selesai'.
- Laporan CSV dapat diunduh dan berisi transaksi sesuai rentang tanggal.
