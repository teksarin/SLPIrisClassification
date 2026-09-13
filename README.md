# Single Layer Perceptron — Klasifikasi Biner Iris

**Nama:** Adzrha Auryn Alius
**NIM:** 24/533582/PA/22594

## Deskripsi tugas

1. Melengkapi perhitungan Single Layer Perceptron untuk klasifikasi biner data Iris pada
   spreadsheet, mencakup fase training dan validasi.
2. Membuat kode Python dari perhitungan tersebut dan mengunggahnya ke GitHub (repositori ini).
3. Menyusun slide presentasi berisi grafik akurasi dan loss dari kedua sumber.

## Struktur repositori

```
.
├── dataset/
│   └── data_iris.csv       
├── grafik/
│   ├── accuracy_chart.png  
│   └── loss_chart.png      
├── .gitignore
├── README.md
└── SLP.ipynb               
```

## Dataset

`dataset/data_iris.csv` memuat 100 baris dari dataset Iris, dibatasi pada dua kelas pertama yaitu Iris-setosa dan Iris-versicolor

Encoding label (setosa = 0, versicolor = 1) dan pembagian data dilakukan di dalam notebook:
40 baris pertama tiap kelas menjadi data training, 10 baris sisanya menjadi data validasi.
Hasilnya 80 baris training (40 setosa + 40 versicolor) dan 20 baris validasi (10 + 10),
identik dengan tab *Data Training* dan *Data Validation* pada spreadsheet.

## Spesifikasi model

| Komponen | Nilai |
|---|---|
| Arsitektur | 4 input -> 1 neuron output, tanpa hidden layer |
| Fungsi aktivasi | Sigmoid, `g(z) = 1 / (1 + e^-z)` |
| Ambang klasifikasi | 0.5 |
| Loss | Squared error, dirata-rata per epoch (MSE) |
| Optimizer | Stochastic gradient descent, update tiap sampel |
| Learning rate | 0.1 |
| Bobot awal | bias dan theta1-theta4 = 0.5 |
| Jumlah epoch | 5 |

## Hasil

| Epoch | Train acc | Train loss | Val acc | Val loss |
|---|---|---|---|---|
| 1 | 0.5250 | 0.449889 | 0.5000 | 0.328951 |
| 2 | 0.9500 | 0.037452 | 0.5000 | 0.247289 |
| 3 | 0.9750 | 0.024372 | 0.5000 | 0.175892 |
| 4 | 0.9750 | 0.017357 | 0.8500 | 0.119381 |
| 5 | 0.9875 | 0.012740 | 1.0000 | 0.081581 |

## Cara menjalankan

```bash
git clone <url-repositori-ini>
cd <nama-folder>
pip install numpy pandas matplotlib jupyter
jupyter notebook SLP.ipynb
```

Jalankan seluruh sel dari atas ke bawah. Grafik akan tersimpan ulang ke folder `grafik/`.
Notebook juga dapat dibuka langsung di VS Code atau Google Colab.
