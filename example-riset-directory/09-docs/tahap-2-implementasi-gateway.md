# 2. Tahap 2 — Implementasi Prototipe Antarmuka

**Status: Selesai**
**Acuan:** [1. Tahap 1 — Perancangan Instrumen & Skenario Eksperimen](1.md)
**Lokasi Desain:** [../05-desain/prototype/](../05-desain/prototype/)

---

## 2.1 Tujuan Implementasi
Membangun prototipe antarmuka interaktif yang merepresentasikan dua kondisi desain sebagai instrumen uji untuk 74 responden:
* **Mode `Clean` (Baseline)**: Desain antarmuka minimalis dengan fokus pada navigasi utama (keranjang kuning dan tombol *checkout*) untuk menciptakan kepadatan visual rendah.
* **Mode `Full` (Intervensi Visual)**: Desain antarmuka yang merepresentasikan kondisi *Live Streaming* TikTok Shop aktual, dengan kepadatan elemen visual tinggi (animasi stiker, *floating* notifikasi *gift*, dan komentar bergerak) sebagai beban kognitif visual.

## 2.2 Komponen Prototipe
* **Framework Desain**: Figma untuk *wireframing* dan *prototyping* interaktif yang menyerupai perilaku asli aplikasi.
* **Elemen Interaktif**: Tombol *checkout* dan keranjang yang memiliki dimensi, warna, dan letak yang konsisten di kedua mode untuk menjaga konsistensi variabel dependen.
* **Variabel Gangguan**: Implementasi elemen *looping animation* pada komponen non-navigasi di mode `Full` guna menciptakan stimulasi visual yang intens bagi responden.

## 2.3 Prosedur Pengujian & Validasi
* **Target Responden**: Penelitian ini melibatkan **74 responden** dari populasi Generasi Z, yang dibagi secara merata menjadi **dua kelompok independen** (masing-masing 37 responden untuk kelompok `Clean` dan 37 responden untuk kelompok `Full`).
* **Platform Pengujian**: Prototipe dijalankan pada perangkat **Samsung A23** untuk menyerupai *User Experience* (UX) yang konsisten.
* **Rekaman Layar**: Penggunaan alat perekam layar untuk menangkap durasi *Time-on-Task* dari setiap detik interaksi responden secara presisi.
* **Validasi Desain**: Uji coba internal dilakukan untuk memastikan tidak terdapat *bug* pada alur navigasi di kedua mode sebelum diujikan kepada seluruh responden.

## 2.4 Catatan Implementasi
* **Standardisasi**: Elemen navigasi dibuat identik di kedua mode agar perbedaan performa hanya disebabkan oleh **kepadatan visual**.
* **Lingkungan Pengujian**: Prototipe diakses secara luring (*offline*) guna mengeliminasi variabel latensi jaringan yang dapat mengganggu pengukuran durasi transaksi.
* **Data Prep**: Data dari 74 responden dikonversi menjadi data numerik ke dalam *spreadsheet* sebagai langkah persiapan sebelum diimpor ke **SPSS** untuk analisis statistik (*Independent Samples T-Test*).