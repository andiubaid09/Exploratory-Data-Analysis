# Exploratory Data Analysis (EDA) - Network Flow Dataset

## 📌 Overview
Repositori ini berisi Analisis Data Eksplorasi (EDA) pada kumpulan data aliran jaringan yang terdiri dari **lalu ​​lintas normal (label = 0)** dan **lalu ​​lintas serangan (label = 1)**. Tujuan utama analisis ini adalah untuk memahami perilaku lalu lintas, mengidentifikasi anomali, dan mengeksplorasi pola yang membedakan aliran normal dan berbahaya.

---

## 📂 Dataset
Dataset ini mencakup fitur-fitur sebagai berikut:
- **Bandwidth metrics**: `rx_kbps`, `tx_kbps`, `tot_kbps`
- **Flow characteristics**: `pktrate`, `pktsperflow`, `bytesperflow`, `dur`
- **Network attributes**: `src`, `dst`, `port_no`
- **Label**:  
  - `0` → Normal traffic  
  - `1` → Attack traffic  

---

## 🔎 Analysis Performed
- **Data Cleaning**  
  - Menangani missing values    
- **Statistik Deskriptif**  
  - Distribusi Penggunaan Bandwidth  
  - Median, min, max, deteksi outlier
  - Distribusi label  
- **Traffic Behavior**  
  - Perbandingan dari Normal vs Attack pada kolom `pktrate`, `byteperflow`, `pktperflow`, `Protocol`, `port_no`, `dur`,`src`  
  - Visualisasi dari sumber serangan (IP-based)
  - Visualisasi dari sumber request Normal  
- **Visualisasi**  
  - Histogram dan boxplot fitur traffic  
  - Diagram lingkaran distribusi label  
  - Plot batang untuk penggunaan pktrate, byteperflow, pktperflow berdasarkan label  

---

## 💡 Visualisasi 
 ### 1. Frekuensi Jumlah Kemunculan src 
 ![Jumlah kemunculan src](Assets/Jumlah%20Frekuensi%20src%20request%20terhadap%20IP%20Sender.png)<br>
 Gambar di atas menunjukkan visualisasi dari frekuensi jumlah kemunculan IP Sender Request pada kolom "src". Ditemukan bahwa, IP Sender Request terbanyak dilakukan dengan alamat IP 10.0.0.3 lalu diikuti dengan alamat IP 10.0.0.7. Sedangkan jumlah yang paling sedikit kemunculan IP Sender Request adalah dengan alamat IP 10.0.0.17.
 ### 2. Frekuensi Serangan Berdasarkan src IP Request Sender
 ![Serangan Berdasarkan src](Assets/Jumlah%20serangan%20terhadap%20IP%20Sender%20Request.png)<br>
 Gambar di atas menunjukkan visualisasi dari frekuensi serangan berlabel 1 terhadap IP Sender Request. Ditemukan bahwa, IP yang mengirim serangan terbanyak adalah 10.0.0.10, lalu diikuti dengan alamat IP 10.0.0.3. Sedangkan IP yang mengirim serangan tersedikit adalah 10.0.0.17. 
 ### 3. Frekuensi Jumlah Request Normal Berdasarkan src IP Request Sender
 ![Request Normal Berdasarkan src](Assets/Jumlah%20Normal%20Request%20terhadap%20IP%20Sender.png)<br>
 Gambar di atas menunjukkan visualisasi grafik dari frekuensi request normal yang berlabel 0 terhadap IP Sender Request. Ditemukan bahwa IP yang mengirim request normal terbanyak dilakukan oleh dengan alamat IP 10.0.0.7, lalu diikuti dengan alamat IP 10.0.0.2. Sedangkan request normal tersedikit melakukan request normal adalah dengan alamat IP 10.0.0.20.
### 4. 



## 📊 Key Insights
- Negative values in flow metrics are strongly associated with **attack traffic**.  
- **Normal traffic** shows relatively stable bandwidth usage.  
- **Attack traffic** is more bursty, with higher packet rates and unusual outliers.  
- Certain **source IP addresses** dominate the attack traffic.  

---

## ⚙️ Tools Used
- **Python**  
- **Pandas** (data handling)  
- **Matplotlib & Seaborn** (visualization)  
- **Jupyter Notebook / VSCode** (analysis environment)  

---

## 🚀 Next Steps
- Feature engineering for ML model training.  
- Build classification models to detect DDoS attacks.   

---