# 06-Output: Hasil Analisis Statistik

Bagian ini menyajikan interpretasi hasil pengolahan data statistik dari pengujian performa sistem menggunakan *Mann-Whitney Test*.

## 1. Statistik Deskriptif
Berdasarkan data yang diolah, berikut adalah ringkasan performa berdasarkan kelompok:

| Variabel | Kelompok 1 (Mean) | Kelompok 2 (Mean) |
| :--- | :--- | :--- |
| **Time_on_Task** | 5.86 detik | 10.73 detik |
| **Klik_Salah** | 0 | 0 |
| **Status** | Succes | Succes |

* **Interpretasi**: Terdapat perbedaan durasi pengerjaan (*Time_on_Task*) yang signifikan antara Kelompok 1 (Optimasi) dan Kelompok 2 (Standar).

## 2. Uji Hipotesis (Mann-Whitney)
Berdasarkan hasil pengujian statistik untuk membandingkan *Time_on_Task* antara dua kelompok, diperoleh hasil sebagai berikut:

* **Nilai Signifikansi (Asymp. Sig. 2-tailed)**: < 0,001
* **Keputusan**: Karena nilai signifikansi < 0,05, maka **H0 ditolak** dan **H1 diterima**.

## 3. Pembahasan
Hasil analisis menunjukkan bahwa terdapat perbedaan signifikan secara statistik pada durasi pengerjaan (*Time_on_Task*) antara sistem dengan optimasi (Kelompok 1) dan sistem standar (Kelompok 2). 

Dengan nilai *Mean Rank* pada Kelompok 1 (19.00) yang lebih rendah dibandingkan Kelompok 2 (56.00), dapat disimpulkan bahwa implementasi mekanisme *caching* dan *rate limiting* pada arsitektur sistem terbukti secara empiris meningkatkan efisiensi waktu respon secara nyata. Sistem yang dikembangkan tidak hanya berhasil menjaga stabilitas operasional, tetapi juga memberikan pengalaman penggunaan yang lebih cepat bagi pengguna pada platform TikTok Shop.

## 4. Kesimpulan Analisis
Data ini memberikan bukti empiris bahwa optimasi sistem pada Kelompok 1 terbukti mempercepat waktu respon (*Time_on_Task*) tanpa mengorbankan tingkat akurasi data. Hasil ini mendukung hipotesis bahwa arsitektur yang diimplementasikan mampu meningkatkan efisiensi sistem secara signifikan.