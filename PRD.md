# Product Requirement Document (PRD)
**Project:** UMKM Helper — Mobile App untuk UMKM (Flutter)
**Author:** Isa
**Date:** 2025-10-29

## Ringkasan Produk
UMKM Helper adalah aplikasi mobile untuk membantu pelaku UMKM dalam mengelola produk, inventori, pesanan, pelanggan, dan pemasaran sederhana. Fokus MVP: manajemen produk, pemrosesan pesanan, laporan penjualan dasar, dan dashboard bisnis.

## Tujuan Produk
- Menyederhanakan operasional penjualan UMKM.
- Memberi laporan ringkas dan insight penjualan.
- Memfasilitasi katalog produk digital dan penerimaan pesanan.

## Target Pengguna
- Pemilik UMKM mikro & kecil yang membutuhkan alat sederhana untuk pengelolaan toko.
- Usia 20–55, memiliki smartphone Android.

## Fitur Utama (MVP)
1. Autentikasi pengguna (email/password, Google Sign-In).
2. Dashboard ringkas (pendapatan hari ini, pesanan terbaru).
3. Manajemen produk (CRUD produk, foto, stok, harga).
4. Manajemen pesanan (buat, ubah status: baru - diproses - dikirim - selesai).
5. Laporan penjualan dasar (filter by date).
6. Notifikasi lokal untuk pesanan baru.
7. Sinkronisasi cloud (opsional) menggunakan Firebase.

## Batasan / Non-MVP
- Integrasi pembayaran online (di luar MVP).
- Multi-merchant / marketplace.
- Modul akuntansi lanjutan.

## Keunggulan dibanding Kompetitor
- **Simpel & fokus**: UI yang dirancang untuk pemula UMKM, kurva belajar rendah.
- **Document-first & AI-assisted onboarding**: template PRD/guide onboarding yang terintegrasi (future), memudahkan setup toko.
- **Offline-first sync**: data dasar bisa diakses offline dan tersinkron saat online.
- **Lightweight & privacy-focused**: penyimpanan minimal data sensitif dan opsi sinkronisasi manual.
- **Ekstensi lokal**: fitur ekspor laporan ke CSV yang mudah untuk administrasi pajak sederhana.

## Metode Monetisasi (opsional)
- Langganan premium untuk fitur laporan lanjutan.
- Biaya setup tema toko / template.

## KPI Sukses MVP (30 hari)
- 100 pengguna terdaftar
- 30 merchant aktif (memasukkan produk)
- 500 transaksi tercatat

