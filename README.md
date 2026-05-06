# 🔨 BidLen ID - Digital Auction House

![Laravel](https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&logo=mysql&logoColor=white)
![PHP](https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white)

**BidLen ID** adalah sistem informasi pelelangan barang digital premium berbasis web. Dibangun menggunakan arsitektur MVC (Model-View-Controller) dengan kerangka kerja Laravel. Sistem ini memfasilitasi proses lelang yang transparan, aman, dan efisien dengan antarmuka pengguna (UI/UX) yang modern.

Proyek ini dikembangkan sebagai bagian dari pemenuhan tugas Uji Kompetensi Keahlian (UKK) jurusan Pengembangan Perangkat Lunak dan Gim (PPLG).

---

## ✨ Fitur Utama

### 🔐 Sistem Multi-Otorisasi (Multi-Auth)
Sistem ini menggunakan tiga peran pengguna dengan hak akses yang terisolasi secara aman:
- **Administrator**: Memiliki kendali penuh atas manajemen pengguna (Petugas & Admin) dan pembuatan laporan pendataan lelang.
- **Petugas**: Bertanggung jawab atas manajemen inventaris (CRUD Barang), pengelolaan barang Draf, serta membuka/menutup sesi lelang.
- **Masyarakat (User)**: Dapat melihat galeri barang lelang, melakukan penawaran (*bidding*), dan melihat riwayat penawaran.

### 📦 Manajemen Inventaris & Draf
- Pemisahan logis antara barang publik dan barang **Draf** (belum dilelang).
- Fitur unggah media dengan manajemen *storage* lokal.
- Pratinjau (*Preview*) barang eksklusif sebelum dipublikasikan ke publik.

### 🎨 Premium User Interface
- Dibangun sepenuhnya dengan **Tailwind CSS**.
- Komponen interaktif (Modals, Dropdowns, Custom Alerts) menggunakan Vanilla JavaScript.
- Desain responsif dan estetika *High-End Gallery*.

---

## 🚀 Panduan Instalasi (Local Development)

Ikuti langkah-langkah berikut untuk menjalankan proyek ini di mesin lokal Anda.

### Prasyarat
- PHP >= 8.1
- Composer
- Node.js & NPM
- MySQL / MariaDB (Rekomendasi: Laragon atau XAMPP)

### Langkah Instalasi

1. **Clone Repositori**
   ```bash
   git clone [https://github.com/USERNAME_GITHUB_ANDA/bidlen-id.git](https://github.com/USERNAME_GITHUB_ANDA/bidlen-id.git)
   cd bidlen-id

2. **Install Dependensi PHP**
   ```bash
   composer install

4. **Install Dependensi Node.js (Tailwind)**
   ```bash
    npm install

6. **Konfigurasi Environment**
   ```bash
   cp .env.example .env

  Buka file .env dan sesuaikan konfigurasi database:
  ```bash
  DB_CONNECTION=mysql
  DB_HOST=127.0.0.1
  DB_PORT=3306
  DB_DATABASE=db_lelang_bidlen
  DB_USERNAME=root
  DB_PASSWORD=

5. **Generate Application Key**
   ```bash
   php artisan key:generate

6. **Migrasi Database & Seeding**
   (Pastikan database db_lelang_bidlen sudah dibuat di MySQL)
   ```bash
   php artisan migrate --seed

7. **Tautkan Storage (Sangat Penting untuk Gambar)**
   Perintah ini wajib dijalankan agar gambar barang lelang dapat diakses oleh publik.
   ```bash
   php artisan storage:link

8. **Jalankan Server Lokal**
   Buka dua terminal, lalu jalankan perintah berikut secara bersamaan:

    Terminal 1 (Menjalankan server PHP):
   ```bash
   php artisan serve

  Terminal 2 (Menjalankan compiler Tailwind CSS):
   ```bash
  npm run dev

9. **Akses Aplikasi**
    Buka browser dan akses: http://localhost:8000

   **🔑 Akun Uji Coba (Default Login)**

   Jika Anda menjalankan php artisan migrate --seed, Anda dapat masuk menggunakan kredensial berikut:
  
Peran	        Username	      Password
Administrator	admin_bidlen	  password
Petugas	      petugas_bidlen	password
Masyarakat	  user_demo	      password

🛠️ Tech Stack & Library
- Framework: Laravel
- Frontend: Blade Templating Engine, HTML5
- Styling: Tailwind CSS
- Database: MySQL
- Icons: Google Material Symbols

👨‍💻 Pengembang
Dikembangkan dengan penuh dedikasi oleh kelompok:
**ZenithCodeCollective**

- SMKN 7 Baleendah

- Jurusan Pengembangan Perangkat Lunak dan Gim (PPLG)

Dibuat untuk keperluan edukasi dan pemenuhan standar Uji Kompetensi Keahlian (UKK).

### Tips Tambahan Sebelum Push ke GitHub:
1. Jangan lupa ganti teks `USERNAME_GITHUB_ANDA` di kode atas dengan *username* GitHub lu yang asli.
2. README ini udah gua kasih peringatan khusus di nomor 7 soal **`storage:link`** biar penguji lu nanti nggak bingung kalau gambarnya nggak muncul pas mereka *testing* aplikasi lu di laptop mereka. 

Tinggal *commit* dan *push*, halaman depan repositori lu bakal langsung kelihatan super rapi!
