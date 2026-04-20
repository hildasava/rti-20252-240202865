# WS-04: Research Question & Hypothesis

> **Bab 4 — Research Question, Contribution & Hypothesis**

---

## Ringkasan Materi

### RQ Bukan Pertanyaan Biasa

Research Question yang baik secara implisit mengandung cetak biru eksperimen: subjek, baseline, metrik, domain, dataset.

| Kualitas | Contoh |
|----------|--------|
| **Buruk** | "Bagaimana pengaruh deep learning terhadap deteksi malware?" |
| **Baik** | "Apakah CNN menghasilkan F1-Score lebih tinggi dari RF pada CIC-MalMem-2022?" |

Perbedaan: RQ yang baik menyebutkan **metode spesifik**, **metrik terukur**, **baseline**, dan **dataset**.

### Tiga Jenis RQ

| Jenis | Pola | Kebutuhan |
|-------|------|-----------|
| **Comparison** | A vs B → mana lebih baik? | ≥ 2 metode, metrik sama |
| **Improvement** | A' vs A → modifikasi lebih baik? | Pre/post, bukti perbaikan |
| **Exploratory** | Faktor X₁...Xₙ → pengaruh terhadap Y? | Multi-variabel, korelasi/regresi |

### Contribution Statement

Tiga jenis kontribusi: **Improvement** (metode terbukti lebih baik), **Comparison** (perbandingan sistematis yang belum ada), **Novel Approach** (pendekatan baru). Kontribusi harus terhubung langsung dengan gap — kontribusi tanpa gap = klaim tanpa justifikasi.

### Hypothesis H₀ / H₁

- **H₀** (Null) = Tidak ada perbedaan signifikan — asumsi default, harus dibuktikan salah
- **H₁** (Alternative) = Ada perbedaan signifikan — diterima hanya jika H₀ ditolak
- Harus **falsifiable**, mengandung **metrik terukur**, dirumuskan **SEBELUM eksperimen**

### Rantai Operasionalisasi

```
RQ → Variable → Metric → Data → Analysis
```

Jika rantai ini tidak lengkap, RQ belum mature. Bi-directional: RQ yang tidak bisa jadi hipotesis testable harus direvisi mundur.

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan pertanyaan | Apa yang harus dibangun? | Apa yang harus dibuktikan? |
| Bentuk jawaban | Sistem yang berfungsi | Bukti empiris terukur |
| Sukses diukur oleh | User satisfaction, uptime | Signifikansi statistik, effect size |
| Jika gagal | Debug dan perbaiki | Laporkan, analisis mengapa |

### Istilah Penting

- **Research Question (RQ)** — Pertanyaan spesifik: variabel terukur + metrik + konteks
- **Contribution Statement** — Apa yang diketahui setelah riset selesai yang sebelumnya belum ada
- **H₀ / H₁** — Null vs Alternative Hypothesis
- **Falsifiability** — Kondisi hipotesis ditolak harus bisa didefinisikan sebelum eksperimen
- **Operationalization** — Proses mewujudkan konsep abstrak menjadi variabel terukur

---

## Template A.4 — RQ-Contribution-Hypothesis

### RQ-CONTRIBUTION-HYPOTHESIS

**Gap Statement:** Penelitian terdahulu (oleh Ade Astian, Afina G., dkk) lebih fokus pada persepsi psikologis konsumen, namun belum ada pengukuran efisiensi teknis (detik/klik) pada antarmuka Live Streaming TikTok Shop yang memiliki kepadatan informasi tinggi (*visual clutter*) dibandingkan fitur belanja standar.

**Research Question:** * **Tipe:** [X] Comparison  [ ] Improvement  [ ] Exploratory
* **Formulasi:** Apakah terdapat perbedaan signifikan pada efisiensi waktu transaksi (*Time-on-Task*) antara penggunaan fitur Live Streaming dengan fitur TikTok Shop Tab konvensional pada pengguna Gen-Z?
* **Variabel IV:** Jenis Antarmuka Fitur (Live Streaming vs TikTok Shop Tab).
* **Variabel DV:** Efisiensi Teknis (*Time-on-Task*).
* **Metrik:** Durasi penyelesaian transaksi (dalam satuan detik).
* **Dataset:** Data primer hasil observasi eksperimen terhadap 30 responden mahasiswa (Gen-Z).
* **Baseline:** Fitur navigasi TikTok Shop Tab (Non-Live).

**Quality Check RQ:** * [X] Variabel spesifik
* [X] Metrik jelas
* [X] Baseline ada
* [X] Konteks disebutkan
* [X] Memerlukan eksperimen (bukan hanya survei literatur)

**Contribution Statement:** * **Apa yang baru diketahui:** Perbandingan performa teknis dan tingkat efisiensi antarmuka pada fitur *social commerce* yang memiliki gangguan visual (*clutter*) dibandingkan dengan antarmuka belanja standar.
* **Jenis kontribusi:** [ ] Improvement  [X] Comparison  [ ] Novel approach
* **Gap yang diisi:** *Method Gap* (pengukuran objektif) dan *Context Gap* (kondisi *visual clutter* pada fitur Live).

**Hypothesis Pair:** * **H₀:** Tidak ada perbedaan signifikan pada rata-rata waktu transaksi antara fitur Live Streaming dan fitur belanja biasa.
* **H₁:** Fitur Live Streaming memiliki waktu transaksi yang lebih lama (kurang efisien) secara signifikan dibandingkan fitur belanja biasa akibat hambatan navigasi visual.
* **Threshold:** p-value < 0.05.
* **Justifikasi threshold:** Merupakan standar tingkat signifikansi (Alpha 5%) dalam pengujian statistik untuk menolak hipotesis nol pada riset interaksi manusia-komputer.

---

## Latihan 1 — Dari Gap ke RQ

Gunakan gap yang ditemukan di WS-03. Transformasikan menjadi Research Question.

**Gap dari WS-03:** Kurangnya pengukuran metrik efisiensi teknis (HCI) pada fitur Live Streaming TikTok Shop yang memiliki kepadatan informasi tinggi (*visual clutter*).

**RQ versi pertama (tulis bebas):**
> Apakah proses belanja lewat Live Streaming di TikTok lebih tidak efisien dibandingkan lewat menu belanja biasa karena layarnya terlalu penuh informasi?

**Evaluasi RQ:**

| Komponen | Ada? | Isi |
|----------|------|-----|
| Metode spesifik | Ya | Perbandingan fitur Live vs Non-Live |
| Metrik terukur | Ya | Efisiensi teknis (*Time-on-Task*) |
| Baseline | Ya | Fitur TikTok Shop Tab konvensional |
| Dataset/konteks | Ya | Pengguna Gen-Z di Indonesia |

**Tipe RQ:** [X] Comparison / [ ] Improvement / [ ] Exploratory

**RQ versi revisi (setelah evaluasi):**
> "Bagaimana perbandingan efisiensi waktu transaksi (*Time-on-Task*) pada antarmuka Live Streaming TikTok Shop dibandingkan dengan fitur TikTok Shop Tab konvensional bagi pengguna Gen-Z?"

---

## Latihan 2 — Hypothesis Pair

Rumuskan pasangan hipotesis dari RQ di Latihan 1.

| Komponen | Isi |
|----------|-----|
| **H₀** | Tidak ada perbedaan efisiensi waktu transaksi (*Time-on-Task*) yang signifikan antara penggunaan fitur Live Streaming dan fitur TikTok Shop Tab. |
| **H₁** | Fitur Live Streaming memiliki durasi transaksi yang lebih lama secara signifikan dibandingkan fitur TikTok Shop Tab akibat adanya *visual clutter*. |
| **Metrik** | *Time-on-Task* (detik) dan *Number of Clicks* (jumlah klik). |
| **Threshold** | *p-value* < 0.05. |
| **Justifikasi threshold** | Merupakan standar tingkat signifikansi (Alpha 5%) yang umum digunakan dalam riset perilaku dan interaksi manusia-komputer untuk menolak hipotesis nol. |

**Apakah hipotesis ini falsifiable?** [X] Ya / [ ] Tidak
> **Bagaimana cara membuktikannya salah?** Hipotesis ini terbukti salah jika setelah dilakukan uji statistik (misalnya *Independent Samples T-Test*), nilai signifikansi (*p-value*) lebih besar dari 0.05, yang berarti tidak ada perbedaan performa yang nyata di antara kedua fitur tersebut.

---

## Latihan 3 — Rantai Operasionalisasi

Lengkapi rantai dari RQ hingga metode analisis.

| Tahap | Isi |
|-------|-----|
| **RQ** | Apakah fitur Live Streaming lebih tidak efisien (waktu lebih lama) dibandingkan fitur TikTok Shop Tab konvensional? |
| **Variable (IV)** | Mode Antarmuka Belanja (Live Streaming vs TikTok Shop Tab). |
| **Variable (DV)** | Efisiensi Pengguna (*User Efficiency*). |
| **Metric** | *Completion Time* (detik) dan *Number of Clicks* (frekuensi klik). |
| **Data source** | Data primer melalui **Rekam Layar (Screen Recording)** saat responden melakukan tugas belanja (*Task Scenario*) untuk dianalisis kembali durasi dan jumlah kliknya. |
| **Analysis method** | *Independent Samples T-Test* (membandingkan rata-rata efisiensi antara dua mode antarmuka). |

**Apakah rantai lengkap?** [X] Ya / [ ] Tidak
> **Jika tidak, tahap mana yang perlu direvisi?** Rantai sudah lengkap dan sinkron; penggunaan rekam layar menjamin data metrik (detik dan klik) menjadi sangat objektif dan akurat.

---

## Refleksi

> Ambil satu judul skripsi/paper yang pernah dibaca. Coba ekstrak RQ-nya. Apakah RQ tersebut memenuhi semua komponen (metode, metrik, baseline, konteks)? Jika tidak, apa yang hilang?

**Judul:** Analisis User Experience Terhadap Purchase Intention Di Tiktok Shop (Tinezia Hairunisya, 2025).

**RQ yang diekstrak:** Apakah variabel User Experience (UX) memiliki pengaruh yang signifikan terhadap Niat Beli (*Purchase Intention*) pengguna pada platform TikTok Shop?

**Komponen yang hilang:** RQ tersebut sudah memiliki konteks (TikTok Shop) dan subjek yang jelas, namun masih **kehilangan komponen metode spesifik dan metrik teknis**. Pertanyaannya masih bersifat umum (eksploratif) dan tidak menyebutkan secara eksplisit **metrik objektif** (seperti durasi waktu atau jumlah klik) serta tidak menyertakan **baseline** (perbandingan dengan antarmuka lain) sebagai standar pengukuran efisiensi.