# Kode dan Hasil

- `Colab_LSTM-AE_Turbofan.ipynb`: notebook Google Colab. Unggah `train_FD002.txt` dan `train_FD004.txt`, atur `QUICK = False`, lalu jalankan semua sel.
- `hasil/`: keluaran eksperimen akhir (3 seed: 42, 43, 44; hingga 40 epoch). `tabel4_hasil.csv` adalah Tabel 4 pada paper.

## Ringkasan hasil (rata-rata tiga seed)
| Subset | Model | Strategi | FAR | Recall fase akhir | Mesin terdeteksi (%) |
|---|---|---|---|---|---|
| FD002 | LSTM-AE | A | 0,021 | 0,841 | 100,0 |
| FD002 | LSTM-AE | B | 0,002 | 0,006 | 3,8 |
| FD004 | LSTM-AE | A | 0,020 | 0,824 | 100,0 |
| FD004 | LSTM-AE | B | 0,003 | 0,005 | 3,4 |
