# Analisis Tingkat Kriminalitas di Provinsi Jawa Barat Tahun 2024

## Struktur Folder
- `data/raw/` : data mentah (tidak diubah manual)
- `data/processed/` : data setelah dibersihkan (missing value, transformasi)
- `scripts/` : kode R untuk import data, fitting model, evaluasi
- `results/figures/` : visualisasi model dan error
- `results/tables/` : ringkasan metrik evaluasi (RMSE, MAE)
- `docs/` : catatan analisis / draft laporan

## 1. Latar Belakang
Penelitian ini ...

## 2. Data
<p align="center">
  <img src="images/logo_bps.png" width="250">
</p>
### Variabel Penjelas (X)

### Variabel Respon (Y)

## 3. Tahapan analisis
1. Mengumpulkan data dari berbagai pangkalan data.
2. Melakukan eksplorasi data dengan mendeskripsikan data yang diperoleh.
3. Menguji sebaran pada peubah respon, apakah benar memiliki sebaran poisson atau tidak.
4. Menentukan model regresi poisson.
5. Mengidentifikasi overdisprsi dengan mengitung nilai koefisien disperse.
6. Menentukan model regresi binomial negatif.
7. Menghitung nilai AIC untuk memilih model terbaik

Commit changes
[  add: README for Analisis Kriminalitas Jabar 2024              ]
( ) Commit directly to the main branch
( ) Create a new branch for this commit and start a pull request
