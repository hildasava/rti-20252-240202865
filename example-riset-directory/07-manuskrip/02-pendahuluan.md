# 02-Pendahuluan

## 2.1 Latar Belakang
Transformasi digital dalam sektor ekonomi telah melahirkan ekosistem *social commerce* yang mengintegrasikan media sosial dengan platform belanja digital sebagai kanal utama perdagangan modern. Di Indonesia, fitur *Live Streaming* pada TikTok Shop telah menjadi ujung tombak strategi penetrasi pasar, khususnya untuk menjangkau target audiens dari klaster Generasi Z yang dikenal sangat adaptif terhadap teknologi digital namun memiliki ekspektasi tinggi terhadap kelancaran navigasi serta kecepatan respons dari antarmuka aplikasi.

Dalam realita industri, dinamika kompetisi yang agresif mendorong para pengembang aplikasi untuk terus memadatkan antarmuka dengan berbagai elemen dinamis guna mendongkrak *engagement* dan retensi pengguna. Fenomena ini menciptakan *visual clutter* yang ekstrem, di mana layar dipenuhi oleh stiker animasi promosi, notifikasi *gift* digital, dan aliran teks komentar yang bergerak cepat secara konstan. Secara psikologis dan teknis, kondisi ini menabrak prinsip dasar *Human-Computer Interaction* (HCI) terkait batas ambang beban kognitif manusia dalam memproses stimulus visual secara bersamaan. Ketika komponen non-transaksi tersebut menutupi ikon navigasi inti seperti tombol keranjang kuning atau tombol *checkout*, efisiensi interaksi pengguna secara nyata terdegradasi. Dampak dari penumpukan elemen visual ini tidak hanya memicu ketidaknyamanan navigasi dan risiko kesalahan klik (*misclick*), tetapi juga secara signifikan memperpanjang durasi transaksi pembelian bagi pengguna Generasi Z yang menuntut efisiensi tinggi.

## 2.2 Rumusan Masalah
Akar masalah penelitian ini bersumber dari benturan arsitektur sistem di mana antarmuka dituntut untuk tetap dinamis demi hiburan, namun di sisi lain harus memfasilitasi transaksi belanja yang menuntut efisiensi teknis dan akurasi tinggi. Berdasarkan permasalahan tersebut, penelitian ini difokuskan pada pengujian sejauh mana tingkat kepadatan elemen visual (*visual clutter*) secara objektif berpengaruh terhadap degradasi performa fisik-motorik pengguna, serta bagaimana perbandingan efisiensi performa transaksi antara antarmuka dalam kondisi *Clean* dan kondisi *Full* dapat digunakan untuk menentukan ambang batas optimal kepadatan elemen visual bagi pengembangan sistem yang lebih efisien.

## 2.3 Tujuan Penelitian
Sejalan dengan rumusan masalah tersebut, penelitian ini bertujuan untuk:
1. Membuktikan secara empiris hubungan kausalitas antara kepadatan stimulus visual dengan degradasi performa fisik-motorik, yang mencakup durasi transaksi dan akurasi klik pada pengguna Generasi Z.
2. Merumuskan spesifikasi teknis bagi pengembangan framework arsitektur antarmuka adaptif yang mampu mengatur kepadatan elemen visual secara dinamis berdasarkan fase kritis transaksi agar efisiensi sistem tercapai secara optimal.

## 2.4 Kontribusi Penelitian
Penelitian ini memberikan kontribusi signifikan bagi pengembangan bidang *social commerce*:

* **Kontribusi Metodologis**: Mengisi celah riset (*method gap*) dengan menerapkan pengujian berbasis metrik teknis objektif (*Time-on-Task* dan *Number of Clicks*) sebagai pengganti metode survei subjektif yang mendominasi literatur terdahulu.
* **Kontribusi Praktis**: Menjadi acuan teknis bagi pengembang sistem dalam merancang arsitektur antarmuka yang cerdas (*adaptive interface*) untuk mengoptimalkan kinerja sistem dan stabilitas *throughput* transaksi pada platform belanja digital.