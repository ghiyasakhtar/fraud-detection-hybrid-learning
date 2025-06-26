# Fraud Detection via Hybrid Learning  
*Clustering-Driven Classification on Bank Transaction Data*

## Overview
Proyek ini bertujuan mengembangkan sistem deteksi kecurangan (fraud) pada transaksi keuangan dengan pendekatan **Hybrid Learning**, yaitu menggabungkan metode **unsupervised learning** (clustering) dan **supervised learning** (klasifikasi). Pendekatan ini berguna ketika data awal tidak memiliki label, dan pelabelan harus dihasilkan secara otomatis sebelum pelatihan model klasifikasi.

## Dataset
- **Nama:** Bank Transaction Dataset for Fraud Detection  
- **Sumber:** [Kaggle](https://www.kaggle.com/datasets)  
- **Jumlah sampel:** 2.537 entri  
- **Format:** CSV  
- **Isi Dataset:**  
  Termasuk atribut transaksi, demografi pelanggan, dan pola penggunaan. Dataset merepresentasikan perilaku transaksi perbankan yang realistis namun tidak dilabeli pada awalnya.

## Metodologi

### 1. Clustering (Unsupervised Learning)
- **Tujuan:** Menghasilkan label/kelas berdasarkan pola kemiripan dalam data.
- **Algoritma:** K-Means Clustering
- **Output:** Dataset baru dengan label hasil clustering sebagai kelas

### 2. Classification (Supervised Learning)
- **Tujuan:** Melatih model untuk memprediksi kelas (hasil clustering) dari data baru.
- **Algoritma:** K-Nearest Neighbors (KNN)
- **Evaluasi:** Accuracy, Precision, Recall, F1-Score

## Tools & Libraries
- Python (Jupyter Notebook)
- [pandas](https://pandas.pydata.org/)
- [numpy](https://numpy.org/)
- [scikit-learn](https://scikit-learn.org/)
- [matplotlib](https://matplotlib.org/)
- [seaborn](https://seaborn.pydata.org/)
- [joblib](https://joblib.readthedocs.io/)
- [yellowbrick](https://www.scikit-yb.org/)

## Struktur Proyek
```

├── notebook_clustering.ipynb # Notebook untuk proses K-Means dan pelabelan
├── notebook_classification.ipynb # Notebook untuk pelatihan KNN
├── decision_tree_model.h5 # Model lain yang diuji
├── explore_KNN_classification.h5
├── model_clustering.h5
├── PCA_model_clustering.h5
├── tuning_classification.h5
├── dataset.csv # Dataset awal dari Kaggle (Already Modified)
└── requirements.txt # Dependensi proyek
```

## Cara Menjalankan

1. **Clone repository** atau buka di Google Colab
    ```bash
    git clone https://github.com/ghiyasakhtar/fraud-detection-hybrid-learning
    cd fraud-detection-hybrid-learning
    ```
2. Pastikan dependensi telah terinstal:
   ```bash
   pip install -r requirements.txt
   ```
3. Jalankan `clustering.ipynb` untuk menghasilkan label dari data tidak berlabel
4. Jalankan `classification.ipynb` untuk melatih model klasifikasi menggunakan label dari clustering
