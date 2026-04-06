# WS-01: Distorsi & Paradigma

> **Bab 1 — Research Mindset in IT**

---

## Ringkasan Materi

### Research Trust Model

Pengetahuan ilmiah tidak muncul langsung dari kenyataan. Ia melewati **6 tahap transformasi** yang masing-masing rawan distorsi:

```
Reality → Data → Processing → Analysis → Inference → Knowledge
```

Etika mencegah distorsi yang disengaja (fabrikasi, cherry-picking). Validitas mendeteksi distorsi yang tidak disengaja (confounding variable, sampling bias).

### Tiga Jenis Validitas

| Jenis | Pertanyaan | Contoh Ancaman |
|-------|-----------|----------------|
| **Internal Validity** | Apakah hubungan kausal benar ada? | Confounding variable |
| **External Validity** | Apakah bisa digeneralisasi? | Dataset terlalu homogen |
| **Construct Validity** | Apakah mengukur hal yang benar? | Metrik tidak sesuai klaim |

### Paradigma Riset

Mata kuliah ini menggunakan pendekatan **Positivist** (fenomena TI bisa diukur objektif melalui eksperimen terkontrol) diperkuat **Design Science Research** (artefak dibuat sebagai instrumen pengujian hipotesis, bukan tujuan akhir).

### Mode Berpikir Peneliti

**Curious** (mempertanyakan fenomena) → **Critical** (mengevaluasi klaim berdasarkan bukti) → **Systematic** (merancang investigasi terstruktur dan reproducible).

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan | Membuat sistem yang bekerja | Menghasilkan pengetahuan yang valid |
| Pertanyaan khas | "Bagaimana membuatnya jalan?" | "Apakah klaim ini benar?" |
| Ukuran sukses | Sistem berfungsi, client puas | Hipotesis terjawab, temuan tervalidasi |
| Kegagalan | Harus dihindari | Harus dilaporkan (negative result = kontribusi) |

### Istilah Penting

- **Research Mindset** — Pola pikir yang menuntut bukti dan mempertanyakan asumsi
- **Research Ethics** — Prinsip perilaku: kejujuran, objektivitas, keterbukaan, akuntabilitas
- **HARKing** — Hypothesizing After Results are Known — merumuskan hipotesis setelah melihat data
- **Falsifiability** — Hipotesis harus bisa dibuktikan salah

---

## Template A.1 — Research Mindset Self-Assessment

```
Nama Peneliti    : Hilda Sva Alzena
Tanggal          : 6 April 2026

1. Ketika membaca klaim "metode X 95% akurat":
   - Pertanyaan pertama saya: Bagaimana komposisi dataset yang digunakan dan apakah pengujian dilakukan pada kondisi dunia nyata (lapangan) atau hanya simulasi laboratorium?
   - Data yang dibutuhkan untuk verifikasi: Distribusi data uji (apakah ada sampling bias?), metrik evaluasi selain akurasi (seperti Precision atau Recall), dan hasil perbandingan dengan metode manual sebelumnya.

2. Posisi paradigma:
   - Pendekatan: [ ] Positivis  [ ] Interpretivis  [X] Design Science  [ ] Mixed
   - Alasan: Riset ini berfokus pada pengembangan artefak berupa sistem informasi (Mobile & Web) untuk memecahkan masalah praktis (pelaporan manual). Keberhasilan riset diukur dari sejauh mana artefak tersebut berfungsi efektif sebagai solusi.

3. Identifikasi distorsi:
   - Asumsi tersembunyi: Peneliti berasumsi bahwa semua staf sekolah memiliki smartphone yang kompetibel dan selalu memiliki akses internet untuk menerima notifikasi secara real-time.
   - Sumber bias potensial: Response Bias dari pihak sekolah saat wawancara awal, karena mereka cenderung menginginkan sistem baru sehingga mungkin melebih-lebihkan masalah pada sistem manual.
   - Langkah mitigasi: Melakukan pengujian langsung (Black Box Testing) secara objektif dan memvalidasi sistem kepada berbagai level pengguna (admin, staf, dan pelapor) untuk mendapatkan perspektif yang luas.

4. Komitmen etika:
   - Data yang tidak akan dimanipulasi: Hasil pengujian sistem (baik itu error maupun kegagalan fitur) dan data laporan kerusakan asli dari lapangan tidak akan diubah demi menaikkan persentase keberhasilan sistem.
   - Batasan yang diakui sejak awal: Sistem ini sangat bergantung pada stabilitas server Firebase dan koneksi internet pengguna; jika koneksi terputus, fitur real-time tidak akan berfungsi maksimal.
```

---

## Latihan 1 — Identifikasi Distorsi

Pilih satu paper riset di bidang TI yang mengklaim "metode X meningkatkan performa." Telusuri setiap tahap Research Trust Model.

**Paper yang dipilih:**
> Judul:
 Sistem Pelaporan Kerusakan Sarana Prasarana Berbasis Mobile Secara Realtime dengan Notifikasi
> Penulis (Tahun): 
Rangga Eka Kusuma Dani & Aris Haris Rismayana (2024)

| Tahap | Apa yang Dilakukan | Potensi Distorsi |
|-------|-------------------|-----------------|
| Reality → Data | Wawancara dan observasi masalah sarpras di SMAN 17 Bandung.|Sampling      Bias: Hanya mengambil data dari satu sekolah saja.|
| Data → Processing |Merancang database MySQL dan alur notifikasi Firebase. | Construct Validity: Menganggap "Notifikasi Cepat" otomatis berarti "Perbaikan Cepat".|
| Processing → Analysis | Pengujian fungsionalitas fitur aplikasi dengan Black Box Testing.| Confirmation Bias: Hanya menguji apakah fitur "jalan", bukan ketahanan sistem.|
| Analysis → Inference |Menyimpulkan sistem efisien karena notifikasi berhasil terkirim. | Inference Distortion: Tidak ada data perbandingan waktu perbaikan sebelum vs sesudah.|
| Inference → Knowledge | Mengklaim aplikasi mobile adalah solusi terbaik manajemen sarpras.| Overclaiming: Mengabaikan faktor eksternal seperti kedisiplinan petugas lapangan.|

**Distorsi paling besar di tahap:** Analysis → Inference

**Dua distorsi spesifik yang teridentifikasi:**
1. Lack of Impact Metrics: Peneliti hanya menguji apakah fitur aplikasi "berjalan" secara teknis, namun tidak mengukur apakah durasi perbaikan sarana di sekolah benar-benar menjadi lebih cepat dibandingkan sistem manual.
2. Environmental Distortion: Pengujian dilakukan dalam kondisi ideal (koneksi stabil dan perangkat modern), sehingga mengabaikan kenyataan di lapangan seperti dead zone sinyal internet di area gudang atau sekolah.
---

## Latihan 2 — Analisis Kasus Etika

Skenario: Seorang peneliti menemukan bahwa jika 3 data point outlier dihapus, hasil eksperimennya menjadi signifikan. Dengan outlier, hasilnya tidak signifikan.

| Perspektif | Analisis |
|------------|---------|
| Kejujuran ilmiah |Peneliti wajib melaporkan seluruh data. Menghapus outlier hanya agar hasil terlihat "bagus" tanpa alasan teknis yang kuat adalah bentuk manipulasi data (falsification). |
| Transparansi |Peneliti harus menjelaskan kriteria penghapusan outlier di bagian metodologi. Jika dihapus, alasan logis (misal: kesalahan sensor atau human error) harus disertakan secara terbuka. |
| Peer review |Penelaah (reviewer) berhak mengetahui kondisi data asli. Menyembunyikan outlier akan menyesatkan peneliti lain yang ingin mereplikasi riset tersebut di masa depan. |

**Keputusan akhir dan justifikasi:**
>Keputusan: Melaporkan hasil eksperimen dengan kedua kondisi (tetap menyertakan outlier) atau memberikan argumen ilmiah yang sangat kuat mengapa outlier tersebut harus dibuang.

>Justifikasi: Integritas riset lebih berharga daripada hasil yang signifikan. Dalam dunia TI (seperti jurnal Rangga dkk.), outlier bisa jadi justru merupakan data penting yang menunjukkan kegagalan sistem pada kondisi tertentu yang harus diperbaiki, bukan disembunyikan.
---

## Latihan 3 — Posisi Paradigma

**Topik riset:** Sistem Pelaporan Kerusakan Sarana Prasarana Berbasis Mobile (Studi Kasus SMAN 17 Bandung)

| Kriteria | Positivis | Interpretivis | Design Science |
|----------|-----------|---------------|----------------|
| Kesesuaian dengan topik (1–5) |3|2|5|
| Jenis data yang dikumpulkan | Angka statistik, hasil pengujian sistem (success rate).| Persepsi atau pengalaman kepuasan pengguna.| Artefak digital (aplikasi) dan efektivitas fungsinya.|
| Limitasi paradigma |Kurang mendalami kenyataan sosial di lapangan. |Terlalu subjektif dan sulit direplikasi secara teknis. |Fokus pada pembuatan alat, bukan pada teori ilmiah murni. |

**Paradigma yang dipilih:** Design Science
**Alasan:** Riset ini berfokus pada pemecahan masalah praktis (masalah pelaporan manual) dengan menciptakan sebuah artefak (aplikasi mobile dan web). Tujuan utamanya adalah fungsionalitas dan kegunaan sistem sebagai solusi digital.

---

## Refleksi

> Sebelum membaca materi ini, apakah pernah mempertanyakan klaim "95% akurat"? Setelah memahami rantai distorsi, pertanyaan apa yang sekarang akan diajukan saat membaca paper?

**Jawaban:**
> Sebelumnya, saya cenderung menerima klaim "95% akurat" sebagai bukti mutlak keberhasilan sebuah sistem tanpa ragu. Saya menganggap angka tinggi tersebut otomatis berarti penelitiannya berkualitas tinggi dan jujur.
> Setelah memahami rantai distorsi, pertanyaan yang akan saya ajukan adalah:
 Apakah 95% itu hasil dari data yang sudah dimanipulasi (cherry-picking), apakah skenario pengujiannya sudah mewakili realitas di lapangan, dan apakah ada variabel penting yang sengaja diabaikan demi mencapai angka tersebut?.
 Saya kini lebih fokus pada integritas proses riset daripada sekadar hasil akhir yang terlihat sempurna.___________________________________________________
