# WS-10: Experiment Execution & Data Collection

> **Bab 10 — Eksekusi Eksperimen & Pengumpulan Data**

---

## Ringkasan Materi

### Experiment Execution Pipeline

```
Design → Execution Plan → Controlled Execution → Data Collection → Data Logging → Dataset for Analysis
```

### Multiple Run = Non-Negotiable

Single run **tidak pernah cukup** untuk klaim ilmiah. Minimum 5-10 run per skenario dengan seed berbeda. Multiple run menghasilkan:
- Mean, std, confidence interval
- Distribusi hasil → uji statistik
- Variabilitas → error bar di grafik

### Execution Plan

Setiap eksperimen harus memiliki plan sebelum eksekusi:
- Daftar skenario
- Jumlah run per skenario
- Random seed per run (pre-determined!)
- Urutan eksekusi (randomisasi/counterbalancing)
- Pre-execution checklist

### Data Logging Komprehensif

Setiap run menghasilkan log terstruktur:
1. **Identitas** — Run ID, timestamp, skenario
2. **Konfigurasi** — Semua parameter, seed, code version
3. **Hasil** — Semua metrik, output detail
4. **Metadata** — Waktu eksekusi, resource usage, warning/error

Format: CSV/JSON/database — **bukan stdout yang di-copy-paste**.

### Engineering vs Research Execution

| Aspek | Engineering | Research |
|-------|-----------|---------|
| Run | Sekali (deploy) | Multiple (min 5-10, seed berbeda) |
| Logging | Error log, access log | Semua parameter, metrik, metadata |
| Anomali | Bug → fix → redeploy | Investigasi → dokumentasi → analisis |
| Urutan | Tidak penting | Bisa bias — perlu randomisasi |

### Anomali = Dokumentasi, Bukan Hapus

Run gagal/anomali tidak boleh dihapus tanpa dokumentasi. Bisa jadi:
- **Bug** → fix & re-run (dokumentasikan!)
- **Batas kemampuan metode** → DNF = temuan
- **Data yang bias** jika hanya simpan run "berhasil"

### Jebakan Kognitif

1. "Satu angka cukup" → tanpa distribusi, tidak bisa diuji
2. "Seed tidak penting" → bahkan algoritma deterministik bisa dipengaruhi library stokastik
3. "Run gagal langsung hapus" → kehilangan temuan potensial
4. "Semua run harus hari ini" → thermal throttling, fatigue

---

## Template A.10 — Execution Plan & Data Log

```
EXECUTION PLAN

| Run # | Skenario | Seed | Parameter | Status | Waktu | Output File |
|-------|----------|------|-----------|--------|-------|-------------|
| 1     | G1: GIFT → CLEAN | Manual (Res-01) | HP A23, DND On, Brightness 60%, Max 180s | Success | GIFT: 45s (2 Klik Salah)<br>CLEAN: 32s (0 Klik Salah) | R_01_GIFT.mp4, R_01_CLEAN.mp4 |
| 2     | G1: GIFT → CLEAN | Manual (Res-02) | HP A23, DND On, Brightness 60%, Max 180s | Success | GIFT: 60s (4 Klik Salah)<br>CLEAN: 40s (1 Klik Salah) | R_02_GIFT.mp4, R_02_CLEAN.mp4 |
| 3     | G1: GIFT → CLEAN | Manual (Res-03) | HP A23, DND On, Brightness 60%, Max 180s | Timeout | GIFT: 180s (7 Klik Salah)<br>CLEAN: 55s (0 Klik Salah) | R_03_GIFT.mp4, R_03_CLEAN.mp4 |
| 4     | G2: CLEAN → GIFT | Manual (Res-21) | HP A23, DND On, Brightness 60%, Max 180s | Success | CLEAN: 38s (0 Klik Salah)<br>GIFT: 50s (3 Klik Salah) | R_21_CLEAN.mp4, R_21_GIFT.mp4 |
| 5     | G2: CLEAN → GIFT | Manual (Res-22) | HP A23, DND On, Brightness 60%, Max 180s | Success | CLEAN: 42s (1 Klik Salah)<br>GIFT: 58s (2 Klik Salah) | R_22_CLEAN.mp4, R_22_GIFT.mp4 |

Jumlah runs per skenario : Kelompok 1 = 20 Responden, Kelompok 2 = 17 Responden
Total runs               : 37 Responden × 2 Kondisi Antarmuka = 74 Sesi Selesai

DATA LOG (per run):
  Run ID    : R-01
  Timestamp : 2026-05-18T09:00:00WIB
  Skenario  : Kelompok 1 (Urutan Tes: Kondisi GIFT Antarmuka Ramah dahulu, baru Kondisi CLEAN)
  Input     : Gawai Penguji + Akun TikTok Penguji (Sudah Terlogin) + Panduan Pembacaan Skenario Tugas Belanja Lisan
  Output    : Video R_01_GIFT.mp4 (Durasi: 45 detik) dan Video R_01_CLEAN.mp4 (Durasi: 32 detik)
  Anomali   : None (Sesi berjalan lancar sesuai kriteria standarisasi batas waktu)
  Catatan   : Responden sempat ragu-ragu selama 4 detik saat pop-up gift menutupi tombol checkout
```

---

## Latihan 1 — Execution Plan

Susun execution plan untuk eksperimen Anda. Tentukan skenario, jumlah run, dan seed sebelum eksekusi.

## Latihan 1 — Execution Plan

Susun execution plan untuk eksperimen Anda. Tentukan skenario, jumlah run, dan seed sebelum eksekusi.

| Run # | Skenario | Seed | Parameter Kunci | Status |
|-------|----------|------|----------------|--------|
| 1     | G1: GIFT → CLEAN | Manual (Res-01) | Akun TikTok Penguji, HP A23, DND On, Max 180s | Planned |
| 2     | G1: GIFT → CLEAN | Manual (Res-02) | Akun TikTok Penguji, HP A23, DND On, Max 180s | Planned |
| 3     | G1: GIFT → CLEAN | Manual (Res-03) | Akun TikTok Penguji, HP A23, DND On, Max 180s | Planned |
| 4     | G2: CLEAN → GIFT | Manual (Res-21) | Akun TikTok Penguji, HP A23, DND On, Max 180s | Planned |
| 5     | G2: CLEAN → GIFT | Manual (Res-22) | Akun TikTok Penguji, HP A23, DND On, Max 180s | Planned |

**Total skenario:** 2 Skenario Urutan Kontrol (G1: GIFT → CLEAN dan G2: CLEAN → GIFT)
**Run per skenario:** Skenario 1 (G1) = 20 Responden, Skenario 2 (G2) = 17 Responden
**Total run keseluruhan:** 37 Responden (Masing-masing melakukan 2 sesi, total menghasilkan 74 rekaman video)

---

## Latihan 2 — Data Log Terstruktur

Desain format data log untuk eksperimen Anda. Tentukan field apa saja yang akan dicatat.

**Identitas:**
| Field | Contoh |
|-------|--------|
| Run ID | *R-01* |
| Timestamp | *2026-05-18T09:00:00WIB* |
| Responden ID | *GenZ-01* |

**Konfigurasi:**
| Field | Contoh |
|-------|--------|
| Seed / Blok Sesi | *Manual Block Allocation (Kelompok 1)* |
| App Version | *TikTok Application Mobile Version 34.2.3* |
| Logistik Aset | *Gawai HP A23 + Akun TikTok Penguji (Sudah Terlogin)* |
| Skenario Urutan | *GIFT-CLEAN (Animasi Gift dahulu baru Layar Bersih)* |

**Hasil:**
| Metrik | Tipe Data | Range Valid |
|--------|----------|-------------|
| Time-on-Task GIFT | *integer (Detik)* | *1 – 180 detik* |
| Time-on-Task CLEAN | *integer (Detik)* | *1 – 180 detik* |
| Jumlah Klik Salah GIFT | *integer (Jumlah)* | *0 – Tidak terbatas* |
| Jumlah Klik Salah CLEAN | *integer (Jumlah)* | *0 – Tidak terbatas* |
| Status Selesai | *string* | *Success / Timeout* |

**Format output:** [ ] CSV / [ ] JSON / [ ] Database / [x] Lainnya: *Microsoft Excel (.xlsx) & SPSS (.sav)*

---

## Latihan 3 — Anomaly Protocol

Rencanakan bagaimana menangani anomali. Untuk setiap jenis, tentukan langkah yang diambil.

| Jenis Anomali | Contoh | Tindakan |
|---------------|--------|----------|
| Run gagal (crash) | Aplikasi TikTok tiba-tiba *force close* atau gawai *freeze* di tengah pengerjaan tugas belanja. | Sesi dihentikan, bersihkan cache aplikasi, lalu lakukan pengujian ulang (*re-run*) kondisi tersebut dari awal. Catat kendala di log. |
| Hasil ekstrem | Responden bingung parah di layar penuh animasi hingga menyentuh batas maksimal (180 detik). | Durasi tetap dicatat penuh **180 detik**, beri status *Timeout*, hitung klik salahnya, dan data tetap disimpan agar analisis tidak bias. |
| Waktu eksekusi anomali | Aplikasi perekam layar (*AZ Screen Recorder*) mendadak berhenti merekam karena memori gawai penuh. | Hapus berkas video yang rusak, kosongkan ruang penyimpanan gawai, lalu minta responden mengulang sesi kondisi tersebut dari awal. |
| Inkonsistensi dengan run lain | Responden tidak sengaja menekan tombol *Back* gawai sehingga keluar dari *room* Live Streaming TikTok. | Arahkan responden kembali ke *room* secara lisan. Jika waktu terbuang >10 detik, batalkan sesi tersebut dan ulang kondisi itu dari awal. |

**Prinsip:** Detect → Investigate → Document → Decide

---

## Refleksi

> Pernahkah Anda melaporkan hasil riset/tugas dari single run? Apa risikonya? Bagaimana multiple run mengubah kepercayaan terhadap hasil?

**Pengalaman sebelumnya:**
> Pernah, pada pengerjaan tugas kuliah analisis atau statistika dasar sebelumnya, saya terkadang hanya mengambil data dari satu kali pengujian sampel per individu tanpa mempertimbangkan variasi acak atau urutan kondisi. Risikonya adalah data tersebut sangat rentan terhadap faktor kebetulan, kelelahan responden, atau efek belajar (*learning effect*). Hasilnya menjadi tidak akurat, bias, dan tidak mencerminkan perilaku pengguna yang sesungguhnya di lapangan.

**Yang akan dilakukan berbeda:**
> Pada riset kali ini, saya menerapkan prinsip *multiple run* ilmiah dengan melibatkan 37 responden Gen Z yang masing-masing menjalankan 2 sesi pengujian berbeda (total 74 sesi rekaman data), lengkap dengan kontrol urutan (*counterbalancing*). Langkah pengulangan terstruktur ini menghasilkan variabilitas data durasi (*Time-on-Task*) serta metrik kesalahan (*Klik Salah*) yang kaya, terdistribusi normal, memiliki tingkat kepercayaan (*confidence interval*) yang tinggi, serta siap diuji secara valid menggunakan software SPSS untuk menarik kesimpulan yang kuat mengenai dampak *visual clutter* animasi hadiah terhadap performa belanja.
