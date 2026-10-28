# Ringkasan Wawancara 01

## Informasi Umum
* **Peran Responden**: Mahasiswa tingkat akhir (semester 8 / calon wisudawan)
* **Kelompok Stakeholder**: Pengguna Akhir (S1)
* **Fokus Layanan**: Pendaftaran wisuda, unggah berkas, jadwal wisuda, dan pengambilan ijazah
* **Metode Pengumpulan Data**: Wawancara langsung (tanpa identitas pribadi)

## Kondisi Saat Ini & Kendala yang Dihadapi
* Mahasiswa harus mengunggah banyak dokumen persyaratan wisuda (transkrip sementara, bukti bebas pustaka, pasfoto, dan bukti penyerahan skripsi), namun sering terjadi kegagalan unggah atau halaman lambat diakses saat hari pertama pendaftaran dibuka.
* Ketika ada berkas yang ditolak oleh petugas, mahasiswa sering tidak mengetahui bagian mana yang salah karena tidak ada pemberitahuan otomatis maupun catatan alasan penolakan yang jelas.
* Informasi pembagian sesi wisuda, nomor kursi, serta kepastian kapan ijazah fisik sudah selesai dan siap diambil di loket masih belum terpusat di satu halaman status.

## Kebutuhan Utama & Ekspektasi Kualitas
1. **Kebutuhan Fungsional**:
   * Formulir pendaftaran wisuda dan unggah berkas secara daring yang praktis.
   * Pelacakan status verifikasi berkas secara langsung (*real-time*) beserta alasan revisi jika berkas ditolak.
   * Informasi jadwal sesi wisuda, nomor kursi, dan jadwal antrean loket pengambilan ijazah.
2. **Ekspektasi Kualitas**:
   * **Efisiensi Kinerja & Ketersediaan**: Halaman pendaftaran tetap cepat diakses (< 3 detik) dan tidak mati (*down*) saat diakses ribuan mahasiswa bersamaan.
   * **Kebergunaan (*Usability*)**: Tampilan ramah perangkat seluler (*mobile-friendly*) dan terdapat notifikasi otomatis setiap ada perubahan status berkas.

## Dampak terhadap Rancangan Arsitektur
* Menjadi dasar penetapan target kinerja pemuatan halaman < 3 detik saat beban puncak dan penyediaan fitur pelacakan status berkas bertahap.
