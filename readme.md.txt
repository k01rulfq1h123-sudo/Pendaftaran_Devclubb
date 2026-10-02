# Documentation: Portal Pendaftaran DevClub SMK Tunas Media
## 1. Deskripsi Proyek
Sistem Pendaftaran Anggota Klub Coding berbasis Web Interaktif (Client-Server Architecture) yang dibangun 
menggunakan kombinasi HTML5, TailwindCSS, JavaScript Async Fetch, dan PHP REST API dengan database MySQL.
## 2. Struktur Direktori Proyek
devclub_portal/
├── index.html       # Antarmuka Form Utama (Frontend Statis & UI)
├── app.js           # Client-side Logic (DOM Event, Validation, Fetch API)
├── api.php          # Backend Handler (Server-side Processing & DB Connection)
└── README.md        # Dokumen Petunjuk & Arsitektur Sistem
## 3. Spesifikasi API Endpoint- **URL**: `api.php?action=daftar`- **Method**: `POST`- **Header**: `Content-Type: application/json`- **Payload Request (JSON)**:
  {
    "nis": "12345678",
    "nama": "Ayam geprek",
    "divisi": "Web Development",
    "email": "Ayamgeprek@dmail.com"
  }- **Response Success (JSON)**:
  {
    "status": "success",
    "message": "Selamat! Data pendaftaran berhasil disimpan."
  }
## 4. Analisis Keamanan & Validasi (Dual-Layer Validation)- **Client-Side (JavaScript RegEx)**: Memvalidasi format NIS agar tepat 8 digit sebelum request dikirim ke server 
untuk efisiensi UX dan bandwidth.- **Server-Side (PHP Prepared Statement)**: Memverifikasi kelengkapan parameter server serta mengamankan query 
database dari serangan SQL Injection.