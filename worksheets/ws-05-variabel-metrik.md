# WS-05: Variabel & Metrik

> **Bab 5 — Metric, Measurement & Data**

---

## Ringkasan Materi

### Measurement Alignment Model

Setiap pengukuran yang valid harus bisa ditelusuri melalui rantai ini tanpa lompatan logis:

```
Problem → Concept → Variable → Metric → Data → Result
```

### Operationalization = Keputusan Desain

Menerjemahkan konsep abstrak menjadi variabel terukur bukan proses mekanis. "Code quality" yang diukur via SonarQube code smells membawa asumsi implisit. Setiap operasionalisasi harus didokumentasikan dan dijustifikasi.

### Empat Tipe Data (NOIR)

| Tipe | Ciri | Contoh | Operasi Valid |
|------|------|--------|---------------|
| **Nominal** | Kategori, tanpa urutan | Jenis algoritma (RF, SVM, CNN) | Modus, chi-square |
| **Ordinal** | Urutan, interval tidak sama | Skala Likert (1-5) | Median, Spearman |
| **Interval** | Jarak bermakna, tanpa nol absolut | Suhu Celsius | Mean, Pearson, t-test |
| **Ratio** | Jarak bermakna + nol absolut | Waktu eksekusi (ms) | Semua operasi |

Tipe data menentukan uji statistik yang valid. Kebanyakan metrik performa TI = ratio; persepsi pengguna = ordinal.

### Kriteria Pemilihan Metrik

- **Representative** — Mewakili konsep yang diteliti
- **Sensitive** — Cukup peka menangkap perbedaan bermakna (hindari ceiling effect)
- **Feasible** — Bisa dikumpulkan dalam batasan waktu dan biaya

### Pre-registration

Metrik harus ditentukan **sebelum** eksperimen. Memilih metrik setelah melihat data = **p-hacking**. Metrik tambahan yang ditemukan kemudian dilaporkan sebagai *exploratory*, bukan *confirmatory*.

### Primary vs Secondary Metric

- **Primary Metric** — Langsung terikat ke hipotesis, menentukan kesimpulan
- **Secondary Metric** — Pendukung, dilaporkan di samping primary; statusnya suplementer

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Pemilihan metrik | Berdasarkan kebiasaan/tool yang ada | Berdasarkan construct validity |
| Anomali | Dihapus untuk laporan bersih | Diinvestigasi — bisa jadi temuan |
| Kapan dipilih | Setelah sistem jadi (monitoring) | Sebelum eksperimen (by design) |

### Istilah Penting

- **Operationalization** — Transformasi konsep abstrak menjadi variabel terukur
- **Construct Validity** — Sejauh mana pengukuran benar-benar mengukur konsep yang dimaksud
- **Measurement Scale** — Klasifikasi data (NOIR) yang menentukan analisis valid
- **Multi-metric Evaluation** — Menggunakan beberapa metrik untuk menangkap konsep kompleks

---

### VARIABLE & METRIC DEFINITION

**Research Question:** Apakah terdapat perbedaan signifikan pada efisiensi waktu transaksi (Time-on-Task) antara penggunaan fitur Live Streaming dengan fitur TikTok Shop Tab konvensional pada pengguna Gen-Z?

| Variabel | Tipe | Konsep | Metrik | Skala | Satuan | Cara Mengukur | Justifikasi |
|----------|------|--------|--------|-------|--------|---------------|-------------|
| **Fitur TikTok** | IV | Antarmuka Belanja | Live vs. Shop Tab | Nominal | - | Pelabelan kategori kelompok eksperimen. | Membedakan objek perlakuan untuk melihat pengaruhnya. |
| **Efisiensi** | DV | Kecepatan Teknis | *Time-on-Task* | Ratio | Detik | Analisis rekaman layar (*screen recording*). | Metrik standar ISO 9241-11 untuk mengukur efisiensi sistem. |
| **Akurasi** | DV | Ketepatan Navigasi | *Number of Clicks* | Ratio | Klik | Menghitung jumlah sentuhan pada rekaman video. | Mengetahui apakah *visual clutter* menyebabkan salah klik. |
| **Keahlian User** | CV | Konsistensi Sampel | Durasi Pemakaian | Ordinal | Tahun | Kuesioner screening awal responden. | Mengontrol bias agar hasil murni karena desain fitur. |

**Alignment Check:**
- [X] RQ → Concept → Variable → Metric → Data → Result
- [X] Setiap langkah terdokumentasi
- [X] Tidak ada "lompatan logis"
- [X] Metrik mengukur apa yang dimaksud (construct validity)

## Latihan 1 — Operationalization Chain

**RQ:** Apakah terdapat perbedaan signifikan pada efisiensi waktu transaksi (*Time-on-Task*) antara penggunaan fitur Live Streaming dengan fitur TikTok Shop Tab konvensional pada pengguna Gen-Z?

| Variabel | Tipe | Konsep Abstrak | Metrik Konkret | Skala (NOIR) | Satuan |
|----------|------|---------------|----------------|-------------|--------|
| **Fitur Belanja** | IV | Mode Antarmuka | *Live Streaming* vs *Shop Tab* | Nominal | - |
| **Efisiensi** | DV | Kecepatan Tugas | *Time-on-Task* (Durasi) | Ratio | Detik |
| **Kemudahan Navigasi** | DV | Kerumitan Interaksi | *Number of Clicks* | Ratio | Klik |
| **Demografi** | CV | Karakteristik User | Kelompok Usia (Gen-Z) | Nominal | - |

**Apakah ada lompatan logis dalam rantai?** [ ] Ya / [X] Tidak
> **Jika ya, di mana?** - (Rantai sudah konsisten karena efisiensi diukur langsung melalui waktu dan klik yang bersifat objektif).

## Latihan 2 — Evaluasi Metrik

Evaluasi metrik DV (**Time-on-Task**) yang dipilih di Latihan 1 menggunakan 3 kriteria.

| Kriteria | Skor (1-5) | Justifikasi |
|----------|-----------|-------------|
| Representative | 5 — Sangat mewakili efisiensi; waktu adalah indikator performa paling objektif dalam HCI. |
| Sensitive | 4 — Satuan detik cukup peka menangkap perbedaan durasi meski selisihnya tipis. |
| Feasible | 5 — Sangat mudah dikumpulkan melalui fitur Screen Record di smartphone responden. |

**Apakah perlu secondary metric?** [X] Ya / [ ] Tidak
> **Jika ya, apa dan mengapa?** *Number of Clicks*. Karena jumlah klik membantu memvalidasi apakah keterlambatan disebabkan oleh antarmuka yang membingungkan atau sekadar masalah teknis (jaringan).

**Contoh kasus ceiling effect untuk metrik ini:**
> Jika skenario tugas terlalu sederhana (misal: hanya satu klik), semua responden akan memiliki waktu yang hampir sama cepatnya, sehingga perbedaan antara fitur Live dan Tab tidak akan terlihat.

## Latihan 3 — Data Quality Check

| Dimensi | Pertanyaan | Jawaban | Strategi Mitigasi |
|---------|-----------|---------|------------------|
| **Completeness** | Apakah semua data point terkumpul? | Ya, data dianggap lengkap jika 30 video rekaman tersimpan tanpa korupsi file. | Melakukan verifikasi file dan backup cloud segera setelah sesi eksperimen berakhir. |
| **Consistency** | Apakah ada kontradiksi internal? | Ada risiko fluktuasi kecepatan internet yang mempengaruhi waktu muat halaman. | Menggunakan koneksi Wi-Fi yang sama dan stabil untuk seluruh 30 responden. |
| **Validity** | Apakah benar-benar mengukur yang dimaksud? | Ya, metode rekam layar menjamin akurasi waktu penyelesaian tugas secara objektif. | Melakukan *pilot test* skenario tugas untuk memastikan tidak ada ambiguitas instruksi. |
| **Representativeness** | Apakah sampel mewakili populasi target? | Ya, responden dipilih dari kategori Gen-Z yang merupakan target utama TikTok Shop. | Melakukan *pre-screening* untuk memastikan responden adalah pengguna aktif fitur belanja. |

## Refleksi

> Mengapa memilih metrik setelah melihat data dianggap p-hacking? Apa bedanya dengan eksplorasi data yang sah?

**Jawaban:**
Memilih metrik setelah melihat data dianggap **p-hacking** karena hal tersebut memungkinkan peneliti untuk secara subjektif memilih metrik yang hanya menunjukkan hasil signifikan (mendukung hipotesis) dan membuang data yang tidak mendukung. Ini merusak objektivitas riset karena hasil akhirnya dimanipulasi agar terlihat "berhasil".

Bedanya dengan **eksplorasi data yang sah** adalah tujuannya. Eksplorasi data bertujuan untuk menemukan wawasan atau anomali baru yang bisa menjadi bahan penelitian di masa depan tanpa klaim pembuktian hipotesis awal. Sedangkan dalam penelitian konfirmatori (seperti WS ini), metrik harus dikunci di awal (*pre-registration*) agar proses pengujian tetap jujur dan transparan.