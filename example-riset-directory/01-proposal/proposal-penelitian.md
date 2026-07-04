# Analisis Eksperimental Efisiensi Antarmuka Live Streaming TikTok Shop Berdasarkan Kepadatan Elemen Visual pada Generasi Z

## RINGKASAN
Penelitian ini bertujuan untuk mengukur secara objektif dampak kepadatan elemen visual (visual clutter) pada antarmuka Live Streaming TikTok Shop terhadap performa transaksi pengguna Generasi Z. Meskipun adopsi social commerce berkembang pesat, desain antarmuka Live Streaming saat ini memiliki kepadatan informasi yang sangat tinggi akibat penumpukan komponen dinamis. Sebagian besar penelitian terdahulu berfokus pada aspek psikologis konsumen dan niat beli (purchase intention), sehingga memunculkan method gap berupa kurangnya pengukuran efisiensi teknis interaksi manusia-komputer.

Eksperimen terkontrol dilakukan dengan membandingkan dua kondisi antarmuka pada satu kelompok subjek berpasangan (within-subject), yaitu kondisi Clean (0% overlay pengganggu) sebagai basis pengujian (baseline) dan kondisi Full (100% overlay stiker, gift, dan komentar) sebagai intervensi perlakuan. Pengujian dilakukan secara rigid menggunakan satu perangkat standar Samsung A23 pada jaringan Wi-Fi terisolasi dengan melibatkan 37 responden mahasiswa aktif dari klaster Generasi Z. Metrik primer yang dievaluasi adalah Time-on-Task (durasi transaksi dalam satuan detik) dan Number of Clicks (frekuensi ketukan layar) yang diekstraksi dari hasil observasi rekaman layar (screen recording).

Data performa dari kedua kondisi dianalisis menggunakan uji statistik parametrik Paired Samples T-Test untuk melihat signifikansi perbedaan performa secara nyata. Luaran yang ditargetkan dari penelitian ini meliputi dataset performa interaksi pengguna, artikel ilmiah tepercaya, serta rekomendasi desain arsitektur antarmuka social commerce yang ergonomis. Manfaat praktis riset ini adalah memberikan acuan bagi desainer UI/UX untuk menekan tingkat error navigasi dan mengoptimalkan kecepatan konversi transaksi pada platform belanja digital.

**Kata Kunci:** Live Streaming TikTok Shop; Visual Clutter; Time-on-Task; Number of Clicks; Generasi Z

---

## I. PENDAHULUAN

Pesatnya perkembangan teknologi informasi dan komunikasi telah mengubah paradigma interaksi manusia dalam pemenuhan kebutuhan ekonomi, khususnya melalui integrasi media sosial dan platform belanja digital yang kini dikenal sebagai ekosistem social commerce. Di Indonesia, transformasi ini berlangsung sangat agresif dan menempatkan fitur Live Streaming sebagai ujung tombak strategi penetrasi pasar untuk menarik minat beli konsumen dari klaster Generasi Z. Namun, dinamika kompetisi platform memicu para pengembang untuk merancang antarmuka yang sangat padat informasi demi mendongkrak keterlibatan interaktif pengguna, tanpa mempertimbangkan batas ambang beban kognitif manusia dalam memproses stimulus visual.

Oleh karena itu, bab pendahuluan ini disusun secara progresif dan sistematis untuk menguraikan seluruh dimensi permasalahan tersebut secara ilmiah. Pembahasan di dalam bab ini akan membedah secara mendalam mulai dari formulasi masalah kepadatan elemen visual (visual clutter) pada fitur Live Streaming TikTok Shop, justifikasi pendekatan eksperimental (ablation study) yang diajukan sebagai solusi, pemetaan posisi riset terhadap literatur terdahulu untuk menegaskan celah metode (method gap) dan kebaruan (novelty), hingga visualisasi peta jalan penelitian (research roadmap) yang komprehensif dari tahap dasar hingga rencana pengembangan sistem adaptif di masa depan.

### 1.1. Latar Belakang dan Rumusan Masalah
Perkembangan ekosistem social commerce menempatkan fitur Live Streaming TikTok Shop sebagai ujung tombak untuk menarik konsumen dari klaster Generasi Z sebagai pihak yang terdampak langsung. Kelompok pengguna ini sangat adaptif terhadap teknologi digital, namun memiliki ekspektasi tinggi terhadap kelancaran navigasi serta kecepatan respon dari antarmuka aplikasi belanja. Namun, gejala masalah yang ditemukan di lapangan saat ini adalah antarmuka tersebut mengalami tingkat kepadatan informasi visual yang ekstrem (visual clutter), di mana layar smartphone dipadati oleh komponen dinamis non-transaksi seperti stiker animasi promosi, notifikasi gift digital, dan aliran teks komentar yang bergerak cepat.

Akar masalahnya bersumber dari benturan arsitektur desain sistem: antarmuka dirancang dinamis untuk mendongkrak unsur hiburan, namun di sisi lain harus memfasilitasi transaksi belanja yang menuntut akurasi dan ketenangan visual. Penumpukan elemen visual ini sering menutupi komponen navigasi utama seperti ikon keranjang kuning atau tombol checkout. Dampaknya, tingginya visual clutter ini membebani kapasitas kognitif pengguna Generasi Z, memicu terjadinya salah klik (misclick), memaksa ekstra ketukan layar, dan memperpanjang waktu transaksi pembelian.

Dalam konteks ilmiah, masalah ini berada dalam ruang lingkup pengujian efisiensi teknis Interaksi Manusia-Komputer (HCI). Oleh karena itu, problem statement penelitian ini berpusat pada fakta bahwa tingginya visual clutter pada antarmuka Live Streaming TikTok Shop berdampak langsung pada penurunan efisiensi waktu transaksi (Time-on-Task) dan peningkatan kesalahan navigasi (Number of Clicks) bagi pengguna Generasi Z.

### 1.2. Pendekatan Pemecahan Masalah
Tujuan utama penelitian ini adalah untuk menguji secara kuantitatif dampak tingkat kepadatan elemen visual antarmuka Live Streaming terhadap efisiensi interaksi pengguna Generasi Z saat melakukan transaksi. Berdasarkan tujuan tersebut, Research Question (RQ) utama yang diajukan adalah: "Bagaimana perbandingan efisiensi performa transaksi antara penggunaan antarmuka Live Streaming kondisi Clean (bebas gangguan visual) dengan kondisi Full (padat visual clutter) pada pengguna Generasi Z?" Sejalan dengan RQ tersebut, hipotesis awal (H_1) yang diajukan adalah antarmuka kondisi Full menghasilkan performa transaksi yang lebih lambat dan kurang efisien secara signifikan dibandingkan kondisi Clean.

Pendekatan solusi atau intervensi yang diusulkan adalah melakukan rekayasa stimulus tampilan layar siaran langsung melalui metode pengkondisian lingkungan antarmuka belanja. Alasan logis pemilihan intervensi ini adalah untuk mengisolasi variabel gangguan secara ketat, sehingga tingkat penurunan efisiensi motorik dapat diatribusikan langsung kepada keberadaan komponen non-transaksi tersebut. Sebagai basis pembanding (baseline), penelitian ini menetapkan kondisi antarmuka Clean, yaitu tampilan siaran langsung yang bersih dari segala bentuk overlay stiker, gift, maupun teks obrolan penonton, sehingga hanya menyisakan komponen video produk dan tombol fungsi transaksi inti.

### 1.3. State Of The Art dan Kebaruan
Kondisi kajian ilmiah mengenai platform belanja sosial (social commerce) dalam beberapa tahun terakhir menunjukkan tren peningkatan yang sangat pesat. Namun, pola studi terdahulu secara konsisten masih didominasi oleh sudut pandang perilaku konsumen, aspek psikologis, serta pengaruhnya terhadap niat beli (purchase intention). Evaluasi pengalaman pengguna yang dilakukan sebelumnya, seperti riset oleh Hairunisya (2025), mayoritas masih mengandalkan metode kuesioner subjektif yang rentan terhadap bias data karena sifat pengukurannya yang berbasis pada persepsi atau ingatan responden (self-reported data).

Kondisi ideal dalam bidang Interaksi Manusia-Komputer (HCI) menuntut adanya pengujian metrik teknis yang bersifat objektif untuk mengukur performa motorik pengguna secara riil di lapangan. Kondisi aktual saat ini menunjukkan adanya Method Gap yang nyata karena belum ada penelitian yang menguji efisiensi interaksi fisik secara objektif, serta Context Gap di mana manipulasi kepadatan elemen visual (visual clutter) belum pernah diuji melalui metode eksperimental terkontrol di laboratorium. Selisih eksplisit antara kebutuhan data performa objektif dan dominasi data persepsi subjektif inilah yang menjadi celah valid dalam riset ini.

Posisi penelitian ini berada sebagai studi konfirmatori kuantitatif yang hadir untuk mengisi celah metodologi tersebut. Kebaruan (novelty) yang ditawarkan dalam riset ini adalah pembuktian hubungan kausalitas empiris antara tingkat kepadatan stimulus visual di layar gawai dengan tingkat degradasi performa fisik-motorik nyata dari pengguna klaster Generasi Z. Pengukuran performa pada eksperimen ini tidak lagi mengandalkan opini subjektif responden, melainkan berbasis pada ekstraksi data rekaman layar secara riil melalui parameter teknis berupa Time-on-Task dan Number of Clicks.

### 1.4. Peta Jalan dan Penelitian
Penelitian ini dirancang sebagai bagian dari peta jalan riset evaluasi antarmuka social commerce berkelanjutan yang berfokus pada efisiensi interaksi pengguna, yang terbagi ke dalam tiga tahapan perkembangan terstruktur:

1) Tahap Dasar (Telah Dicapai): Melakukan studi literatur mendalam terhadap teori beban kognitif (Cognitive Load Theory) dalam Interaksi Manusia-Komputer (HCI), mengidentifikasi kelemahan metodologi pengujian subjektif berbasis kuesioner SUS pada paper baseline (Hairunisya, 2025), melakukan survei awal karakteristik belanja mahasiswa Generasi Z di lingkungan Universitas Putra Bangsa, serta merumuskan parameter fungsional komponen visual clutter (stiker, gift, komentar) yang akan dieksperimenkan.

2) Tahap Usulan Saat Ini (Dikerjakan pada Usulan Ini): Melaksanakan eksperimen terkontrol berbasis laboratorium menggunakan metode observasi langsung terhadap 37 responden menggunakan perangkat fisik standar Samsung A23 pada jaringan Wi-Fi terisolasi. Fokus utama tahap ini adalah mengumpulkan data mentah kuantitatif durasi transaksi (Time-on-Task) dan jumlah klik (Number of Clicks) pada kondisi antarmuka Clean versus Full, melakukan uji signifikansi statistik Paired Samples T-Test, serta menghasilkan dokumen rekomendasi batas aman kepadatan visual antarmuka belanja yang ergonomis bagi desainer UI/UX.

3) Tahap Lanjutan (Direncanakan): Memanfaatkan dokumen rekomendasi desain hasil temuan eksperimen pada usulan ini untuk membangun sebuah experimental artifact berupa prototipe sistem framework layout antarmuka adaptif. Sistem masa depan ini direncanakan memiliki kemampuan mendeteksi penurunan performa transaksi pengguna secara otomatis dan melakukan reduksi komponen overlay visual secara dinamis ketika pengguna memasuki fase krusial pengisian data pembayaran (checkout stage).

---

## II. METODE

Bab metode ini menguraikan secara komprehensif mengenai rancangan eksperimen laboratorium terkontrol (controlled laboratory experiment) yang disusun secara sistematis untuk menguji dampak tingkat kepadatan elemen visual terhadap efisiensi interaksi digital. Pendekatan metodologi yang diterapkan dalam riset ini berfokus pada pengumpulan data performa fisik-motorik secara objektif dan empiris. Pendekatan ini dipilih guna mengeliminasi kelemahan dari pengujian berbasis opini subjektif yang mendominasi studi terdahulu, sehingga mampu menjawab Research Question (RQ) secara valid dan reliabel. Pengujian ini dilaksanakan dengan melibatkan 37 responden yang dipilih secara ketat dari klaster Generasi Z, di mana seluruh rangkaian pengujian dilakukan di dalam lingkungan laboratorium yang disterilkan dari interferensi variabel pengganggu (confounding variables).

### 2.1. Desain Penelitian dan Unit Analisis
Penelitian kuantitatif ini menggunakan desain eksperimen laboratorium terkontrol dengan pendekatan Within-Subject Design. Melalui desain ini, seluruh 37 responden akan menguji kedua kondisi antarmuka secara bergantian sehingga setiap individu bertindak sebagai kontrol bagi dirinya sendiri guna meminimalkan variasi antar-individu. Pertanyaan penelitian yang diajukan adalah bagaimana perbandingan efisiensi performa transaksi antara penggunaan antarmuka Live Streaming kondisi Clean yang bebas gangguan dengan kondisi Full yang padat visual clutter pada pengguna Generasi Z.

### 2.2. Variabel, Metric, Instrumen, dan Data
Penelitian eksperimental ini menggunakan Tingkat Kepadatan Elemen Visual (Visual Clutter Overlay) sebagai Variabel Independen Tunggal, yang dimanipulasi menjadi dua kondisi. Dampak dari manipulasi ini diukur pada Variabel Dependen berupa efisiensi performa transaksi pengguna Generasi Z. 

Pengukuran variabel dependen menggunakan dua metrik utama berbasis skala rasio:
1. Time-on-Task (satuan detik): mengukur durasi penyelesaian tugas transaksi.
2. Number of Clicks (satuan frekuensi): mengukur jumlah ketukan layar sebagai indikator akurasi navigasi.

### 2.3. Skenario dan Prosedur Pengujian
Prosedur pembandingan antara kondisi baseline (Clean) dan intervensi (Full) diatur menggunakan teknik penyeimbangan (counterbalancing) melalui metode Latin Square Simpel untuk mengeliminasi efek pembelajaran dan efek kelelahan fisik.

### 2.4. Artifact, Setup, atau Kesiapan Implementasi
Penelitian ini tidak membangun artifact perangkat lunak baru, melainkan memanfaatkan sistem existing berupa antarmuka fitur Live Streaming aplikasi belanja sosial yang direkayasa secara terkontrol sebagai instrumen alat uji laboratorium.

### 2.5. Teknik Analisis, Asumsi, dan Validitas
Teknik analisis statistik utama yang digunakan untuk membandingkan data adalah Paired Samples T-Test (Uji T Berpasangan). Data akan diuji normalitasnya menggunakan metode Shapiro-Wilk. Ancaman validitas utama diidentifikasi pada validitas internal (carryover effect) dan validitas eksternal (ecological validity) yang dimitigasi melalui pengacakan urutan dan penggunaan aplikasi nyata.

---

## III. HASIL YANG DIHARAPKAN
Hasil utama yang diharapkan dari penelitian eksperimental ini adalah sebuah kesimpulan ilmiah yang terukur mengenai ada atau tidaknya pengaruh signifikan dari tingkat kepadatan elemen visual terhadap tingkat efisiensi performa transaksi pengguna Generasi Z.

Luaran konkret yang dijanjikan:
1. Draf artikel ilmiah.
2. Dataset primer yang bersih dan tervalidasi mengenai metrik performa motorik fisik dari 37 responden.
3. Dokumen laporan teknis rekomendasi desain (UX Design Guidelines).

---

## IV. JADWAL PENELITIAN

| No | Nama Kegiatan | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 |
|---|---|---|---|---|---|---|---|---|---|
| 1 | Identifikasi masalah dan topik | ✓ | | | | | | | |
| 2 | Literatur dan gap | ✓ | ✓ | | | | | | |
| 3 | RQ dan desain metode | | ✓ | ✓ | | | | | |
| 4 | Implementasi atau instrumen | | | | ✓ | ✓ | | | |
| 5 | Pengujian atau eksperimen | | | | | | ✓ | | |
| 6 | Analisis dan penulisan | | | | | | | ✓ | |
| 7 | Revisi final | | | | | | | | ✓ |

---

## DAFTAR PUSTAKA
- Cahyani, A. A., & Widyatmoko. (2026). Analisis Tiktok Shop, live streaming, dan harga terhadap gaya hidup konsumtif Generasi-Z. SOLUSI: Jurnal Ilmiah Bidang Ilmu Ekonomi, 24(1), 138-154.
- Ghaissani, A. (2024). Analisis faktor-faktor pendorong pembelian impulsif (impulsive buying) melalui live streaming shopping TikTok Shop (Skripsi).
- Hairunisya, T. (2025). Pengaruh influencer attribute, live streaming marketing, brand image dan user experience terhadap purchase intention di Tiktok Shop (Skripsi).
- Jannah, A. K. (2024). Pengaruh live streaming tiktok, potongan harga, dan celebrity endorsement terhadap keputusan pembelian produk kecantikan (Studi kasus pada produk Facetology di Yogyakarta) (Laporan Penelitian).
- Nielsen, J., & Pernice, K. (2010). Eyetracking web usability. New Riders.
- Sari, T. O. (2025). Implementasi pemanfaatan digital marketing melalui live shopping platform social commerce Tiktok pada UMKM aromaterapi Natureline (Laporan Penelitian).
- Sauro, J., & Lewis, J. R. (2016). Quantifying the user experience: Practical statistics for user research (2nd ed.). Morgan Kaufmann.
- Wickens, C. D., Helton, W. S., Hollands, J. G., & Banbury, S. (2021). Engineering psychology and human performance (5th ed.). Routledge.