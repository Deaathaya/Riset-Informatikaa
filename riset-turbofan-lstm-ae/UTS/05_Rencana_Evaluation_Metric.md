# Rencana Evaluation Metric

Data tidak memiliki label anomali, sehingga evaluasi memakai definisi fase: **fase sehat** = 30% siklus awal setiap mesin (f ≤ 0,30), **fase akhir** = 20% siklus terakhir (f ≥ 0,80), dengan f = c / T_f. Fase di antaranya tidak dievaluasi. Evaluasi dilakukan per mesin pada 20% mesin validasi.

| Metrik | Definisi | Arah baik |
|---|---|---|
| False alarm rate (FAR) | Proporsi jendela fase sehat yang ditandai anomali | Rendah |
| Recall fase akhir | Proporsi jendela fase akhir yang ditandai anomali | Tinggi |
| Lead time | T_f − siklus alarm pertama | Tinggi, selama alarm bukan alarm dini palsu |
| Mesin terdeteksi (%) | Proporsi mesin yang memicu alarm | Tinggi |
| Alarm dini palsu (%) | Proporsi mesin dengan alarm pertama di fase sehat | Rendah |

**Aturan alarm:** alarm pertama dibunyikan saat 3 jendela berturut-turut memiliki galat rekonstruksi di atas ambang τ = μ_e + 3σ_e (dari validasi fase sehat).

**Pelaporan:** rata-rata ± simpangan baku dari tiga random seed untuk LSTM-AE Strategi A, LSTM-AE Strategi B, dan Isolation Forest, pada FD002 dan FD004 secara terpisah.
