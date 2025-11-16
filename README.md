<img width="77" height="21" alt="image" src="https://github.com/user-attachments/assets/a7fe4720-4787-486e-b96b-4f5e069313d3" /><p align="center">
  <img src="results/figures/Logo_IPB.png" width="200">
</p>

# Analisis Faktor Sosial Ekonomi terhadap Tingkat Kriminalitas di Jawa Barat Tahun 2024 Menggunakan Regresi Binomial Negatif
Proyek ini adalah tugas akhir mata kuliah Pemrograman Statistika (STA2511) yang menganalisis data kriminalitas di 24 wilayah hukum (Polres/Polresta/Polrestabes) di Jawa Barat dan hubungannya dengan faktor-faktor sosial ekonomi.
Karena data kriminalitas (data cacahan) terbukti mengalami **overdispersi**, proyek ini menggunakan **Regresi Binomial Negatif** sebagai model analisis utama.

## Struktur Folder
- `data/raw/` : data mentah (tidak diubah manual)
- `data/processed/` : data setelah dibersihkan (missing value, transformasi)
- `scripts/` : kode R untuk import data, fitting model, evaluasi
- `results/figures/` : visualisasi model dan error
- `results/tables/` : ringkasan metrik evaluasi (RMSE, MAE)
- `docs/` : catatan analisis / draft laporan

## 🎯 Relevansi dengan Materi Pemrograman Statistika

Proyek ini dirancang untuk memenuhi capaian pembelajaran mata kuliah, terutama pada tiga pilar utama sesuai panduan tugas PDF:

1.  `📁` **Teknik Munging/Wrangling (Pertemuan 3)**
    * Kami menggabungkan dua sumber data (Data Pidana & Data Sosek BPS).
    * Melakukan **agregasi** untuk menangani wilayah gabungan (misal: Kab. Bandung Barat & Kota Cimahi yang diwakili oleh **Polres Cimahi**) menggunakan `group_by()` dan `summarise()`.
    * *Hasil Akhir:* `data_final_bersih.xlsx`
    * *Laporan Lengkap:* `outputs/html/DataWranglingKelompok1.html`

2.  `🗺️` **Pemrograman Grafik (Pertemuan 4)**
    * Membuat visualisasi eksploratif (histogram, boxplot, scatter plot) menggunakan `ggplot2` untuk memahami distribusi data.
    * Membuat **visualisasi peta koroplet (choropleth map)** menggunakan paket `sf` dan `ggplot2` untuk memetakan sebaran geografis kriminalitas, sekaligus menangani pemetaan dari 27 Kab/Kota ke 24 Wilayah Hukum Polres.
    * *Laporan Lengkap:* `outputs/html/VisualisasiDataKelompok1.html`

3.  `📈` **Komputasi Regresi (Pertemuan 11)**
    * Menganalisis data respon (Jumlah Kejahatan) yang merupakan **data cacahan (count data)**.
    * Mengidentifikasi adanya **overdispersi** (varians > mean) pada data respon.
    * Membandingkan dua model: `glm()` (Regresi Poisson) dan `glm.nb()` (Regresi Binomial Negatif) untuk menemukan model yang paling sesuai.
    * *Laporan Lengkap:* `outputs/html/projek-github-pemro.html`

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

## 🏁 Kesimpulan

1.  Data kriminalitas di Jawa Barat (level Polres) menunjukkan karakteristik **data cacahan yang mengalami overdispersi kuat**, sehingga tidak dapat dianalisis dengan regresi linear biasa atau Regresi Poisson.
2.  Visualisasi peta menunjukkan bahwa tingkat kriminalitas cenderung lebih tinggi di wilayah urban dan sub urban yang padat penduduk (sekitar Jakarta dan Bandung Raya).
3.  Model **Regresi Binomial Negatif** terbukti sebagai model yang paling robust dan akurat secara statistik (AIC terendah) untuk menjelaskan hubungan antara faktor sosial ekonomi dan tingkat kriminalitas di Jawa Barat.

## 👥 Team Members
<table align="center">
  <tr>
    <td align="center">
      <a href="https://github.com/sabrorfalah-maker">
        <img src="https://github.com/sabrorfalah-maker.png" width="120" style="border-radius:50%">
        <br><sub><b>Sigap Abror Falah</b></sub>
      </a>
    </td>
    <td align="center">
      <a href="https://github.com/Lenipamularsih">
        <img src="https://github.com/Lenipamularsih.png" width="120" style="border-radius:50%">
        <br><sub><b>Leni Pamularsih</b></sub>
      </a>
    </td>
    <td align="center">
      <a href="https://github.com/wiliasondriva">
        <img src="https://github.com/wiliasondriva.png" width="120" style="border-radius:50%">
        <br><sub><b>Wilia Sondriva</b></sub>
      </a>
    </td>
    <td align="center">
      <a href="https://github.com/lilikavitaa">
        <img src="https://github.com/lilikavitaa.png" width="120" style="border-radius:50%">
        <br><sub><b>Lilik Avitadia Prichanti</b></sub>
      </a>
    </td>
    <td align="center">
      <a href="https://github.com/aridhapebriani">
        <img src="https://github.com/aridhapebriani.png" width="120" style="border-radius:50%">
        <br><sub><b>Aridha Pebriani Kusmiran</b></sub>
      </a>
    </td>
  </tr>
</table>
---
