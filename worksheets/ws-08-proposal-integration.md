# WS-08: Proposal Integration (UTS)

> **Bab 8 — Proposal & Checkpoint**

---

## Ringkasan Materi

### Proposal = Satu Argumen Utuh

Proposal riset bukan kumpulan bab yang independen. Ia adalah **satu argumen** yang mengalir dari masalah ke rencana solusi. Jika satu koneksi putus, seluruh proposal kehilangan koherensi.

### Integration Map — 6 Koneksi Kritis

```
Problem (Bab 2) → Gap (Bab 3) → RQ & H (Bab 4) → Metrik (Bab 5) → Sistem (Bab 6) → Eksperimen (Bab 7)
```

| Koneksi | Pertanyaan Verifikasi |
|---------|----------------------|
| Problem → Gap | Apakah gap muncul dari analisis literatur terhadap masalah? |
| Gap → RQ | Apakah RQ langsung menjawab gap yang teridentifikasi? |
| RQ → Metrik | Apakah setiap variabel di RQ punya metrik terdefinisi? |
| Metrik → Sistem | Apakah setiap metrik bisa diukur oleh komponen sistem? |
| Sistem → Eksperimen | Apakah desain eksperimen menggunakan sistem sebagai instrumen? |

### Koherensi Vertikal + Horizontal

- **Vertikal** — Alur logis atas-ke-bawah (problem → experiment). Setiap section menjawab pertanyaan yang diangkat section sebelumnya dan memunculkan pertanyaan baru.
- **Horizontal** — Konsistensi terminologi (nama variabel di RQ = di hipotesis = di metrik = di desain)

**Operasionalisasi Red Thread** (benang merah):
```
Bab 2 (Problem) → | memperkenalkan masalah X + evidensi |
                          ↓ menimbulkan pertanyaan: "apa akar gap-nya?"
Bab 3 (Gap)     → | menjawab pertanyaan tadi + membuka "lalu apa yang perlu diteliti?" |
                          ↓
Bab 4 (RQ/H)    → | menjawab gap dengan pertanyaan spesifik + prediksi terukur |
                          ↓
Bab 5-7 (Method)→ | menjawab RQ melalui desain eksperimen yang tepat |
```
Jika ada lompatan (section B tidak menjawab pertanyaan section A), red thread putus.

### Jebakan Kognitif

| Jebakan | Deskripsi |
|---------|----------|
| "Selling" Introduction | Menulis promosi, bukan menyajikan data dan gap |
| Copy-paste Methodology | Menyalin deskripsi tekstbook tanpa menyesuaikan ke RQ |
| Optimistic Timeline | Meremehkan waktu implementasi; selalu tambah buffer 30-50% |
| No Possibility of Failure | Mengimplikasikan hasil pasti sukses — proposal jujur mengakui H₀ mungkin tidak ditolak |

### Struktur Proposal

1. **Pendahuluan** — Latar belakang + problem statement (Bab 1-2)
2. **Tinjauan Pustaka** — Literature review + gap + baseline (Bab 3)
3. **RQ / Kontribusi / Hipotesis** — (Bab 4)
4. **Metodologi** — Metrik + sistem + desain eksperimen (Bab 5-7)
5. **Timeline & Output**

### Istilah Penting

- **Integration Map** — Diagram 6 koneksi kritis antar komponen proposal
- **Vertical Coherence** — Alur logis atas-ke-bawah
- **Horizontal Coherence** — Konsistensi terminologi di semua bagian
- **Checkpoint** — Titik self-assessment sebelum transisi dari desain ke eksekusi

---

## Template A.8 — Integration Checklist


PROPOSAL INTEGRATION CHECKLIST

Koneksi Vertikal (Flow Atas-Bawah):
  [x] Problem → Gap: masalah terdokumentasi di literatur
  [x] Gap → RQ: pertanyaan menjawab gap spesifik
  [x] RQ → Hypothesis: hipotesis memprediksi jawaban
  [x] Hypothesis → Metric: metrik mengukur variabel dalam hipotesis
  [x] Metric → System: komponen sistem menghasilkan/mengukur metrik
  [x] System → Experiment: desain eksperimen menggunakan sistem

Koneksi Horizontal (Konsistensi):
  [x] Istilah sama di semua bagian
  [x] Variabel di RQ = variabel di hipotesis = metrik di desain
  [x] Scope tidak berubah dari masalah ke eksperimen

Cognitive Trap Checklist:
  [ ] Tidak ada paragraf "promosi" di pendahuluan (hanya data & gap)
  [ ] Metodologi disesuaikan ke RQ, bukan copy-paste textbook
  [ ] Timeline sudah ditambah buffer 30-50% dari estimasi awal
  [ ] Proposal mengakui kemungkinan H0 tidak ditolak (honest uncertainty)
  [ ] Tidak ada klaim "pasti berhasil" atau "meningkatkan signifikan"

Rubrik Self-Assessment:
<<<<<<< HEAD
| Kriteria    | 1 (Lemah) | 2 (Cukup) | 3 (Baik) | Skor |
|-------------|-----------|-----------|----------|------|
| Koherensi   |           |           |    [x]   |   3  |
| Specificity |           |           |    [x]   |   3  |
| Feasibility |           |           |    [x]   |   3  |
| Rigor       |           |           |    [x]   |   3  |
=======
| Kriteria     | 1 (Lemah)                                        | 2 (Cukup)                                     | 3 (Baik)                                           | Skor |
|------------- |--------------------------------------------------|-----------------------------------------------|----------------------------------------------------|------|
| Koherensi    | >2 koneksi vertikal terputus                     | 1-2 koneksi lemah, argumen masih bisa diikuti | Semua 6 koneksi terhubung, red thread jelas        |      |
| Specificity  | Variabel/metrik masih abstrak, tidak ada angka   | Sebagian metrik terdefinisi numerik           | Semua metrik + threshold + unit pengukuran jelas   |      |
| Feasibility  | Timeline >6 bulan tanpa memperhitungkan sumber   | Timeline 3-6 bulan dengan asumsi tertentu     | Timeline 1-3 bulan realistis dengan rencana detail |      |
| Rigor        | Baseline tidak jelas atau straw man              | 1-2 baseline dengan justifikasi partial       | 2+ baseline SOTA + justifikasi pemilihan lengkap   |      |
```
>>>>>>> ffac99b58491f20c5b78603a2b315eb77ca446fd

---

## Latihan 1 — Kompilasi Proposal Mini

Kumpulkan hasil dari WS-02 sampai WS-07 menjadi satu ringkasan proposal.

| Komponen | Sumber | Isi (1-2 kalimat) |
|----------|--------|-------------------|
| Problem Statement | WS-02 | Tingginya kepadatan informasi visual (*visual clutter*) pada fitur belanja *live streaming social commerce* diduga menurunkan kenyamanan pengguna. Namun, degradasi performa interaksi fisik pengguna akibat gangguan visual tersebut belum diteliti secara objektif. |
| Gap | WS-03 | Terdapat *Method Gap* di mana riset terdahulu mayoritas menggunakan kuesioner subjektif (seperti Hairunisya, 2025), serta *Context Gap* di mana manipulasi kepadatan elemen visual belum pernah diuji melalui metode eksperimental terkontrol. |
| RQ | WS-04 | Apakah manipulasi tingkat kepadatan elemen visual (*Visual Clutter Overlay*) pada antarmuka *live streaming* memengaruhi efisiensi waktu transaksi (*Time-on-Task*) dan jumlah kesalahan ketukan (*Number of Clicks*) pengguna Generasi Z? |
| Hipotesis | WS-04 | H_1: Kondisi antarmuka *Clean* menghasilkan rata-rata durasi *Time-on-Task* yang lebih cepat dan nilai *Number of Clicks* yang lebih rendah secara signifikan dibandingkan Kondisi *Full*. |
| Variabel & Metrik | WS-05 | Independent Variable (IV) = Tingkat kepadatan elemen visual (Kondisi *Clean* vs *Full*). Dependent Variable (DV) = *Time-on-Task* (satuan detik) dan *Number of Clicks/User Error* (frekuensi salah klik). |
| Sistem | WS-06 | Prototipe simulasi aplikasi *social commerce* dengan fitur perekam layar internal (1080p, 60fps) dan penunjuk titik sentuh (*Show Taps*) untuk mencatat interaksi fisik responden secara riil. |
| Desain Eksperimen | WS-07 | Eksperimen laboratorium terkontrol menggunakan desain *Within-Subject (Repeated Measures)* pada 37 responden Generasi Z dengan gawai standar Samsung A23 dan menerapkan teknik *counterbalancing*. |

---

## Latihan 2 — Integration Checklist

Verifikasi 6 koneksi kritis. Isi dengan merujuk tabel di Latihan 1.

| Koneksi | Status | Bukti |
|---------|--------|-------|
| Problem → Gap | ✅ | Gap muncul langsung dari analisis literatur terkait tiadanya data performa objektif pada fitur *live streaming* akibat tumpukan visual clutter. |
| Gap → RQ | ✅ | RQ secara spesifik mempertanyakan pengaruh manipulasi visual clutter terhadap efisiensi interaksi objektif pengguna Generasi Z. |
| RQ → Hypothesis | ✅ | Hipotesis secara tegas memprediksi arah penurunan performa (*Time-on-Task* dan *Clicks*) dari kondisi *Clean* ke *Full*. |
| Hypothesis → Metric | ✅ | Variabel dalam hipotesis diukur langsung secara numerik melalui metrik durasi detik (*Time-on-Task*) dan frekuensi (*Number of Clicks*). |
| Metric → System | ✅ | Komponen sistem prototipe simulasi dan fitur *screen recording* (*Show Taps*) mampu mengekstraksi data metrik waktu dan klik per *frame*. |
| System → Experiment | ✅ | Desain eksperimen menggunakan prototipe simulasi tersebut sebagai instrumen uji utama yang dioperasikan langsung oleh 37 responden di lab. |

**Koneksi mana yang paling lemah?** Koneksi *Metric → System* pada tahap ekstraksi data visual rekaman layar.

**Bagaimana cara memperkuatnya?**
> Proses ekstraksi data dari rekaman layar perlu menggunakan lembar matriks pengamatan (*coding sheet*) baku yang divalidasi silang oleh dua pengamat (*inter-rater reliability*) untuk menghindari subjektivitas manual saat menghitung jumlah klik dan detik.

**Konsistensi horizontal — apakah istilah dan scope konsisten?** [x] Ya / [ ] Tidak
> Jika tidak, di bagian mana terjadi inkonsistensi? -

**Konsistensi horizontal — apakah istilah dan scope konsisten?** [ ] Ya / [ ] Tidak
> Jika tidak, di bagian mana terjadi inkonsistensi? _________

---

## Latihan 3 — Rubrik Self-Assessment

Evaluasi proposal mini menggunakan rubrik.

| Kriteria | Skor (1-3) | Justifikasi |
|----------|-----------|-------------|
| Koherensi | 3 | Alur riset sangat lurus dan logis, sejak penentuan masalah *visual clutter* hingga pengujian statistiknya menggunakan *Paired Samples T-Test*. |
| Specificity | 3 | Variabel, metrik (detik dan frekuensi klik), spesifikasi gawai (Samsung A23), serta jumlah sampel (37 responden Gen Z) sudah terdefinisi secara eksak. |
| Feasibility | 3 | Aplikasi simulasi bersifat lokal di laboratorium terkontrol dan jumlah responden (37 mahasiswa) sangat realistis diselesaikan dalam target waktu yang ada. |
| Rigor | 3 | Desain eksperimen menggunakan *Within-Subject* lengkap dengan mitigasi bias berupa *counterbalancing*, uji normalitas *Shapiro-Wilk*, serta opsi uji *Wilcoxon*. |

**Skor total:** 12 / 12

**Apakah proposal siap untuk fase eksekusi?** [x] Ya / [ ] Belum
> Jika belum, apa yang perlu diperbaiki? -
---

## Refleksi

> Dari seluruh proses WS-01 sampai WS-08, bagian mana yang paling mudah dan paling sulit? Mengapa? Apa yang akan dilakukan berbeda jika mengulang dari awal?

**Bagian termudah:** Menyusun Variabel dan Metrik (WS-05) karena parameter efisiensi dalam bidang Interaksi Manusia-Komputer (HCI) sudah baku dan terukur jelas, yaitu mengukur aspek waktu (*Time-on-Task*) dan tingkat kesalahan (*error rate*).

**Bagian tersulit:** Mengintegrasikan Desain Eksperimen dengan Analisis Validitas (WS-07). Hal ini sulit karena memerlukan ketelitian tinggi untuk merancang mitigasi *learning effect* (melalui *counterbalancing*) agar data performa motorik yang diambil dari 37 responden tidak bias.

**Yang akan dilakukan berbeda:**
> Jika mengulang dari awal, saya akan melakukan studi rintis (*pilot study*) kecil dengan 2–3 responden terlebih dahulu di awal pengerjaan tugas untuk memastikan sistem perekaman *Show Taps* berjalan lancar sebelum proposal final ini disahkan.