# 06-Kesimpulan dan Saran

## 6.1 Kesimpulan
Penelitian ini telah membuktikan secara empiris bahwa kepadatan elemen visual (*visual clutter*) pada antarmuka *live streaming* memiliki korelasi negatif yang signifikan terhadap efisiensi transaksi pengguna Generasi Z. Berdasarkan hasil pengujian dan analisis data, poin-poin kesimpulan penelitian adalah sebagai berikut:

* **Validasi Hipotesis**: Dengan nilai p = 0,004 (p < 0,05), H_0 ditolak dan H_1 diterima. Hal ini mengonfirmasi bahwa terdapat perbedaan signifikan secara statistik pada efisiensi transaksi (durasi dan akurasi) antara antarmuka kondisi *Clean* dan *Full*.
* **Peningkatan Efisiensi**: Penerapan *adaptive interface* yang menyederhanakan antarmuka pada fase transaksi krusial terbukti meningkatkan efisiensi waktu sebesar 52.4% dan mengurangi *misclick* sebesar 85.7%.
* **Stabilitas Teknis**: Integrasi skema *Hybrid Caching* dan validasi JWKS terbukti efektif menjaga stabilitas sistem dengan *latency* p95 di bawah 200ms, bahkan di bawah beban trafik tinggi hingga 500 *Virtual Users*.
* **Framework Adaptif**: Penelitian ini berhasil merumuskan spesifikasi teknis untuk *framework* antarmuka yang mampu melakukan penyesuaian kepadatan visual secara dinamis, yang menjadi solusi teknis atas benturan antara kebutuhan hiburan (*engagement*) dan kebutuhan transaksi (*conversion*).

## 6.2 Saran Penelitian Lanjutan
Meskipun penelitian ini telah memberikan acuan teknis yang solid, terdapat beberapa aspek yang dapat dikembangkan lebih lanjut pada studi mendatang:

1. **Eksplorasi Variabel Psikologis**: Penelitian selanjutnya dapat mengintegrasikan *eye-tracking technology* untuk memetakan *focal point* pengguna secara lebih mendalam guna memahami pola visual pengguna saat menghadapi kepadatan elemen yang berbeda.
2. **Skalabilitas Sistem**: Mengingat eksperimen dilakukan pada lingkungan simulasi, penelitian di masa depan dapat menguji implementasi *adaptive UI* ini pada platform *social commerce* skala produksi dengan jutaan pengguna serentak untuk mengukur efektivitas *caching* yang lebih kompleks.
3. **Diversifikasi Profil Pengguna**: Menguji *framework* antarmuka adaptif ini pada kelompok demografi selain Generasi Z untuk melihat apakah pola perilaku navigasi dan batas beban kognitif memiliki perbedaan yang signifikan.
4. **Optimasi AI-Driven**: Mengembangkan algoritma *Machine Learning* yang mampu memprediksi "fase kritis" pengguna secara *real-time* berdasarkan perilaku interaksi, sehingga transisi antarmuka menjadi lebih *seamless* dan personal.