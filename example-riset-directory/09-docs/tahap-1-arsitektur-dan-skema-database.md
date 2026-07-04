# 1. Tahap 1 — Perancangan Instrumen & Skenario Eksperimen

**Status: Selesai.**

## 1.1 Komponen Eksperimen
Rancangan riset ini berfokus pada perbandingan performa manusia dalam berinteraksi dengan antarmuka digital, dengan dua varian instrumen utama:

* **Antarmuka `Clean` (Baseline)**: Desain antarmuka minimalis di mana elemen navigasi (tombol *checkout*, keranjang kuning) menjadi fokus utama dengan kepadatan visual rendah.
* **Antarmuka `Full` (Intervensi Visual)**: Desain antarmuka yang merepresentasikan kondisi *live streaming* aktual di TikTok Shop, dengan kepadatan elemen visual tinggi (animasi stiker, notifikasi *gift*, dan komentar bergerak).

## 1.2 Prosedur Skenario
Skenario pengujian dirancang untuk mengukur efisiensi interaksi (bukan latensi server):

* **Tugas Utama**: Pengguna diminta untuk melakukan transaksi pembelian (klik keranjang kuning hingga ke tahap *checkout* akhir).
* **Variabel Independen**: Kepadatan elemen visual (`Clean` vs `Full`).
* **Variabel Dependen**: 
    * *Time-on-Task*: Durasi waktu mulai dari instruksi awal hingga klik tombol *checkout*.
    * *Klik Salah*: Frekuensi *misclick* atau navigasi tidak relevan.

## 1.3 Skema Data & Pengukuran
Karena ini adalah penelitian eksperimental, data disimpan dalam bentuk dataset SPSS untuk analisis statistik. Berikut adalah struktur data yang digunakan:

| Variabel | Tipe Data | Deskripsi |
|---|---|---|
| `Responden_ID` | Nominal | ID unik responden (1–37) |
| `Kelompok` | Nominal | 1 (Clean), 2 (Full) |
| `Time_on_Task` | Rasio | Durasi transaksi dalam detik |
| `Klik_Salah` | Rasio | Frekuensi klik di luar elemen navigasi |
| `Status` | Ordinal | Keberhasilan transaksi (Sukses/Gagal) |

## 1.4 Keputusan Teknis Eksperimen
* **Metode Pengujian**: *Within-Subject Design*, di mana setiap responden (N=37) diuji pada kedua kondisi antarmuka untuk meminimalkan bias variasi individu.
* **Alat Ukur**: Analisis rekaman layar (*screen recording*) yang kemudian diekstraksi ke dalam *spreadsheet* dan diimpor ke **SPSS** untuk uji beda (*Paired Samples T-Test*).
* **Standardisasi**: Penggunaan perangkat yang seragam (Samsung A23) untuk memastikan ukuran layar dan responsivitas UI konsisten bagi seluruh responden.
* **Validitas**: Seluruh data akan diolah menggunakan SPSS untuk menentukan apakah perbedaan durasi transaksi antara `Clean` dan `Full` memiliki signifikansi statistik (p < 0,05).