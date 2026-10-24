# B1. Identifikasi dan Klasifikasi Karakteristik

Penanggung jawab : Muh.Fajrin






## 1. Identifikasi Kandidat Karakteristik

Karakteristik arsitektur merupakan ciri atau kebutuhan penting yang memengaruhi rancangan, pengembangan, dan pengoperasian suatu sistem.

Kategori karakteristik yang digunakan:
- **Operasional:** berkaitan dengan perilaku sistem ketika digunakan.
- **Struktural:** berkaitan dengan susunan komponen dan hubungan antarkomponen.
- **Lintas sektor:** berkaitan dengan kebutuhan yang memengaruhi berbagai bagian atau fungsi organisasi.

Sifat karakteristik dibedakan menjadi:
- **Eksplisit:** dinyatakan secara langsung dalam kebutuhan atau kebijakan.
- **Implisit:** tidak dinyatakan secara langsung, tetapi dapat disimpulkan dari kebutuhan organisasi.

| No. | Karakteristik | Kategori | Sifat | Alasan |
|---|---|---|---|---|
| 1 | Kinerja (*Performance*) | Operasional | Eksplisit | Sistem harus merespons permintaan pengguna dalam waktu yang dapat diterima. |
| 2 | Keamanan (*Security*) | Lintas sektor | Eksplisit | Sistem harus melindungi data dan membatasi akses berdasarkan hak pengguna. |
| 3 | Skalabilitas (*Scalability*) | Struktural | Implisit | Arsitektur perlu mengakomodasi peningkatan jumlah pengguna dan volume data. |
| 4 | Ketersediaan (*Availability*) | Operasional | Eksplisit | Sistem diharapkan dapat digunakan ketika dibutuhkan dan meminimalkan waktu henti. |
| 5 | Kemudahan Pemeliharaan (*Maintainability*) | Struktural | Implisit | Perubahan fitur dan perbaikan sebaiknya dapat dilakukan tanpa mengganggu keseluruhan sistem. |
| 6 | Interoperabilitas (*Interoperability*) | Lintas sektor | Eksplisit | Sistem perlu bertukar data dengan aplikasi atau unit organisasi lain. |
| 7 | Keandalan (*Reliability*) | Operasional | Implisit | Sistem diharapkan beroperasi secara konsisten dan menghasilkan keluaran yang benar. |
| 8 | Kemudahan Penggunaan (*Usability*) | Operasional | Eksplisit | Antarmuka perlu mudah dipahami agar pengguna dapat menyelesaikan tugas secara efektif. |
| 9 | Modularitas (*Modularity*) | Struktural | Implisit | Pemisahan sistem menjadi modul membantu mengurangi ketergantungan antarkomponen. |
| 10 | Konsistensi Data dan Proses | Lintas sektor | Implisit | Berbagai unit organisasi perlu menggunakan definisi, aturan, dan data yang selaras. |



## 2. Tiga Ciri Karakteristik Arsitektur sebagai Alat Uji

Karakteristik diuji menggunakan tiga ciri berikut:

1. **Dampak terhadap keputusan arsitektur:** karakteristik memengaruhi pemilihan teknologi, pola arsitektur, atau komponen sistem.
2. **Dapat diuji atau diukur:** karakteristik dapat dinilai menggunakan indikator atau kriteria penerimaan.
3. **Dampak lintas komponen:** karakteristik memengaruhi beberapa bagian sistem atau keputusan jangka panjang.

| No. | Karakteristik | Dampak pada Arsitektur | Dapat Diuji | Dampak Lintas Komponen |
|---|---|---|---|---|
| 1 | Kinerja | Ya | Ya, melalui pengukuran waktu respons | Ya |
| 2 | Keamanan | Ya | Ya, melalui pengujian hak akses | Ya |
| 3 | Skalabilitas | Ya | Ya, melalui uji beban | Ya |
| 4 | Ketersediaan | Ya | Ya, melalui pengukuran waktu aktif | Ya |
| 5 | Kemudahan Pemeliharaan | Ya | Ya, melalui pengujian perubahan | Ya |
| 6 | Interoperabilitas | Ya | Ya, melalui pengujian integrasi | Ya |
| 7 | Keandalan | Ya | Ya, melalui pengujian kegagalan | Ya |
| 8 | Kemudahan Penggunaan | Ya | Ya, melalui pengujian pengguna | Dapat bervariasi |
| 9 | Modularitas | Ya | Ya, melalui analisis ketergantungan | Ya |
| 10 | Konsistensi Data dan Proses | Ya | Ya, melalui validasi data | Ya |



## 3. Pemilihan Tiga Karakteristik Pendorong

### 3.1 Keamanan (*Security*)

Keamanan dipilih karena sistem informasi dapat menyimpan data penting dan melayani berbagai jenis pengguna dengan hak akses berbeda.

- **Alasan:** kelemahan keamanan dapat menyebabkan kebocoran data dan penyalahgunaan akses.
- **Pengaruh terhadap arsitektur:** menentukan mekanisme autentikasi, otorisasi, enkripsi, dan audit.
- **Cara pengujian:** pengujian hak akses, pengujian keamanan, dan pemeriksaan jejak audit.

### 3.2 Kinerja (*Performance*)

Kinerja dipilih karena sistem harus memberikan respons yang memadai agar pengguna dapat bekerja secara efektif.

- **Alasan:** waktu respons yang lambat dapat menghambat proses bisnis dan menurunkan produktivitas.
- **Pengaruh terhadap arsitektur:** memengaruhi pemilihan teknologi, strategi caching, desain basis data, dan distribusi beban.
- **Cara pengujian:** mengukur waktu respons, throughput, dan penggunaan sumber daya.

### 3.3 Skalabilitas (*Scalability*)

Skalabilitas dipilih karena kebutuhan organisasi dapat berkembang dari sisi jumlah pengguna, volume data, dan jumlah transaksi.

- **Alasan:** sistem yang tidak mampu berkembang dapat mengalami penurunan kinerja atau membutuhkan perubahan arsitektur yang mahal.
- **Pengaruh terhadap arsitektur:** memengaruhi pemisahan layanan, desain basis data, dan distribusi beban.
- **Cara pengujian:** menjalankan uji beban bertahap dan mengevaluasi kemampuan sistem mempertahankan target kinerja saat beban meningkat.




<!-- Penanggung jawab: [nama] -->
<!-- Yang diminta: Daftar 8-10 kandidat karakteristik, dengan kategori (operasional, struktural, lintas sektor) dan alasan. -->
<!-- Hapus komentar ini setelah bagian selesai. -->

