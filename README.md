<img width="77" height="21" alt="image" src="https://github.com/user-attachments/assets/a7fe4720-4787-486e-b96b-4f5e069313d3" /><p align="center">
  <img src="results/figures/Logo_IPB.png" width="200">
</p>

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

## 2. Tujuan Penelitian


## 3. Data dan Variabel
<p align="center">
  <img src="results/figures/Logo_bps.png" width="200" style="margin-right: 20px;">
  <img src="results/figures/Logo Dinas Pendidikan Jawa Barat.png" width="200">
</p>

### Variabel Penjelas (X)
- Upah Minimum Kabupaten
- Kepadatan Penduduk
- Produk Domestik Regional Bruto (PDRB)
- Tingkat Pengangguran Terbuka
- Jumlah Putus Sekolah

### Variabel Respon (Y)
- Jumlah Kejahatan yang dilaporkan

### Dataset
| No | Satuan Wilayah Hukum      | Jumlah Kejahatan | Upah Minimum Kab. | Kepadatan Penduduk |  PDRB  | T. Pengangguran Terbuka | Putus Sekolah |
|----|---------------------------|------------------|-------------------|--------------------|--------|-------------------------|---------------|
| 1  | Polres Bogor              | 4030             | 4579541           | 1.942              | 54857  | 7.34                    | 24            |
| 2  | Polres Ciamis             | 1077             | 2089464           | 813                | 34336  | 3.37                    | 5             |
| 3  | Polres Cianjur            | 1951             | 2915102           | 727                | 24914  | 5.99                    | 27            |
| …  | …                         | …                | …                 | …                  | …      | …                       | …             |
| 21 | Polresta Kota Bogor       | 1576             | 4813988           | 10.273             | 56616  | 8.13                    | 1             |
| 22 | Polresta Cirebon          | 1719             | 2517730           | 2.312              | 28140  | 6.74                    | 3             |
| 23 | Polrestabes Kota Bandung  | 4036             | 4209309           | 15.557             | 147081 | 7.4                     | 17            |

### Scatterplot Variabel X terhadap Y
<p align="center">
  <img src="results/figures/scatterplot.png" width="800">
</p>

## 3. Metodologi


## 4. Tahapan analisis
1. Mengumpulkan data dari berbagai pangkalan data.
2. Melakukan eksplorasi data dengan mendeskripsikan data yang diperoleh.
3. Menguji sebaran pada peubah respon, apakah benar memiliki sebaran poisson atau tidak.
4. Menentukan model regresi poisson.
5. Mengidentifikasi overdisprsi dengan mengitung nilai koefisien disperse.
6. Menentukan model regresi binomial negatif.
7. Menghitung nilai AIC untuk memilih model terbaik

## 5. Visualisasi
### Peta Kriminalitas Jawa Barat
<p align="center">
  <img src="results/figures/Peta Kriminalitas.png" width="1000">
</p>

## 👥 Team Members
<p align="center">
  <a href="https://github.com/sigapafalah">
    <img src="https://github.com/sigapafalah.png" width="120" style="border-radius:50%">
    <br><sub><b>Sigap Abror Falah</b></sub>
  </a>
  &nbsp;&nbsp;&nbsp;&nbsp;
  <a href="https://github.com/Lenipamularsih">
    <img src="https://github.com/Lenipamularsih.png" width="120" style="border-radius:50%">
    <br><sub><b>Leni Pamularsih</b></sub>
  </a>
  &nbsp;&nbsp;&nbsp;&nbsp;
  <a href="https://github.com/wiliasondriva">
    <img src="https://github.com/wiliasondriva.png" width="120" style="border-radius:50%">
    <br><sub><b>Wilia Sondriva</b></sub>
  </a>
  &nbsp;&nbsp;&nbsp;&nbsp;
  <a href="https://github.com/lilikavitaa">
    <img src="https://github.com/lilikavitaa.png" width="120" style="border-radius:50%">
    <br><sub><b>Lilik Avitadia Prichanti</b></sub>
  </a>
  &nbsp;&nbsp;&nbsp;&nbsp;
  <a href="https://github.com/aridhapebriani">
    <img src="https://github.com/aridhapebriani.png" width="120" style="border-radius:50%">
    <br><sub><b>Aridha Pebriani Kusmiran</b></sub>
  </a>
</p>
