
# ADR-001: Arsitektur Aplikasi Web Terpusat

- **Status:** Diterima
- **Tanggal:** 28-10-2026
- **Pengambil keputusan:** Tim Pengembang Sistem

## Context

Sistem Layanan Wisuda BAA UMI membutuhkan platform untuk mendukung pendaftaran wisuda, pengunggahan dokumen persyaratan, verifikasi berkas, penjadwalan, dan pengambilan dokumen.

Keputusan ini berkaitan dengan ASR pada A4 sebagai berikut:

- **ASR-1 (Fungsional):** Kebutuhan login dan pengelolaan hak akses memengaruhi rancangan autentikasi serta pemisahan akses mahasiswa dan admin.
- **ASR-2 (Atribut Kualitas):** Kebutuhan waktu respons yang cepat memengaruhi rancangan pemrosesan permintaan dan komunikasi antarkomponen.
- **ASR-3 (Batasan):** Teknologi yang ditetapkan organisasi membatasi pilihan bahasa pemrograman, framework, dan teknologi pendukung.

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
