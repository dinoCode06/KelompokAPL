# BAB IV. Penutup

<!-- Kesimpulan dan saran. Penanggung jawab: [Muh Fadhil Aqila Salzabil] -->

## 4.1 Kesimpulan

Berdasarkan hasil analisis dan perancangan arsitektur pada Layanan Pendaftaran dan Perubahan Plan (Core Subscription & Billing Subsystem), dapat disimpulkan bahwa:

1. Identifikasi Konteks dan ASR: Pemetaan konteks teknis, proyek, bisnis, dan profesional berhasil merumuskan batasan serta kebutuhan arsitektural utama (ASR). Sistem membutuhkan kepatuhan keamanan ketat (PCI-DSS), toleransi kegagalan operasional (zero-downtime), dan latensi pemrosesan yang rendah ($p99 < 2.0$ detik pada beban puncak 5.000 TPS).

2. Keputusan Arsitektur Terintegrasi: Penerapan pola Event Sourcing (ADR-01) menjamin audit trail data keuangan yang bersifat immutable, sementara pola Circuit Breaker (ADR-02) berhasil mencegah hilangnya ketersediaan layanan akibat dampak domino (cascading failures) dari integrasi vendor payment gateway eksternal.

3. Penyelarasan Mutu dan Trade-off: Berdasarkan standar ISO/IEC 25010, tiga karakteristik pendorong utama (Performance, Availability, dan Data Integrity) telah berhasil dipetakan ke dalam ukuran numerik terukur. Analisis trade-off secara tegas memprioritaskan Keamanan dan Integritas Data dibanding efisiensi performa mentah guna menjaga kepatuhan dan keandalan transaksi keuangan.
   
## 4.2 Saran

1. Pelaksanaan Test Chaos Engineering: Tim Site Reliability Engineering (SRE) disarankan untuk rutin menjalankan skenario Chaos Engineering (seperti simulasi network latency injection dan node drop) di lingkungan staging untuk memastikan ambang batas Circuit Breaker dan mekanisme failover otomatis bekerja sesuai ekspektasi.

2. Pemantauan Biaya Otomatis (FinOps): Mengingat adanya batasan anggaran operasional cloud, perlu diimplementasikan perangkat pemantauan biaya komputasi real-time yang terintegrasi dengan mekanisme auto-scaling Kubernetes agar pemanfaatan sumber daya tetap berada di bawah ambang anggaran bisnis yang ditentukan.

3. Pemberlakuan Review ADR Terjadwal: Dokumen Architecture Decision Record (ADR) hendaknya ditinjau ulang secara berkala setiap 6 bulan oleh Architecture Review Board (ARB) untuk mengevaluasi apakah asumsi teknologi dan konteks bisnis yang digunakan masih relevan dengan perkembangan platform SaaS di masa mendatang.
