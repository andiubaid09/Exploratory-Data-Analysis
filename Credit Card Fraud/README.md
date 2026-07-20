# 💳 Credit Card Fraud Detection - Exploratory Data Analysis (EDA)

## 📌 Project Overview

Proyek ini berfokus pada **Exploratory Data Analysis (EDA)** terhadap dataset transaksi kartu kredit untuk memahami karakteristik transaksi normal dan transaksi fraud. Analisis dilakukan untuk menemukan pola, hubungan antar fitur, serta memperoleh insight yang dapat digunakan sebagai dasar dalam membangun model Machine Learning untuk mendeteksi transaksi fraud.

---

## 🎯 Objectives

Tujuan dari proyek ini adalah:

- Memahami struktur dan karakteristik dataset.
- Mengidentifikasi distribusi transaksi fraud dan non-fraud.
- Menganalisis hubungan setiap fitur terhadap label fraud.
- Menemukan pola transaksi yang berpotensi mengindikasikan aktivitas fraud.
- Mengidentifikasi fitur-fitur yang memiliki potensi tinggi sebagai prediktor pada model Machine Learning.

---

## 📂 Dataset Features

Dataset terdiri dari beberapa fitur berikut.

| Feature | Description |
|----------|-------------|
| transaction_id | Unique transaction identifier |
| amount | Transaction amount |
| transaction_hour | Transaction hour (0–23) |
| merchant_category | Merchant category |
| foreign_transaction | Indicates whether the transaction is international |
| location_mismatch | Transaction location differs from cardholder location |
| device_trust_score | Device trust score |
| velocity_last_24h | Number of transactions within the last 24 hours |
| cardholder_age | Cardholder age |
| is_fraud | Target variable |

---

# 📊 Exploratory Data Analysis

## 1. Fraud Distribution

![Fraud Distribution](Assets/Distribusi%20Fraud.png)

### Insight

- Total transaksi normal : **9849**
- Total transaksi fraud : **151**
- Fraud hanya sebesar **1.53%** dari keseluruhan transaksi.
- Dataset memiliki **class imbalance**, sehingga perlu dipertimbangkan teknik penanganan imbalance pada tahap Machine Learning.

---

## 2. Numerical Feature Distribution

![Numerical Distribution](Assets/Distribusi%20Kolom(Fitur)%20Numerik.png)

### Insight

- Fitur numerik yang menunjukkan karakteristik **skewed distribution right-skewed** yakni amount.
- Fitur amount mengindikasikan bahwa sebagian besar transaksi bernilai kecil dengan sedikit transaksi bernilai sangat besar.
- Distribusi ini memberikan indikasi perlunya preprocessing sebelum modeling.

---

## 3. Outlier Amount

![Outlier](Assets/DIstribusi%20of%20Outlier%20semua%20fitur.png)

### Insight

- Fitur amount ini menunjukkan distribusi yang bersifat **right-skewed** dengan jumlah outlier yang cukup banyak pada nilai transaksi tinggi.
- Mayoritas transaksi memiliki nominal relatif kecil, sedangkan hanya sebagian kecil transaksi bernilai sangat besar.
- Outlier pada fitur ini tidak langsung dihapus karena dapat merepresentasikan transaksi bernilai tinggi yang berpotensi berkaitan dengan aktivitas fraud.

---

# 📈 Feature Analysis

## Amount vs Fraud

![Amount](Assets/Amount%20vs%20Fraud.png)

### Insight

- Median transaksi fraud sebesar **160**
- Median transaksi normal sebesar **170**

---

## Cardholder Age vs Fraud

![Age](Assets/cardholder_age%20by%20fraud.png)

### Insight

- Rentang usia transaksi fraud berada pada **30-60**
- Tidak terdapat perbedaan rentang usia cardholder.

---

## Device Trust Score vs Fraud

![Trust Score](Assets/device_trust_score%20by%20fraud.png)

### Insight

- Device Trust Score pada transaksi fraud cenderung memiliki rentang**30-40** poin
- Device Trust Score pada transaksi fraud bahkan memiliki nilai poin tinggi seperti pada angka 60-100.
- Hal ini menunjukkan bahwa perangkat dengan tingkat kepercayaan rendah bahkan tinggi memiliki potensi risiko fraud yang lebih tinggi.

---

## Velocity Last 24 Hours vs Fraud

![Velocity](Assets/velocity_last_24h%20by%20fraud.png)

### Insight

- Transaksi fraud terjadi pada kartu yang memiliki aktivitas transaksi lebih banyak dalam 24 jam terakhir dibandingkan transaksi normal.
- Sebagian besar transaksi fraud memiliki nilai velocity yang lebih tinggi daripada transaksi normal
- Nilai velocity pada transaksi fraud lebih bervariasi.
- Nilai velocity yang tinggi pada transaksi fraud bukan hanya disebabkan oleh beberapa transaksi ekstrem, tetapi merupakan pola yang muncul pada banyak transaksi fraud.

---

# 🌍 Categorical Feature Analysis

## Foreign Transaction vs Fraud

![Foreign](Assets/Foreign_transaction%20vs%20Fraud.png)

### Insight

- Fraud lebih banyak ditemukan pada sebagian besar transaksi **luar negeri (foreign)**
- Fraud Rate transaksi domestic (dalam negeri) cukup tinggi dibanding di luar negeri.

---

## Location Mismatch vs Fraud

![Location](Assets/Location_mismatch%20vs%20Fraud.png)

### Insight

- Fraud lebih banyak ditemukan pada location mismatch dibanding yang no mismatch
- Sebagian besar transaksi normal tidak location mismatch, hanya sebagian kecil yang mismatch

---

## Merchant Category vs Fraud

![Merchant](Assets/Merchant%20Category%20vs%20Fraud.png)

### Insight

- Merchant dengan jumlah fraud terbanyak adalah **Grocery**
- Namun jumlah transaksi tidak selalu menunjukkan tingkat risiko fraud.

---

# 📊 Fraud Rate Analysis

## Fraud Rate by Merchant Category

![Merchant Fraud Rate](Assets/Fraud%20Rate%20by%20Merchant%20Category.png)

### Insight

- Merchant dengan Fraud Rate tertinggi adalah **Grocery**
- Merchant dengan Fraud Rate terendah adalah **Clothing**

---

## Fraud Rate by Foreign Transaction

![Foreign Rate](Assets/Fraud%20Rate%20by%20Foreign%20Transaction.png)

### Insight

- Fraud Rate transaksi luar negeri mencapai **90%**
- Fraud Rate transaksi domestik sebesar **10%**

---

## Fraud Rate by Location Mismatch

![Location Rate](Assets/Fraud%20Rate%20by%20Location%20Mismatch.png)

### Insight

- Fraud Rate meningkat ketika terjadi ketidaksesuaian lokasi transaksi.

---

## Fraud Rate by Transaction Hour

![Hour Rate](Assets/Fraud%20Rate%20by%20transaction_hour.png)

### Insight

- Aktivitas fraud paling tinggi terjadi pada pukul **00.00**
- Aktivitas fraud paling rendah terjadi pada pukul **22.00**

---

## Fraud vs Normal Transaction Hour

![Hour Comparison](Assets/Fraud%20vs%20Normal%20Transaction%20Hour.png)

### Insight

- Pola transaksi fraud berbeda dibanding transaksi normal tiap jam

---

## Fraud Rate by Foreign Transaction & Merchant Category

![Foreign Merchant](Assets/Fraud%20Rate%20by%20Foreign%20Transaction%20dan%20Merchant%20Category.png)

### Insight

- Kombinasi transaksi luar negeri dan merchant **Grocery** memiliki Fraud Rate tertinggi.

---

## Fraud Rate by Transaction Hour & Foreign Transaction

![Hour Foreign](Assets/Fraud%20Rate%20by%20Transaction%20Hour%20dan%20Foreign%20Transaction.png)

### Insight

- Kombinasi transaksi luar negeri pada pukul **02.00** memiliki Fraud Rate sebesar **41%**
- Kombinasi fitur ini berpotensi menjadi feature engineering yang baik.

---

# 🔗 Correlation Analysis

## Correlation Matrix

![Correlation](Assets/Matriks%20Korelasi%20Semua%20Antar%20Fitur.png)

### Insight

- Korelasi tertinggi terdapat antara fitur **foreign_transaction**, **velocity_last_24h** dan **location_mismatch**
- Tidak ditemukan multikolinearitas yang sangat tinggi antar fitur.

---

# 🤖 Feature Importance

## Top Feature Importance

![Feature Importance](Assets/Top%20Feature%20Importance%20Potensial%20Digunakan.png)

### Insight

Fitur yang memiliki kontribusi terbesar terhadap prediksi fraud menggunakan RF adalah:

1. **device_trust_score**
2. **transaction_hour**
3. **foreign_transaction**
4. **velocity_last_24h**
5. **location_mismatch**

Temuan ini menunjukkan bahwa fitur-fitur tersebut berpotensi menjadi prediktor utama dalam pembangunan model Machine Learning.

---

# 📌 EDA Summary

Berdasarkan hasil Exploratory Data Analysis diperoleh beberapa temuan penting:

- Dataset memiliki class imbalance dengan fraud sebesar **99%**.
- Device Trust Score pada transaksi fraud cenderung memiliki poin tingkat kepercayaan**rendah**
- Fraud lebih sering terjadi pada transaksi **luar negeri (foreign)**
- Location Mismatch meningkatkan peluang terjadinya fraud.
- Aktivitas fraud meningkat pada jam **00 hingga 04 am**
- Kombinasi **Foreign Transaction** dan **Transaction Hour** menunjukkan Fraud Rate tertinggi.
- Merchant Category memiliki tingkat risiko fraud yang berbeda-beda.
- Feature Importance menunjukkan bahwa fitur **device_trust_score** merupakan fitur paling berpengaruh.

---

# 🚀 Next Step

Tahapan selanjutnya yang dapat dilakukan adalah:

- Data Preprocessing
- Feature Engineering
- Feature Selection
- Handling Class Imbalance (SMOTE / Class Weight)
- Model Building
    - Logistic Regression
    - Decision Tree
    - Random Forest
    - XGBoost
- Model Evaluation

---

## 🛠️ Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

---

## 👨‍💻 Author

**Muhammad Andi Ubaidillah**
