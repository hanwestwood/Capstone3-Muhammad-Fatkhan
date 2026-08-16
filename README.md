# 📦 Data-Driven Turnaround Strategy for JNE Express: SLA Recovery & Operational Cost Mitigation

## 📌 Executive Summary
Proyek Capstone ini membedah operasional logistik PT Tiki Jalur Nugraha Ekakurir (JNE Express) dari hulu (gerai agen) hingga hilir (*last-mile delivery*). Melalui pendekatan *data-driven*, analisis ini mengidentifikasi tiga kebocoran operasional masif: runtuhnya standar layanan premium YES (74,71% *SLA Miss*), ledakan biaya operasional akibat retur COD (25,52% RTS), dan kebocoran omzet akibat cacatnya tata kelola data. Proyek ini tidak sekadar menyajikan metrik statistik, melainkan menghasilkan cetak biru (*blueprint*) rekomendasi strategis beserta peta jalan (*roadmap*) eksekusinya untuk menyelamatkan profitabilitas dan *brand trust* JNE.

---

## 🏢 Business Context & Problem Statement
Sebagai salah satu *market leader* dalam industri jasa pengiriman ekspres di Indonesia, JNE mengandalkan jaringan *Hub-and-Spoke*. Namun, kompleksitas operasional memunculkan titik-titik kritis (*bottlenecks*):
1. **Efisiensi Waktu:** Evaluasi kemacetan pemrosesan di hub sortir atau *linehaul* yang memicu pembengkakan selisih *pickup* dan *delivered*, berujung pada pelanggaran SLA. 
2. **Efisiensi Biaya (Risiko COD):** Tingginya angka penolakan paket saat kurir mengantar barang COD, memicu status *Return to Sender* (RTS).
3. **Penyelamatan Omzet (Revenue Recovery):** Terdapat kebocoran omzet akibat *human error* input beban barang di gerai agen yang memunculkan anomali *weight outliers* (berat < 0 atau > 50 kg).
4. **Tata Kelola Data (Data Governance):** Inkonsistensi input teks (seperti *typo* layanan) dan *logical error* dari sistem *scanner* (seperti paket sampai sebelum dikirim).

---

## 🛠️ Dataset & Tech Stack
*   **Bahasa Pemrograman:** Python
*   **Library Utama:** Pandas (Data Manipulation), Matplotlib & Seaborn (Data Visualization), SciPy (Inferential Statistics).
*   **Dataset:** Terdiri dari transaksi pengiriman, master data pelanggan, dan data cabang operasional. *(Catatan: Data telah melalui proses cleansing mendalam, termasuk standarisasi teks, penanganan missing values, dan penyaringan anomali untuk membentuk Golden Record yang suci hama)*.

---

## 📊 Key Insights & Statistical Validation

### 1. Runtuhnya SLA Layanan YES (Kecacatan Infrastruktur Sistemik)
Layanan prioritas YES (Yakin Esok Sampai) yang menargetkan SLA 1 Hari, mencatatkan tingkat kegagalan (*SLA Miss*) di angka krisis **74,71%**. Uji statistik membuktikan:
*   **Pearson Correlation:** Tidak ada korelasi signifikan antara lonjakan volume paket harian dengan tingkat keterlambatan. Ini membuktikan masalah **bukan pada *overload* kapasitas gudang**.
*   **Chi-Square Test:** Tingkat keterlambatan tidak memiliki dependensi terhadap provinsi/kota tertentu, membuktikan ini adalah **kecacatan infrastruktur pemrosesan secara nasional**.

### 2. Ledakan Retur COD (Pendarahan Biaya Operasional)
Metode pembayaran tunai (COD) mencatatkan rasio kegagalan (*Return to Sender* / RTS) sebesar **25,52%**, lima kali lipat lebih berisiko dibandingkan transaksi Non-COD (5,09%).
*   **Chi-Square Test:** Uji statistik membuktikan tingginya rasio penolakan RTS ini murni kecacatan perilaku konsumen terhadap sistem COD secara nasional, bukan dipengaruhi oleh wilayah demografis tertentu.

### 3. Kebocoran Omzet & Reliabilitas Data
Ditemukan kebocoran omzet akibat paket yang lolos dengan berat minus atau 0 kg akibat lemahnya validasi di level gerai agen (*frontend input risk*). Selain itu, ditemukan *logical error* pada sistem *scanner* di mana status waktu *Delivered* tercatat lebih dulu daripada *Pickup*.

---

## 💡 Actionable Recommendations & Implementation Roadmap

Untuk mengeksekusi temuan di atas tanpa mengganggu operasional harian, berikut adalah Peta Jalan Eksekusi (*Roadmap*) yang direkomendasikan:

### Fase 1: *Quick Wins* & Tahap Pengembangan (Kuartal 1)
*   **Mitigasi Kerugian COD:** Menerapkan sistem *Auto-Blacklist* (konsumen diblokir jika menolak paket 5 kali dalam 1 tahun) dan mewajibkan *merchant* membayar "Asuransi Retur COD" (0,2% dari harga barang + admin Rp5.000). Ini memutus pembakaran *Cost of Failed Delivery* armada kurir yang sia-sia.
*   **Modernisasi Infrastruktur IT (Dev Phase):** Merancang pembaruan *Point of Sale* (POS) agen dengan sistem *hard-rule* (memblokir ketikan angka minus dan menggunakan *dropdown* layanan), serta menanamkan *Pipeline Logic* pada *database* pusat untuk menolak *logical error* waktu.

### Fase 2: *Deployment* & Proyek Percontohan (Kuartal 2 - 4)
*   **IT Roll-out:** Rilis massal pembaruan POS ke seluruh gerai agen secara nasional.
*   **Skenario Penyelamatan SLA YES (Fokus Pulau Jawa):** Mengingat masalah bersumber dari infrastruktur, Direktorat Operasional wajib mewajibkan **Jalur Pemisahan Fisik (*Physical Fast-Track Lane*)** khusus paket YES sejak tahap *unloading* dari truk. Proyek ini difokuskan di Pulau Jawa dengan target pragmatis menekan *SLA Miss* ke batas toleransi **15%**. Langkah lokalisasi ini diproyeksikan mampu menyelamatkan lebih dari 21.670 paket premium dan meruntuhkan persentase *SLA Miss* Nasional dari 74,71% menjadi 44,95%.

### Fase 3: Ekspansi Nasional (Tahun 2)
*   Setelah *blueprint* pemisahan jalur YES terbukti menekan angka *SLA Miss* secara stabil di episentrum Pulau Jawa, SOP yang sama mulai diekspansi secara bertahap ke *Sorting Hub* di pulau-pulau besar lainnya.

---

## 💻 How to Run the Analysis
1. *Clone* repositori ini: `git clone [URL_REPO_ANDA]`
2. Pastikan Python 3.x dan Jupyter Notebook telah terinstal.
3. *Install dependencies*: `pip install pandas matplotlib seaborn scipy`
4. Buka dan jalankan `Capstone_Project_3.ipynb` secara berurutan.
