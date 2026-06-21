# WS-13: Data Preprocessing

> **Bab 13 — Preprocessing & Persiapan Data untuk Analisis**

---

## Ringkasan Materi

### Data Refinement Pipeline

```
Raw Data → Cleaning → Transformation → Normalization → Processed Data → Analysis Ready
```

Setiap tahap memiliki tujuan berbeda. **Preprocessing bukan langkah teknis biasa** — setiap keputusan preprocessing adalah keputusan riset yang bisa mengubah kesimpulan.

### Empat Prinsip Preprocessing

| Prinsip | Deskripsi |
|---------|----------|
| **Consistency** | Metode sama untuk data yang sama |
| **Transparency** | Setiap langkah terdokumentasi |
| **Reproducibility** | Orang lain bisa mengulang dengan hasil sama |
| **Minimal Distortion** | Ubah sesedikit mungkin; jika normalisasi tidak perlu, jangan lakukan |

### Cleaning Triad

| Masalah | Strategi | Risiko |
|---------|---------|--------|
| **Missing values** | | |
| — Listwise deletion | Missing < 5%, random | Data loss |
| — Mean/median imputation | Sedikit missing, dist. normal | Mengurangi variabilitas |
| — Model-based imputation | Banyak missing, pola sistematis | Introduces dependency |
| — Flag & separate | Missing karena alasan substantif | Kompleksitas analisis |
| **Duplikat** | Identifikasi → verifikasi → hapus | False positive (data mirip ≠ duplikat) |
| **Error format** | Standardisasi tipe, encoding | Kehilangan informasi saat konversi |

### Normalisasi — Kapan & Metode Mana

| Metode | Formula | Output | Sensitif Outlier? |
|--------|---------|--------|-------------------|
| Min-max | (x-min)/(max-min) | [0, 1] | Ya |
| Z-score | (x-mean)/std | Unbounded | Lebih robust |
| Robust scaling | (x-median)/IQR | Unbounded | Paling robust |

**Kunci:** Parameter normalisasi harus dihitung dari **training set saja** — bukan seluruh data. Pelanggaran = **data leakage**.

### Data Leakage Prevention

Data leakage terjadi ketika informasi dari test set "bocor" ke preprocessing:
- Normalisasi parameter dari seluruh dataset ← **SALAH**
- Cross-validation dilakukan sebelum split ← **SALAH**
- Feature selection menggunakan label test set ← **SALAH**

### Jebakan Kognitif

1. "Preprocessing cuma teknis — tidak perlu detail" → bisa ubah kesimpulan
2. "Lebih banyak preprocessing = lebih bersih = lebih baik" → over-processing distorsi data
3. "Normalisasi selalu diperlukan" → belum tentu, tergantung metode analisis
4. "Imputation sama untuk semua situasi" → strategi harus sesuai konteks

---

## Template A.13 — Preprocessing Documentation Log


PREPROCESSING LOG

Dataset           : Data Eksperimen UI/UX TikTok Shop (Clean vs Full Sticker)
Jumlah data awal  : 74 responden

Cleaning:
| Masalah | Jumlah Kasus | Penanganan | Justifikasi |
|---------|-------------|------------|-------------|
| Missing | 0 Kasus      | Tidak ada  | Data kuesioner sudah lengkap dan bersih sejak di Excel. |
| Duplikat| 0 Kasus      | Tidak ada  | Semua data ID responden bersifat unik. |
| Error   | 0 Kasus      | Tidak ada  | Format input angka sudah konsisten. |

Transformation:
| Transformasi | Variabel | Detail | Alasan |
|-------------|----------|--------|--------|
| Coding Data  | Status   | Mengubah teks "Clean" menjadi 1, dan "Full Sticker" menjadi 2 | Agar bisa dibaca dan diproses oleh variabel Grouping di SPSS. |

Normalization:
  Metode    : Tidak dilakukan normalisasi
  Alasan    : Uji hipotesis menggunakan statistik non-parametrik (Mann-Whitney U), sehingga tidak memerlukan normalisasi skala.
  Parameter : (dihitung dari: seluruh data)

Leakage Check:
  [✓] Parameter normalisasi dari training set saja
  [✓] Tidak ada informasi test set dalam preprocessing
  [✓] Cross-validation dilakukan setelah split

Jumlah data akhir : 74 responden
Script tersedia   : [✓] Ya → path: SPSS Syntax / Excel Worksheet | [ ] Belum


## Latihan 1 — Cleaning Plan

Periksa dataset Anda (atau dataset contoh) dan dokumentasikan masalah yang ditemukan.

| Masalah | Jumlah Kasus | Penanganan | Justifikasi |
|---------|-------------|------------|-------------|
| Missing Value | 0 Kasus | Tidak ada tindakan | Data kuesioner dari Google Form/Excel sudah terisi penuh oleh 74 responden tanpa ada kolom kosong. |
| Duplikat Data | 0 Kasus | Tidak ada tindakan | Hasil verifikasi ID responden menunjukkan setiap baris data bersifat unik (tidak ada input ganda). |
| Error Format | 0 Kasus | Tidak ada tindakan | Seluruh entri data waktu (Time on Task) dan kesalahan klik (Klik Salah) sudah dalam bentuk angka numerik yang valid. |

**Jumlah data sebelum cleaning:** 74  
**Jumlah data setelah cleaning:** 74  
**Persentase data yang hilang/berubah:** 0%

---

## Latihan 2 — Normalisasi Decision

Tentukan apakah data Anda perlu normalisasi, dan jika ya, metode apa yang tepat.

| Variabel | Range Asli | Distribusi | Outlier? | Metode Normalisasi | Alasan |
|----------|-----------|-----------|----------|-------------------|--------|
| `time_on_task` | 4.0 – 8.0s | Tidak Normal (Skewed) | Tidak | Tidak Perlu | Analisis menggunakan uji non-parametrik Mann-Whitney yang tidak sensitif terhadap asumsi distribusi normalitas data. |
| `klik_salah` | 0.0 – 1.0 | Tidak Normal | Tidak | Tidak Perlu | Data berupa skor diskrit berskala kecil dan tidak menggunakan algoritma berbasis jarak (*distance-based*). |

**Apakah normalisasi diperlukan?** [ ] Ya / [✓] Tidak
**Justifikasi:**
> Analisis pengujian hipotesis pada riset ini diarahkan menggunakan metode statistik non-parametrik (Uji Mann-Whitney U). Karena metode pengujian ini bekerja berdasarkan peringkat nilai (*ranks*) dan bukan nilai absolut datanya, maka proses transformasi skala atau normalisasi nilai sama sekali tidak diperlukan karena tidak akan mengubah struktur peringkat maupun hasil signifikansi akhirnya.

**Leakage check:**
- [✓] Parameter dihitung dari training set saja *(Not Applicable karena tidak ada normalisasi)*
- [✓] Normalisasi diterapkan setelah train-test split *(Not Applicable karena tidak ada normalisasi)*

---

## Latihan 3 — Preprocessing Report

Buat ringkasan preprocessing lengkap — dokumentasi yang cukup bagi orang lain untuk mereplikasi.

```
PREPROCESSING SUMMARY

1. Dataset: Eksperimen UI/UX TikTok Shop (Clean vs Full Sticker)
2. Data awal: 74 records, 3 features
3. Cleaning:
   - Missing values: 0 kasus, metode: -
   - Duplikat: 0 kasus, tindakan: -
   - Error: 0 kasus, tindakan: -
4. Transformation: Data Coding pada variabel 'Status' (Mengubah teks kelompok "Clean" menjadi kode angka 1, dan kelompok "Full Sticker" menjadi kode angka 2)
5. Normalisasi: Tidak dilakukan normalisasi (metode), parameter dari seluruh data
6. Data akhir: 74 records, 3 features
7. Leakage check: [✓] Lulus / [ ] Ada masalah
```

---

## Refleksi

> Apakah Anda pernah melakukan normalisasi "karena biasa dilakukan" tanpa mempertimbangkan apakah benar-benar diperlukan? Apa risiko over-preprocessing?

> Ya, sebelumnya saya sempat berpikir bahwa normalisasi adalah langkah wajib dalam setiap *preprocessing*. Namun, setelah mempelajari materi ini, saya menyadari bahwa normalisasi hanya diperlukan jika metode analisis yang digunakan bersifat *distance-based* (seperti K-Means atau KNN) atau jika skala antar variabel sangat timpang. 
>
> Risiko dari *over-preprocessing* adalah terjadinya distorsi informasi. Jika kita melakukan normalisasi pada data yang sebenarnya tidak memerlukan transformasi skala (seperti pada data yang akan diuji dengan metode non-parametrik), kita justru berisiko menghilangkan variasi alami data yang penting bagi hasil interpretasi. Selain itu, *over-preprocessing* meningkatkan kompleksitas analisis tanpa memberikan nilai tambah, bahkan bisa membuat hasil analisis menjadi kurang intuitif atau sulit dijelaskan maknanya secara substantif.