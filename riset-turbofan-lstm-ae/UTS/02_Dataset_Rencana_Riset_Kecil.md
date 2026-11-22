# Dataset Rencana Riset Kecil

**Dataset:** NASA C-MAPSS (Commercial Modular Aero-Propulsion System Simulation), simulasi propagasi kerusakan mesin turbofan hingga gagal.

**Sumber yang dipakai:** Kaggle, "NASA Turbofan Jet Engine Data Set" oleh behrad3d — https://www.kaggle.com/datasets/behrad3d/nasa-cmaps (salinan data NASA Prognostics Center of Excellence).

**Referensi sumber asli:** A. Saxena, K. Goebel, D. Simon, and N. Eklund, "Damage propagation modeling for aircraft engine run-to-failure simulation," in *Proc. PHM*, 2008, doi: 10.1109/PHM.2008.4711414.

## Subset yang dipilih
| Atribut | FD002 | FD004 |
|---|---|---|
| Jumlah mesin data latih | 260 | 249 |
| Jumlah baris data latih (siklus) | 53.759 | 61.249 |
| Jumlah regime operasi | 6 | 6 |
| Modus kegagalan | 1 (HPC) | 2 (HPC dan fan) |

FD001 dan FD003 tidak dipakai karena hanya memiliki satu regime operasi.

## Struktur data
26 kolom tanpa header: nomor mesin, nomor siklus, 3 operational setting (altitude, bilangan Mach, throttle resolver angle), dan 21 sensor.

## Fitur yang dipakai
14 sensor: s2, s3, s4, s7, s8, s9, s11, s12, s13, s14, s15, s17, s20, s21. Sensor s1, s5, s6, s10, s16, s18, s19 dibuang karena konstan atau hampir konstan pada setiap regime.

## Rencana pemakaian
Hanya data latih bawaan (train_FD002.txt, train_FD004.txt) yang dipakai karena lintasan data uji bawaan terpotong sebelum mesin gagal, sehingga lead time tidak dapat dihitung. Berkas ada di `UAS/02_Dataset`.
