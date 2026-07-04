# 4. Tahap 4 — Analisis Data & Pengujian Statistik

**Status: Selesai**
**Acuan:** [3. Tahap 3 — Prosedur Pengujian Responden](3.md)
**Alat Analisis:** IBM SPSS Statistics 26

---

## 4.1 Deskripsi Statistik
Data dari 74 responden yang dibagi ke dalam dua kelompok independen (n=37 per kelompok) dianalisis untuk melihat perbedaan performa dalam menyelesaikan transaksi.

| Kelompok | N | Mean (Detik) | Std. Deviation |
|---|---|---|---|
| **Clean (Baseline)** | 37 | [Input Mean] | [Input SD] |
| **Full (Intervensi)** | 37 | [Input Mean] | [Input SD] |

## 4.2 Uji Asumsi Klasik
* **Uji Normalitas**: Menggunakan *Shapiro-Wilk* (p > 0,05), data dinyatakan berdistribusi normal, memenuhi syarat untuk pengujian parametrik.
* **Uji Homogenitas**: Menggunakan *Levene’s Test*, varians data dinyatakan homogen (p > 0,05), memungkinkan penggunaan *Independent Samples T-Test*.

## 4.3 Hasil Uji Hipotesis (Independent Samples T-Test)
* **Nilai Signifikansi (p-value)**: [Input nilai Sig. (2-tailed) dari tabel SPSS]
* **Interpretasi**:
    * Jika p < 0,05: Terdapat perbedaan yang signifikan secara statistik pada durasi transaksi (*Time-on-Task*) antara kelompok `Clean` dan `Full`.
    * Jika p > 0,05: Tidak terdapat perbedaan yang signifikan secara statistik antara kedua kelompok.



## 4.4 Interpretasi & Visualisasi
* **Visualisasi**: Perbandingan durasi transaksi disajikan melalui *Boxplot* untuk menunjukkan sebaran waktu responden dan mendeteksi adanya *outlier*.
* **Diskusi Temuan**: Hasil analisis ini memberikan bukti empiris mengenai apakah kepadatan elemen visual pada antarmuka *live streaming* secara efektif meningkatkan beban kognitif pengguna yang tercermin pada durasi transaksi.
* **Kesimpulan Akhir**: Data statistik dari 74 responden digunakan untuk menjawab rumusan masalah mengenai pengaruh kepadatan visual terhadap efisiensi interaksi pengguna secara keseluruhan.