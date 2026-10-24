# A4. Kebutuhan Signifikan (ASR)

Penanggung jawab : Muh.Fajrin


## 1. Identifikasi Kebutuhan Signifikan

ASR (*Architecturally Significant Requirements*) adalah kebutuhan yang memiliki pengaruh besar terhadap keputusan desain dan struktur arsitektur sistem. Kebutuhan ini dapat berupa kebutuhan fungsional, atribut kualitas, atau batasan sistem.

| No. | Jenis Kebutuhan | Kebutuhan Signifikan (ASR) | Alasan Mengapa Memengaruhi Arsitektur |
|---|---|---|---|
| 1 | Fungsional | Sistem harus menyediakan fitur login dan pengelolaan hak akses pengguna. | Kebutuhan ini memengaruhi desain autentikasi, otorisasi, pengelolaan identitas, dan perlindungan data. |
| 2 | Atribut Kualitas | Sistem harus memberikan waktu respons yang cepat ketika pengguna mengakses fitur utama. | Kebutuhan ini memengaruhi pemilihan teknologi, desain basis data, strategi caching, dan komunikasi antarkomponen. |
| 3 | Batasan | Sistem harus menggunakan teknologi atau basis data yang telah ditetapkan oleh organisasi. | Batasan ini memengaruhi pemilihan teknologi, integrasi, struktur sistem, dan biaya pemeliharaan. |

## 2. Penjelasan Kebutuhan Signifikan

### 2.1 Kebutuhan Fungsional: Login dan Hak Akses

Sistem harus menyediakan fitur login dan pengelolaan hak akses agar hanya pengguna yang berwenang dapat mengakses fitur dan data tertentu.

**Alasan signifikansi:** kebutuhan ini menentukan bagaimana identitas pengguna dikelola, bagaimana hak akses diterapkan, dan bagaimana data dilindungi. Oleh karena itu, mekanisme keamanan perlu dipertimbangkan sejak tahap perancangan arsitektur.

### 2.2 Atribut Kualitas: Kinerja Sistem

Sistem harus mampu memberikan respons yang memadai ketika pengguna menjalankan fitur utama.

**Alasan signifikansi:** kebutuhan kinerja memengaruhi desain basis data, pemrosesan permintaan, komunikasi antarkomponen, dan strategi caching. Jika tidak dipertimbangkan sejak awal, sistem dapat mengalami keterlambatan ketika jumlah pengguna meningkat.

### 2.3 Batasan: Penggunaan Teknologi yang Ditentukan

Sistem harus menggunakan teknologi atau basis data yang telah ditetapkan oleh organisasi.

**Alasan signifikansi:** batasan teknologi memengaruhi pilihan desain, kompatibilitas, integrasi, pemeliharaan, dan kebutuhan sumber daya. Arsitektur harus dirancang agar tetap memenuhi kebutuhan sistem dalam batasan tersebut.




<!-- Penanggung jawab: [nama] -->
<!-- Yang diminta: Minimal 3 ASR beserta alasan kebutuhan itu signifikan secara arsitektural. -->
<!-- Hapus komentar ini setelah bagian selesai. -->

