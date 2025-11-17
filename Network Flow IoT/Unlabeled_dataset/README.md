# Exploratory Data Analysis (EDA) - Network Flow Dataset

## 📌 Overview
Repositori ini berisi Analisis Data Eksplorasi (EDA) pada kumpulan data aliran jaringan yang tidak terdapat label atau label = NaN. Tujuan utama analisis ini adalah untuk memahami perilaku lalu lintas, dan mengeksplorasi datasheet agar dapat memutuskan teknik preprocessing yang akan digunakan saat membuat model unsupervised learning. Datasheet ini merupakan bagian dari datasheet yang memiliki labeled yang sebelumnya telah dilakukan EDA dengan jumlah rows + 5 juta rows.

---

## 📂 Dataset
Dataset ini mencakup fitur-fitur sebagai berikut:
- **Bandwidth metrics**: `rx_kbps`, `tx_kbps`, `tot_kbps`
- **Flow characteristics**: `pktrate`, `pktsperflow`, `bytesperflow`, `dur`
- **Network attributes**: `src`, `dst`, `port_no`
- **Label**: NaN 

---

## 🔎 Analysis Performed   
- **Statistik Deskriptif**  
  - Distribusi Penggunaan Bandwidth  
  - Median, min, max, deteksi outlier  
- **Visualisasi**  
  - plot bar frekuensi kemunculan Protocol dengan jumlah TCP terbanyak yaitu 5 juta TCP 
- **Catatan**
  - Datasheet merupakan pemotongan dari data mentah yang memiliki 15 juta rows network flow IoT, dimana 104 ribu memiliki label dan 5 juta kami ambil untuk keperluan pengaplikasian unsupervised learning.
  - Datasheet memiliki karakteristik yang berbeda dengan labeled_dataset.csv, dimana memiliki port_no yang berjumlah ribuan. Tx_bytes, tx_kbps, dur_nsec bernilai nol. Kami mencurigai bahwa tidak ada aktivitas serangan DDoS pada datasheet, namun kami akan mencoba mendeteksi anomali traffic menggunakan model yang ada di unsupervised learning.
  - Kami tidak dapat memvisualisasikan semuanya seperti yang kami lakukan di labeled_dataset.csv, namun, anda bisa membukannya dan melihat hal-hal yyang banyak dari beberapa features.

---

## 📊Visualisasi 
### 1. Frekuensi Distribusi Jumlah Data Protocol
![Distribusi Data Protocol](Assets/Frekuensi%20kemunculan%20protocol.png)<br>
Gambar di atas menampilkan grafik visualisasi jumlah distribusi data dari kolom Protocol. Pada kolom ini terdapat nama unik berjumlah 3 yaitu, ICMP, UDP, dan TCP. Ditemukan bahwa, distribusi jumlah data terbanyak pada Protocol ICMP dengan jumlah di sekitar 5.000.000, ICMP berjumlah 32763 dan UDP berjumlah 19136.

---

## ⚙️ Tools Used
- **Python**  
- **Pandas** (data handling)  
- **Matplotlib & Seaborn** (visualization)  
- **Jupyter Notebook / VSCode** (analysis environment)  

---

## 🚀 Next Steps
- Build clustering model use K-Means.   

---