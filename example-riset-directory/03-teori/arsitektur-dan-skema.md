# 03-Teori: Analisis Empiris Performa Sistem

Bagian ini menyajikan landasan teori yang menghubungkan hasil uji statistik dengan implementasi arsitektur sistem mitigasi *JWKS flooding*.

## 1. Landasan Empiris (Hasil Uji Mann-Whitney)
Berdasarkan pengujian statistik menggunakan *Mann-Whitney Test* pada data sistem, ditemukan perbedaan yang signifikan antara kondisi sistem sebelum dan setelah penerapan mekanisme mitigasi.

* **Hasil Signifikansi**: Nilai *Asymp. Sig. (2-tailed)* sebesar <,001 (untuk VAR00002) menunjukkan bahwa mekanisme pertahanan sistem (caching dan rate limiting) memberikan peningkatan performa yang signifikan secara statistik.
* **Analisis Teoretis**: Perbedaan ini membuktikan bahwa arsitektur sistem yang diuji tidak sekadar berfungsi secara teknis, tetapi mampu secara konsisten menjaga efisiensi respons dibandingkan sistem yang tidak memiliki proteksi terhadap trafik tinggi.

## 2. Arsitektur Komponen (Mitigasi Serangan)
Diagram ini menjelaskan alur kerja sistem yang menjadi subjek uji dalam penelitian. Logika "Fail-Closed" dan "Redis Cache" adalah variabel yang berkontribusi pada stabilitas yang terukur dalam hasil SPSS.



[Image of API gateway architecture diagram]


```mermaid
graph TD
    User((User)) --> Gateway[API Gateway - Go Echo]
    Gateway --> Cache{Redis Cache}
    Cache -- Hit --> Valid[Validasi JWT/Session]
    Cache -- Miss --> Limit{Rate Limit}
    Limit -- Aman --> DB[(PostgreSQL)]
    Limit -- Flood --> Reject[Fail-Closed]
    DB --> Cache