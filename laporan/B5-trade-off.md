# B5. Analisis Trade-off

<!-- Penanggung jawab: [Muh Fadhil Aqila Salzabil] -->
Pasangan Trade-off 1: Keamanan (Security) vs Performa (Performance Efficiency)
Dampak Konflik:
Menerapkan mekanisme keamanan ketat—seperti enkripsi end-to-end (AES-256) pada payload data transaksi sensitif, pemeriksaan token JWT/OAuth2 di setiap lapisan layanan, serta validasi tokenisasi PCI-DSS—menambah beban CPU dan durasi eksekusi algoritma enkripsi. Hal ini secara langsung meningkatkan latensi pemrosesan permintaan (response time) sekitar 15–25% dan menurunkan total throughput transaksi.

Karakteristik yang Didahulukan: Keamanan (Security).

Alasan dan Pertimbangan:
Pada subsistem keuangan dan penagihan, dampak pelanggaran data (data breach) atau manipulasi saldo berpotensi mengakibatkan sanksi hukum dari regulator, pembekuan izin operasional, denda PCI-DSS, serta hilangnya reputasi bisnis secara permanen. Penurunan kinerja akibat enkripsi dapat diatasi secara fungsional melalui teknik pencahayaan memori (caching), optimasi query, dan penambahan alokasi sumber daya CPU (horizontal scaling).

Pasangan Trade-off 2: Integritas Data (Data Integrity) vs Ketersediaan (Availability)
Dampak Konflik:
Sesuai batasan Teorema CAP, untuk menjamin integritas dan konsistensi data yang mutlak (Strong Consistency), sistem harus menggunakan transaksi terdistribusi sinkron (seperti Two-Phase Commit / 2PC) serta synchronous database replication. Jika terjadi kegagalan jaringan (network partition) atau salah satu node basis data mengalami gangguan, sistem secara sengaja menolak atau menunda transaksi baru guna mencegah kondisi split-brain atau pemotongan saldo ganda. Taktik ini menurunkan nilai ketersediaan (availability) runtime sistem.

Karakteristik yang Didahulukan: Integritas Data (Data Integrity).

Alasan dan Pertimbangan:
Gagal memproses transaksi penagihan dan menampilkan pesan kesalahan (graceful failure) jauh lebih dapat diterima daripada transaksi berhasil diproses namun menghasilkan data keuangan yang salah (misalnya saldo terpotong tanpa ada hak langganan yang diperbarui). Ketidakcocokan catatan keuangan membutuhkan biaya rekonsilasi manual yang sangat tinggi dan merusak kepercayaan pelanggan secara fundamental.
