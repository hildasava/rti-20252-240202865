# WS-06: System-Experiment Mapping

> **Bab 6 — System Design sebagai Experimental Artifact**

---

## Ringkasan Materi

### Sistem = Instrumen Pengujian, Bukan Produk

Seorang engineer bertanya "apakah sistem bekerja?" — seorang peneliti bertanya "apa yang bisa dibuktikan sistem ini?" Sistem dalam riset adalah **artifact** — objek yang sengaja dibuat untuk menguji klaim spesifik.

### System as Experiment Model

```
RQ → Variable → System Component → Experimental Setup → Output
```

Setiap komponen sistem harus bisa ditelusuri ke variabel riset (top-down), dan setiap pengukuran harus menjawab RQ (bottom-up).

### Mapping Variabel ke Komponen

| Tipe Variabel | Peran di Sistem | Contoh |
|---------------|----------------|--------|
| **IV** (Independent) | Modul yang bisa di-toggle/swap | Algoritma A vs B |
| **DV** (Dependent) | Modul pengukuran | Logger, metrics collector |
| **CV** (Control) | Config yang dikunci | Dataset, parameter tetap |

Jika variabel tidak bisa di-map ke komponen apapun → arsitektur perlu didesain ulang.

### 4 Prinsip Desain Eksperimental

| Prinsip | Pertanyaan Kunci |
|---------|-----------------|
| **Traceability** | Komponen ini melayani variabel yang mana? |
| **Modularity** | Bisakah IV diubah tanpa memengaruhi yang lain? |
| **Controllability** | Apakah CV dieksternalisasi ke config file? |
| **Measurability** | Apakah sistem otomatis menghasilkan data yang dibutuhkan? |

### Variable Isolation melalui Arsitektur

- **Modular architecture** — Pisahkan berdasarkan variabel
- **Configuration-driven** — Ubah config (YAML/JSON), bukan code
- **Feature toggles** — On/off flag untuk ablation study

  Contoh config YAML dengan feature toggles:
  ```yaml
  model:
    type: cnn          # IV: ganti "rf" untuk kondisi baseline
  features:
    use_temporal: true  # toggle komponen temporal
    use_normalization: true  # toggle preprocessing
  experiment:
    seed: 42
    runs: 5
  ```
  Dengan pendekatan ini, berbeda kondisi eksperimen = berbeda satu baris config, **tanpa mengubah kode**.

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan sistem | Memenuhi kebutuhan user | Menguji hipotesis, menghasilkan bukti |
| Arsitektur | Optimasi performa & skalabilitas | Optimasi isolasi variabel & reprodusibilitas |
| Konfigurasi | Sering hardcoded | Dieksternalisasi ke config file |
| Fitur tambahan | Menambah nilai user | Menambah noise jika tidak terkait RQ |

### Istilah Penting

- **Artifact** — Objek yang sengaja dibuat untuk memecahkan masalah atau menguji proposisi
- **Traceability** — Kemampuan menelusuri hubungan RQ → variabel → komponen → output
- **Variable Isolation** — Mengubah hanya satu variabel sambil menahan yang lain konstan
- **Ablation Study** — Menguji kontribusi tiap komponen dengan melepasnya satu per satu
- **Configuration-driven Execution** — Semua parameter di config file, bukan hardcoded

---

## Template A.6 — Mapping RQ ke Arsitektur Sistem

### SYSTEM-EXPERIMENT MAPPING

**Research Question:**
Bagaimana efisiensi antarmuka fitur Live Streaming TikTok Shop diukur menggunakan metode observasi langsung dengan metrik Time-on-Task dan Number of Clicks terhadap dataset pengguna Generasi Z, untuk dibandingkan dengan baseline analisis User Experience (UX) dari Tinezia Hairunisya (2025)?

**Variable → Component Mapping:**

| Variabel | Tipe | Komponen Sistem | Cara Manipulasi/Pengukuran |
|----------|------|-----------------|---------------------------|
| Desain Antarmuka (*Visual Clutter*) | **IV** | Interface Overlay Module | Mengatur level kemunculan stiker, gift, dan komentar (Low vs High Clutter). |
| Efisiensi Transaksi | **DV** | Activity Tracker & Logger | Pencatatan otomatis waktu checkout (detik) dan jumlah klik (count) secara real-time. |
| Profil Pengguna & Lingkungan | **CV** | Screening & Config Module | Mengunci kriteria responden (Gen Z saja) dan standarisasi perangkat/jaringan internet. |

**4 Prinsip Desain:**
- [x] **Traceability** — Setiap komponen visual (overlay) berhubungan langsung dengan variabel bebas (IV).
- [x] **Variable Isolation** — Kita bisa mematikan/menyalakan fitur "stiker" tanpa mengubah alur navigasi utama "keranjang kuning".
- [x] **Measurement Integration** — Pengukuran waktu dan klik sudah tertanam dalam protokol observasi (built-in logging).
- [x] **Reproducibility** — Skenario tugas (task scenario) yang sama diberikan kepada setiap responden untuk hasil yang konsisten.

**Experimental Setup:**
- **Input data:** Skenario simulasi belanja saat Live Streaming berlangsung.
- **Parameter:** Tingkat kepadatan elemen visual (stiker/gift per menit) dan durasi sesi.
- **Output format:** Log file (.csv atau .xlsx) berisi daftar responden, jumlah klik, dan total waktu penyelesaian tugas (Time-on-Task).

---

## Latihan 1 — Variable-to-Component Mapping

**RQ:** Bagaimana efisiensi antarmuka fitur Live Streaming TikTok Shop diukur menggunakan metode observasi langsung dengan metrik Time-on-Task dan Number of Clicks terhadap dataset pengguna Generasi Z, untuk dibandingkan dengan baseline analisis User Experience (UX) dari Tinezia Hairunisya (2025)?

| Variabel | Tipe | Komponen Sistem | Cara Manipulasi / Pengukuran |
|----------|------|-----------------|---------------------------|
| Tingkat Kepadatan Informasi (*Visual Clutter*) | **IV** | Interface Overlay Module | Mengubah intensitas tampilan stiker/gift via simulator atau rekaman sesi. |
| Efisiensi Transaksi (Waktu & Klik) | **DV** | Interaction Logger & Timer | Pencatatan otomatis timestamp awal-akhir dan counter jumlah klik pada tombol checkout. |
| Profil Responden & Device | **CV** | User Screening Database | Memfilter partisipan melalui kuesioner kriteria (Gen Z) dan menyamakan spek device pengujian. |

**Apakah semua variabel bisa di-map?** [x] Ya / [ ] Tidak
> **Jika tidak, komponen apa yang perlu ditambahkan?** (Sudah terpetakan semua ke dalam komponen observasi dan logging sistem).
---

## Latihan 2 — 4 Prinsip Desain

Evaluasi desain sistem terhadap 4 prinsip.

| Prinsip | Status | Bukti / Penjelasan |
|---------|--------|-------------------|
| **Traceability** | ✅ Terpenuhi | Setiap elemen UI (keranjang, stiker, tombol bayar) dilacak langsung pengaruhnya terhadap jumlah tap yang dilakukan user. |
| **Modularity** | ✅ Terpenuhi | Skenario pengujian dipisah antara layar yang "bersih" dan layar yang "ramai" (*visual clutter*) tanpa mengubah alur transaksi utama. |
| **Controllability** | ✅ Terpenuhi | Variabel kontrol dikunci pada responden Gen Z dan penggunaan aplikasi TikTok versi yang sama untuk meminimalkan gangguan teknis. |
| **Measurability** | ✅ Terpenuhi | Data bersifat kuantitatif dan objektif karena diukur langsung menggunakan satuan detik (timer) dan jumlah ketukan layar (counter). |

**Prinsip mana yang paling sulit dipenuhi?** *Modularity (Isolasi Variabel).*

**Strategi untuk mengatasinya:**
Menggunakan simulasi rekaman layar *Live Streaming* yang sudah diatur tingkat keramaian elemen visualnya, sehingga setiap responden mendapatkan beban gangguan yang sama persis saat dihitung waktunya.
---

## Latihan 3 — Ablation Study Planning

Jika sistem memiliki 3 komponen utama, rencanakan ablation study.

<<<<<<< HEAD
| Kondisi | Komponen A (Overlay Stiker/Gift) | Komponen B (Komentar Real-time) | Komponen C (Banner Promo) | Hasil yang Diharapkan |
=======
> **Panduan jumlah kondisi:** Untuk 3 komponen (A, B, C), kondisi minimal yang direkomendasikan:
> Full + (-A) + (-B) + (-C) = **4 kondisi dasar**. Jika waktu memungkinkan, tambahkan kombinasi ganda: (-A,-B), (-A,-C), (-B,-C) = **7 kondisi**. Sesuaikan dengan *computational cost* dan tenggat waktu penelitian.

| Kondisi | Komponen A | Komponen B | Komponen C | Hasil yang Diharapkan |
>>>>>>> ffac99b58491f20c5b78603a2b315eb77ca446fd
|---------|-----------|-----------|-----------|----------------------|
| **Full** | ✅ Aktif | ✅ Aktif | ✅ Aktif | *Baseline*: Efisiensi terendah (Waktu terlama & jumlah tap terbanyak). |
| **– A** | ❌ Dinonaktifkan | ✅ Aktif | ✅ Aktif | Kecepatan transaksi meningkat karena area tombol "Beli" tidak tertutup. |
| **– B** | ✅ Aktif | ❌ Dinonaktifkan | ✅ Aktif | Gangguan visual berkurang, fokus user pada produk lebih stabil. |
| **– C** | ✅ Aktif | ✅ Aktif | ❌ Dinonaktifkan | Navigasi lebih bersih, risiko salah klik (misclick) menurun. |

**Komponen mana yang diprediksi paling berkontribusi?** Komponen A (Overlay Stiker/Gift).

**Mengapa?**
> Karena komponen ini bersifat *pop-up* yang muncul secara tiba-tiba dan seringkali menutupi elemen navigasi utama (seperti keranjang kuning atau tombol *checkout*). Hal ini secara langsung memaksa pengguna melakukan ekstra tap untuk menutup stiker atau menunggu stiker hilang, yang secara signifikan menambah *Time-on-Task*.
---

## Refleksi

> **Apa risiko jika sistem dibangun seperti produk (monolitik, fitur lengkap) lalu baru dilakukan eksperimen? Mengapa arsitektur modular penting untuk riset?**

**Jawaban:**

Risiko utama jika sistem dibangun secara **monolitik** (seperti produk jadi yang fiturnya lengkap dan menyatu) adalah munculnya **bias variabel atau *noise*** yang tinggi. Dalam riset, kita perlu tahu secara pasti fitur mana yang memengaruhi hasil. Jika sistemnya monolitik, peneliti akan sulit membedakan apakah efisiensi pengguna menurun karena desain tombol yang buruk, gangguan dari stiker, atau banyaknya komentar, karena semuanya aktif secara bersamaan. Akibatnya, kita tidak bisa menarik kesimpulan yang valid mengenai penyebab utama masalah.

**Arsitektur modular** sangat penting untuk riset karena memungkinkan terjadinya **Variable Isolation (Isolasi Variabel)**. Dengan desain yang modular (terbagi per modul), peneliti bisa melakukan *Ablation Study*—yaitu mematikan atau menyalakan satu komponen saja (misalnya fitur stiker) tanpa mengganggu fungsi sistem yang lain. Hal ini memastikan bahwa perubahan pada variabel terikat (*Time-on-Task* dan *Number of Clicks*) memang benar-benar disebabkan oleh variabel bebas yang sedang diuji, sehingga data yang dihasilkan menjadi objektif, akurat, dan dapat dipertanggungjawabkan secara ilmiah.