# 3. Tahap 3 — Prosedur Pengujian Responden

**Status: Selesai**
**Acuan:** [2. Tahap 2 — Implementasi Prototipe Antarmuka](2.md)
**Lokasi Data:** [../06-data/raw-results/](../06-data/raw-results/)

---

## 3.1 Skenario Pengujian
Pengujian dilakukan untuk mengukur efisiensi interaksi pengguna secara langsung melalui perbandingan dua varian antarmuka.

* **Subjek**: 74 Responden (Generasi Z).
* **Desain Eksperimen**: *Between-Subject Design* (37 responden kelompok `Clean`, 37 responden kelompok `Full`).
* **Instruksi**: Responden diberikan skenario tugas tunggal: melakukan transaksi pembelian dari masuk ke *live streaming* hingga klik tombol *checkout* akhir.

## 3.2 Prosedur Pelaksanaan
1. **Briefing**: Responden diberikan penjelasan singkat mengenai tugas yang harus diselesaikan tanpa memaparkan tujuan desain yang diuji.
2. **Eksekusi**: Responden melakukan interaksi pada prototipe menggunakan perangkat **Samsung A23** sesuai dengan kelompoknya (Clean atau Full).
3. **Observasi**: Setiap sesi direkam menggunakan perekam layar untuk memastikan akurasi data durasi dan perilaku klik.
4. **Ekstraksi Data**: Data durasi interaksi (*Time-on-Task*) dan jumlah *misclick* dicatat secara manual dari rekaman layar ke dalam *spreadsheet* master untuk setiap responden.

## 3.3 Metrik Pengukuran
* **Time-on-Task (ToT)**: Durasi waktu (dalam detik) dari awal tugas hingga penyelesaian transaksi.
* **Error Rate (Klik Salah)**: Frekuensi klik yang dilakukan responden di luar area elemen navigasi utama.
* **Success Rate**: Status akhir transaksi (Berhasil/Gagal) untuk memastikan validitas data.

## 3.4 Pengolahan Data
* **Standardisasi**: Seluruh data dari 74 responden diverifikasi untuk memastikan tidak ada *outlier* ekstrem akibat kendala teknis.
* **Coding Data**: Data durasi dan frekuensi klik dikodekan ke dalam format numerik yang kompatibel dengan **SPSS**.
* **Analisis Statistik**: Data siap diolah menggunakan *Independent Samples T-Test* di **SPSS** untuk menentukan apakah perbedaan kepadatan visual pada antarmuka memiliki signifikansi statistik ($p < 0,05$) terhadap efisiensi interaksi pengguna.