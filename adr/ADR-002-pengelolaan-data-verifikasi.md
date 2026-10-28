
# ADR-002: Pengelolaan Data dan Verifikasi Berkas

- **Status:** Diterima
- **Tanggal:** 28-10-2026
- **Pengambil keputusan:** Tim Pengembang Sistem

## Context

Sistem Layanan Wisuda BAA UMI membutuhkan pengelolaan data mahasiswa, pendaftaran, dokumen persyaratan, hasil verifikasi, jadwal layanan, dan status pengambilan dokumen.

Keputusan ini berkaitan dengan ASR pada A4 sebagai berikut:

- **ASR-1 (Fungsional):** Kebutuhan login dan pengelolaan hak akses memengaruhi cara sistem membatasi akses terhadap data mahasiswa dan dokumen.
- **ASR-2 (Atribut Kualitas):** Kebutuhan waktu respons cepat memengaruhi desain query, struktur tabel, dan pengambilan data.
- **ASR-3 (Batasan):** Ketentuan organisasi mengenai teknologi atau basis data memengaruhi pemilihan sistem penyimpanan data.

Pengelolaan data yang tidak terstruktur dapat menyebabkan duplikasi, kesalahan pencatatan, dan kesulitan menelusuri status permohonan.

## Consequences

**Dampak positif:**
- Data pendaftaran tersimpan secara terstruktur.
- Duplikasi dan kesalahan pencatatan dapat dikurangi.
- Proses verifikasi lebih mudah dipantau.
- Akses terhadap dokumen pribadi dapat dibatasi.
- Perubahan status layanan dapat ditelusuri.

**Dampak negatif:**
- Perancangan database membutuhkan analisis kebutuhan yang matang.
- Penyimpanan dan pencadangan dokumen membutuhkan ruang tambahan.
- Perubahan struktur tabel dapat memerlukan migrasi data.
- Validasi dan kontrol akses menambah kompleksitas pengembangan.

**Trade-off:** Konsistensi dan keamanan data diprioritaskan dengan konsekuensi kebutuhan pengelolaan database dan validasi yang lebih ketat.

## Compliance

- Memeriksa relasi tabel, primary key, foreign key, dan integritas data.
- Menguji proses pendaftaran, unggah dokumen, verifikasi, dan perubahan status.
- Memastikan mahasiswa dan admin hanya dapat mengakses data sesuai haknya.
- Memvalidasi jenis dan ukuran dokumen yang diunggah.
- Menyimpan kata sandi menggunakan metode hashing yang aman.
- Melakukan pencadangan dan pengujian pemulihan database secara berkala.

