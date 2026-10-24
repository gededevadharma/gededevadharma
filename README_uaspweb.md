# uaspweb — Aplikasi Manajemen Perpustakaan

Aplikasi web manajemen perpustakaan berbasis **CodeIgniter 3**, dibuat
sebagai **UAS mata kuliah Pemrograman Web**. Aplikasi ini mengelola data
buku, peminjam, dan peminjaman, lengkap dengan login dan area admin.

## Fitur

- Login dan autentikasi pengguna (`Auth`)
- Dashboard ringkasan (`Dashboard`)
- CRUD Buku (`Buku`)
- CRUD Peminjam (`Peminjam`)
- CRUD Peminjaman (`Peminjaman`)
- Area admin (`controllers/admin`, `views/admin`)

## Teknologi

- PHP
- CodeIgniter 3
- MySQL
- HTML, CSS, JavaScript

## Struktur

```
uaspweb/
  application/
    controllers/   ← Auth, Buku, Dashboard, Peminjam, Peminjaman, admin/
    models/        ← Buku_model, Peminjam_model, Peminjaman_model, User_model
    views/         ← auth, buku, dashboard, peminjam, peminjaman, admin, templates
    config/        ← database.php, config.php, dan konfigurasi lainnya
  system/          ← framework CodeIgniter
  db_perpus.sql    ← skema + data awal database perpustakaan
  index.php        ← entry point aplikasi
  backend/         ← salinan kedua aplikasi (struktur CodeIgniter yang sama)
  presentasi.html  ← materi presentasi UAS
```

## Instalasi

### 1. Clone repo

```bash
git clone https://github.com/gededevadharma/uaspweb.git
cd uaspweb
```

### 2. Buat database

Import `db_perpus.sql` ke MySQL, lewat phpMyAdmin atau command line:

```bash
mysql -u root -p -e "CREATE DATABASE db_perpus"
mysql -u root -p db_perpus < db_perpus.sql
```

### 3. Atur koneksi database

Edit `application/config/database.php`, sesuaikan dengan MySQL kamu:

```php
'hostname' => 'localhost',
'username' => 'root',
'password' => '',
'database' => 'db_perpus',
```

### 4. Atur base URL

Edit `application/config/config.php`:

```php
$config['base_url'] = 'http://localhost/uaspweb/';
```

## Cara Menjalankan

### Opsi A — XAMPP / Laragon (disarankan)

1. Pindahkan folder `uaspweb` ke `htdocs` (XAMPP) atau `www` (Laragon).
2. Jalankan Apache dan MySQL.
3. Buka `http://localhost/uaspweb/` di browser.

### Opsi B — PHP built-in server

```bash
php -S localhost:8000
```

Lalu buka `http://localhost:8000/` di browser.

## Cara Pakai

1. Buka aplikasi, lalu login lewat halaman Auth.
2. Dari dashboard, buka menu **Buku** untuk menambah, mengubah, atau
   menghapus data buku.
3. Menu **Peminjam** untuk mengelola data peminjam.
4. Menu **Peminjaman** untuk mencatat dan mengelola peminjaman buku.
5. Menu admin tersedia untuk pengelolaan lanjutan.

## Lisensi

MIT (lihat `license.txt`).
