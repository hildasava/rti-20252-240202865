# WS-03: Literature Mapping & Gap

> **Bab 3 — Literature Review, Research Gap & Baseline**

---

## Ringkasan Materi

### Literature Review = Positioning, Bukan Ringkasan

Literature review bukan merangkum paper satu per satu. Pendekatan yang benar adalah **concept-centric** — organisasi berdasarkan tema, metode, atau variabel. Tujuan: menemukan **pola, kontradiksi, dan gap**.

### Empat Jenis Research Gap

| Jenis Gap | Deskripsi | Contoh |
|-----------|----------|--------|
| **Performance Gap** | Performa belum memadai | Akurasi deteksi hanya 78% pada kasus tertentu |
| **Method Gap** | Pendekatan belum diterapkan | Belum ada yang pakai transformer untuk task ini |
| **Data Gap** | Dataset terbatas/tidak representatif | Semua studi pakai dataset sintetis |
| **Context Gap** | Belum diuji pada konteks berbeda | Belum ada evaluasi di negara berkembang |

Gap terkuat = kombinasi 2+ jenis.

### Systematic Search Strategy

1. **Database**: IEEE Xplore, ACM DL, Scopus, Google Scholar
2. **Boolean query** yang terdokumentasi eksplisit
3. **Snowballing**: backward (telusuri referensi) + forward (cari yang mengutip)
4. Klaim "belum ada penelitian" harus didukung **bukti pencarian**

### Baseline Selection — 3 Kriteria

| Kriteria | Pertanyaan |
|----------|-----------|
| **Relevan** | Apakah menyelesaikan masalah yang sama? |
| **Representatif** | Apakah mewakili common practice? |
| **State-of-the-Art** | Apakah terbaru/terbaik? |

Membandingkan deep learning 2024 dengan decision tree sederhana tanpa justifikasi = **straw man comparison** (perbandingan tidak jujur).

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan baca literatur | Mencari solusi yang sudah ada | Memahami apa yang belum terjawab |
| Cara membaca paper | Tutorial, how-to | Metode, limitasi, gap |
| Baseline | Framework terpopuler | State-of-the-art yang rigorous |
| Dokumentasi pencarian | Tidak diperlukan | Wajib (reproducible) |

### Istilah Penting

- **Concept-centric** — Organisasi literatur berdasarkan konsep/metode, bukan per penulis
- **Snowballing** — Backward (telusuri referensi) + Forward (cari yang mengutip paper kunci)
- **Research Position** — Pernyataan eksplisit posisi riset terhadap studi sebelumnya
- **Straw man comparison** — Memilih baseline lemah agar metode sendiri terlihat lebih baik

---

## Template A.3 — Literature Mapping & Gap Identification

```
LITERATURE MAPPING

Topik      : Analisis Efisiensi UI TikTok Shop pada Fitur Live Streaming.
Database   : Google Scholar
Query      : "Analisis UI UX TikTok Shop", "Usability TikTok Live Streaming", "Efisiensi Transaksi Social Commerce".
Tahun      : 2023 - 2026.
Hasil awal : 15 paper → Screening → 5 paper final

Literature Matrix (concept-centric):

| Study | Tahun | Method | Data | Result | Limitation |
|-------|-------|--------|------|--------|------------|
|AdeA.C.| 2026  |Kuantitatif (SEM) |Gen Z di Kediri|Penggunaan TikTok Shop & Live berpengaruh pada konsumerisme|Fokus pada   perilaku ekonomi, bukan efisiensi teknis UI.|
|Afina G.|2024|Kuantitatif|134 Responden|Daya tarik visual Live Streaming memicu pembelian impulsif.|Tidak mengukur waktu transaksi (Time-on-Task)|
|Annisa K. J.|2024|Kuantitatif|Konsumen di Yogyakarta|Fitur Live Streaming meningkatkan keputusan pembelian secara signifikan.|Fokus pada konten promosi, bukan kemudahan navigasi sistem.|
|Tiara O. S.|2025|Kualitatif (Observasi)|UMKM Aromaterapi|Penggunaan elemen visual (diskon/voucher) kunci keberhasilan.|Data bersifat subjektif dari sisi penjual, bukan data performa user.|
|Tinezia H.|2025|Kuantitatif|276 Responden|User Experience (UX) berpengaruh positif pada niat beli.|Tidak membedah detail elemen antarmuka yang menyebabkan hambatan.|

Pola yang ditemukan:
  Metode dominan     : Kuantitatif (kuesioner) fokus pada psikologi konsumen.
  Dataset umum       : Pengguna Generasi Z di wilayah Indonesia.
  Limitasi berulang  : Kebanyakan penelitian fokus pada "kenapa orang beli", tapi sangat sedikit yang mengukur "seberapa cepat/mudah proses teknisnya" (efisiensi).

GAP IDENTIFICATION

Gap 1: [Jenis: performance & method Gap ]
  Deskripsi    : Kurangnya pengukuran performa teknis seperti kecepatan transaksi (Time-on-Task) dan jumlah klik (Number of Clicks) secara objektif.
  Bukti        : Studi Afina (2024) dan Tinezia (2025) fokus pada persepsi subjektif melalui kuesioner, bukan observasi waktu nyata.
  Signifikansi : Penting untuk mengetahui apakah "kemacetan" transaksi disebabkan oleh mental pengguna atau memang desain UI yang terlalu rumit.

Gap 2: [Jenis: Context Gap]
  Deskripsi    : Belum adanya analisis mendalam tentang efisiensi desain overlay (tampilan bertumpuk) pada layar Live Streaming yang padat informasi.
  Bukti        : Tiara (2025) menyebutkan visual penting, tapi tidak meneliti gangguan (visual clutter) dari stiker/komentar saat proses checkout.
  Signifikansi : Membantu desainer UI mengurangi beban kognitif pengguna agar tidak gagal saat flash sale.

Baseline Selection:
| Baseline | Relevansi | Representatif | Source |
|----------|-----------|---------------|--------|
|Analisis User Experience (UX) |Membahas pengaruh pengalaman pengguna secara langsung terhadap niat beli di TikTok Shop.|Mewakili penelitian kuantitatif terbaru (2025) dengan sampel besar (276 responden).|Tinezia Hairunisya (2025)|
|Daya Tarik Visual Live Streaming|Meneliti bagaimana elemen visual pada Live TikTok mendorong pembelian spontan (impulsive).|Menjadi rujukan utama untuk memahami variabel "Visual Appeal" pada antarmuka Live.|Afina Ghaissani (2024)|
```

---

## Latihan 1 — Concept-Centric Literature Table

Gunakan topik riset dari WS-02. Cari minimal 5 paper relevan menggunakan Google Scholar atau database lain.

**Topik riset:** Analisis Efisiensi UI TikTok Shop pada Fitur Live Streaming.
**Query pencarian:"Analisis UI UX TikTok Shop", "Usability TikTok Live Streaming", "Efisiensi Transaksi Social Commerce".
**Database:** Google Scholar.

| # | Study | Tahun | Method | Dataset | Result | Limitasi |
|---|---|---|---|---|---|---|
| 1 | Ade Astian Cahyani | 2026 | Kuantitatif (PLS-SEM) | Gen-Z di Kediri | Penggunaan TikTok Shop dan fitur Live memicu gaya hidup konsumtif. | Fokus pada dampak ekonomi/perilaku, bukan efisiensi teknis UI. |
| 2 | Afina Ghaissani | 2024 | Kuantitatif | 134 Responden | Daya tarik visual (Visual Appeal) pada Live memicu pembelian impulsif. | Tidak mengukur waktu penyelesaian transaksi (Time-on-Task). |
| 3 | Annisa Khulil Jannah | 2024 | Kuantitatif | Konsumen di Yogyakarta | Live streaming dan potongan harga berpengaruh pada keputusan pembelian. | Fokus pada faktor eksternal (promo), bukan alur navigasi sistem. |
| 4 | Tiara Octaviolita Sari | 2025 | Kualitatif (Observasi) | UMKM Natureline | Tampilan diskon dan voucher saat live adalah kunci keberhasilan transaksi. | Data bersifat subjektif, tidak ada metrik teknis jumlah klik. |
| 5 | Tinezia Hairunisya | 2025 | Kuantitatif | 276 Responden | User Experience (UX) berpengaruh positif terhadap niat beli (Purchase Intention). | Belum menganalisis hambatan navigasi akibat kepadatan layar (clutter). |

**Pola yang terlihat — Metode dominan:** Mayoritas penelitian menggunakan metode Kuantitatif untuk menguji hubungan antar variabel perilaku melalui kuesioner.

**Limitasi yang berulang:** Penelitian yang ada (Ade, Afina, Annisa, Tiara, Tinezia) lebih banyak membahas sisi psikologi konsumen dan hasil penjualan. Belum ada yang melakukan pengukuran teknis (HCI) secara objektif seperti efisiensi jumlah klik atau durasi waktu transaksi di tengah kondisi layar yang padat (visual clutter).

---

## Latihan 2 — Gap Identification

Berdasarkan tabel di Latihan 1, identifikasi gap.

| Jenis Gap | Ditemukan? | Gap Statement |
|-----------|-----------|---------------|
| Performance Gap | [X] Ya / [ ] Tidak | Belum ada data performa teknis mengenai kecepatan transaksi (latency/throughput) saat kondisi trafik tinggi pada fitur Live Streaming TikTok Shop. |
| Method Gap | [X] Ya / [ ] Tidak | Mayoritas penelitian menggunakan kuesioner persepsi; belum ada yang menerapkan metode observasi metrik HCI seperti pengukuran Time-on-Task (detik) dan Number of Clicks. |
| Data Gap | [ ] Ya / [ ] Tidak | - |
| Context Gap | [X] Ya / [ ] Tidak | Belum adanya analisis efisiensi antarmuka pada layar Live yang memiliki kepadatan informasi tinggi (visual clutter) seperti tumpukan stiker, komentar, dan gift. |

**Gap utama yang dipilih:** Method Gap & Context Gap.

**Mengapa gap ini penting (bukan sekadar "belum ada yang meneliti")?**
> Karena dalam ekosistem Social Commerce yang bersifat real-time, kecepatan dan kemudahan navigasi adalah kunci keberhasilan transaksi. Jika UI tidak efisien karena terlalu padat informasi (visual clutter), pengguna akan mengalami kelelahan kognitif dan kesulitan melakukan checkout tepat waktu. Penelitian ini penting untuk memberikan bukti teknis (bukan sekadar persepsi) guna mengoptimalkan desain antarmuka agar proses belanja menjadi lebih efektif bagi pengguna dan UMKM.

---

## Latihan 3 — Baseline Selection

Pilih 2 baseline dari literatur yang sudah dibaca.

| # | Baseline | Mengapa Relevan | Mengapa Representatif | Apakah SOTA? | Sumber |
|---|----------|----------------|----------------------|-------------|--------|
| 1 | Analisis User Experience (UX) | Karena riset ini mengukur pengaruh kemudahan penggunaan terhadap niat beli di TikTok Shop. | Mewakili indikator standar dalam riset interaksi pengguna pada platform TikTok Shop. | Ya (2025) | Tinezia Hairunisya (2025) |
| 2 | Visual Appeal & Impulsive Buying | Fokus pada elemen visual antarmuka saat Live Streaming yang memicu reaksi cepat pengguna. | Mewakili studi kasus spesifik pada fitur Live Streaming dengan jumlah responden yang memadai. | Ya (2024) | Afina Ghaissani (2024) |

**Apakah pemilihan baseline ini bisa dianggap straw man?** [ ] Ya / [X] Tidak
> Justifikasi: Pemilihan baseline ini bukan straw man karena kedua penelitian tersebut merupakan studi terbaru (2024 & 2025) yang memiliki variabel sangat kuat dan relevan dengan objek penelitian. Membandingkan riset ini dengan hasil studi yang sudah stabil dan berkualitas tinggi memastikan bahwa kebaruan (novelty) yang diusulkan benar-benar teruji.
---

## Refleksi

> Apa perbedaan antara "belum ada yang meneliti ini" (klaim tanpa bukti) dengan research gap yang valid? Bagaimana cara membuktikan bahwa sebuah gap benar-benar ada?

**Jawaban:**
> Perbedaan mendasarnya terletak pada dasar argumentasi dan bukti literatur. Klaim "belum ada yang meneliti" sering kali hanya asumsi subjektif tanpa penelusuran mendalam. Sebaliknya, research gap yang valid adalah kesenjangan yang ditemukan setelah melakukan pemetaan literatur secara sistematis, di mana peneliti bisa menunjukkan secara spesifik bagian mana yang belum diselesaikan (misalnya: variabel, metode, atau konteks tertentu).

> Cara membuktikan bahwa sebuah gap benar-benar ada adalah dengan menyusun Literature Matrix (concept-centric) seperti pada Latihan 1. Melalui matriks tersebut, kita membandingkan penelitian terdahulu (seperti karya Ade Astian, Afina, Annisa, Tiara, dan Tinezia) dan menunjukkan pola limitasi yang konsisten. Dengan membuktikan bahwa penelitian yang sudah ada memiliki batasan yang sama (contohnya: semua masih fokus pada persepsi kualitatif/kuesioner), maka gap untuk melakukan penelitian teknis secara kuantitatif/objektif menjadi terbukti secara ilmiah.
