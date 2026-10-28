
# ADR-001: Arsitektur Aplikasi Web Terpusat

- **Status:** Diterima
- **Tanggal:** 28-10-2026
- **Pengambil keputusan:** Tim Pengembang Sistem

## Context

Sistem Layanan Wisuda BAA UMI membutuhkan platform untuk mendukung:

- Pendaftaran wisuda.
- Pengunggahan dan verifikasi berkas.
- Pengelolaan jadwal layanan.
- Informasi pengambilan dokumen.

Arsitektur harus mudah diakses, aman, dan mudah dipelihara. Keputusan ini berkaitan dengan ASR pada A4, terutama aksesibilitas dan pemeliharaan sistem.

## Decision

Kami akan menggunakan arsitektur aplikasi web terpusat dengan komponen berikut:

- **Frontend:** HTML, CSS, dan JavaScript.
- **Backend:** PHP untuk memproses logika bisnis.
- **Database:** MySQL untuk menyimpan data sistem.
- **Kontrol akses:** Pemisahan hak akses mahasiswa dan admin.

## Consequences

**Dampak positif:**
- Sistem dapat diakses melalui browser.
- Pengelolaan data lebih terpusat.
- Fitur lebih mudah dikembangkan.
- Pembaruan sistem lebih mudah dilakukan.

**Dampak negatif:**
- Sistem bergantung pada server dan internet.
- Gangguan server dapat memengaruhi pengguna.
- Pemeliharaan keamanan perlu dilakukan berkala.

**Trade-off:** Kemudahan akses dan pengelolaan terpusat dipilih dengan konsekuensi ketergantungan pada server.

## Compliance

- Meninjau kode agar sesuai dengan arsitektur yang ditetapkan.
- Menguji pendaftaran, verifikasi, dan penjadwalan.
- Memastikan hak akses mahasiswa dan admin berjalan benar.
- Melakukan pencadangan data secara berkala.
