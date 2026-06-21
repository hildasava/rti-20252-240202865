# WS-11: Data Validation & Integrity

> **Bab 11 — Validasi Data & Integritas**

---

## Ringkasan Materi

### Data Trust Model

```
Raw Data → Data Cleaning → Consistency Check → Validation Process → Trusted Data
```

Data mentah belum bisa dipercaya. Harus melewati pipeline validasi sebelum siap untuk analisis statistik.

### Empat Pilar Data Quality

| Pilar | Deskripsi | Contoh Pelanggaran |
|-------|----------|-------------------|
| **Accuracy** | Nilai dalam range masuk akal | Akurasi = 1.5 (di luar [0,1]) |
| **Consistency** | Format seragam di semua run | Run 1: CSV, Run 2: JSON |
| **Completeness** | Tidak ada data hilang dari plan | 97 dari 100 run tercatat |
| **Validity** | Data sesuai desain eksperimen | Parameter baseline tercampur treatment |

### Proses Validasi Progresif

1. **Format validation** — Tipe file, header, kolom
2. **Range validation** — Nilai dalam batas logis
3. **Consistency validation** — Format seragam antar-run
4. **Logic validation** — Data cocok dengan desain eksperimen

Jika gagal di langkah awal → tidak perlu lanjut.

### Anomaly Detection — 3 Jenis

| Jenis | Deskripsi | Deteksi |
|-------|----------|---------|
| **Statistical outlier** | Nilai di luar distribusi normal | IQR: < Q1-1.5×IQR atau > Q3+1.5×IQR |
| **Contextual anomaly** | Normal absolut, abnormal dalam konteks | Run 1-10: ~91%, Run 11-20: ~88% |
| **Pattern anomaly** | Pola sistematis (bukan random) | Performa menurun berurutan |

**Prinsip:** Detect → Investigate → Document → Decide — **JANGAN langsung hapus.**

### Engineering vs Research Validation

| Aspek | Engineering | Research |
|-------|-----------|---------|
| Tujuan | Data sesuai spesifikasi bisnis | Data layak untuk analisis statistik |
| Missing data | Impute / set default | Investigasi penyebab → dokumentasi |
| Outlier | Bug → fix | Mungkin temuan → investigasi |
| Dokumentasi | Minimal (log error) | Komprehensif (anomali + keputusan) |

### Jebakan Kognitif

1. "Logging otomatis ≠ data benar" → bisa ada bug di logger
2. "Outlier = hapus" → bisa jadi temuan penting
3. "Dataset kecil tidak perlu validasi" → justru lebih rentan
4. "Mean normal = data benar" → [94, 95, 93, **44**, 94] → mean 84% terlihat wajar

---

## Template A.11 — Data Validation Checklist

```

DATA VALIDATION CHECKLIST

Completeness:
  [✓] Semua skenario tercakup
  [✓] Jumlah run sesuai rencana
  [✓] Tidak ada file output hilang
  Missing: 0 dari 74 data points

Format Consistency:
  [✓] Semua file format sama (Excel/CSV)
  [✓] Header konsisten
  [✓] Tipe data konsisten (numerik tetap numerik)

Range & Logic:
  [✓] Nilai dalam range masuk akal
  [✓] Tidak ada waktu negatif
  [✓] Metrik 0–100%, tidak di luar range
  Anomali ditemukan: Tidak ditemukan anomali atau data minus pada metrik Time_on_Task maupun Klik_Salah.

Cross-Validation:
  [✓] Run identik → hasil mendekati
  [✓] Trend konsisten dengan ekspektasi teori (Waktu pengerjaan pada kondisi Full Sticker lebih lama dibanding kondisi Clean akibat adanya elemen distraksi visual).

Keputusan:
  [✓] Data siap analisis
  [ ] Perlu cleaning
  [ ] Perlu re-run (skenario: —)
  
  ```
## Latihan 1 — Completeness Check

Verifikasi apakah semua data yang direncanakan sudah terkumpul.

| Skenario               | Run Direncanakan | Run Tercatat | Missing | Alasan |
|------------------------|------------------|--------------|---------|--------|
| Kondisi CLEAN          | 37               | 37           | 0       | Seluruh 37 responden berhasil menyelesaikan pengujian tanpa kendala sistem. |
| Kondisi FULL STICKER   | 37               | 37           | 0       | Seluruh 37 responden berhasil menyelesaikan pengujian tanpa kendala sistem. |

Total expected: 74 | Total actual: 74 | Missing: 0

Keputusan untuk data missing:
> Karena nilai data yang hilang (Missing) adalah 0, maka seluruh rangkaian pengujian dari 37 responden untuk kedua skenario (total 74 sesi) dinyatakan lengkap dan utuh. Tidak diperlukan tindakan pengujian ulang (re-run), dan seluruh dataset ini valid untuk langsung dibawa ke tahap analisis statistik berikutnya.
---

## Latihan 2 — Anomaly Investigation

Periksa data Anda untuk anomali. Gunakan metode IQR atau z-score.

**Dataset sampel (atau data Anda sendiri):**

| Run                  | Time on Task (s) |
|----------------------|------------------|
| 1 (Res_01 - Clean)   | 5.0              |
| 2 (Res_02 - Clean)   | 5.0              |
| 3 (Res_03 - Clean)   | 5.0              |
| 38 (Res_01 - Full)   | 10.0             |
| 39 (Res_02 - Full)   | 11.0             |

Deteksi outlier:
- Q1 = 6.0 | Q3 = 10.0 | IQR = 4.0
- Batas bawah (Q1 - 1.5×IQR) = 0.0
- Batas atas (Q3 + 1.5×IQR) = 16.0
- Outlier terdeteksi: 0 (Tidak ada outlier yang terdeteksi)

Investigasi (untuk setiap outlier):

| Outlier | Nilai | Kemungkinan Penyebab | Keputusan |
|---------|-------|---------------------|-----------|
| —       | —     | Seluruh data berada dalam rentang batas logis (4–13 detik), tidak ada data ekstrem yang melebihi batas IQR. | Semua data valid dan dipertahankan 100% untuk analisis statistik. |
---

## Latihan 3 — Validation Report

Buat laporan validasi ringkas untuk dataset eksperimen Anda.

1. Completeness: 100% data terkumpul (74 dari 74 sesi tercatat penuh)
2. Format: [✓] Konsisten / [ ] Ada inkonsistensi: —
3. Range check (anomali): Aman (0 data anomali ditemukan, semua nilai Time_on_Task berada di dalam rentang batas aman IQR antara 0.0 hingga 16.0 detik)
4. Logic check: [✓] Parameter sesuai plan / [ ] Ada ketidaksesuaian: —

Kesimpulan: [✓] Data siap analisis / [ ] Perlu tindakan: —
---

## Refleksi

> Apa perbedaan antara "data yang benar" dan "data yang dipercaya"? Mengapa proses validasi formal diperlukan meskipun data dikumpulkan secara otomatis?

Jawaban:
- "Data yang benar" adalah data mentah (raw data) berisi angka apa adanya yang terekam secara otomatis oleh lembar observasi atau sistem log saat pengujian berlangsung. 
- "Data yang dipercaya" (trusted data) adalah data yang telah melewati proses pipeline validasi formal (seperti kelengkapan, konsistensi format, dan deteksi anomali/outlier menggunakan statistik IQR), sehingga data tersebut dijamin memiliki integritas dan layak digunakan untuk analisis statistik.

Proses validasi formal tetap diperlukan meskipun data dikumpulkan secara otomatis karena pengumpulan otomatis tidak menjamin bebas dari kesalahan logika atau teknis. Validasi formal memastikan tidak ada anomali tersembunyi (seperti kesalahan human error saat penyalinan data, responden yang tidak serius, atau isu teknis lainnya) yang dapat merusak akurasi pengambilan kesimpulan ilmiah pada uji statistik selanjutnya.
