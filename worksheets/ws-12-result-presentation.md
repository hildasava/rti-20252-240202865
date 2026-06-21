# WS-12: Result Presentation & Visualization

> **Bab 12 — Penyajian Hasil & Visualisasi**

---

## Ringkasan Materi

### Data → Insight Model

```
Validated Data → Structured Presentation → Visualization → Pattern Recognition → Insight
```

Penyajian **mendahului** analisis. Tabel dan grafik membantu peneliti "melihat" data sebelum menghitung. Langsung ke uji statistik tanpa visualisasi berisiko kesimpulan yang secara teknis benar tapi kontekstual salah (Anscombe's Quartet, 1973).

### Tabel = Presisi, Grafik = Pola

Keduanya **saling melengkapi**:
- Tabel: angka presisi, self-contained (dipahami tanpa teks), sortable
- Grafik: pola visual, tren, perbandingan cepat

### Jenis Grafik Berdasarkan Tujuan

| Tujuan | Jenis Grafik |
|--------|-------------|
| Perbandingan antar-skenario | Bar chart (grouped/stacked) |
| Distribusi per-skenario | Box plot / violin plot |
| Tren temporal | Line chart |
| Korelasi dua variabel | Scatter plot |
| Proporsi (total = 100%) | Pie chart (hati-hati!) |

### Contoh Tabel Hasil yang Baik

| Model | Accuracy (%) | F1-Score (%) | Training Time (min) |
|-------|-------------|-------------|---------------------|
| BERT | 88.4 ± 1.2 | 87.1 ± 1.4 | 45.2 ± 3.1 |
| LSTM | 86.1 ± 1.8 | 84.5 ± 2.0 | 12.8 ± 1.2 |
| SVM | 82.3 ± 0.9 | 80.7 ± 1.1 | 0.3 ± 0.1 |

*N=10 per model. Mean ± std. Diurutkan berdasarkan Accuracy.*

### Visualization Bias — Yang Harus Dihindari

| Bias | Deskripsi | Dampak |
|------|----------|--------|
| Truncated axis | Y tidak dari 0 | Memperbesar perbedaan kecil |
| Inconsistent scale | Dua grafik skala beda | Perbandingan menyesatkan |
| Cherry-picked data | Hanya tampilkan yang "menang" | Selektif, tidak jujur |
| 3D effects | Efek 3D tanpa dimensi data ke-3 | Distorsi tanpa informasi |
| Missing error bar | Tidak ada variabilitas | Menyembunyikan ketidakpastian |

### Engineering vs Research Presentation

| Aspek | Engineering | Research |
|-------|-----------|---------|
| Tujuan grafik | Dashboard monitoring | Mendukung argumen ilmiah |
| Informasi wajib | KPI, threshold | Mean, std, CI, N, p-value |
| Bias handling | Less critical | Wajib dihindari (peer-review) |

---

## Template A.12 — Result Presentation Plan


RESULT PRESENTATION PLAN

Research Question : Apakah terdapat perbedaan signifikan pada nilai Time on Task dan jumlah Klik Salah antara pengguna yang bertransaksi menggunakan antarmuka Kondisi CLEAN dibandingkan Kondisi FULL STICKER di Tiktokshop?
Metrik Utama      : Time on Task (detik) dan Klik Salah (jumlah klik)

Tabel Hasil:
| Skenario             | Time on Task (mean ± std) | Klik Salah (mean ± std)  | n   |
|----------------------|---------------------------|---------------------------|-----|
| Kondisi CLEAN        | 6.24 ± 1.14 detik         | 0.16 ± 0.37 klik          | 37  |
| Kondisi FULL STICKER | 10.95 ± 1.25 detik        | 1.35 ± 0.92 klik          | 37  |

Visualisasi yang Direncanakan:
| # | Jenis Grafik            | Pesan Utama                                                                               | Metrik       |
|---|-------------------------|-------------------------------------------------------------------------------------------|--------------|
| 1 | Bar Chart + Error Bar   | Menunjukkan rata-rata durasi pengerjaan Kondisi Full Sticker lebih lama dibanding Clean   | Time on Task |
| 2 | Box Plot                | Menunjukkan sebaran distribusi data dan rentang konsistensi waktu antar kelompok          | Time on Task |

Bias Check:
  [✓] Y-axis mulai dari 0 (atau dijustifikasi)
  [✓] Error bar/CI ditampilkan
  [✓] Semua data disertakan (tidak cherry-picked)
  [✓] Tidak menggunakan 3D tanpa alasan


## Latihan 1 — Tabel Hasil

Buat tabel hasil eksperimen Anda (boleh dengan data simulasi jika belum punya data riil).

| Skenario             | Time on Task (mean ± std) | Klik Salah (mean ± std)  | n   |
|----------------------|---------------------------|---------------------------|-----|
| Kondisi CLEAN        | 6.24 ± 1.14 detik         | 0.16 ± 0.37 klik          | 37  |
| Kondisi FULL STICKER | 10.95 ± 1.25 detik        | 1.35 ± 0.92 klik          | 37  |

Checklist tabel:
- [✓] Self-contained (judul jelas, satuan ada, N tercantum)
- [✓] Mean ± std (bukan single number)
- [✓] Diurutkan berdasarkan metrik utama
- [✓] Format konsisten di semua baris
---

## Latihan 2 — Rencana Visualisasi

Rencanakan 2-3 grafik untuk menyajikan data dari Latihan 1. Setiap grafik = satu pesan.

| # | Jenis Grafik            | Pesan                                                                                     | Data yang Digunakan |
|---|-------------------------|-------------------------------------------------------------------------------------------|---------------------|
| 1 | Bar Chart + Error Bar   | Menampilkan visualisasi perbandingan rata-rata durasi waktu transaksi antar kedua skenario. | Mean ± Std dari Time on Task |
| 2 | Box Plot                | Menunjukkan rentang sebaran distribusi data waktu dan membuktikan tidak adanya outlier.    | Seluruh nilai individu Time on Task |
| 3 | Grouped Bar Chart       | Menunjukkan perbedaan jumlah kesalahan klik (Klik Salah) yang melonjak di Full Sticker.    | Mean ± Std dari Klik Salah |
---

## Latihan 3 — Bias Detection

Evaluasi visualisasi berikut untuk bias (skenario dari contoh):

**Skenario:** Metode A = 91.2%, Metode B = 90.8%. Bar chart dengan Y-axis mulai dari 90%.

| Pertanyaan | Jawaban |
|-----------|---------|
| Apakah Y-axis menyesatkan? | Ya — Sumbu Y yang dipotong mulai dari 90% mendistorsi visual, sehingga Metode A terlihat seolah 2 kali lipat lebih unggul dari Metode B padahal selisih aslinya hanya 0.4%. |
| Apakah error bar ditampilkan? | Tidak ditampilkan pada skenario contoh, yang merupakan kesalahan karena menyembunyikan variabilitas dan ketidakpastian data asli. |
| Apakah semua kondisi ditampilkan? | Ya, kedua kondisi (Metode A dan Metode B) sudah ditampilkan secara berdampingan. |
| Apa solusinya? | Mengubah pengaturan sumbu Y (Y-axis) agar wajib dimulai dari angka 0% agar perbandingan tinggi bar proporsional, serta menambahkan komponen error bar (Std) pada setiap bar grafik. |

Evaluasi grafik Anda sendiri dari Latihan 2:
  [✓] Semua bias check lulus
  [ ] Ada yang perlu diperbaiki: — (Seluruh grafik rencana dipastikan memulai sumbu Y dari angka 0 dan menyertakan error bar standar).
---

## Refleksi

> Mengapa tabel dan grafik keduanya diperlukan — tidak cukup salah satu saja? Pernahkah Anda membuat grafik yang (tanpa sengaja) menyesatkan?

Jawaban:
Tabel dan grafik memiliki fungsi yang saling melengkapi dalam sebuah laporan ilmiah dan tidak bisa saling menggantikan. Tabel sangat diperlukan ketika pembaca membutuhkan ketepatan data secara presisi hingga angka desimal (seperti nilai rata-rata akurat dan standar deviasi), sedangkan grafik sangat unggul dalam memperlihatkan tren visual, pola distribusi, dan perbandingan antar kelompok secara cepat dalam sekali lihat. Jika hanya menggunakan salah satu, kita akan kehilangan salah satu dari akurasi detail angka atau kemudahan pemahaman pola data.

Saya pribadi belum pernah membuat grafik yang menyesatkan dalam skala riset formal, namun hal ini sangat mudah terjadi secara tidak sengaja apabila kita menggunakan pengaturan otomatis (default) dari software spreadsheet seperti Excel. Terkadang, software otomatis memotong batas bawah sumbu Y (truncated axis) menyesuaikan rentang data agar grafik terlihat penuh, padahal hal tersebut justru mendistorsi perbedaan data yang sebenarnya di mata pembaca.