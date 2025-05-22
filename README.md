<p align="center">
  <img src="https://raw.githubusercontent.com/zhrnisrina/NZcompetition/main/Logo-IPB-University-Horizontal-600x157.png" alt="Logo IPB University" width="400">
</p>

<h2 align="center">KLASIFIKASI KELOMPOK INDEKS
 KETAHANAN PANGAN</h2>

<p align="center">
  <b> NEWTON
</p>

![image](https://github.com/user-attachments/assets/7fcd1985-49c8-444e-8fda-444da36df7ff)

## 🧭 Latar Belakang

Ketahanan pangan merupakan aspek fundamental yang mempengaruhi kesejahteraan sosial, ekonomi, dan kesehatan masyarakat. Dalam konteks global yang semakin kompleks, ketahanan pangan tidak hanya dipengaruhi oleh faktor produksi pangan, tetapi juga oleh aksesibilitas, distribusi, dan kualitas pangan. Oleh karena itu, pemantauan dan evaluasi ketahanan pangan melalui Indeks Ketahanan Pangan (IKP) menjadi sangat penting. IKP digunakan untuk mengukur sejauh mana suatu wilayah atau kelompok masyarakat dapat mengakses dan memanfaatkan pangan yang cukup, bergizi, dan aman, serta menilai kerentanannya terhadap risiko pangan, seperti krisis pangan, bencana alam, atau fluktuasi harga pangan.

Seiring dengan kemajuan teknologi, penelitian mengenai ketahanan pangan kini semakin dimungkinkan dengan penerapan metode machine learning. Metode ini memungkinkan pengolahan data yang lebih kompleks dan besar, serta pengenalan pola yang lebih akurat dalam berbagai faktor yang memengaruhi ketahanan pangan. Dengan menggunakan algoritma machine learning, seperti klasifikasi (classification), regresi (regression), dan clustering, kita dapat mengklasifikasikan wilayah atau kelompok ke dalam kategori IKP, seperti sangat rentan dan atau tahan terhadap ketahanan pangan. Proses ini memberikan keunggulan dalam mengidentifikasi perbedaan ketahanan pangan antar wilayah atau kelompok masyarakat dengan tingkat akurasi yang lebih tinggi.

Penerapan machine learning dalam analisis IKP bukan hanya memperbaiki akurasi dalam mengklasifikasikan ketahanan pangan, tetapi juga memungkinkan identifikasi faktor-faktor penyebab ketahanan pangan yang lebih mendalam dan berbasis data yang lebih komprehensif. Dengan demikian, penelitian ini diharapkan dapat memberikan kontribusi signifikan dalam merancang kebijakan ketahanan pangan yang lebih efektif dan berkelanjutan, serta memitigasi kerentanannya, terutama bagi kelompok masyarakat yang paling terdampak.

---

## 🎯 Tujuan

*  Mengklasifikasikan wilayah ke dalam kelompok-kelompok Indeks Ketahanan Pangan secara sistematis dan terukur.
*  Meningkatkan akurasi pemetaan ketahanan pangan, sehingga hasil klasifikasi dapat dimanfaatkan untuk perumusan kebijakan, penentuan prioritas intervensi, serta monitoring dan evaluasi program pembangunan pangan daerah.
---

## 📊 Data

*  Data yang digunakan berasal dari **Portal Satu Data Indonesia** melalui tautan: [https://data.go.id/](https://data.go.id/)
*  Observasi mencakup seluruh **514 kabupaten/kota di Indonesia**, yang mencerminkan kondisi sosial-ekonomi dan tingkat ketahanan pangan di masing-masing wilayah.

---

| **Variabel** | **Keterangan**             | **Deskripsi**                                                                               | **Satuan**              |
| ------------ | -------------------------- | ------------------------------------------------------------------------------------------- | ----------------------- |
| **Y**        | Indeks Ketahanan Pangan    | Mencerminkan tingkat ketahanan pangan di suatu wilayah                                      | Indeks (1 dan 2)        |
| **X1**       | Persentase Balita Stunting | Proporsi balita yang mengalami *stunting*, mencerminkan permasalahan gizi kronis            | Persentase (%)          |
| **X2**       | Akses Listrik              | Persentase rumah tangga dengan akses terhadap listrik sebagai indikator infrastruktur dasar | Persentase (%)          |
| **X3**       | Produksi Padi              | Total produksi padi sebagai indikator ketersediaan pangan utama                             | Ton                     |
| **X4**       | Laju Pertumbuhan Ekonomi   | Laju pertumbuhan ekonomi sebagai gambaran kondisi pembangunan wilayah                       | Persentase (%)          |

---
## 🔁 Diagram Alir
![Image](https://github.com/user-attachments/assets/7aef87a9-7448-42bd-a653-7167ae09b414)

---

## Proporsi Kelompok IKP 
![image](https://github.com/user-attachments/assets/49e527ca-b397-4250-94c9-94b8b612081c)


---


## 🔧 Penanganan Missing Value

Variabel `Produksi Padi` memiliki sejumlah nilai kosong (missing) pada beberapa kabupaten/kota. Untuk memastikan kualitas analisis, dilakukan **imputasi data** dengan metode berikut:

* 🔍 **Strategi**:
  Nilai yang hilang diisi dengan **median Produksi Padi dari provinsi tempat kabupaten/kota tersebut berada**.

* ✅ **Alasan Pemilihan Median**:

  * Lebih robust terhadap outlier dibanding rata-rata
  * Tetap mencerminkan karakteristik wilayah provinsi secara umum
  * Memungkinkan pengisian yang konsisten dan berbasis wilayah administratif
 
 ---

 ## 🤖 Model Klasifikasi 

| Metode                                         | Accuracy (%)  | Balanced Accuracy (%) |
| ---------------------------------------------- | ------------  | --------------------- |
| K-Nearest Neighbors (KNN)                      | 71.57         | 69.54                 |
| Decision Tree                                  | 82.35         | 81.50                 |
| Random Forest (RF)                             | 83.33         | 82.27                 |
| Bagging Reglog (Bagging + Logistic Regression) | 84.31         | 83.04                 |
| SVM Bagging                                    | 74.51         | 68.94                 |

 ---

 ## 📌 Interpretasi

🔍 **Bagging Reglog** memberikan performa terbaik dengan **accuracy sebesar 84.31%** dan **balanced accuracy sebesar 83.04%**. Hal ini menunjukkan bahwa model ini tidak hanya akurat secara keseluruhan, tetapi juga seimbang dalam mengklasifikasikan kedua kelas IKP (1 dan 2).

🌲 **Random Forest** dan **Decision Tree** juga menunjukkan performa yang tinggi, menandakan bahwa model pohon keputusan cukup baik dalam menangkap pola non-linear dari variabel prediktor.

🧠 **SVM Bagging** memiliki accuracy yang cukup baik, namun **balanced accuracy-nya rendah**, mengindikasikan ketidakseimbangan dalam mengklasifikasi kelas minoritas.

👟 **KNN** memiliki performa paling rendah dalam kedua metrik, yang bisa jadi disebabkan oleh sensitivitasnya terhadap skala data atau distribusi observasi yang padat di wilayah tertentu.

---

## 💡 Kesimpulan

Model ensemble seperti **Bagging Reglog** dan **Random Forest** terbukti unggul dalam memodelkan klasifikasi ketahanan pangan berbasis data sosial-ekonomi dan produksi. Ini menunjukkan bahwa penggabungan beberapa model (**ensemble**) dapat meningkatkan akurasi dan kestabilan prediksi.

---
    
## 👥Anggota Kelompok

| Nama Lengkap                  | NIM         | 
|-------------------------------|-------------|
| Putri Nisrina Az-Zahra        | M0501241050 |
| Zamrah Mutmainnah             | M0501241066 |
| Nabillah Rahmatiah Tangke     | M0501241070 |   
| Nur'aini                      | M0501241058 |
