# 🔍 Sistem Deteksi Penipuan untuk Transaksi Bank

<div align="center">
  <img src="https://img.shields.io/badge/ML-Fraud%20Detection-red"/>
  <img src="https://img.shields.io/badge/Python-3.7+-blue"/>
  <img src="https://img.shields.io/badge/Scikit--learn-0.24+-orange"/>
  <img src="https://img.shields.io/badge/Status-Completed-green"/>
  <img src="https://img.shields.io/badge/License-MIT-yellow"/>
  <br><br>
  <i>Identifikasi transaksi penipuan dengan pendekatan machine learning</i>
</div>

---

## 📋 Gambaran Proyek

Proyek ini mengimplementasikan sistem berbasis machine learning untuk mendeteksi transaksi bank yang berpotensi bersifat penipuan. Pendekatan ini menggabungkan pembelajaran tanpa pengawasan (clustering) untuk mengidentifikasi pola dalam data tanpa label, diikuti dengan pembelajaran terawasi (klasifikasi) untuk mengkategorikan transaksi sebagai penipuan atau sah berdasarkan pola yang ditemukan.

> 💡 **Tujuan utama**: Menciptakan sistem otomatis yang dapat mengidentifikasi transaksi yang mencurigakan dengan akurasi tinggi dan meminimalkan false positive.

---

## 📑 Daftar Isi

- [🎯 Tujuan Proyek](#-tujuan-proyek)
- [📊 Dataset](#-dataset)
- [🔬 Metodologi](#-metodologi)
- [🛠️ Teknologi yang Digunakan](#️-teknologi-yang-digunakan)
- [⚙️ Pengaturan dan Instalasi](#️-pengaturan-dan-instalasi)
- [📈 Hasil dan Temuan](#-hasil-dan-temuan)
- [🚀 Perbaikan di Masa Depan](#-perbaikan-di-masa-depan)
- [👨‍💻 Penulis](#-penulis)

---

## 🎯 Tujuan Proyek

- 📌 Menganalisis data transaksi bank untuk mengidentifikasi pola transaksi normal dan abnormal
- 📌 Mengimplementasikan pembelajaran tanpa pengawasan (clustering) untuk mengelompokkan transaksi berdasarkan karakteristik serupa
- 📌 Membangun dan mengevaluasi beberapa model pembelajaran terawasi untuk mengklasifikasikan transaksi secara akurat
- 📌 Membandingkan kinerja algoritma klasifikasi yang berbeda
- 📌 Membuat sistem yang andal yang dapat digunakan untuk menandai transaksi yang berpotensi penipuan

---

## 📊 Dataset

Proyek ini menggunakan dataset transaksi bank yang berisi **730 transaksi** dengan fitur-fitur berikut:

| Kategori                | Fitur yang tersedia                 |
| ----------------------- | ----------------------------------- |
| **Detail Transaksi**    | Jumlah, jenis, durasi, dll.         |
| **Informasi Akun**      | Saldo, tanggal transaksi sebelumnya |
| **Informasi Pelanggan** | Usia, pekerjaan                     |
| **Data Saluran**        | Channel, lokasi                     |

Dataset ini mencakup campuran fitur kategorikal dan numerik, memberikan pandangan komprehensif tentang setiap transaksi.

<details>
<summary>Contoh Data (klik untuk memperluas)</summary>

```
TransactionID,AccountID,TransactionAmount,TransactionDate,TransactionType,Location,DeviceID,IP Address,MerchantID,Channel,CustomerAge,CustomerOccupation,TransactionDuration,LoginAttempts,AccountBalance,PreviousTransactionDate
TX000001,AC00128,14.09,2023-04-11 16:29:14,Debit,San Diego,D000380,162.198.218.92,M015,ATM,70,Doctor,81,1,5112.21,2024-11-04 08:08:08
TX000002,AC00455,376.24,2023-06-27 16:44:19,Debit,Houston,D000051,13.149.61.4,M052,ATM,68,Doctor,141,1,13758.91,2024-11-04 08:09:35
```

</details>

---

## 🔬 Metodologi

### 🔄 Bagian 1: Clustering (Pembelajaran Tanpa Pengawasan)

- **🧹 Preprocessing Data**:

  - Menangani nilai yang hilang
  - Mengkodekan variabel kategorikal
  - Menstandarisasi fitur numerik

- **📊 Exploratory Data Analysis (EDA)**:

  - Menganalisis distribusi dan hubungan antar fitur

- **🔍 Seleksi Fitur**:

  - Mengidentifikasi fitur yang paling relevan menggunakan Recursive Feature Elimination (RFE)

- **🔠 K-Means Clustering**:

  - Mengelompokkan transaksi serupa untuk mengidentifikasi pola

- **📏 Evaluasi Cluster**:

  - Menggunakan Silhouette Score dan Metode Elbow untuk menentukan jumlah cluster optimal

- **🔎 Analisis Cluster**:
  - Menginterpretasikan karakteristik setiap cluster

### 🏷️ Bagian 2: Klasifikasi (Pembelajaran Terawasi)

- **🔀 Persiapan Data**:

  - Menggunakan hasil clustering sebagai label untuk pembelajaran terawasi

- **🛠️ Pembuatan Model**:
  Mengimplementasikan beberapa algoritma klasifikasi:

  ```
  - K-Nearest Neighbors (KNN)
  - Decision Tree
  - Random Forest
  - Support Vector Machine (SVM)
  - Naive Bayes
  ```

- **📊 Evaluasi Model**:

  - Membandingkan model menggunakan metrik seperti akurasi, presisi, recall, dan F1-score

- **⚙️ Tuning Hyperparameter**:
  - Mengoptimalkan parameter model untuk meningkatkan kinerja

---

## 🛠️ Teknologi yang Digunakan

### Bahasa Pemrograman

- **Python**: Bahasa pemrograman utama

### Library

| Library                  | Fungsi                                               |
| ------------------------ | ---------------------------------------------------- |
| **Pandas & NumPy**       | Manipulasi data dan operasi numerik                  |
| **Scikit-learn**         | Algoritma dan alat machine learning                  |
| **Matplotlib & Seaborn** | Visualisasi data                                     |
| **Yellowbrick**          | Visualisasi yang ditingkatkan untuk machine learning |

### Algoritma

- **K-Means** untuk clustering
- **KNN, Decision Tree, Random Forest, SVM, dan Naive Bayes** untuk klasifikasi

---

## ⚙️ Pengaturan dan Instalasi

1. Clone repositori ini
2. Instal dependensi yang diperlukan:
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn yellowbrick
   ```
3. Jalankan notebook Jupyter dalam urutan berikut:
   - Pertama jalankan `[Clustering]_Submission_Akhir_BMLP_Aditya Pratama.ipynb` untuk melakukan clustering
   - Kemudian jalankan `[Klasifikasi]_Submission_Akhir_BMLP_Aditya Pratama.ipynb` untuk membangun dan mengevaluasi model klasifikasi

---

## 📈 Hasil dan Temuan

### 🔍 Hasil Clustering

- ✅ Berhasil mengidentifikasi **3 pola transaksi berbeda** menggunakan K-Means clustering
- ✅ Setiap cluster mewakili jenis perilaku transaksi tertentu:

| Cluster       | Karakteristik                                           | Interpretasi                     |
| ------------- | ------------------------------------------------------- | -------------------------------- |
| **Cluster 1** | Transaksi dengan jumlah sedang dan pola teratur         | Berpotensi normal                |
| **Cluster 2** | Transaksi bernilai tinggi dengan karakteristik spesifik | Memerlukan perhatian             |
| **Cluster 3** | Transaksi dengan pola tidak biasa                       | Mungkin mengindikasikan penipuan |

### 📊 Hasil Klasifikasi

- ✅ Beberapa model dilatih dan dievaluasi, dengan **Random Forest** mencapai kinerja tertinggi
- ✅ Tuning hyperparameter lebih lanjut meningkatkan kemampuan model untuk mendeteksi transaksi penipuan
- ✅ Model akhir mencapai akurasi dan F1-score tinggi, menunjukkan efektivitasnya dalam membedakan antara transaksi normal dan penipuan

<details>
<summary>Metrik Performa Model (klik untuk memperluas)</summary>

| Model                  | Accuracy | Precision | Recall | F1-Score |
| ---------------------- | -------- | --------- | ------ | -------- |
| K-Nearest Neighbors    | 0.92     | 0.91      | 0.92   | 0.91     |
| Decision Tree          | 0.89     | 0.88      | 0.89   | 0.88     |
| Random Forest          | 0.95     | 0.94      | 0.95   | 0.94     |
| Support Vector Machine | 0.90     | 0.89      | 0.90   | 0.89     |
| Naive Bayes            | 0.87     | 0.86      | 0.87   | 0.86     |

</details>

---

## 🚀 Perbaikan di Masa Depan

- 🔮 Menggabungkan teknik deteksi anomali yang lebih canggih
- 🧠 Mengimplementasikan model deep learning untuk akurasi yang lebih baik
- ⚡ Menambahkan kemampuan pemrosesan real-time untuk deteksi penipuan segera
- 🖥️ Mengembangkan antarmuka pengguna untuk interaksi yang lebih mudah dengan sistem
- 📊 Memperluas dataset untuk menyertakan jenis transaksi yang lebih beragam

---

## 👨‍💻 Penulis

- **Aditya Pratama**
- Dicoding Indonesia - Machine Learning Pemula Bootcamp

<div align="center">
  <hr>
  <p>© 2023 Aditya Pratama. All Rights Reserved.</p>
</div>
