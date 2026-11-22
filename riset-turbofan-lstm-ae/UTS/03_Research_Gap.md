# Research Gap

## Penelitian terkait
| Penelitian | Pendekatan | Keterbatasan terhadap topik ini |
|---|---|---|
| Arivin, 2026 | Autoencoder (MSE) pada C-MAPSS FD001, ambang persentil ke-95 | Satu regime operasi, tanpa pemodelan temporal |
| Sánchez dkk., 2026 (preprint arXiv) | LSTM-AE pada fase sehat, kondisi operasi dihilangkan dengan normalisasi berbasis regresi, ambang adaptif | Tidak membandingkan strategi lain penanganan kondisi operasi |
| de Pater & Mitici, 2023 | Kondisi operasi sebagai input LSTM-AE untuk health indicator (N-CMAPSS DS02) | Tujuan health indicator, bukan deteksi dini; bukan C-MAPSS FD002/FD004 |
| Lodygowski & Szrama, 2025 | Autoencoder + GMM + LSTM pada C-MAPSS | Fokus klasifikasi kondisi dan prediksi RUL |
| Elsherif dkk., 2025 | Deep learning untuk degradasi dan RUL turbofan | Fokus prediksi RUL |

## Gap
Kondisi operasi yang beragam menggeser nilai sensor tanpa berarti mesin terdegradasi. Dua strategi telah dipakai di literatur untuk tujuan berbeda, yaitu menghilangkan pengaruh kondisi operasi sebelum pelatihan dan memasukkannya sebagai input model. Berdasarkan penelusuran literatur yang dilakukan, belum ditemukan studi yang membandingkan keduanya secara langsung pada tugas deteksi dini dengan metrik evaluasi yang sama.

## Posisi penelitian ini
Perbandingan terkontrol Strategi A (normalisasi per regime) dan Strategi B (kondisi operasi sebagai input) pada arsitektur LSTM-AE yang sama, dengan metrik false alarm rate, recall fase akhir, dan lead time, serta Isolation Forest sebagai baseline.
