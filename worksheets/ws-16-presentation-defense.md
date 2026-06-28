# WS-16: Presentation & Defense (UAS)

> **Bab 16 — Presentasi & Pertahanan Ilmiah**

---

## Ringkasan Materi

### Scientific Defense Model

```
Research Work → Presentation → Questioning → Defense → Evaluation → Acceptance
```

### Presentasi ≠ Ringkasan Paper

| Paper | Presentasi |
|-------|-----------|
| Dibaca (self-paced) | Didengar (presenter-paced) |
| Detail lengkap | Ide kunci + highlight |
| Tabel numerik detail | Grafik visual + angka kunci |
| Pembaca bisa re-read | Audiens dengar sekali |

**Prinsip:** Presentasi membutuhkan **reformulasi**, bukan kompresi. Medium berbeda = pendekatan berbeda.

### Claim-Evidence-Reasoning (CER)

Setiap jawaban defense harus memiliki:
1. **Claim** — Pernyataan yang dijawab
2. **Evidence** — Data/fakta pendukung
3. **Reasoning** — Logika yang menghubungkan evidence ke claim

**Contoh:**
| Pertanyaan | Bad Answer | Good Answer (CER) |
|-----------|-----------|-------------------|
| "Kenapa hanya 3 dataset?" | "Tiga sudah cukup" | "3 dataset mewakili variasi: small-clean, medium-clean, medium-noisy [E]. Generalisasi perlu validasi lanjut — listed as limitation [R]" |
| "Hasil DS-3 menurun?" | "Itu outlier" | "Ya, karena distribusi heavy-tail melanggar asumsi Gaussian [E]. Ini menunjukkan boundary condition metode [R]" |
| "Effect size?" | "p=0.003, jadi signifikan" | "Cohen's d=1.2 (large effect) [E] — bukan hanya signifikan tapi substansial [R]" |

### Slide Design — One Slide, One Message

**Optimal 9-Slide Plan (15 menit):**

| # | Slide | Waktu | Pesan |
|---|-------|-------|-------|
| 1 | Title + context | 1 min | Apa ini tentang apa |
| 2 | Problem + motivation | 2 min | Mengapa penting |
| 3 | Gap + RQ | 1.5 min | Apa yang belum terjawab |
| 4 | Method overview | 2 min | Bagaimana dijawab (diagram) |
| 5 | Key result — tabel | 2 min | Temuan utama |
| 6 | Key result — grafik | 2 min | Pola visual |
| 7 | Interpretation + failure | 2 min | Apa artinya |
| 8 | Limitation + future | 1.5 min | Batasan & arah |
| 9 | Conclusion + contribution | 1 min | Closing message |

### Anticipatory Defense

Prediksi pertanyaan berdasarkan kategori:

| Kategori | Contoh Pertanyaan |
|---------|------------------|
| Problem | "Mengapa masalah ini penting?" |
| Gap | "Bagaimana dengan studi X yang sudah menjawab ini?" |
| Method | "Mengapa metode ini, bukan Y?" |
| Results | "Bagaimana menjelaskan anomali di DS-3?" |
| Generalization | "Apakah bisa diterapkan di domain lain?" |

### Tiga Prinsip Jawaban

1. **Direct** — Jawab dulu, elaborasi kemudian
2. **Data-based** — Tunjuk evidence spesifik
3. **Honest** — Akui limitasi jika memang ada

### Jebakan Kognitif

1. "Presentasi = semua yang ada di paper" → terlalu padat
2. "Slide cantik = presentasi bagus" → konten > estetika
3. "Tidak bisa jawab = gagal" → "I don't know, but..." menunjukkan kejujuran
4. "Tidak perlu latihan — saya paham riset saya" → latihan = menemukan celah

---

## Template A.16 — Defense Preparation Sheet

```
## DEFENSE PREPARATION

Slide Deck Plan:
  Total slides   : 11 (target: 10-12 konten + title/closing)
  Time per slide : ~1.5 - 2 min
  Total time     : 15 menit

Slide Outline:
| # | Pesan Utama | Visual | Waktu |
|---|-------------|--------|-------|
| 1 | Title + Context | Title Slide + Screenshot TikTok Shop Live | 1 min |
| 2 | Problem + Motivation | Bar Chart perbandingan beban kognitif & durasi | 2 min |
| 3 | Gap + Research Question | Tabel literatur gap & rumusan masalah | 1.5 min |
| 4 | Method Overview | Diagram alur eksperimen (Clean vs Full) | 2 min |
| 5 | Experimental Setup | Ilustrasi within-subject (37 responden, 74 observasi) | 1 min |
| 6 | Key Results: Statistik | Tabel Mean, Std Dev, Mann-Whitney U Test | 1.5 min |
| 7 | Key Results: Visualisasi | Grafik Box Plot sebaran durasi transaksi | 1.5 min |
| 8 | Interpretation | Diagram kausalitas visual clutter ke beban kognitif | 1.5 min |
| 9 | Limitation & Boundary Condition | Checklist ancaman validitas (internal/external) | 1 min |
| 10 | Conclusion | Poin jawaban tegas atas RQ & ringkasan kontribusi | 1 min |
| 11 | Closing | Q&A Slide | 30s |

Anticipatory Defense Matrix:
| Kategori | Pertanyaan Potensial | Jawaban (CER) |
|----------|---------------------|---------------|
| Problem | "Mengapa fokus pada kepadatan visual di TikTok Shop?" | [C] Kepadatan elemen visual yang ekstrem pada antarmuka social commerce berisiko membebani kognitif pengguna. [E] Data tren adopsi live streaming menunjukkan durasi interaksi yang tinggi. [R] Oleh karena itu, pengukuran efisiensi sangat krusial untuk memastikan kenyamanan dan kelancaran transaksi. |
| Gap | "Bukankah riset soal desain antarmuka sudah banyak dilakukan?" | [C] Studi yang ada masih didominasi oleh survei persepsi subjektif semata. [E] Terdapat celah minimnya data objektif berbasis rekaman interaksi teknis. [R] Riset ini mengisi celah tersebut dengan metrik kuantitatif terukur (Time-on-Task & Number of Clicks). |
| Method | "Mengapa menggunakan within-subject design, bukan between-subject?" | [C] Desain within-subject memberikan kontrol optimal terhadap variasi antar individu. [E] Sebanyak 37 responden mengeksekusi kedua skenario (Clean dan Full) sehingga menghasilkan 74 observasi yang valid. [R] Pendekatan ini meningkatkan statistical power secara signifikan tanpa memerlukan sampel masif. |
| Results | "Hasil Anda menunjukkan perbedaan signifikan, tetapi apakah itu berdampak secara praktis?" | [C] Perbedaan tidak hanya signifikan secara statistik, melainkan juga substansial secara praktis. [E] Nilai effect size (r) yang tinggi mengindikasikan penghematan waktu yang krusial bagi conversion rate bisnis. [R] Peningkatan efisiensi ini secara langsung memengaruhi pengalaman pengguna secara keseluruhan. |
| Generalization | "Apakah temuan ini dapat diterapkan pada aplikasi e-commerce konvensional?" | [C] Boundary condition dari riset ini membatasi generalisasi hanya pada antarmuka social commerce yang dinamis. [E] E-commerce konvensional tidak memiliki penumpukan elemen visual (notifikasi gift, stiker, komentar) sepadat live streaming. [R] Penerapan pada domain lain memerlukan validasi dan penyesuaian lebih lanjut. |

Latihan:
  Latihan 1: 29-06-2026 — [Durasi 18 menit, kelebihan waktu di bagian Method, perlu penyederhanaan penjelasan alur]
  Latihan 2: 02-07-2026 — [Durasi 15.5 menit, tanya-jawab Q&A sudah mengalir dan sesuai teknik CER]
  Latihan 3: 05-07-2026 — [Durasi 14.5 menit, siap untuk presentasi sidang akhir]
```

---

## Latihan 1 — Slide Outline

Rencanakan presentasi 15 menit untuk riset Anda.

| # | Pesan Utama | Visual yang Digunakan | Waktu |
|---|-------------|----------------------|-------|
| 1 | Judul, Nama, & Konteks Social Commerce | Title Slide + Screenshot UI TikTok Shop | 1 min |
| 2 | Problem: Efek Visual Clutter pada Beban Kognitif | Bar Chart: Komparasi durasi transaksi | 2 min |
| 3 | Gap + RQ: Kurangnya data objektif efisiensi teknis | Tabel komparasi gap literatur (Survey vs Objective Data) | 1.5 min |
| 4 | Method: Eksperimen Within-Subject (n=37) | Diagram alur prosedur & *Task Scenario* | 2 min |
| 5 | Results: Tabel Statistik Transaksi | Tabel Ringkasan (Mean/Std Dev/Signifikansi) | 1.5 min |
| 6 | Results: Visualisasi Pola Transaksi | Box Plot: Kondisi Clean vs Full | 1.5 min |
| 7 | Discussion: Interpretasi & Beban Kognitif | Diagram hubungan UI Complexity -> User Efficiency | 2 min |
| 8 | Limitation & Future Work | Checklist ancaman validitas riset | 1.5 min |
| 9 | Conclusion: Kontribusi UI Design | Poin ringkasan kunci & rekomendasi desain | 1 min |

**Total waktu estimasi:** 14 menit

---

## Latihan 2 — Anticipatory Defense

Prediksi 5 pertanyaan yang mungkin diajukan penguji, lalu siapkan jawaban CER.

## Latihan 2 — Anticipatory Defense

| # | Kategori | Pertanyaan | Claim | Evidence | Reasoning |
|---|----------|-----------|-------|----------|-----------|
| 1 | Problem | Mengapa riset ini fokus pada visual clutter di TikTok Shop? | Platform ini memiliki densitas elemen visual tertinggi di social commerce | Screenshot UI saat live streaming (banyak gift/sticker) | Densitas tinggi berkorelasi dengan peningkatan beban kognitif pengguna |
| 2 | Method | Apakah n=37 responden cukup representatif? | Dengan within-subject design, n=37 menghasilkan 74 observasi unik | Data log validasi pada WS-11 | Jumlah observasi memenuhi syarat untuk uji statistik non-parametrik yang robust |
| 3 | Results | Mengapa ada perbedaan signifikan pada durasi tapi tidak pada klik salah? | Desain Clean vs Full hanya mempengaruhi kecepatan akses, bukan akurasi input | Tabel hasil statistik deskriptif di Bab 14 | Desain interface mempengaruhi kognisi pemrosesan, namun tidak mengubah task-flow |
| 4 | Failure | Bagaimana Anda menjelaskan jika hasil riset tidak sesuai ekspektasi? | Hipotesis yang tidak terdukung adalah temuan empiris (boundary condition) | Analisis kegagalan (failure analysis) pada Bab 14 | Temuan negatif tetap merupakan kontribusi ilmiah untuk mencegah bias publikasi |
| 5 | Generalization | Apakah temuan ini bisa diterapkan ke aplikasi lain? | Prinsip kognitif (Nielsen) bersifat universal | Literatur HCI & eksperimen kontrol | Pola efisiensi akan berulang jika kepadatan visual serupa diterapkan pada domain lain |

---

## Latihan 3 — Simulasi Q&A

Minta teman/kolega mengajukan 3 pertanyaan tentang riset Anda. Catat pertanyaan dan evaluasi jawaban Anda.

## Latihan 3 — Simulasi Q&A

| # | Pertanyaan | Jawaban Saya | Evaluasi |
|---|-----------|-------------|---------|
| 1 | "Data durasi transaksi kamu bisa saja dipengaruhi koneksi internet, bukan desain UI. Bagaimana kamu mengontrol itu?" | "Saya menggunakan *local screen recording* di perangkat yang sama dengan jaringan terisolasi untuk memastikan *latency* tidak menjadi variabel pengganggu. Variabel yang diukur murni *time-on-task* dari aksi klik user." | [✓] Direct [✓] Data-based [✓] Honest |
| 2 | "Apakah hasil riset ini tidak bias karena responden teman seangkatan kamu sendiri?" | "Eksperimen menggunakan *within-subject design* di mana responden menjadi kontrol bagi diri sendiri. Fokusnya bukan pada *demografi* responden, melainkan perbandingan respon user terhadap dua kondisi antarmuka yang berbeda." | [✓] Direct [✓] Data-based [✓] Honest |
| 3 | "Rekomendasi desain kamu apa untuk TikTok agar tetap bisa jualan tapi tidak *clutter*?" | "TikTok bisa menerapkan fitur *Adaptive UI*. Elemen stiker/notifikasi hanya muncul saat durasi tertentu atau interaksi user, bukan tampil *overlay* secara permanen selama transaksi berlangsung." | [✓] Direct [✓] Data-based [✓] Honest |

**Pertanyaan yang paling sulit dijawab:**
> Pertanyaan mengenai validitas responden (apakah bias pertemanan berpengaruh pada hasil eksperimen).

**Apa yang perlu disiapkan lebih baik:**
> Memperkuat penjelasan teknis tentang mengapa *within-subject design* secara otomatis mengeliminasi bias karakteristik individu, sehingga penguji tidak lagi meragukan komposisi responden saya.
---

## Refleksi

> Dari seluruh proses WS-01 sampai WS-16 — dari paradigma riset hingga presentasi — bagian mana yang paling mengubah cara Anda berpikir tentang riset? Apa satu hal yang akan selalu Anda terapkan di riset berikutnya?

**Insight terbesar:**
> Perubahan terbesar adalah pemahaman bahwa riset bukan sekadar proses "mengumpulkan data", melainkan proses "membangun argumen". Awalnya saya berpikir riset adalah tentang apa yang saya temukan, namun ternyata riset yang baik adalah tentang bagaimana saya mengaitkan temuan tersebut dengan teori yang ada untuk menjawab gap penelitian secara logis. Proses dari WS-01 hingga WS-16 mengajarkan saya bahwa setiap langkah—mulai dari preprocessing data, analisis statistik, hingga visualisasi—harus memiliki alasan (justifikasi) yang kuat agar argumen riset saya tidak mudah dipatahkan.

**Yang akan selalu diterapkan:**
> Saya akan selalu menerapkan "Consistency Matrix" sebagai fondasi utama di setiap awal riset. Dengan memastikan keselarasan antara Pertanyaan Penelitian (RQ), Metodologi, Hasil, dan Kesimpulan sejak awal, saya dapat menghindari risiko "penulisan yang melebar" atau variabel yang tidak relevan. Memastikan setiap klaim memiliki bukti (Evidence) dan logika (Reasoning) yang jelas—prinsip CER—akan menjadi standar operasional saya dalam menulis karya ilmiah di masa depan.
