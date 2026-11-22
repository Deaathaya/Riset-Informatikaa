# Proposal Penelitian

**Judul:** Perbandingan Strategi Penanganan Kondisi Operasi pada LSTM Autoencoder untuk Deteksi Dini Degradasi Mesin Turbofan

## 1. Latar Belakang
Pemantauan kondisi mesin turbofan berbasis data sensor penting untuk pemeliharaan prediktif karena kegagalan komponen pesawat berdampak pada keselamatan dan biaya operasional. Pendekatan prediksi sisa umur pakai (RUL) terawasi membutuhkan lintasan run-to-failure berlabel yang jarang tersedia di industri. Deteksi anomali tak terawasi dengan LSTM autoencoder (LSTM-AE) hanya membutuhkan data kondisi normal. Pada mesin dengan kondisi operasi beragam, perubahan altitude dan kecepatan menggeser nilai sensor tanpa berarti mesin terdegradasi, sehingga cara penanganan kondisi operasi memengaruhi kualitas deteksi.

## 2. Rumusan Masalah
1. Bagaimana kinerja LSTM-AE untuk deteksi dini degradasi turbofan bila kondisi operasi ditangani dengan normalisasi per regime operasi (Strategi A)?
2. Bagaimana kinerjanya bila kondisi operasi dimasukkan sebagai input tambahan dengan normalisasi global (Strategi B)?
3. Bagaimana kedua strategi dibandingkan dengan baseline Isolation Forest?

## 3. Tujuan
Membandingkan Strategi A dan Strategi B pada arsitektur LSTM-AE yang sama, berdasarkan false alarm rate, recall fase akhir, dan lead time, pada C-MAPSS FD002 dan FD004.

## 4. Batasan
- Data: C-MAPSS FD002 dan FD004 (data latih bawaan), data simulasi tanpa label anomali.
- Fase sehat diasumsikan 30% siklus awal dan fase akhir 20% siklus terakhir setiap mesin.
- Baseline: Isolation Forest.

## 5. Metode Ringkas
1. Bagi mesin 80% latih dan 20% validasi.
2. Normalisasi dengan Strategi A (K-means 6 regime, standardisasi per regime) atau Strategi B (standardisasi global, 3 operational setting sebagai fitur).
3. Jendela geser 30 siklus.
4. Latih LSTM-AE (64-32-32-64) pada jendela fase sehat.
5. Ambang τ = μ + 3σ dari galat rekonstruksi validasi sehat; alarm bila 3 jendela berturut-turut melampaui τ.
6. Evaluasi dengan tiga seed dan bandingkan dengan Isolation Forest.

## 6. Luaran
Draft paper seminar nasional, kode eksperimen (Google Colab), dan hasil evaluasi yang dapat direproduksi.

## 7. Referensi Awal
Daftar pustaka lengkap ada pada draft paper (`UAS/01_Draft_Paper`).
