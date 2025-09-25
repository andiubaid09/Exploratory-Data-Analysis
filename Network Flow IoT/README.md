# Exploratory Data Analysis (EDA) - Network Flow Dataset

## 📌 Overview
This repository contains Exploratory Data Analysis (EDA) on a network flow dataset consisting of **normal traffic (label = 0)** and **attack traffic (label = 1)**.  
The main goal of this analysis is to understand traffic behavior, identify anomalies, and explore patterns that differentiate normal and malicious flows.

---

## 📂 Dataset
The dataset includes features such as:
- **Bandwidth metrics**: `rx_kbps`, `tx_kbps`, `tot_kbps`
- **Flow characteristics**: `pktrate`, `pktsperflow`, `bytesperflow`, `dur`
- **Network attributes**: `src`, `dst`, `port_no`
- **Label**:  
  - `0` → Normal traffic  
  - `1` → Attack traffic  

---

## 🔎 Analysis Performed
- **Data Cleaning**  
  - Handling missing values  
  - Removing invalid / negative values (e.g., negative packet rate)  
- **Descriptive Statistics**  
  - Distribution of bandwidth usage  
  - Median, min, max, outlier detection  
- **Traffic Behavior**  
  - Comparison of normal vs attack in `pktrate`, `byteperflow`, `pktperflow`, `Protocol`, `port_no`, `dur`,`src`  
  - Visualization of attack sources (IP-based)  
- **Visualizations**  
  - Histograms and boxplots of traffic features  
  - Pie chart of label distribution  
  - Bar plots for port usage by label  

---

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
- Deploy lightweight detection model to IoT devices (e.g., Raspberry Pi, ESP32).  

---

## 📧 Contact
For questions or collaboration, feel free to reach out.  
