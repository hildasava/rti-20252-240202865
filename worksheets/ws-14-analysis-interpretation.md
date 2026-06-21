# WS-14: Analysis, Interpretation & Failure Analysis

> **Bab 14 — Analisis Data, Interpretasi & Failure Analysis**

---

## Ringkasan Materi

### Data → Knowledge Model

```
Data → Analysis → Interpretation → Explanation → Knowledge
```

Tiga level yang berbeda:
- **Analysis** — "Apa yang terjadi?" (deskriptif + inferensial)
- **Interpretation** — "Apa artinya?" (konteks RQ + literatur)
- **Failure Analysis** — "Mengapa tidak berhasil?" (boundary conditions)

### Beyond p-value

**Statistical significance ≠ practical significance.** Selalu laporkan:
1. p-value (signifikansi statistik)
2. Effect size (besarnya efek)
3. Confidence interval (rentang ketidakpastian)

| Effect Size (Cohen's d) | Interpretasi |
|-------------------------|-------------|
| < 0.2 | Small |
| 0.2 – 0.8 | Medium |
| > 0.8 | Large |

### Pemilihan Uji Statistik

| Kondisi | Uji yang Tepat |
|---------|---------------|
| 2 grup, normal, paired | Paired t-test |
| 2 grup, non-normal | Wilcoxon signed-rank |
| > 2 grup, normal | One-way ANOVA + post-hoc |
| > 2 grup, non-normal | Kruskal-Wallis + post-hoc |
| 2 variabel kontinu | Pearson (normal) / Spearman (rank) |

### Failure Analysis as Contribution

Hipotesis yang ditolak adalah **temuan yang berharga**:

| Dataset | New (F1) | Baseline (F1) | p-value | Cohen's d |
|---------|---------|--------------|---------|-----------|
| DS-1 (small, clean) | 94.2±1.1 | 89.3±1.5 | <0.001 | **3.7** |
| DS-4 (medium, noisy) | 78.3±3.2 | 82.1±2.8 | 0.008 | **-1.3** |
| DS-5 (large, noisy) | 71.6±4.1 | 80.5±3.0 | <0.001 | **-2.5** |

**Insight:** Metode baru unggul di data bersih tapi gagal di data noisy → asumsi Gaussian dilanggar → **boundary condition** ditemukan → hybrid approach direkomendasikan.

**Partial failure + deep analysis = kontribusi lebih kaya daripada full success tanpa analisis.**

### Limitation Types

| Jenis | Contoh |
|-------|--------|
| Internal validity | Confounders yang tidak dikontrol |
| External validity | Generalisasi ke domain lain |
| Construct validity | Metrik mengukur apa yang dimaksud? |
| Statistical limitation | Sample size, asumsi distribusi |

### Jebakan Kognitif

1. "Signifikan statistik = penting secara praktis" → cek effect size
2. "Hipotesis tidak didukung → cari sudut baru" → p-hacking
3. "Kegagalan tidak perlu dilaporkan detail" → missed insight
4. "Limitasi cukup disebutkan, tidak perlu dianalisis" → kedalaman hilang

---

## Template A.14 — Analysis & Interpretation Report

```
## ANALYSIS & INTERPRETATION

1. Statistik Deskriptif:
   | Skenario | Mean | Std | Median | Min | Max | n |
   |----------|------|-----|--------|-----|-----|---|
   | Clean    | 19.0 | 2.1 | 19.0   | 16  | 23  | 37 |
   | Full Stk | 56.0 | 4.5 | 56.0   | 48  | 65  | 37 |

2. Uji Hipotesis:
   Uji yang digunakan  : Mann-Whitney U Test
   Justifikasi         : Data tidak berdistribusi normal (non-parametrik) dan membandingkan dua kelompok independen.
   Hasil: p < 0.001, effect size (r) = 0.82
   CI 95%              : [32.4, 41.2]

3. Keputusan:
   [✓] H₀ ditolak → H₁ diterima
   [ ] H₀ tidak ditolak

4. Interpretasi:
   Hubungan ke RQ         : Desain antarmuka Clean secara signifikan meningkatkan efisiensi waktu pengerjaan tugas pengguna.
   Practical significance : Penghematan waktu sebesar ±37 detik per transaksi sangat krusial bagi conversion rate e-commerce.
   Perbandingan literatur : Konsisten dengan prinsip minimalisme Jacob Nielsen terkait beban kognitif pengguna.

5. Limitation:
   | Jenis | Ancaman | Dampak | Mitigasi |
   |-------|---------|--------|----------|
   | External | Generalisasi | Terbatas pada aplikasi belanja | Uji silang dengan domain aplikasi lain |
   | Construct | Pengukuran | Efek Hawthorne (diamati) | Melakukan pengujian tanpa sepengetahuan user |

6. Failure Analysis (jika H₀ tidak ditolak):
   Penyebab potensial  : N/A (Hipotesis didukung secara signifikan)
   Boundary condition  : N/A
   Insight             : Variabel "klik salah" tetap rendah di kedua kelompok, menunjukkan desain Clean tidak mengorbankan akurasi.
```

---

## Latihan 1 — Pemilihan Uji Statistik

Tentukan uji statistik yang tepat untuk eksperimen Anda.

| Pertanyaan | Jawaban |
|-----------|---------|
| Berapa grup yang dibandingkan? | 2 Grup (Clean Design vs Full Sticker Design) |
| Apakah data berpasangan (paired)? | Tidak (Independent Samples) |
| Apakah distribusi normal? (uji normalitas) | Tidak Normal (berdasarkan uji Shapiro-Wilk/Kolmogorov-Smirnov) |
| **Uji yang dipilih:** | Mann-Whitney U Test |
| **Justifikasi:** | Karena data bersifat independen, terdiri dari dua kelompok, dan tidak memenuhi asumsi normalitas, maka uji non-parametrik Mann-Whitney U adalah pilihan yang paling valid dan robust terhadap outlier. |

**Effect size yang akan dilaporkan:** [ ] Cohen's d / [ ] Eta-squared / [✓] Lainnya: r (Rank-biserial correlation)
---

## Latihan 2 — Interpretasi Hasil

Gunakan data berikut (atau data riil Anda) untuk berlatih interpretasi.

**Data:**
| Model | Accuracy (mean ± std) | n |
|-------|----------------------|---|
| A | 89.2 ± 1.5 | 10 |
| B | 87.8 ± 2.1 | 10 |

p = 0.045, Cohen's d = 0.74, CI 95% = [0.03, 2.77]

| Aspek | Interpretasi |
|-------|-------------|
| Signifikansi statistik | p = 0.045 < 0.05, maka hasilnya signifikan secara statistik pada α=0.05. |
| Effect size | Cohen's d = 0.74, menunjukkan *medium-to-large effect* (pengaruh yang cukup kuat antara dua model). |
| Practical significance | Meski signifikan, perbedaan akurasi sebesar 1.4% perlu dipertimbangkan apakah memberikan dampak nyata bagi performa bisnis/pengguna. |
| Hubungan ke RQ | Menjawab pertanyaan penelitian bahwa terdapat perbedaan performa yang signifikan antar model yang diuji. |
| Perbandingan literatur | Hasil ini sejalan dengan studi terdahulu yang menunjukkan bahwa perbedaan arsitektur model dapat memengaruhi akurasi meskipun dalam rentang yang tipis. |

---

## Latihan 3 — Failure Analysis

Latih kemampuan failure analysis: hipotesis TIDAK didukung. Apa yang bisa dipelajari?

**Skenario:** Metode baru Anda mendapat F1 = 83.2%, baseline = 84.7%. p = 0.12 (tidak signifikan).

## Latihan 3 — Failure Analysis

| Pertanyaan | Jawaban |
|-----------|---------|
| Apakah ini "gagal"? | Bukan gagal total. Hipotesis yang tidak terdukung adalah temuan empiris yang valid dan mencegah orang lain melakukan riset serupa di masa depan (mengurangi bias publikasi). |
| Kemungkinan penyebab? | Metode baru menambah kompleksitas komputasi (+40% waktu) tanpa peningkatan F1 yang cukup. Overhead komputasi tidak sebanding dengan gain performa yang didapat. |
| Boundary condition? | Metode baru hanya efektif untuk dataset skala besar (≥ 10.000 record). Pada dataset kecil (< 1.000 record), baseline terbukti lebih stabil dan efisien. |
| Insight yang bisa diambil? | Terdapat trade-off antara kompleksitas model dan ukuran dataset. Direkomendasikan menggunakan *hybrid approach* atau model selektif yang beradaptasi berdasarkan jumlah data. |
| Apakah layak dilaporkan? Mengapa? | Sangat layak. *Negative result* yang disertai analisis mendalam (boundary condition) adalah kontribusi nyata bagi komunitas riset (seperti ACL/SIGIR) karena memberikan batasan pengetahuan yang jelas. |

**Limitation terkait:**
| Jenis | Ancaman | Dampak |
|-------|---------|--------|
| Statistical | Hanya 5 run per skenario | *Power test* rendah, risiko hasil tidak stabil. |
| Computational | Overhead waktu 40% | Menurunkan efisiensi operasional sistem. |
| Construct | Dataset kecil (<1.000) | Tidak merepresentasikan skenario dunia nyata yang besar. |

## Refleksi

> Apakah "failure" dalam riset benar-benar gagal, atau justru kontribusi? Bagaimana failure analysis mengubah cara Anda melihat hasil negatif?

> Dalam riset, "kegagalan" hipotesis bukanlah sebuah kegagalan (failure), melainkan sebuah temuan (finding). Hasil negatif atau hasil yang tidak sesuai dengan hipotesis awal justru merupakan kontribusi yang berharga bagi komunitas ilmiah karena memberikan batasan pengetahuan (*boundary conditions*) yang jelas. Jika kita hanya melaporkan riset yang sukses saja, kita berisiko membiarkan orang lain mengulangi kesalahan yang sama.
>
> *Failure analysis* mengubah cara pandang saya dengan menggeser fokus dari "apakah hipotesis saya terbukti?" menjadi "mengapa fenomena ini terjadi?". Pendekatan ini membuat saya lebih kritis, jujur secara metodologis, dan mampu melihat kegagalan sebagai pintu masuk untuk memahami perilaku data yang lebih dalam. Hasil negatif pun akhirnya menjadi data yang kaya akan insight, bukan sekadar data yang tidak terpakai.