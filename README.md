# 🔮 Analisis Perbandingan Model Multivariate ARIMA dan Fuzzy Multi-Factor Time Series dalam Peramalan Harga Emas di Indonesia

## 📘 Deskripsi Proyek

Proyek ini bertujuan untuk **membangun dan membandingkan dua model peramalan deret waktu multivariat** — **Multivariate ARIMA (MARIMA)** dan **Fuzzy Multi-Factor Time Series (FMFTS)** — dalam memprediksi **harga emas di Indonesia** berdasarkan faktor-faktor makroekonomi utama:

* Inflasi
* Policy Rate (BI-Rate)
* Suku Bunga Riil
* Kurs USD/IDR
* Harga Minyak Dunia

Analisis dilakukan menggunakan data bulanan periode **Januari 2018 – Agustus 2025** dari sumber resmi seperti **Bank Indonesia** dan **Investing.com**.

---

## 🎯 Tujuan

1. Menganalisis hubungan antara harga emas dan faktor-faktor makroekonomi.
2. Membangun model **MARIMA** untuk menangkap dinamika linear antarvariabel ekonomi.
3. Membangun model **FMFTS** untuk menangkap hubungan **non-linear** dan **ketidakpastian** dalam data.
4. Membandingkan akurasi kedua model menggunakan metrik evaluasi **MAE, RMSE, dan MAPE**.

---

## 🧠 Metodologi

### 1. Data Preparation

* Periode: Jan 2018 – Aug 2025 (92 observasi)
* Frekuensi: Bulanan
* Transformasi: Logaritmik natural untuk variabel dengan skala besar (kurs, minyak, harga emas).

### 2. Model 1 — Multivariate ARIMA (MARIMA)

* Uji Stasioneritas (ADF Test)
* Uji Kointegrasi (Johansen Test)
* Penentuan Lag Optimal (AIC/BIC)
* Estimasi model VAR/VECM
* Evaluasi menggunakan **Impulse Response Function (IRF)** dan **Forecast Error Variance Decomposition (FEVD)**

### 3. Model 2 — Fuzzy Multi-Factor Time Series (FMFTS)

* Pembentukan himpunan fuzzy dan interval data
* Pembentukan aturan transisi fuzzy antar variabel
* Defuzzifikasi hasil prediksi
* Evaluasi menggunakan metrik kesalahan yang sama

---

## 📊 Hasil Analisis

### Statistik Deskriptif (2018–2025)

| Variabel           | Mean      | Std Dev | Korelasi dgn Harga Emas |
| ------------------ | --------- | ------- | ----------------------- |
| Inflasi            | 2.77%     | 1.08%   | -0.358                  |
| Policy Rate        | 4.96%     | 0.99%   | +0.266                  |
| Suku Bunga Riil    | 2.25%     | 1.26%   | +0.516                  |
| Kurs USD/IDR       | 14.903    | 833     | **+0.819**              |
| Harga Minyak Dunia | 1.013.174 | 272.410 | +0.259                  |
| Harga Emas         | 965.994   | 293.111 | —                       |

💡 **Insight utama:**
Harga emas menunjukkan tren naik signifikan dengan volatilitas tinggi, terutama saat pandemi (2020) dan periode inflasi global (2022–2023). Korelasi terkuat ditemukan antara **kurs USD/IDR dan harga emas**, menunjukkan peran emas sebagai **aset lindung terhadap depresiasi rupiah**.

📈 **Interpretasi:**

* **MARIMA** unggul dalam menangkap **hubungan jangka pendek dan efek kebijakan moneter**.
* **FMFTS** memberikan hasil **lebih fleksibel dan akurat pada pola non-linear**, terutama saat volatilitas tinggi.
* Kedua metode **memiliki keunggulan masing-masing** tergantung konteks prediksi:

  * Gunakan **MARIMA** untuk stabilitas dan interpretabilitas ekonomi.
  * Gunakan **FMFTS** untuk ketepatan prediksi dalam kondisi pasar dinamis.

---

## 📍 Kesimpulan

* Harga emas di Indonesia sangat dipengaruhi oleh **kurs USD/IDR** dan **suku bunga riil**.
* Model **Fuzzy Multi-Factor Time Series** cenderung memberikan akurasi lebih baik dalam periode fluktuasi tinggi.
* Pendekatan **MARIMA** tetap relevan untuk analisis struktural dan interpretasi hubungan antar variabel ekonomi.
* Kombinasi kedua pendekatan (**hybrid MARIMA–Fuzzy**) berpotensi menjadi solusi optimal untuk riset lanjutan.

---

## 🧩 Tools & Library

* Python (NumPy, pandas, statsmodels, scikit-fuzzy, matplotlib, seaborn)
* Jupyter Notebook / Google Colab
* Data source: [Bank Indonesia](https://www.bi.go.id/) · [Investing.com](https://www.investing.com/)
