# Jadwal & Log Pelaksanaan Penelitian

Catatan kronologis pelaksanaan tiap tahap dari WS-01 hingga WS-16.

## Log Pelaksanaan (Detail Workshop)

| Tanggal | Tahap | Aktivitas | Referensi (Workset) |
|---|---|---|---|
| 06–13 April | **Tahap 1** | WS-01: Distorsi Paradigma, WS-02: Problem Statement, WS-03: Literature Gap | [ws-01](../ws-01-distorsi-paradigma.md), [ws-02](../ws-02-problem-statement.md), [ws-03](../ws-03-literature-gap.md) |
| 20 April – 11 Mei | **Tahap 2** | WS-04: RQ & Hypothesis, WS-05: Variabel & Metrik, WS-06: System Experiment | [ws-04](../ws-04-rq-hypothesis.md), [ws-05](../ws-05-variabel-metrik.md), [ws-06](../ws-06-system-experiment.md) |
| 11–25 Mei | **Tahap 3** | WS-07: Experiment Design, WS-08: Proposal Integration, WS-09: Implementation, WS-10: Execution & Data | [ws-07](../ws-07-experiment-design.md), [ws-08](../ws-08-proposal-integration.md), [ws-09](../ws-09-implementation.md), [ws-10](../ws-10-execution-data.md) |
| 21 Juni | **Tahap 4** | WS-11: Data Validation, WS-12: Result Presentation, WS-13: Preprocessing, WS-14: Analysis & Interpretation | [ws-11](../ws-11-data-validation.md), [ws-12](../ws-12-result-presentation.md), [ws-13](../ws-13-preprocessing.md), [ws-14](../ws-14-analysis-interpretation.md) |
| 28 Juni | **Tahap 5** | WS-15: Scientific Writing, WS-16: Presentation Defense | [ws-15](../ws-15-scientific-writing.md), [ws-16](../ws-16-presentation-defense.md) |

## Log Teknis (Dataset n=40)

- **2026-06-12 s.d. 06-13**: Perancangan arsitektur, API Gateway Go (Echo), implementasi skrip k6, dan matrix pengujian awal (50 run).
- **2026-06-15**: Finalisasi replikasi (n=40 per kombinasi, total 400 run), flushing Redis, pembaruan pipeline `run_all.py`, dan sinkronisasi statistik akhir.

## Item Tindak Lanjut (Checklist Sebelum Submission)

- [x] Lengkapi matriks literatur (18 referensi terverifikasi) — [02-literatur/matriks-literatur.md](../02-literatur/matriks-literatur.md)
- [x] Verifikasi CVE-2026-48524 (PyJWT, CVSS 3.7) — [GHSA-fhv5-28vv-h8m8](https://github.com/advisories/GHSA-fhv5-28vv-h8m8)
- [ ] Tetapkan bahasa final naskah (Indonesia/Inggris)
- [ ] Pindahkan konten [07-manuskrip/naskah-jurnal.md](../07-manuskrip/naskah-jurnal.md) ke template jurnal tujuan
- [ ] Finalisasi penempatan figure/tabel sesuai gaya jurnal
- [ ] Review akhir seluruh klaim numerik (dataset n=40)
## Korespondensi

*(belum ada — tambahkan catatan korespondensi dengan pembimbing/editor jurnal di sini saat tersedia)*
