# PROJECT_SPEC.md

## Project Name

UMKM Culinary Analytics Platform

## Tujuan Project

Membangun aplikasi web pencatatan transaksi sederhana untuk UMKM kuliner yang berfungsi sebagai:

* Digitalisasi pencatatan transaksi.
* Pengumpul dataset untuk penelitian skripsi Demand Forecasting menggunakan XGBoost.
* Portofolio Software Engineering dan Business Analytics.
* Fondasi aplikasi yang dapat dikembangkan menjadi produk SaaS.

Prioritas utama adalah **mengumpulkan data transaksi sebanyak mungkin**, bukan membuat POS yang kompleks.

---

# Tech Stack

## Backend

* FastAPI
* SQLAlchemy 2.0
* Alembic
* MySQL
* JWT Authentication
* Pydantic V2

## Frontend

* React
* TypeScript
* Vite
* Tailwind CSS
* React Router
* Axios

---

# Database

Menggunakan database yang telah disepakati.

Tabel:

* stores
* users
* menus
* transactions
* transaction_items

Jangan mengubah struktur database tanpa instruksi.

---

# Role

Hanya ada 2 role.

## Admin

Dapat:

* Login
* Mengelola Menu
* Mengelola Pegawai
* Input Transaksi
* Melihat Riwayat
* Export CSV
* Export Excel
* Melihat Dashboard

## Cashier

Dapat:

* Login
* Input Transaksi
* Melihat Riwayat
* Dashboard sederhana

Cashier tidak boleh mengelola Menu maupun Pegawai.

---

# Multi Store

Setiap user hanya boleh mengakses data milik tokonya.

Semua query WAJIB difilter menggunakan:

store_id

Tidak boleh menampilkan data toko lain.

---

# Struktur Folder Backend

app/

* api/
* core/
* database/
* models/
* repositories/
* schemas/
* services/
* utils/

main.py

---

# Struktur Folder Frontend

src/

* components/
* pages/
* layouts/
* services/
* hooks/
* router/
* assets/

---

# Fitur MVP

## Authentication

* Login
* Logout
* JWT Authentication

---

## Dashboard

Menampilkan:

* Total Revenue Hari Ini
* Total Transaksi Hari Ini
* Total Item Terjual Hari Ini
* Top 5 Menu Terlaris
* Penjualan 7 Hari Terakhir

---

## Menu

Admin dapat:

* Tambah Menu
* Edit Menu
* Hapus (Nonaktifkan) Menu
* Lihat Daftar Menu

---

## Pegawai

Admin dapat:

* Tambah Pegawai
* Edit Pegawai
* Nonaktifkan Pegawai

Cashier tidak dapat mengakses menu ini.

---

## Transaksi

Kasir/Admin dapat:

* Membuat transaksi
* Memilih menu
* Mengubah quantity
* Menghapus item sebelum disimpan
* Menyimpan transaksi

Field transaksi:

* Transaction Code
* Transaction DateTime
* Sales Channel
* Payment Method
* Total Item
* Total Amount

Detail transaksi:

* Menu
* Quantity
* Unit Price
* Subtotal

---

## Riwayat

Menampilkan:

* Nomor Transaksi
* Tanggal
* Total
* Channel
* Metode Pembayaran

Dapat melihat detail transaksi.

---

## Export

Admin dapat:

* Export CSV
* Export Excel

Export hanya data toko yang sedang login.

---

# Coding Rules

* Gunakan type hints.
* Gunakan SQLAlchemy ORM.
* Gunakan Pydantic V2.
* Pisahkan Model, Repository, Service, dan API.
* Jangan menaruh query database di API.
* Jangan membuat logika bisnis di Router.
* Semua response menggunakan JSON.
* Semua endpoint menggunakan REST API.

---

# Aturan Claude

Saat mengerjakan tugas:

* Hanya membuat file yang diminta.
* Jangan mengubah file lain.
* Jangan membuat fitur di luar permintaan.
* Jangan mengubah struktur database.
* Jangan membuat asumsi tambahan.
* Berikan kode lengkap untuk file yang diminta.
* Pastikan kode dapat langsung digunakan.

---

# Target MVP

1. Login
2. Dashboard
3. CRUD Menu
4. CRUD Pegawai
5. Input Transaksi
6. Riwayat Transaksi
7. Export CSV
8. Export Excel
9. Deploy
10. Digunakan UMKM untuk mengumpulkan data transaksi.
