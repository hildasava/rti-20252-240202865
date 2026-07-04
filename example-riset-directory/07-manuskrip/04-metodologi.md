# 04-Metodologi

## 4.1 Arsitektur Eksperimen
Penelitian ini menggunakan pendekatan eksperimental terkontrol dengan metode *micro-behavioral analysis*. Objek penelitian berupa aplikasi *prototype* e-commerce yang mensimulasikan antarmuka *live streaming*. Eksperimen dibagi menjadi dua kelompok uji: 
* **Kondisi Clean**: Antarmuka minimalis, di mana elemen non-transaksional disembunyikan otomatis pada fase *checkout*.
* **Kondisi Full**: Antarmuka standar yang padat dengan *stiker*, *gift*, dan komentar.

Data dikumpulkan melalui *logging* otomatis pada setiap interaksi pengguna Generasi Z. Setiap tindakan seperti waktu mulai transaksi, durasi berpindah antar komponen, hingga jumlah klik tercatat secara *timestamped*. Dengan metode ini, data yang diperoleh bersifat objektif, menghindari bias subjektivitas yang sering ditemukan pada metode kuesioner konvensional.

## 4.2 Skema Hybrid Caching
Untuk menjamin stabilitas sistem selama simulasi trafik tinggi, diterapkan strategi *hybrid caching* yang menggabungkan *in-memory caching* dan *browser caching*:
* **Client-Side Caching**: Menyimpan *assets* statis (ikon dan elemen visual statis) secara lokal pada *browser* pengguna, sehingga mengurangi *bandwidth consumption* dan mempercepat *first contentful paint* (FCP).
* **Server-Side Redis Caching**: Menggunakan Redis untuk menyimpan status *session* pengguna dan *public keys* dari JWKS. Dengan pendekatan ini, sistem tidak perlu melakukan *handshake* berulang kali ke *identity provider* saat memvalidasi JWT, sehingga latensi *authentication* menurun drastis dan beban *database* utama diminimalisir.

## 4.3 Skenario Pengujian k6
Pengujian menggunakan **k6** untuk mensimulasikan perilaku pengguna dalam lingkungan *stress testing*:
1. **Ramp-Up Phase**: Simulasi lonjakan trafik dari 50 hingga 500 *Virtual Users* (VU) dalam durasi 10 menit guna menentukan ambang batas kemampuan sistem sebelum mengalami penurunan *throughput*.
2. **End-to-End Transaction Flow**: Fokus pada alur krusial, mulai dari keranjang hingga verifikasi pembayaran melalui *endpoint* `/checkout` dan `/payment`.
3. **Security-Integrated Testing**: Setiap *request* wajib menyertakan JWT yang divalidasi oleh *public key* yang di-*fetch* dari *JWKS endpoint*. Hal ini memastikan mekanisme keamanan tidak menjadi *bottleneck* saat sistem memproses *caching*.
4. **Thresholds Setting**: Menetapkan standar performa di mana *Response Time* (p95) harus di bawah 200ms dan *Error Rate* maksimal 0.1%.

## 4.4 Prosedur Pengukuran dan Analisis Data
Data yang terkumpul akan dianalisis melalui tahap berikut:
* **Pengukuran Objektif**: Menghitung *Time-on-Task* (selisih waktu antara aksi pertama dan konfirmasi pembayaran) dan *Number of Clicks* (efisiensi navigasi).
* **Uji Hipotesis**: Untuk membuktikan validitas perbedaan performa, digunakan uji statistik dengan tingkat signifikansi 0,05 (\alpha = 0,05$). Jika nilai p < 0,05, maka hipotesis penelitian diterima, yang berarti terdapat perbedaan performa yang signifikan secara statistik antara antarmuka kondisi *Clean* dan kondisi *Full*.
* **Interpretasi Sistem**: Mengintegrasikan hasil performa sistem (RPS dan latensi dari k6) dengan efisiensi interaksi pengguna untuk memberikan kesimpulan komprehensif bagi pengembangan arsitektur *adaptive interface*.