# Ringkasan Wawancara 02

- **Tanggal:** 21-10-2026
- **Responden (peran saja):** Staf pengembang sistem akademik (analis sistem & *developer*)
- **Pewawancara:** [Ihyanul Hakim]
- **Layanan yang dibahas:** Layanan wisuda dan ijazah (pendaftaran, verifikasi berkas, jadwal, dan pengambilan ijazah)

## Pertanyaan dan ringkasan jawaban

| Pertanyaan | Ringkasan jawaban |
| :--- | :--- |
| Apa tantangan teknis terbesar dalam mengembangkan dan memelihara modul wisuda dan ijazah? | Aturan syarat berkas wisuda dan format cetakan blangko ijazah terkadang berubah menjelang periode wisuda, sehingga butuh aturan bisnis (*business rules*) yang jelas sejak awal. |
| Bagaimana keterkaitan layanan wisuda ini dengan modul lain di SIAKAD? | Modul wisuda sangat bergantung pada data kelulusan yudisium, nilai transkrip, serta status bebas tunggakan dari modul keuangan agar mahasiswa yang belum memenuhi syarat otomatis tertahan. |
| Apa kebutuhan utama tim pengembang agar sistem mudah diuji dan dikembangkan? | Dokumentasi skema *database* SIAKAD dan API yang lengkap, serta arsitektur kode yang modular agar perubahan *template* ijazah tidak merusak modul akademik lainnya. |

## Temuan yang dipakai pada laporan

- Kebutuhan utama **S2 (Tim Pengembang Sistem)** pada `A2-stakeholder.md`: kepastian aturan bisnis syarat berkas, penjadwalan, format ijazah, serta dokumentasi integrasi *database* SIAKAD.
- Ekspektasi kualitas *Modularity*, *Testability*, dan *Maintainability* pada pemetaan ISO/IEC 25010 (perubahan aturan berkas atau *template* ijazah dapat diterapkan < 2 hari kerja tanpa mengganggu modul lain).
