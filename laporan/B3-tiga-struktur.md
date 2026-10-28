# B3. Tiga Struktur Desain

<!-- penanggung jawab: [Muh Fadhil Aqila Salzabil] -->

#### 1. Struktur Modul (*Layered Module Structure*)
Mengatur pengelompokan kode sumber berdasarkan batasan kognitif dan pemisahan tanggung jawab logis (*Separation of Concerns*).

```text
+-------------------------------------------------------------------+
|                     API PRESENTATION LAYER                        |
|   [ SubscriptionController ]        [ PaymentWebhookController ]  |
+----------------------------------+--------------------------------+
                                   |
                                   v (Menyediakan DTO & Validasi Skema)
+-------------------------------------------------------------------+
|                       APPLICATION LAYER                           |
|   [ ProcessPaymentCommandHandler ]   [ UpgradePlanUseCase ]       |
+----------------------------------+--------------------------------+
                                   |
                                   v (Invocations Logika Bisnis murni)
+-------------------------------------------------------------------+
|                         DOMAIN LAYER                              |
|   [ SubscriptionAggregate ]          [ BillingPolicy ]            |
+----------------------------------+--------------------------------+
                                   |
                                   v (Dibalikkan via Dependency Inversion)
+-------------------------------------------------------------------+
|                     INFRASTRUCTURE LAYER                          |
|   [ PostgresEventStoreImpl ]    [ MidtransPaymentGatewayAdapter ] |
+-------------------------------------------------------------------+
Keterangan:
Struktur modul menerapkan prinsip Hexagonal / Clean Architecture untuk mengisolasi aturan bisnis utama (Domain Layer) dari ketergantungan teknologi luar (Infrastructure Layer). Komunikasi antarlapis menggunakan aturan ketergantungan searah ke dalam (Inward Dependency Rule). Dengan demikian, perubahan pada penyedia payment gateway eksternal atau database engine di Infrastructure Layer sama sekali tidak mengganggu atau memerlukan modifikasi pada kode logika transaksi dan perhitungan tagihan di Domain Layer.

2. Struktur Komponen dan Konektor (C&C Structure)
Mengatur entitas runtime komputasi dan jalur/protokol komunikasi data saat sistem beroperasi secara aktif.

+------------------------+
                      |   Client Application   |
                      +-----------+------------+
                                  | HTTPS / JSON (OAuth2 Token)
                                  v
                      +------------------------+
                      |      API Gateway       |
                      +-----------+------------+
                                  | gRPC / Protobuf (Low Latency)
                                  v
                      +------------------------+
                      | Subscription Service   |
                      +-----+------------+-----+
                            |            |
     Publish Transaction    |            | Synchronous Verification
     (Kafka Protocol)       v            v (REST API over TLS)
  +-------------------+-----+   +--------+------------+
  |   Apache Kafka    |         |  Payment Gateway    |
  |  (Message Broker) |         |  (Vendor Eksternal) |
  +---------+---------+         +---------------------+
            |
            | Consume Event (Asynchronous)
            v
  +-------------------+         +---------------------+
  |  Billing Worker   +-------->| PostgreSQL Database |
  |     Service       | SQL     | (Transactional Store|
  +-------------------+         +---------------------+

Keterangan:
Struktur C&C menggambarkan interaksi pemrosesan data secara langsung (runtime execution). Permintaan dari klien diterima oleh API Gateway dan diteruskan ke Subscription Service menggunakan protokol gRPC untuk meminimalkan latensi jaringan. Pemrosesan tagihan berat dan sinkronisasi status dilakukan secara asinkron (non-blocking) melalui antrean pesan Apache Kafka menuju Billing Worker Service, guna mengisolasi kegagalan (fault-isolation) serta menjaga tingkat responsivitas sistem saat terjadi lonjakan beban transaksi.

3. Struktur Alokasi (Deployment Allocation Structure)
Memetakan artefak dan kontainer aplikasi ke elemen infrastruktur fisik/lokasi cloud provider.

+------------------------------------------------------------------------+
|                       KUBERNETES CLUSTER (AWS EKS)                     |
|                                                                        |
|  +---------------------------+    +---------------------------------+  |
|  | Worker Node 1 (AZ-a)      |    | Worker Node 2 (AZ-b)            |  |
|  |  +---------------------+  |    |  +---------------------------+  |  |
|  |  | Subscription Pod A  |  |    |  | Subscription Pod B        |  |  |
|  |  +---------------------+  |    |  +---------------------------+  |  |
|  |  | Billing Worker Pod  |  |    |  | Redis Cache Pod (Replica) |  |  |
|  |  +---------------------+  |    |  +---------------------------+  |  |
|  +---------------------------+    +---------------------------------+  |
+------------------------------------------------------------------------+
                                   |
                                   v AWS VPC Peering (Private Subnet)
+------------------------------------------------------------------------+
|                     MANAGED DATABASE SERVICES                          |
|  +--------------------------------+  +------------------------------+  |
|  | AWS RDS PostgreSQL (Master)    |  | AWS RDS PostgreSQL (Standby) |  |
|  | Zone: us-east-1a               |  | Zone: us-east-1b             |  |
|  +--------------------------------+  +------------------------------+  |
+------------------------------------------------------------------------+

Keterangan:
Struktur alokasi mendeskripsikan penempatan komponen perangkat lunak pada lingkungan fisik dan jaringan Amazon Web Services (AWS). Kontainer aplikasi dijalankan di atas AWS Elastic Kubernetes Service (EKS) yang didistribusikan secara Multi-AZ (Availability Zone) untuk menjamin toleransi terhadap kegagalan tingkat pusat data (datacenter outage). Komponen basis data PostgreSQL diletakkan pada privat subnet terpisah dengan konfigurasi replikasi sinkron Master-Standby guna memenuhi persyaratan pemulihan data Zero Data Loss (RPO = 0).
