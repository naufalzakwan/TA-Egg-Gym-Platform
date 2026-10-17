# Egg Gym

Tugas Akhir — D3 Teknik Informatika, Politeknik Negeri Pontianak
Oleh: Muhammad Naufal Zakwan (3202316112)

**Tech Stack:** Laravel (PHP) · Flutter (Dart) · MySQL · Pakasir Payment Gateway

---

Egg Gym merupakan sistem informasi layanan gym yang terdiri atas aplikasi mobile Flutter untuk Member dan Personal Trainer serta Web Admin berbasis Laravel.

## Akun Demo

Akun berikut tersedia setelah database diisi menggunakan seeder (`php artisan migrate:fresh --seed`).

| Peran | Email | Password | Akses |
|---|---|---|---|
| Admin | admin@egggym.com | admin12345 | Web Admin |
| Member | member@egggym.com | member12345 | Aplikasi mobile |
| Personal Trainer | adrian@egggym.com | trainer12345 | Aplikasi mobile |

Akun Personal Trainer lain yang dapat digunakan adalah elena@egggym.com dan julian@egggym.com dengan password yang sama, yaitu trainer12345.

## URL Akses

- Halaman login Web Admin: `http://localhost:8000/admin/login`
- Dashboard Web Admin setelah login: `http://localhost:8000/admin`
- API lokal: `http://localhost:8000/api/v1`

Login Member dan Personal Trainer dilakukan langsung melalui halaman Login pada aplikasi mobile, bukan melalui browser.

Jika aplikasi dijalankan pada perangkat fisik, ganti `localhost` dengan alamat IP komputer pada jaringan Wi-Fi yang sama, misalnya `http://192.168.1.19:8000`. Pastikan alamat tersebut juga tercantum pada `egg_gym/lib/data/services/backend_api_config.dart`.

## Menjalankan Sistem

### 1. Menjalankan Backend dan Web Admin

Buka terminal pada folder `egg_gym_api`, kemudian jalankan:

```bash
composer install
php artisan migrate:fresh --seed
php artisan storage:link
php artisan serve --host=0.0.0.0 --port=8000
```

Pastikan konfigurasi database pada `egg_gym_api/.env` sudah benar sebelum menjalankan migrasi. Perintah `migrate:fresh` menghapus seluruh data pada database terkait dan mengisinya kembali dengan data demo.

### 2. Menjalankan Aplikasi Mobile

Buka terminal lain pada folder `egg_gym`, kemudian jalankan:

```bash
flutter pub get
flutter devices
flutter run -d <device_id>
```

Backend Laravel harus tetap berjalan agar aplikasi dapat login dan mengambil data. Untuk emulator Android, aplikasi juga menyediakan kandidat alamat `http://10.0.2.2:8000`.

## Langkah Singkat Penggunaan

### Guest
- Buka aplikasi mobile.
- Pada halaman Login, pilih Lanjut sebagai Guest.
- Lihat informasi publik seperti paket membership, Personal Trainer, alat gym, dan jam operasional.
- Pilih Daftar jika ingin membuat akun Member atau kembali ke halaman Login untuk masuk.

### Member
- Masuk melalui aplikasi mobile menggunakan akun Member pada tabel akun demo atau pilih Daftar untuk membuat akun baru.
- Gunakan menu Beranda untuk melihat ringkasan membership dan layanan yang tersedia.
- Buka menu Membership, pilih paket, lanjutkan ke checkout, lalu ikuti instruksi pembayaran Pakasir. Status pembayaran dapat dipantau melalui riwayat transaksi.
- Pilih Personal Trainer, tentukan jadwal yang tersedia, jumlah sesi, dan kirim permintaan booking.
- Setelah Trainer mengonfirmasi booking, unggah bukti pembayaran sesi PT sesuai informasi pembayaran Trainer.
- Pantau jadwal, status booking, Program PT, latihan mandiri, progres fisik, dan notifikasi melalui menu yang tersedia.
- Gunakan menu Profil untuk memperbarui data akun atau keluar dari aplikasi.

### Personal Trainer
- Masuk melalui aplikasi mobile menggunakan salah satu akun Personal Trainer pada tabel akun demo.
- Buka menu Jadwal untuk mengatur ketersediaan serta melihat permintaan booking dari Member.
- Buka detail booking, kemudian konfirmasi atau tolak permintaan sesuai jadwal.
- Setelah Member mengunggah bukti pembayaran, periksa dan verifikasi bukti tersebut.
- Buat Program PT untuk Member yang pembayarannya telah diverifikasi, kemudian tambahkan sesi dan latihan.
- Saat sesi berlangsung, catat progres latihan Member dan selesaikan sesi agar sesi berikutnya dapat terbuka.
- Gunakan menu Klien, Program, dan Profil untuk memantau Member, mengelola program, dan memperbarui informasi akun.

### Admin
- Buka `http://localhost:8000/admin/login` melalui browser.
- Masuk menggunakan email admin@egggym.com dan password admin12345.
- Gunakan dashboard untuk melihat ringkasan data operasional.
- Kelola paket membership, akun Member, profil Personal Trainer, alat gym, dan jam operasional melalui menu Web Admin.
- Pantau booking, program latihan, progres Member, transaksi, dan laporan.
- Gunakan menu Notifikasi untuk mengirim informasi kepada pengguna dan menu Audit Trail untuk melihat riwayat aktivitas sistem.
- Klik Logout setelah selesai menggunakan Web Admin.

## Catatan

- Akun Admin hanya digunakan pada Web Admin. Akun Member dan Personal Trainer digunakan pada aplikasi mobile.
- Member baru dapat mendaftar melalui aplikasi, sedangkan akun Personal Trainer dibuat dan dikelola oleh Admin.
- Jika aplikasi gagal terhubung, pastikan backend aktif, perangkat berada pada jaringan yang sama, firewall mengizinkan port 8000, dan alamat IP backend pada konfigurasi mobile sudah sesuai.
- Jangan gunakan akun dan password demo untuk lingkungan production.
