# 💧 SPK Bantuan Air - Weighted Product (WP)

> Sistem Pendukung Keputusan (SPK) untuk menentukan prioritas daerah penerima bantuan air bersih. Dibangun menggunakan framework Laravel dan Filament Panel untuk antarmuka dashboard yang interaktif dan efisien.

---

## 🧠 Pendekatan & Metodologi
Sistem ini menggunakan algoritma **Weighted Product (WP)**. Pemilihan WP didasarkan pada kemampuannya mengevaluasi beberapa alternatif (daerah/desa) terhadap sekumpulan kriteria (tingkat kekeringan, jumlah penduduk, jarak sumber air, dll). 

Keunggulan penerapan WP pada kasus ini adalah penggunaan operasi matematika perkalian yang memberikan pembobotan lebih ketat pada kriteria *cost* dan *benefit*, sehingga daerah dengan tingkat krisis air paling parah akan secara matematis mendominasi hasil akhir (Vektor V).

## 🛠️ Tech Stack
* **Backend:** Laravel 11.x
* **Admin Dashboard & UI:** Filament (TALL Stack: Tailwind CSS, Alpine.js, Laravel, Livewire)
* **Database:** MySQL / PostgreSQL
* **Arsitektur:** Monolith (Tanpa implementasi API Token/Sanctum untuk menjaga efisiensi *resource*)

## ✨ Fitur Utama
1. **Manajemen Kriteria & Bobot:** Admin dapat menyesuaikan bobot untuk masing-masing kriteria (*Benefit* atau *Cost*) secara dinamis melalui dashboard.
2. **Kalkulasi WP Otomatis:** Perhitungan Vektor S (preferensi alternatif) dan Vektor V (nilai akhir) diproses *real-time* berdasarkan data terbaru.
3. **Dashboard Analitik Filament:** Menampilkan *ranking* daerah prioritas yang paling layak mendapatkan bantuan air bersih dalam bentuk tabel interaktif.
4. **Manajemen Alternatif:** CRUD data daerah/desa yang terdampak kekeringan.

## 💻 Cara Instalasi (Local Environment)

Pastikan *environment* lokal sudah mendukung PHP >= 8.2 dan Composer.

1. **Clone repository ini:**
   ```bash
   git clone [https://github.com/Dream23978/UTS_WEB.git](https://github.com/Dream23978/UTS_WEB.git)
   cd UTS_WEB
   
2. Install Dependencies:

Bash
composer install
npm install && npm run build


3. **Setup Environment:**
   Copy file `.env.example` menjadi `.env` lalu konfigurasi koneksi database.
   ```bash
   cp .env.example .env
Generate Key, Migrate & Seed:
Jalankan migrasi untuk membangun skema database Filament dan tabel SPK.

Bash
php artisan key:generate
php artisan migrate:fresh --seed
(Note: Seeder sudah termasuk pembuatan akun Admin Filament default dan data dummy kriteria).

Buat User Admin Filament (Jika tidak menggunakan seeder):

Bash
   php artisan filament:user
Jalankan Aplikasi:

Bash
php artisan serve

   Akses dashboard SPK melalui: `http://localhost:8000/admin`

---

## 🧑‍💻 Pengembang
* **Ferdian Iswara** 
* Sistem Informasi - Universitas Muhammadiyah Pontianak

