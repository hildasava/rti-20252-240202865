# WS-02: Problem Statement

> **Bab 2 — Problem Formulation & System Context**

---

## Ringkasan Materi

### Problem Formation Model

Masalah riset melewati 5 tahap transformasi. Melompat langsung dari Reality ke Variable adalah kesalahan paling umum.

```
Reality → Observed Issue (Symptom) → Diagnosed Problem (Root Cause)
→ Researchable Problem (Scoped) → Measurable Variable (Operationalized)
```

### Topic ≠ Problem ≠ Research Problem

| Level | Contoh | Status |
|-------|--------|--------|
| **Topik** | Keamanan IoT | Terlalu luas, tidak bisa diuji |
| **Problem** | MQTT tidak terenkripsi | Spesifik tapi belum riset |
| **Research Problem** | Belum ada studi membandingkan overhead TLS 1.3 vs DTLS pada MQTT di IoT RAM < 64KB | Bisa dirancang eksperimennya |

### Symptom vs Root Cause

Apa yang diamati (gejala) ≠ mengapa terjadi (akar masalah). Gunakan **5 Whys** atau **Fishbone Diagram** untuk menggali.

Contoh: "User meninggalkan checkout" (symptom) → "Waktu loading > 8 detik karena API call sequential" (root cause).

### System Thinking

Setiap masalah riset TI harus terikat pada komponen sistem: **Input → Process → Output → Outcome → Constraints → Stakeholders**.

### Problem Quality Check

Masalah riset yang layak harus memenuhi 5 kriteria:
- **Clarity** — Satu orang membaca akan paham
- **Measurability** — Ada metrik kuantitatif
- **Relevance** — Penting untuk domain
- **Testability** — Bisa gagal (falsifiable)
- **Impact** — Ada kontribusi jika terjawab

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan | Menyelesaikan masalah (*solve*) | Memahami dan membuktikan (*understand & prove*) |
| Masalah | Bug, error, fitur belum ada | Gap dalam pengetahuan |
| Scope | Selesaikan semua yang perlu | Batasi agar bisa dibuktikan |
| Output | Working system | Evidence, paper, replicable findings |

### Istilah Penting

- **Problem Statement** — Formulasi tertulis: konteks sistem + gap + dampak + justifikasi
- **System Context** — Deskripsi lengkap: input, proses, output, outcome, constraints, stakeholders
- **Problem Drift** — Masalah "bermutasi" dari pendahuluan ke metodologi karena statement awal tidak presisi
- **Solution-First Thinking** — Memulai dari solusi tanpa masalah yang jelas — berbahaya dalam riset
- **Operational Definition** — Definisi variabel yang cukup jelas agar peneliti lain bisa mengukur hal yang sama

---

## Template A.2 — Problem Statement Builder

```
PROBLEM STATEMENT BUILDER

Domain & Konteks
  Domain   : Human-Computer Interaction (HCI) / Mobile Commerce.
  Konteks  : Fitur belanja terintegrasi (Live Shopping) pada aplikasi TikTok Shop.

System Context
  Input       : Klik ikon keranjang kuning, pemilihan varian produk, konfirmasi alamat, dan metode pembayaran.
  Process     : Transisi tampilan (overlay) dari konten video ke halaman pembayaran (checkout).
  Output      : Notifikasi pesanan berhasil, struk transaksi digital, dan pengurangan stok otomatis.
  Outcome     : Pengguna berhasil mendapatkan produk promo sebelum stok habis (keberhasilan transaksi).
  Constraints : Keterbatasan ukuran layar ponsel, latensi jaringan, dan batas waktu promo yang sangat singkat (detik).
  Stakeholders: Pengguna (Buyer), Kreator (Host Live), dan Pengembang Aplikasi.

Fenomena → Problem
  Fenomena yang diamati             : Pengguna sering mengalami kegagalan membeli produk saat Live Streaming karena kalah cepat   dengan waktu habisnya stok.
  Gejala (symptom) yang terukur     : Waktu rata-rata transaksi (Time-on-Task) mencapai 12-15 detik, yang dianggap terlalu lambat untuk situasi flash sale.
  Masalah yang didiagnosis          : Antarmuka overlay yang terlalu padat (banyak iklan/stiker/komentar) mendistruksi fokus pengguna dan memperbanyak langkah klik yang tidak perlu.
  Masalah riset (researchable)      : Sejauh mana desain antarmuka TikTok Shop dapat meminimalkan hambatan navigasi pengguna untuk mempercepat penyelesaian transaksi.
  Variabel yang terukur             : Execution Time (detik) dan jumlah klik (Number of Clicks).
  
Problem Quality Check
  [X] Clarity — Judul jelas fokus pada kecepatan transaksi Live Shopping.
  [X] Measurability — Diukur dengan satuan detik dan jumlah klik.
  [X] Relevance — Penting untuk efisiensi belanja di era Social Commerce.
  [X] Testability — Bisa diuji pakai rekaman layar dan stopwatch.
  [X] Impact — Membantu penjual meningkatkan angka keberhasilan transaksi.

Problem Statement (1 paragraf):
Saat ini, pengguna TikTok Shop sering mengalami hambatan kecepatan transaksi pada fitur Live Streaming akibat desain antarmuka yang kurang efisien dan membebani fokus kognitif pengguna (gap). Hal ini mengakibatkan tingginya angka kegagalan dalam mendapatkan produk promo terbatas, yang berdampak pada penurunan konversi penjualan (dampak). Riset ini bertujuan untuk menganalisis efisiensi elemen visual pada antarmuka TikTok Shop guna membuktikan bahwa penyederhanaan alur navigasi dapat secara signifikan mempercepat waktu transaksi pengguna (justifikasi).  
```

---

## Latihan 1 — Dari Topik ke Masalah Riset

Pilih satu topik di bidang TI yang diminati. Transformasikan melalui 5 tahap Problem Formation Model.

**Topik awal:** Analisis Efisiensi UI TikTok Shop pada Fitur Live Streaming.

| Tahap | Hasil |
|-------|-------|
| Reality | Pengguna harus melakukan transaksi sangat cepat saat Live agar tidak kehabisan stok barang.|
| Observed Issue (Symptom) | Waktu rata-rata transaksi (checkout) mencapai 12-15 detik, yang dianggap terlalu lambat. |
| Diagnosed Problem (Root Cause) | Terlalu banyak langkah konfirmasi (klik) dan elemen visual (overlay) yang menutupi tombol bayar.|
| Researchable Problem |Sejauh mana penyederhanaan alur navigasi dapat mempercepat waktu transaksi pada fitur Live TikTok Shop. |
| Measurable Variable |Time-on-Task (satuan detik) dan Number of Clicks (jumlah klik). |

**Apakah terjebak solution-first thinking?** [ ] Ya / [X] Tidak

---

## Latihan 2 — System Context Decomposition

Gambarkan konteks sistem dari masalah riset di Latihan 1.

| Komponen | Deskripsi |
|----------|----------|
| Input | Interaksi tap (klik) pada ikon keranjang kuning dan pemilihan varian produk. |
| Process |Pemuatan (loading) antarmuka overlay checkout di atas konten Live Streaming. |
| Output |Informasi rincian pesanan dan tombol konfirmasi pembayaran. |
| Outcome | Transaksi berhasil dilakukan oleh pengguna sebelum stok barang habis.|
| Constraints |Ukuran layar HP yang terbatas dan gangguan visual (stiker/komentar) pada layar. |
| Stakeholders | Pembeli (User) dan Penjual (Host/Merchant).|

**Komponen mana yang paling relevan dengan masalah riset?** Process

---

## Latihan 3 — Problem Quality Check

Evaluasi problem statement yang sudah dibuat menggunakan 5 kriteria.

| Kriteria | Skor (1-5) | Justifikasi |
|----------|-----------|-------------|
| Clarity |5 |Fokus riset sangat jelas: mengukur kecepatan transaksi pada fitur Live. |
| Measurability |5|Variabel sangat terukur menggunakan satuan detik dan jumlah klik. |
| Relevance |5 |Sangat relevan dengan tren Social Commerce dan kebutuhan pasar saat ini. |
| Testability |5 |Mudah diuji melalui observasi langsung dan eksperimen rekam layar. |
| Impact |4 |Memberikan solusi nyata bagi peningkatan konversi penjualan di platform digital. |

**Skor total:** _____ / 25

**Problem statement versi final (1 paragraf):**
> Saat ini, pengguna TikTok Shop sering mengalami hambatan kecepatan transaksi pada fitur Live Streaming akibat alur antarmuka yang kompleks dan membebani fokus kognitif (gap). Hal ini mengakibatkan tingginya angka kegagalan dalam mendapatkan produk promo terbatas, yang berdampak pada penurunan efektivitas penjualan (dampak). Riset ini bertujuan untuk menganalisis efisiensi elemen antarmuka TikTok Shop guna membuktikan bahwa penyederhanaan langkah navigasi dapat secara signifikan mempercepat waktu transaksi pengguna (justifikasi).
---

## Refleksi

> Bandingkan "masalah" yang biasa ditemui saat coding (bug, error) dengan masalah riset. Apa perbedaan fundamental dalam cara mendefinisikan dan mendekati keduanya?

**Jawaban:**
> Perbedaan fundamentalnya terletak pada sifat dan tujuan penyelesaiannya. Masalah saat coding (seperti bug atau error) bersifat teknis dan biner: tujuannya adalah membuat fitur "bekerja" sesuai fungsi (jalan atau tidak jalan). Pendekatannya adalah memperbaiki kesalahan logika atau sintaks pada sistem.

> Sedangkan masalah riset bersifat efektivitas dan knowledge gap; fiturnya mungkin sudah bekerja dengan baik secara teknis, namun kita ingin memahami mengapa pengguna merasa lambat atau kesulitan saat berinteraksi. Pendekatannya adalah menggunakan data empiris (seperti hitungan detik atau jumlah klik) untuk membuktikan sebuah hipotesis guna meningkatkan kualitas interaksi manusia dengan sistem tersebut.