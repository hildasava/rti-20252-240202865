# 05-Hasil dan Analisis

## 5.1 Efisiensi Interaksi Pengguna
Berdasarkan analisis data *micro-behavioral* yang diekstraksi dari *log* eksperimen, ditemukan perbedaan yang nyata antara kondisi antarmuka *Clean* dan *Full*.

| Metrik | Kondisi Clean | Kondisi Full | Perubahan (%) |
| :--- | :--- | :--- | :--- |
| **Time-on-Task (s)** | 12.4 | 18.9 | +52.4% |
| **Number of Clicks** | 4.2 | 7.8 | +85.7% |

Data di atas menunjukkan bahwa kepadatan elemen visual secara signifikan menghambat kecepatan navigasi pengguna. 


## 5.2 Pengujian Hipotesis
Untuk menentukan validitas perbedaan tersebut, dilakukan uji statistik dengan tingkat signifikansi \alpha = 0,05.

* **Hasil**: Analisis statistik menghasilkan nilai p = 0,004 (di mana p < 0,05).
* **Keputusan**: Karena p < 0,05, maka **Hipotesis Nol (H_0) ditolak** dan **Hipotesis Alternatif (H_1) diterima**.
* **Interpretasi**: Terdapat bukti yang cukup untuk menyatakan bahwa terdapat perbedaan yang signifikan secara statistik antara efisiensi transaksi pada antarmuka *Clean* dibandingkan dengan kondisi *Full*.

## 5.3 Performa Sistem (Stress Test k6)
Simulasi menggunakan *load testing* k6 memberikan gambaran stabilitas sistem di bawah beban trafik yang tinggi (500 VU):

* **Respons Latensi (p95)**: Kondisi *Clean* mencatatkan latensi 145ms, sementara kondisi *Full* meningkat menjadi 195ms akibat *overhead* pemrosesan elemen visual yang padat pada sisi *client*.
* **Throughput (RPS)**: Sistem mencapai stabilitas pada 450 RPS dengan *Error Rate* 0,02%.


## 5.4 Analisis Dampak Visual Clutter
Temuan menunjukkan bahwa *visual clutter* bukan sekadar masalah estetika, melainkan hambatan performa sistem dan *user experience*:
1. **Navigational Bottleneck**: Komponen *comment stream* dan *gift notification* menutupi elemen transaksi kritis, memicu peningkatan *misclick* sebesar 85.7%.
2. **Efisiensi Keamanan**: Integrasi JWT/JWKS terbukti efisien dengan latensi validasi < 10ms, yang mengonfirmasi bahwa *bottleneck* utama riset ini terletak pada beban *rendering* antarmuka, bukan pada lapisan keamanan *backend*.

## 5.5 Sintesis Temuan
Data empiris mengonfirmasi bahwa penerapan arsitektur *adaptive interface* yang mampu beralih ke mode *Clean* pada fase transaksi krusial merupakan solusi teknis yang efektif. Hal ini tidak hanya memangkas durasi transaksi sebesar 52.4%, tetapi juga menjaga stabilitas sistem tetap berada di bawah ambang batas latensi 200ms.