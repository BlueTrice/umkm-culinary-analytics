# CLAUDE_RULES.md

# AI Development Rules

Dokumen ini berisi aturan yang WAJIB dipatuhi selama proses pengembangan aplikasi UMKM Culinary Analytics Platform.

Selalu gunakan PROJECT_SPEC.md sebagai acuan utama.

---

# Tujuan

Fokus utama adalah menyelesaikan MVP secepat mungkin agar aplikasi dapat segera digunakan UMKM untuk mengumpulkan data transaksi.

Jangan menambahkan fitur di luar MVP.

---

# General Rules

1. Selalu mengikuti PROJECT_SPEC.md.
2. Jangan mengubah struktur database.
3. Jangan mengubah struktur folder project.
4. Jangan membuat fitur baru tanpa diminta.
5. Jangan membuat asumsi di luar PROJECT_SPEC.md.
6. Gunakan praktik terbaik FastAPI, SQLAlchemy, React, dan TypeScript.
7. Selalu gunakan type hints.
8. Kode harus bersih, mudah dibaca, dan siap digunakan.
9. Hindari duplikasi kode.
10. Jangan membuat kode yang tidak digunakan.

---

# Task Rules

Setiap prompt hanya mengerjakan SATU task.

Setiap task hanya membuat SATU file.

Jika file yang diminta membutuhkan file lain, cukup gunakan import yang sesuai tanpa membuat file tersebut.

Jangan melanjutkan ke task berikutnya.

---

# File Rules

Hanya buat file yang diminta.

Jangan membuat file tambahan.

Jangan menghapus file lain.

Jangan mengubah isi file lain kecuali diminta secara eksplisit.

Berikan isi file secara lengkap.

---

# Backend Rules

Gunakan:

* FastAPI
* SQLAlchemy 2.0
* Pydantic V2
* JWT Authentication

Pisahkan kode menjadi:

* Models
* Schemas
* Repositories
* Services
* API Routers

Jangan menaruh query database di Router.

Jangan menaruh logika bisnis di Router.

Repository hanya mengakses database.

Service hanya menangani logika bisnis.

Router hanya menerima request dan mengembalikan response.

---

# Frontend Rules

Gunakan:

* React
* TypeScript
* Vite
* TailwindCSS

Pisahkan menjadi:

* Pages
* Components
* Services
* Layouts

Komponen harus reusable.

Jangan membuat styling berulang.

Gunakan Axios untuk komunikasi API.

---

# Database Rules

Seluruh data harus mengikuti struktur database yang telah ditentukan.

Jangan membuat tabel baru.

Jangan mengubah nama kolom.

Jangan mengubah relasi.

Gunakan SQLAlchemy ORM.

---

# Authentication Rules

Gunakan JWT.

Password harus di-hash.

Seluruh endpoint yang membutuhkan login harus menggunakan autentikasi.

Role yang digunakan:

* admin
* cashier

---

# Multi Store Rules

Setiap user hanya boleh mengakses data milik tokonya.

Semua query harus difilter menggunakan store_id.

Tidak boleh menampilkan data toko lain.

---

# Coding Style

Gunakan:

* clean code
* meaningful variable name
* function yang singkat
* komentar seperlunya

Jangan membuat kode yang terlalu kompleks.

---

# Output Rules

Saat mengerjakan task:

Berikan:

1. Nama file.

2. Isi file lengkap.

3. Tidak perlu menjelaskan teori.

4. Tidak perlu membuat file lain.

5. Tidak perlu membuat dokumentasi tambahan.

---

# Jika Terjadi Error

Jika terdapat dependency yang belum tersedia:

Jangan membuat file dependency tersebut.

Cukup gunakan import yang sesuai.

Asumsikan file tersebut akan dibuat pada task berikutnya.

---

# Scope MVP

Fitur yang boleh dibuat:

* Login
* Dashboard
* Master Menu
* Pegawai
* Transaksi
* Riwayat
* Export CSV
* Export Excel

Di luar daftar tersebut jangan dibuat.

---

# Prompt Workflow

Setiap kali menerima prompt:

1. Baca PROJECT_SPEC.md.
2. Ikuti TASK_LIST.md.
3. Kerjakan satu task saja.
4. Hasilkan satu file saja.
5. Jangan mengubah file lain.
6. Pastikan file siap digunakan.
7. Selesai.

---

# Definition of Done

Sebuah task dianggap selesai apabila:

* File berhasil dibuat.
* Tidak ada syntax error.
* Mengikuti PROJECT_SPEC.md.
* Mengikuti struktur project.
* Siap digunakan pada task berikutnya.
