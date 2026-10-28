
# ADR-002: Pengelolaan Data dan Verifikasi Berkas

- **Status:** Diterima
- **Tanggal:** 28-10-2026
- **Pengambil keputusan:** Tim Pengembang Sistem

## Context

Sistem Layanan Wisuda BAA UMI membutuhkan pengelolaan data pendaftaran mahasiswa, dokumen persyaratan, hasil verifikasi, jadwal layanan, dan status pengambilan dokumen. Data harus konsisten, mudah ditelusuri, dan terlindungi dari akses yang tidak berwenang.

Keputusan ini berkaitan dengan ASR pada A4, khususnya kebutuhan integritas data, keamanan informasi, dan kemudahan pemeliharaan. Pengelolaan data yang tidak terstruktur dapat menyebabkan duplikasi, kesalahan pencatatan, dan kesulitan dalam menelusuri status permohonan.

## Decision

Kami akan menggunakan database relasional MySQL untuk menyimpan dan mengelola data sistem.

Kami akan menerapkan:

- **Relasi database:** Menghubungkan data pengguna, pendaftaran, dokumen, verifikasi, jadwal, dan pengambilan.
- **Validasi data:** Memeriksa kelengkapan dan kesesuaian data sebelum disimpan.
- **Kontrol akses:** Membatasi akses data berdasarkan peran mahasiswa dan admin.
- **Keamanan dokumen:** Menyimpan berkas pada lokasi yang tidak dapat diakses langsung oleh publik.
- **Log aktivitas:** Mencatat perubahan status penting untuk memudahkan penelusuran.

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

