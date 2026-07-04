# 03-Tinjauan Pustaka

## 3.1 Human-Computer Interaction dan Beban Kognitif
Penelitian ini berlandaskan pada teori *Cognitive Load* yang menyatakan bahwa kapasitas pemrosesan informasi manusia memiliki batas ambang. Dalam konteks *social commerce*, paparan stimulus visual yang berlebihan (*visual clutter*) pada antarmuka *live streaming* secara langsung meningkatkan beban kognitif pengguna. Beban kognitif yang tinggi berbanding lurus dengan peningkatan waktu respons (*Time-on-Task*) dan probabilitas kesalahan interaksi (*misclick*).

## 3.2 Efisiensi Antarmuka dan Navigasi Pengguna
Dalam perancangan antarmuka pengguna (*User Interface*), efisiensi navigasi merupakan parameter utama untuk mencapai *usability* yang optimal. 
* **Fitts's Law**: Prinsip ini digunakan untuk memprediksi waktu yang dibutuhkan untuk menggerakkan kursor atau jari menuju target (seperti tombol *checkout*). Dalam lingkungan yang padat elemen visual, target menjadi sulit dijangkau karena terdistraksi oleh *noise* visual.
* **Minimalisme Visual**: Pendekatan desain yang berfokus pada pengurangan elemen yang tidak diperlukan untuk mengurangi beban kognitif. Dalam *live streaming*, penyederhanaan elemen saat fase transaksi krusial terbukti membantu pengguna dalam memproses informasi navigasi dengan lebih cepat dan akurat.

## 3.3 Mitigasi Visual Clutter
Mitigasi dilakukan dengan menerapkan mekanisme penyaringan stimulus visual. Pada fase kritis transaksi (seperti proses *checkout*), sistem harus mampu melakukan adaptasi antarmuka untuk mereduksi elemen-elemen non-transaksional. Hal ini bertujuan untuk memusatkan perhatian pengguna (*focal attention*) pada elemen navigasi inti, sehingga stabilitas performa fisik-motorik pengguna tetap terjaga.

## 3.4 Related Work
Penelitian terdahulu yang relevan antara lain:
1. Studi mengenai pengaruh kepadatan antarmuka terhadap *User Experience* pada platform *e-commerce* yang menekankan bahwa penyederhanaan antarmuka (*interface minimalism*) mampu meningkatkan tingkat konversi transaksi hingga 15%.
2. Penelitian tentang efisiensi sistem berbasis *adaptive UI* yang menunjukkan bahwa pengurangan elemen gangguan visual secara otomatis saat fase transaksi krusial terbukti secara signifikan menurunkan *Time-on-Task* pengguna Generasi Z.
3. Riset mengenai hubungan antara *visual noise* dan kecepatan eksekusi tugas pada aplikasi *mobile* yang membuktikan bahwa antarmuka yang bersih pada saat *checkout* menurunkan tingkat *misclick* secara drastis dibandingkan antarmuka yang penuh dengan elemen promosi.

Penelitian ini memposisikan diri untuk menjembatani celah riset tersebut dengan mengintegrasikan metrik teknis (efisiensi navigasi dan waktu eksekusi) untuk menentukan ambang batas optimal kepadatan elemen visual.