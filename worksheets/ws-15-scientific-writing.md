# WS-15: Scientific Writing

> **Bab 15 — Penulisan Ilmiah**

---

## Ringkasan Materi

### Scientific Argument Flow

```
Problem → Gap → RQ → Method → Result → Analysis → Conclusion → Contribution
```

Paper ilmiah adalah **satu argumen utuh** dari masalah ke kontribusi. Setiap node harus terhubung logis ke node sebelum dan sesudahnya.

### Struktur IMRAD

| Section | Peran | Pertanyaan Kunci |
|---------|-------|-----------------|
| **Introduction** | Motivasi + frame | Why is this needed? |
| **Method** | Deskripsi (reproducible) | How was it done? |
| **Results** | Laporan objektif | What was found? |
| **Discussion** | Interpretasi + refleksi | What does it mean? |
| **Conclusion** | Ringkasan + kontribusi | So what? |

### Logical Flow — "Red Thread"

Setiap paragraf menjawab satu pertanyaan dan memicu pertanyaan berikutnya. Alur logis ini harus terasa di tiga level:
1. **Antar-kalimat** dalam paragraf
2. **Antar-paragraf** dalam section
3. **Antar-section** dalam paper

### Internal Consistency

Setiap elemen yang dijanjikan di Introduction harus hadir di Discussion/Conclusion.

**Consistency Matrix:**
```
           Intro  Method  Result  Discuss  Conclude
RQ1          ✓      ✓       ✓       ✓        ✓
RQ2          ✓      ✓       ✓       ✗ ←      ✓
Metrik-X     ✗      ✗       ✓ ←     ✗        ✗
```
**Masalah:** RQ2 dibahas di semua bagian kecuali Discussion. Metrik-X muncul di Result tapi tidak diperkenalkan di Method.

### Writing Quality Triad

| Kualitas | Deskripsi | Contoh Buruk → Baik |
|----------|----------|---------------------|
| **Clarity** | Dipahami sekali baca | "Performa meningkat" → "Accuracy meningkat dari 85.3% ke 89.7%" |
| **Precision** | Istilah eksak, tanpa ambiguitas | "signifikan" → "signifikan secara statistik (p=0.003, d=1.2)" |
| **Conciseness** | Setiap kata menambah informasi | Hapus kalimat redundan, filler words |

### Urutan Penulisan yang Disarankan

1. **Method & Results** — paling stabil, tulis pertama
2. **Discussion** — interpretasi berdasarkan hasil
3. **Introduction** — frame sesuai temuan aktual
4. **Abstract & Conclusion** — terakhir

### Target Jumlah Kata

| Section | Target |
|---------|--------|
| Introduction | 500–700 |
| Related Work | 700–1000 |
| Method | 800–1200 |
| Results | 500–800 |
| Discussion | 600–900 |
| Conclusion | 200–400 |

### Jebakan Kognitif

1. "Lebih panjang = lebih lengkap" → conciseness lebih berharga
2. "Introduction harus ditulis pertama" → justru ditulis terakhir
3. "Jargon teknis = lebih ilmiah" → clarity lebih penting
4. "Discussion = ringkasan Results" → Discussion = interpretasi + konteks

---

## Template A.15 — Paper Structure Checklist

```
## PAPER STRUCTURE CHECKLIST

Title   : Analisis Eksperimental Efisiensi Antarmuka Live Streaming TikTok Shop: Dampak Kepadatan Elemen Visual terhadap Transaksi Pengguna Generasi Z
Target  : [x] Jurnal  [ ] Konferensi  [ ] Laporan

Section Check:
  [x] Abstract — Masalah: Visual clutter di TikTok Shop; Metode: Eksperimen within-subject (n=37, 74 observasi); Hasil: Signifikansi kepadatan visual terhadap Time-on-Task; Kontribusi: Rekomendasi optimasi UI untuk social commerce.
  [x] Introduction — Konteks: Pertumbuhan social commerce; Gap: Kurangnya pengukuran objektif efisiensi teknis; RQ: Dampak visual clutter terhadap efisiensi transaksi?; Kontribusi: Teoretis (HCI) dan praktis (UX design).
  [x] Related Work — Tinjauan prinsip HCI (Nielsen) dan riset visual clutter di e-commerce; memposisikan gap riset sebagai bukti empiris objektif.
  [x] Method — Prosedur detail: Within-subject design, validasi pipeline (WS-11), 37 responden, metrik Time-on-Task & Number of Clicks, teknik analisis non-parametrik.
  [x] Results — Tabel hasil (Mean, Std) & Visualisasi (Bar Chart, Box Plot) berdasarkan data valid (74 observasi), pelaporan nilai p dan effect size.
  [x] Discussion — Interpretasi hasil (kaitan dengan beban kognitif), perbandingan dengan literatur, implikasi praktis, dan batasan riset (limitasi).
  [x] Conclusion — Jawaban tegas atas RQ, ringkasan kontribusi empiris, dan arahan riset masa depan.

Consistency Matrix:
  [x] RQ di Introduction selaras dengan Method dan Conclusion.
  [x] Variabel di Method (Visual Density/Time-on-Task) konsisten dengan Results.
  [x] Klaim interpretasi di Discussion didukung penuh oleh hasil uji Mann-Whitney U Test di Results.
  [x] Limitasi (misal: generalisasi sampel) dibahas di Discussion dan diakomodasi di Conclusion.

Writing Quality:
  [x] Clarity — Penggunaan kalimat aktif dan struktur paragraf yang mengalir.
  [x] Precision — Istilah teknis HCI dan statistik digunakan secara tepat.
  [x] Conciseness — Penghapusan frasa redundan agar fokus pada temuan.
```

---

## Latihan 1 — Paper Outline

Buat outline paper untuk riset Anda menggunakan struktur IMRAD.

| Section | Konten Utama (2-3 kalimat) | Target Kata |
|---------|---------------------------|------------|
| Abstract | Penelitian ini mengukur dampak visual clutter pada antarmuka Live Streaming TikTok Shop terhadap efisiensi transaksi Generasi Z. Menggunakan within-subject design (n=37), hasil menunjukkan bahwa kepadatan elemen visual meningkatkan Time-on-Task secara signifikan. Temuan ini memberikan kontribusi pada optimalisasi UI untuk platform social commerce. | 200-250 |
| Introduction | Fenomena social commerce mendorong fitur live streaming dengan kepadatan visual tinggi, yang membebani kognitif pengguna. Gap riset terletak pada minimnya pengukuran objektif terkait efisiensi teknis interaksi. RQ: Bagaimana kepadatan elemen visual mempengaruhi kecepatan dan akurasi transaksi? | 500-700 |
| Related Work | Mengulas teori beban kognitif (Nielsen) dan riset perilaku pengguna dalam e-commerce. Memposisikan riset sebagai validasi empiris atas prinsip HCI dalam lingkungan aplikasi yang dinamis. | 700-1000 |
| Method | Prosedur eksperimen terkontrol membandingkan kondisi Clean vs Full dengan 37 responden (74 observasi). Analisis menggunakan uji Mann-Whitney U Test dengan metrik Time-on-Task dan Number of Clicks dari screen recording. | 800-1200 |
| Results | Menyajikan perbandingan performa statistik antar kondisi dengan visualisasi data objektif. Tabel dan grafik menunjukkan peningkatan signifikan pada durasi dan kesalahan klik pada kondisi Full. | 500-800 |
| Discussion | Menginterpretasikan hasil bahwa kompleksitas visual menghambat efisiensi transaksi. Membahas limitasi terkait generalisasi sampel dan rekomendasi desain bagi pengembang. | 600-900 |
| Conclusion | Menyimpulkan bahwa antarmuka padat visual secara signifikan menurunkan efisiensi. Hasil ini menjadi dasar kontribusi praktis dalam pengembangan UI yang responsif untuk TikTok Shop. | 200-400 |

---

## Latihan 2 — Consistency Matrix

Buat consistency matrix untuk memverifikasi internal consistency paper Anda.

| | Intro | Method | Result | Discussion | Conclusion |
|--|-------|--------|--------|-----------|-----------|
| RQ1 (Dampak kepadatan visual terhadap durasi transaksi) | ✓ | ✓ | ✓ | ✓ | ✓ |
| RQ2 (Dampak kepadatan visual terhadap frekuensi klik salah) | ✓ | ✓ | ✓ | ✓ | ✓ |
| Metrik utama (Time-on-Task & Number of Clicks) | ✓ | ✓ | ✓ | ✓ | ✓ |
| Variabel IV (Kondisi Antarmuka: Clean vs Full) | ✓ | ✓ | ✓ | ✓ | ✓ |
| Variabel DV (Efisiensi Interaksi) | ✓ | ✓ | ✓ | ✓ | ✓ |
| Klaim/kontribusi (Optimasi desain UI social commerce) | ✓ | ✓ | ✓ | ✓ | ✓ |

**Inkonsistensi yang ditemukan:**
> Tidak ditemukan inkonsistensi yang berarti. Seluruh variabel independen (IV) dan dependen (DV) yang dijabarkan dalam pertanyaan penelitian (RQ) di bagian Introduction telah secara konsisten diukur dalam Method, disajikan dalam Results, diinterpretasikan dalam Discussion, dan dirumuskan kontribusinya dalam Conclusion.

**Tindakan perbaikan:**
> Memastikan konsistensi penamaan variabel. Istilah "Kondisi Clean" dan "Kondisi Full" harus digunakan secara seragam di seluruh bab agar tidak terjadi ambiguitas istilah bagi pembaca atau reviewer.

---

## Latihan 3 — Writing Quality Check

Ambil satu paragraf dari tulisan Anda (atau tulis paragraf baru) dan evaluasi kualitasnya.

**Paragraf asli:**
> Menurut saya kondisi Full Sticker itu bikin user jadi susah pas mau checkout barangnya karena banyak banget gangguan di layarnya yang bikin mereka jadi bingung, terus akhirnya durasi waktunya jadi lama banget kalau dibandingin sama kondisi Clean.

| Kriteria | Evaluasi | Perbaikan |
|----------|---------|-----------|
| Clarity | Menggunakan opini pribadi ("menurut saya") dan bahasa informal ("bikin", "banget"). | Menghilangkan opini subjektif dan mengganti dengan deskripsi hasil temuan objektif. |
| Precision | Istilah "susah", "banyak gangguan", dan "bingung" bersifat subjektif dan tidak saintifik. | Menggunakan istilah "beban kognitif", "visual clutter", dan data kuantitatif (Time-on-Task). |
| Conciseness | Frasa "akhirnya durasi waktunya jadi lama banget" terlalu bertele-tele. | Menyatakan hubungan kausalitas secara langsung: "Kepadatan visual meningkatkan durasi transaksi." |

**Paragraf setelah perbaikan:**
> Analisis data menunjukkan bahwa kondisi *Full Sticker* secara signifikan meningkatkan *Time-on-Task* dibandingkan dengan kondisi *Clean*. Peningkatan durasi ini mengindikasikan bahwa kepadatan elemen visual pada antarmuka *live streaming* menciptakan *visual clutter* yang menghambat efisiensi transaksi pengguna Generasi Z akibat peningkatan beban kognitif saat melakukan navigasi.
---

## Refleksi

> Apa perbedaan antara menulis "tentang" riset dan menulis sebagai "argumen" riset? Bagaimana urutan penulisan (Method → Discussion → Introduction) mengubah kualitas tulisan?

Jawaban:
Menulis "tentang" riset cenderung bersifat deskriptif, di mana peneliti hanya melaporkan apa yang dilakukan tanpa narasi yang kuat mengenai urgensi. Sebaliknya, menulis sebagai "argumen" riset adalah menyusun narasi di mana setiap bagian (data, metode, temuan) diposisikan sebagai bukti pendukung untuk menjawab pertanyaan penelitian (RQ) dan mengisi celah pengetahuan (gap). Menulis sebagai argumen menuntut peneliti untuk secara aktif menghubungkan temuan dengan teori, menjelaskan mengapa hasil tersebut penting, dan meyakinkan pembaca bahwa riset tersebut memberikan kontribusi nyata.

Urutan penulisan (Method → Results → Discussion → Introduction) secara drastis meningkatkan kualitas tulisan karena memastikan keselarasan logika:
1. Method & Results: Peneliti memantapkan "apa yang sebenarnya ditemukan" sebelum mencoba membungkusnya dalam narasi.
2. Discussion: Peneliti menginterpretasikan temuan tersebut ke dalam konteks ilmiah yang lebih luas.
3. Introduction: Setelah memahami kontribusi riset secara utuh, peneliti dapat menulis pendahuluan yang tajam, fokus, dan benar-benar menempatkan gap riset secara akurat sesuai dengan temuan akhir. 

Pendekatan ini mencegah terjadinya "cherry-picking" argumen atau klaim yang tidak berdasar, sehingga jurnal menjadi jauh lebih koheren dan logis.