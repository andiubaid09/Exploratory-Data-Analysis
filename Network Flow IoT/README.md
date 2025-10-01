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
- **Descriptive Statistics**  
  - Distribution of bandwidth usage  
  - Median, min, max, outlier detection  
- **Traffic Behavior**  
  - Comparison of normal vs attack in `pktrate`, `byteperflow`, `pktperflow`, `Protocol`, `port_no`, `dur`,`src`  
  - Visualization of attack sources (IP-based)  
- **Visualizations**  
  - Histograms and boxplots of traffic features  
  - Pie chart of label distribution  
  - Bar plots for port_no usage by label  

---
## 📊 Visualisasi 
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