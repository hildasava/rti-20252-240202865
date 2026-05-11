# WS-07: Experimental Design & Validity

> **Bab 7 — Experimental Design & Validity**

---

## Ringkasan Materi

### Correlation ≠ Causality

Kausalitas membutuhkan 3 syarat:
1. **Covariance** — X dan Y bergerak bersama
2. **Temporal precedence** — X berubah sebelum Y
3. **Elimination of alternatives** — Tidak ada faktor lain yang menjelaskan Y

Controlled experiment adalah satu-satunya metode yang bisa membuktikan kausalitas.

### Empat Jenis Validitas

| Jenis | Pertanyaan | Ancaman Umum |
|-------|-----------|-------------|
| **Internal** | Apakah hubungan IV→DV nyata? | Confounding variable, selection bias |
| **External** | Apakah bisa digeneralisasi? | Dataset terlalu spesifik |
| **Construct** | Apakah mengukur konsep yang benar? | Metrik tidak sesuai |
| **Conclusion** | Apakah kesimpulan statistik valid? | Sample size kecil, uji salah |

Internal dan external validity sering berkonflik: semakin terkontrol (internal kuat) → semakin artificial (external lemah).

### Tiga Tipe Eksperimen dalam Riset TI

| Tipe | Deskripsi | Kapan Digunakan |
|------|----------|----------------|
| **Comparison Study** | Metode A vs B pada kondisi identik | Membandingkan pendekatan berbeda |
| **Ablation Study** | Full system → lepas komponen satu per satu | Mengukur kontribusi tiap komponen |
| **Parameter Study** | Variasikan satu parameter, amati dampak | Uji sensitifitas/robustness |

### Fairness dalam Perbandingan

Perbandingan yang adil = **kondisi identik** untuk semua metode: dataset sama, preprocessing sama, tuning effort sebanding, environment sama, metrik sama.

Contoh tidak adil: Transformer (30 fitur tambahan + Bayesian optimization) vs RF (default params) → hasilnya misleading.

### Threats to Validity = Diidentifikasi Sebelum Eksperimen

Ancaman validitas harus diidentifikasi **sebelum** eksperimen dan mitigasinya dirancang sebagai bagian dari desain — bukan ditulis sebagai boilerplate setelah selesai.

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan testing | Memastikan sistem memenuhi requirement | Membuktikan hubungan kausal antar variabel |
| Baseline | Versi sebelumnya (last release) | Metode tervalidasi dari literatur |
| Kegagalan | Bug → fix → release | H₀ tidak ditolak → tetap kontribusi ilmiah |
| Sukses | 100% test pass | Evidence valid — mendukung atau menolak hipotesis |

### Istilah Penting

- **Causality** — Hubungan sebab-akibat (covariance + temporal + elimination)
- **Controlled Experiment** — Ubah satu variabel, kontrol sisanya, amati efek
- **Fairness** — Semua metode diuji pada kondisi yang benar-benar identik
- **Threats to Validity** — Faktor yang bisa melemahkan kesimpulan jika tidak dimitigasi
- **Conclusion Validity** — Validitas statistik: power, sample size, uji yang tepat

---

## Template A.7 — Desain Eksperimen Lengkap

**EXPERIMENT DESIGN**

**Research Question:** Bagaimana efisiensi antarmuka fitur Live Streaming TikTok Shop diukur menggunakan metode observasi langsung dengan metrik Time-on-Task dan Number of Clicks terhadap dataset pengguna Generasi Z?

**Hypothesis:** Tingkat visual clutter (stiker/gift) yang tinggi pada layar Live Streaming secara signifikan meningkatkan durasi waktu transaksi (Time-on-Task) dan jumlah ketukan layar (Number of Clicks).

**Tipe Eksperimen:** [x] Comparison  [x] Ablation  [ ] Parameter

**Kondisi Eksperimen:**
| Kondisi | Deskripsi | IV Value | CV Settings |
|---------|-----------|----------|-------------|
| **Control** | Antarmuka "Clean" (Hanya fitur belanja inti tanpa gangguan visual). | Low Clutter (0% Overlay) | Gen Z, Smartphone Samsung A23, Wi-Fi 50Mbps. |
| **Treatment** | Antarmuka "Full" (Fitur belanja dengan overlay stiker, gift, dan komentar). | High Clutter (100% Overlay) | Gen Z, Smartphone Samsung A23, Wi-Fi 50Mbps. |

**Fairness Checklist:**
- [x] Dataset identik untuk semua kondisi (Video rekaman Live yang sama).
- [x] Preprocessing setara (Instruksi tugas belanja yang sama).
- [x] Tuning effort setara (Setiap responden diberi 1 menit latihan trial).
- [x] Environment identik (Ruangan tenang, koneksi internet stabil).
- [x] Metrik evaluasi sama (Satuan detik dan jumlah tap/klik).

**Threat Analysis:**
| Threat Type | Ancaman Spesifik | Mitigasi |
|-------------|-----------------|----------|
| **Internal** | *Learning Effect* (Responden hafal alur tombol di tes kedua). | *Counterbalancing* (Urutan tes diacak antar responden). |
| **External** | Karakteristik Gen Z tidak mewakili kelompok usia lain. | Penegasan batasan populasi khusus untuk Generasi Z. |
| **Construct** | Kecepatan respons aplikasi dipengaruhi beban server. | Menggunakan simulasi prototipe atau rekaman layar terkendali. |
| **Conclusion** | Variansi data tinggi karena jumlah sampel kecil (37). | Penggunaan uji statistik Paired T-Test (sampel berpasangan). |

**Statistical Plan:**
- **Uji statistik:** Paired T-Test (Uji-t Berpasangan).
- **Justifikasi:** Membandingkan rata-rata performa dari kelompok subjek yang sama pada dua kondisi berbeda (Clean vs Full).
- **Alpha:** 0.05
- **Effect size min:** 0.5 (Medium effect).
---

## Latihan 1 — Desain Eksperimen

Susun desain eksperimen berdasarkan RQ, variabel, dan sistem dari WS-04 sampai WS-06.

**RQ:** Bagaimana efisiensi antarmuka fitur Live Streaming TikTok Shop diukur menggunakan metode observasi langsung dengan metrik Time-on-Task dan Number of Clicks terhadap dataset pengguna Generasi Z?

**Tipe eksperimen:** [x] Comparison / [x] Ablation / [ ] Parameter

| Kondisi | Deskripsi | IV Value | CV Settings |
|---------|-----------|----------|-------------|
| **Control** | Antarmuka "Clean" (Kondisi layar Live Streaming yang bersih dari elemen visual pengganggu). | *Low Clutter* (Tanpa Stiker/Gift) | Responden Gen Z, Smartphone Samsung A23, Wi-Fi 50Mbps, Video Live A. |
| **Treatment** | Antarmuka "Full" (Kondisi layar Live Streaming yang dipenuhi elemen visual seperti stiker, gift, dan komentar). | *High Clutter* (Banyak Stiker/Gift) | Responden Gen Z, Smartphone Samsung A23, Wi-Fi 50Mbps, Video Live A. |
---

## Latihan 2 — Fairness Checklist

Evaluasi apakah desain eksperimen di Latihan 1 sudah fair.

| Kriteria | Status | Detail |
|----------|--------|--------|
| **Dataset identik** | ✅ | Semua responden menonton video rekaman Live Streaming TikTok yang sama di kedua kondisi. |
| **Preprocessing setara** | ✅ | Instruksi tugas (skenario belanja) diberikan dengan kalimat yang sama persis kepada semua responden. |
| **Tuning effort setara** | ✅ | Setiap responden diberikan waktu 1 menit untuk mencoba (trial) navigasi di Samsung A23 sebelum data diambil. |
| **Environment identik** | ✅ | Pengujian dilakukan di lokasi yang sama dengan koneksi Wi-Fi 50Mbps yang stabil. |
| **Metrik evaluasi sama** | ✅ | Keduanya diukur menggunakan detik (Time-on-Task) dan jumlah tap (Number of Clicks). |

**Ada yang tidak fair?** [ ] Ya / [x] Tidak
> Jika ya, bagaimana cara memperbaikinya? Mengontrol variabel lingkungan secara ketat, seperti memastikan semua responden menggunakan perangkat Samsung A23 yang sama, berada di jaringan Wi-Fi yang stabil (tanpa gangguan pengguna lain), dan mendapatkan instruksi skenario yang identik sebelum memulai tes untuk menghindari bias informasi.

---

## Latihan 3 — Threat Analysis

Identifikasi ancaman validitas untuk desain eksperimen ini.

| Threat Type | Ancaman Spesifik | Mitigasi |
|-------------|-----------------|----------|
| **Internal** | *Learning Effect*: Responden hafal letak tombol setelah tes pertama. | Menggunakan *Counterbalancing* (Acak urutan: ada yang mulai dari 'Clean' dulu, ada yang 'Full' dulu). |
| **External** | Hasil hanya mewakili Gen Z, belum tentu berlaku untuk Gen X atau Boomer. | Menetapkan batasan generalisasi secara tegas bahwa riset ini khusus untuk karakteristik pengguna Gen Z. |
| **Construct** | Kecepatan respons dipengaruhi oleh memori/RAM HP yang penuh saat tes. | Melakukan *restart* aplikasi dan membersihkan *cache* Samsung A23 sebelum setiap responden memulai tes. |
| **Conclusion** | Variansi data tinggi karena jumlah responden terbatas (23 orang). | Menggunakan uji statistik yang kuat untuk sampel berpasangan, yaitu *Paired T-Test*. |

**Ancaman mana yang paling sulit dimitigasi?** *Internal Validity (Learning Effect).*

**Mengapa?**
> Karena kita tidak bisa menghapus ingatan manusia. Sekalipun urutan tes sudah diacak, responden yang sudah melakukan tes pertama pasti memiliki "gambaran" letak tombol keranjang kuning, sehingga secara alami mereka akan lebih cepat di tes kedua dibandingkan jika mereka benar-benar baru pertama kali melihatnya.

## Refleksi

> Sebuah paper melaporkan "metode kami mengalahkan semua baseline." Apa 3 pertanyaan pertama yang harus diajukan untuk mengevaluasi klaim ini?

**Jawaban:**
1. **Apakah Baseline sudah di-tuning dengan adil?** (Seringkali peneliti membiarkan metode pembanding/baseline menggunakan pengaturan standar yang lemah agar metode baru mereka terlihat jauh lebih unggul).
2. **Apakah lingkungan pengujian (Hardware/Network) benar-benar identik?** (Dalam kasus risetmu, apakah semua diuji di HP yang setara dengan Samsung A23 atau malah baseline-nya diuji di HP jadul yang lambat?).
3. **Apakah peningkatannya signifikan secara statistik?** (Apakah bedanya cuma 0,01 detik yang bisa jadi karena kebetulan, atau memang ada perbedaan nyata yang dibuktikan lewat uji statistik seperti Paired T-Test?).