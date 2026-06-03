# WS-09: Implementation & Environment

> **Bab 9 — Implementasi Riset & Kontrol Lingkungan**

---

## Ringkasan Materi

### Implementasi Riset ≠ Coding Biasa

Tujuan implementasi riset bukan membuat software yang berfungsi, melainkan membangun **instrumen pengukuran yang konsisten**. Setiap modul harus di-mapping ke variabel (dari Bab 6), parameter harus config-driven, dan logging aktif dari hari pertama.

### Reproducible Implementation Model

```
Design → Implementation → Environment Setup → Execution Consistency → Reproducibility → Trustworthy Result
```

Setiap transisi memiliki syarat:
- Design → Implementation: kode sesuai mapping variabel-ke-komponen
- Implementation → Environment: versi, dependency, seed, path, OS eksplisit
- Environment → Consistency: seed terkunci, urutan deterministik
- Consistency → Reproducibility: dokumentasi lengkap
- Reproducibility → Trust: siapa pun ikuti dokumentasi → hasil sama/serupa

### Repeatability vs Reproducibility

| Level | Peneliti | Environment | Hasil |
|-------|---------|-------------|-------|
| **Repeatability** | Sama | Sama | Sama persis |
| **Reproducibility** | Berbeda | Berbeda (ikuti docs) | Sama/serupa |

Capai **repeatability** dulu, baru **reproducibility**.

### Engineering vs Research Perspective

| Aspek | Engineering | Research |
|-------|-----------|---------|
| Tujuan | Sistem berfungsi untuk user | Instrumen pengukuran konsisten |
| Dependency | Update ke terbaru | Lock di versi spesifik |
| Testing | Unit, integration, E2E | Repeatability test (run ulang → sama?) |
| Dokumentasi | User guide, API docs | Environment spec, execution steps, expected output |
| Config | Default masuk akal | Setiap parameter eksplisit & adjustable |

### Jebakan Kognitif

1. Menunda environment setup → bug sulit dilacak
2. Tidak pakai version control → hasil tidak bisa direkonstruksi
3. Menolak Docker/container → "di laptop saya bisa" saat review
4. 3× hasil sama ≠ repeatable (bisa cache/state tersimpan)

### Istilah Penting

- **Environment Specification** — Deskripsi lengkap: hardware, OS, runtime, library + versi, config, seed
- **Dependency** — Komponen eksternal yang harus di-lock versinya
- **Config-driven** — Parameter dieksternalisasi ke file konfigurasi, bukan hardcode

---

## Template A.9 — Dokumentasi Setup Eksperimen

```
EXPERIMENT SETUP DOCUMENTATION

Hardware:
  CPU     : Qualcomm Snapdragon 680 (Octa-core 4x2.4 GHz & 4x1.9 GHz)
  RAM     : 6 GB LPDDR4X
  GPU     : Adreno 610
  Storage : 128 GB UFS 2.2

Software:
  OS        : Android 13 (One UI 5.1)
  Runtime   : Android Runtime (ART) / WebView Runtime
  Framework : TikTok Mobile Application Environment
  
Dependencies:
| Library / App | Version | Sumber | Hash/Checksum |
|---------|---------|--------|---------------|
| AZ Screen Recorder | 6.0.4 | Google Play Store | Native-APK-604 |
| Figma Mobile App | 21.14.0 | Google Play Store | Native-APK-2114 |

Konfigurasi:
  Config file     : None (Pengujian dipandu langsung lewat Skenario Lisan / Oral Script)
  Random seed     : None (Manual block allocation: 20 GIFT-CLEAN / 17 CLEAN-GIFT)
  Hyperparameters : Video Resolution: 1080p, Framerate: 60fps, Pointer: Show Taps ON, Max Duration: 180s (Timeout)

Reproducibility Check:
  [x] Dependency terdokumentasi (requirements.txt / lock file) (Menggunakan aplikasi TikTok v34.2.3 dan AZ Screen Recorder v6.0.4 dari Google Play Store)
  [x] Seed ditetapkan di semua level (Python, NumPy, framework) (Alokasi manual dikunci konsisten: 20 responden kelompok GIFT-CLEAN dan 17 responden kelompok CLEAN-GIFT)
  [x] Config di version control (Menggunakan standardisasi parameter fisik: kecerahan layar 60%, mode Jangan Ganggu aktif, dan batas waktu 180 detik)
  [x] README instruksi reproduksi lengkap (Panduan langkah pengujian dan pembacaan skenario tugas secara lisan sudah dibakukan di lembar instruksi)
```

---

## Latihan 1 — Environment Specification

Dokumentasikan environment untuk eksperimen Anda (boleh environment saat ini atau yang direncanakan).

| Komponen | Spesifikasi |
|----------|------------|
| CPU | Qualcomm Snapdragon 680 (Octa-core 4x2.4 GHz & 4x1.9 GHz) |
| RAM | 6 GB LPDDR4X |
| GPU | Adreno 610 |
| OS | Android 13 (One UI 5.1) |
| Runtime | Android System WebView (v120.0) |
| Framework | Figma Mobile Prototyping Engine |
| Random Seed | None (Alokasi Manual: 20 Responden GIFT-CLEAN, 17 Responden CLEAN-GIFT) |

**Dependencies (minimal 5):**

| Library / Tool | Version | Alasan Dibutuhkan |
|----------------|---------|-------------------|
| Android OS System | 13 (API 33) | Sistem operasi utama standarisasi gawai responden |
| AZ Screen Recorder | 6.0.4 | Merekam layar interaksi dengan batas maksimal 180 detik |
| Developer Options | Native | Mengaktifkan fitur "Show Taps" (tanda ketukan fisik) |
| Figma Client App | 21.14.0 | Merender antarmuka interaktif kondisi Clean & Full Clutter (Gift) |
| VLC Media Player | 3.5.4 | Analisis rekaman video per frame (ekstraksi metrik durasi detik) |

---

## Latihan 2 — Repeatability Test Plan

Rancang tes repeatability sederhana: jalankan kode yang sama 3× di environment yang sama.

| Run | Seed | Metrik Utama | Hasil Sama? |
|-----|------|-------------|-------------|
| 1 | Manual (20 GIFT / 17 CLEAN) | Rata-rata *Time-on-Task* (Detik) | — |
| 2 | Manual (20 GIFT / 17 CLEAN) | Rata-rata *Time-on-Task* (Detik) | [x] Ya / [ ] Tidak |
| 3 | Manual (20 GIFT / 17 CLEAN) | Rata-rata *Time-on-Task* (Detik) | [x] Ya / [ ] Tidak |

**Jika hasil berbeda, kemungkinan penyebab:**
> Terjadinya *learning effect* (efek belajar) di mana responden menjadi jauh lebih hafal letak tombol target pada run berikutnya, atau adanya gangguan performa gawai (seperti *thermal throttling* pada Snapdragon 680) jika pengujian dilakukan maraton tanpa jeda, serta potensi responden menyentuh batas *timeout* 180 detik.

**Checklist kontrol yang sudah diterapkan:**
- [x] Alokasi blok counterbalancing di-set konsisten (20 GIFT-CLEAN / 17 CLEAN-GIFT)
- [x] Tidak ada background process yang mengganggu (Mode "Jangan Ganggu" aktif)
- [x] Cache aplikasi Figma dibersihkan antar-run
- [x] Config file yang sama untuk semua run (Batas waktu lock 180 detik)

---

## Latihan 3 — README Eksperimen

Tulis README minimum untuk eksperimen Anda (6 komponen wajib).

```
# Judul Eksperimen: Analisis Dampak Visual Clutter (Gift Animation) pada Live Streaming TikTok Shop Terhadap Kinerja Interaksi Pengguna Gen Z

## 1. Environment
> Gawai Utama: Samsung Galaxy A23 (RAM 6GB, Snapdragon 680)

> OS: Android 13 (One UI 5.1)

> Runtime/Framework: Android Runtime (ART) / TikTok Mobile Application Environment

> Alokasi Sesi: Manual (20 Responden GIFT-CLEAN, 17 Responden CLEAN-GIFT)

## 2. Installation
> Unduh dan install aplikasi TikTok resmi dari Google Play Store ke gawai Samsung A23 yang digunakan sebagai gawai uji.

> Aktifkan menu "Developer Options" (Pilihan Pengembang) pada pengaturan sistem Android, lalu aktifkan fitur "Show Taps" (Tampilkan Ketukan) agar setiap sentuhan responden terekam.

> Unduh dan pasang aplikasi AZ Screen Recorder dari Google Play Store untuk keperluan merekam video interaksi belanja.
## 3. Data
> - Dataset Awal (Input): Sesi Live Streaming TikTok Shop pada gawai uji dengan 2 kondisi kontrol visual, yaitu Kondisi GIFT (layar penuh dengan animasi saweran/gift yang ramai) dan Kondisi CLEAN (tampilan layar bersih dari pop-up gift animasi).
> - Data Intermediet (Proses): Lembar kerja Microsoft Excel (`.xlsx`) yang digunakan untuk mentabulasi data mentah hasil pengamatan rekaman video .MP4 (maksimal 180 detik), berisi kolom: ID Responden, Urutan Kelompok, Kondisi Antarmuka, dan Nilai Eksak *Time-on-Task* (dalam satuan detik).
> - Output Data (Akhir): Berkas dataset format `.sav` pada perangkat lunak SPSS yang telah divalidasi dan siap diuji secara statistik untuk melihat signifikansi perbedaan performa waktu antar kedua kondisi.
## 4. Execution
> Buka aplikasi AZ Screen Recorder, aktifkan tombol perekaman layar gawai.

> Berikan gawai kepada responden sesuai urutan kelompok manualnya (Kelompok 1: Jalankan sesi GIFT dulu baru CLEAN; Kelompok 2: Jalankan CLEAN dulu baru GIFT).

> Berikan perintah skenario tugas secara lisan agar responden melakukan simulasi pembelian sampai menekan tombol "Check Out".

> Matikan perekaman layar jika responden berhasil menekan "Check Out" atau jika waktu pengerjaan sudah menyentuh batas maksimal 180 detik (timeout).

## 5. Configuration
> Berkas Konfigurasi: None (Tidak menggunakan file digital, melainkan menggunakan lembar panduan skenario instruksi lisan penguji yang dibacakan secara seragam kepada setiap responden).
Parameter Kunci Sesi:
> Kecerahan Layar Gawai (*Screen Brightness*): Dikunci wajib pada tingkat 60%.
> Mode Gawai (*Device Mode*): Wajib mengaktifkan mode "Jangan Ganggu" (*Do Not Disturb*) untuk memblokir notifikasi masuk selama pengujian.
> Batas Durasi Maksimal (*Timeout Limit*): Batas waktu pengerjaan tugas dibatasi maksimal 180 detik (3 menit) per sesi kondisi antarmuka.
## 6. Expected Output
> Berkas video mentah rekaman layar interaksi belanja responden berformat `.mp4` (resolusi 1080p, 60fps) yang menampilkan indikator titik ketukan jari (*Show Taps*) responden secara jelas selama pengujian.
> Lembar tabulasi data mentah pada Microsoft Excel (`.xlsx`) dengan struktur kolom: `Responden_ID`, `Kelompok_Urutan`, `Kondisi_Antarmuka`, `Time_on_Task_Detik`, dan `Status_Selesai` (Success/Timeout).
> Berkas dataset akhir siap uji pada perangkat lunak SPSS berformat `.sav` yang bersumber dari hasil *input* lembar tabulasi Excel tersebut.
```

---

## Refleksi

> Apakah eksperimen Anda saat ini bisa direproduksi oleh orang lain tanpa bantuan Anda? Komponen apa yang masih hilang?

**Level saat ini:** [x] Repeatability / [ ] Reproducibility / [ ] Belum keduanya

**Komponen yang belum terdokumentasi:**
> 1. Lembar teks fisik berisi naskah skenario tugas (*task scenario/oral script*) yang dibacakan secara lisan oleh penguji kepada responden belum dilampirkan secara tertulis. Hal ini penting agar intonasi dan pilihan kata tetap seragam jika diuji oleh orang lain.
> 2. Panduan operasional atau *Standard Operating Procedure* (SOP) mengenai cara penentuan titik mulai (*start*) dan titik akhir (*stop*) perhitungan detik waktu (*Time-on-Task*) saat menonton ulang rekaman video .MP4 di VLC Player belum dibakukan, sehingga berpotensi memicu selisih hitungan milidetik antar-penguji.