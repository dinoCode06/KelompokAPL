# BAB I. Pendahuluan

Penanggung jawab : Muh.Fajrin

<!-- Gambaran subsistem dan layanan inti yang ditugaskan, ruang lingkup, dan sumber data. -->
<!-- Penanggung jawab: [nama] -->

## 1.1 Gambaran layanan inti
Subsistem yang dibahas dalam tugas ini adalah **Academic Management**, khususnya layanan wisuda dan ijazah. Subsistem ini merupakan bagian dari sistem pengelolaan akademik yang mendukung proses administrasi mahasiswa menjelang kelulusan hingga pengambilan ijazah.

Layanan inti yang menjadi fokus pembahasan meliputi empat proses utama, yaitu:

1. **Pendaftaran wisuda:** layanan untuk mengajukan pendaftaran wisuda oleh mahasiswa yang telah memenuhi persyaratan kelulusan.
2. **Verifikasi berkas:** layanan untuk memeriksa kelengkapan dan kesesuaian dokumen persyaratan wisuda dan ijazah.
3. **Penjadwalan wisuda:** layanan untuk mengelola dan menyampaikan informasi jadwal pelaksanaan wisuda kepada mahasiswa yang telah memenuhi persyaratan.
4. **Pengambilan ijazah:** layanan untuk mengelola proses penyerahan ijazah kepada lulusan setelah persyaratan administrasi terpenuhi.
   
Keempat layanan tersebut saling berkaitan untuk mendukung proses administrasi kelulusan yang teratur, akurat, dan efisien. Dengan adanya pengelolaan layanan secara terintegrasi, informasi mengenai status pendaftaran, hasil verifikasi, jadwal wisuda, dan status pengambilan ijazah diharapkan dapat dikelola dengan lebih baik.


## 1.2 Ruang lingkup (3-5 kasus penggunaan)
Ruang lingkup subsistem Academic Management difokuskan pada layanan wisuda dan ijazah. Pembahasan mencakup lima kasus penggunaan utama berikut.

| No. | Kasus Penggunaan | Aktor | Deskripsi |
|---|---|---|---|
| 1 | Pendaftaran Wisuda | Mahasiswa | Mahasiswa mengisi dan mengirim formulir pendaftaran wisuda melalui sistem. |
| 2 | Verifikasi Berkas | Staf Akademik | Staf akademik memeriksa kelengkapan dan kesesuaian dokumen persyaratan wisuda. |
| 3 | Pengelolaan Jadwal Wisuda | Admin Akademik | Admin mengatur dan memperbarui jadwal pelaksanaan wisuda. |
| 4 | Melihat Status dan Jadwal Wisuda | Mahasiswa | Mahasiswa melihat status pendaftaran, hasil verifikasi berkas, dan jadwal wisuda. |
| 5 | Pengambilan Ijazah | Staf Akademik dan Lulusan | Staf memeriksa persyaratan dan mencatat penyerahan ijazah kepada lulusan. |


## 1.3 Sumber data

### 1. Pengalaman sebagai Pengguna

Pengumpulan data dilakukan dengan mencoba sendiri layanan akademik yang tersedia, seperti SIAKAD, SPADA UMI-Kalam, atau layanan lain yang relevan. Kelompok mencatat alur penggunaan, kendala yang ditemukan, serta mengumpulkan tangkapan layar sebagai dokumentasi pendukung. Pengamatan difokuskan pada proses pendaftaran wisuda, verifikasi berkas, informasi jadwal wisuda, dan pengambilan ijazah, sejauh layanan tersebut dapat diakses.

### 2. Informasi Publik

Data juga diperoleh dari informasi publik yang diterbitkan oleh Universitas Muslim Indonesia melalui situs resmi [umi.ac.id](https://umi.ac.id), panduan akademik, pengumuman wisuda, dan peraturan yang relevan. Informasi tersebut digunakan untuk memahami persyaratan administrasi, prosedur layanan, jadwal wisuda, dan ketentuan pengambilan ijazah.

### 3. Wawancara atau survei singkat
| Kode | Stakeholder | Kelompok | Peran dalam Layanan | Kebutuhan Utama (Main Needs) | Ekspektasi Kualitas (Quality Attributes) | Prioritas |
| :---: | :--- | :--- | :--- | :--- | :--- | :---: |
| **S1** | **Mahasiswa Tingkat Akhir / Calon Wisudawan** | Pengguna Akhir | Pendaftar wisuda dan penerima ijazah | • Pendaftaran wisuda dan unggah berkas syarat secara *online*.<br>• Pelacakan status verifikasi berkas secara *real-time* (diterima/revisi).<br>• Informasi jadwal sesi wisuda, nomor kursi, dan jadwal antrean pengambilan ijazah. | **Usability & Availability:** Antarmuka intuitif (ramah *mobile*), notifikasi status otomatis, dan sistem tidak *down* saat pendaftaran dibuka. | **Tinggi** |
| **S2** | **Tim Pengembang Sistem (System Analyst, Developer, QA)** | Tim Pengembang | Perancang, pembuat, dan penguji modul | • Spesifikasi aturan bisnis (*business rules*) syarat berkas, penjadwalan, dan format ijazah yang jelas.<br>• Dokumentasi skema *database* SIAKAD untuk integrasi status kelulusan/yudisium dan keuangan. | **Modularity & Testability:** Arsitektur kode modular, dokumentasi API jelas, dan mudah diuji sebelum rilis. | **Tinggi** |
| **S3** | **Staf Biro Administrasi Akademik (BAAK) – Unit Wisuda & Ijazah** | Tim Operasional | Pengelola operasional harian layanan wisuda & ijazah | • Fitur verifikasi berkas mahasiswa dan pemberian catatan revisi.<br>• Pengaturan kuota/sesi jadwal wisuda dan daftar hadir.<br>• Pencetakan draf/blangko ijazah serta pencatatan status serah terima (pengambilan) ijazah di loket. | **Reliability & Operability:** Proses verifikasi cepat, ekspor data cetak ijazah akurat (bebas *typo*), serta *audit trail* pengambilan ijazah yang jelas. | **Sangat Tinggi** |
| **S4** | **Tim IT Support & Infrastruktur Kampus** | Tim Operasional | Pemelihara server, jaringan, dan *helpdesk* teknis | • Pemantauan kapasitas server (*server load*) dan penyimpanan file berkas wisuda.<br>• Sistem *backup* rutin dan log *error* untuk penanganan kendala teknis. | **Maintainability & Scalability:** Sistem mudah dipantau (*monitoring*) dan kapasitas penyimpanan dokumen teroptimasi. | **Rendah** |
| **S5** | **Wakil Rektor Bidang Akademik (WR I) & Kepala BAAK** | Manajer Bisnis | Pemilik proses bisnis (*Process Owner*) & penentu kebijakan akademik | • *Dashboard* eksekutif untuk memantau jumlah pendaftar, keterisian kuota jadwal wisuda, dan progres verifikasi berkas.<br>• Otorisasi penetapan jadwal wisuda dan pengesahan daftar lulusan penerima ijazah. | **Data Integrity & Security:** Data lulusan 100% valid dan konsisten, keamanan akses berbasis peran (*Role-Based Access Control*), serta patuh kalender akademik. | **Sangat Tinggi** |
| **S6** | **Kemdiktisaintek (PDDikti & Sistem PISN)** | Pihak Eksternal | Regulator nasional penomoran & keabsahan ijazah | • Sinkronisasi data kelulusan mahasiswa dengan PDDikti.<br>• Pemenuhan syarat pengajuan **PIN (Penomoran Ijazah Nasional)** agar ijazah sah dan terdaftar secara nasional. | **Interoperability & Compliance:** Format data ekspor/API sesuai standar skema PDDikti/PISN dan validasi syarat SKS/masa studi terpenuhi. | **Tinggi** |


### 3. Pengamatan Langsung

Pengamatan langsung dilakukan untuk memahami alur layanan wisuda dan ijazah pada subsistem Academic Management di Universitas Muslim Indonesia (UMI). Pengamatan difokuskan pada proses pendaftaran wisuda, verifikasi berkas, penyampaian informasi jadwal wisuda, dan pengambilan ijazah.

Aspek yang diamati meliputi:

1. **Pendaftaran wisuda:** cara mahasiswa memperoleh informasi persyaratan dan melakukan pendaftaran.
2. **Verifikasi berkas:** proses pemeriksaan kelengkapan dokumen dan penyampaian informasi apabila terdapat berkas yang perlu diperbaiki.
3. **Informasi jadwal wisuda:** cara informasi jadwal disampaikan dan diakses oleh mahasiswa.
4. **Pengambilan ijazah:** prosedur yang harus dipenuhi lulusan serta proses pencatatan penyerahan ijazah.


<!-- Pengalaman pengguna, informasi publik, wawancara responden. Tanpa identitas pribadi. -->
