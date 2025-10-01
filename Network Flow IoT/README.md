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

## 📊Visualisasi 
### 1. Frekuensi Distribusi Data Jumlah Kemunculan src 
![Jumlah kemunculan src](Assets/Jumlah%20Frekuensi%20src%20request%20terhadap%20IP%20Sender.png)<br>
Gambar di atas menunjukkan visualisasi dari frekuensi jumlah kemunculan IP Sender Request pada kolom "src". Ditemukan bahwa, IP Sender Request terbanyak dilakukan dengan alamat IP 10.0.0.3 lalu diikuti dengan alamat IP 10.0.0.7. Sedangkan jumlah yang paling sedikit kemunculan IP Sender Request adalah dengan alamat IP 10.0.0.17.
### 2. Frekuensi Distribusi Data Jumlah Serangan Berdasarkan src IP Request Sender
![Serangan Berdasarkan src](Assets/Jumlah%20serangan%20terhadap%20IP%20Sender%20Request.png)<br>
Gambar di atas menunjukkan visualisasi dari frekuensi serangan berlabel 1 terhadap IP Sender Request. Ditemukan bahwa, IP yang mengirim serangan terbanyak adalah 10.0.0.10, lalu diikuti dengan alamat IP 10.0.0.3. Sedangkan IP yang mengirim serangan tersedikit adalah 10.0.0.17. 
### 3. Frekuensi Distribusi Data Jumlah Request Normal Berdasarkan src IP Request Sender
![Request Normal Berdasarkan src](Assets/Jumlah%20Normal%20Request%20terhadap%20IP%20Sender.png)<br>
Gambar di atas menunjukkan visualisasi grafik dari frekuensi request normal yang berlabel 0 terhadap IP Sender Request. Ditemukan bahwa IP yang mengirim request normal terbanyak dilakukan oleh dengan alamat IP 10.0.0.7, lalu diikuti dengan alamat IP 10.0.0.2. Sedangkan request normal tersedikit melakukan request normal adalah dengan alamat IP 10.0.0.20.
### 4. Frekuensi Distribusi Data Kolom dur(Duration)
![Distribusi Data Kolom dur](Assets/Grafik%20dari%20kolom%20dur%20(duration).png)<br>
Gambar di atas menampilkan grafik histogram distribusi data dari kolom dur(Duration) yang telah diplot menggunakan skala logaritmik pada sumbu horizontal (Sumbu X). Terdapat lonjakan peak duration di atas 10^2. Secara umum duration ini terdistribusi secara flat (rata) dan sangat tinggi di rentang nilai yang luas. Temuan frekuensi batang (bar) histogram hampir seragam dan maksimal (sekitar 7000 - 8000) di sebagian besar rentang sumbu X. Grafik duration saat ini tidak memberikan insight yang akurat mengenai sebaran durasi networkflow, mungkin karena ukura skala yang diberikan pada sumbu y.
### 5. Distribusi Data Duration Terhadap Label
![Distribusi Data Duration Terhadap Label](Assets/Distribusi%20duration%20by%20label%20Normal%20dan%20Attack.png)<br>
Gambar di atas menampilkan grafik histogram distribusi data dari kolom dur(Duration) terhadap label 0 = Normal dan 1 = Attack. Warna biru mewakili label 0 dan warna orange mewakili label 1. Ditemukan bahwa Label 0 banyak terjadi di duration rentang 0-250 dan merupakan paling banyak dibanding label 1. Sedangkan label 1 terjadi pada duration dengan rentang 0-500 dan bisa dikatakan cukup banyak juga. Rentang di atas 500 label 1 cukup tersebar merata. Sedangkan label 0 hanya sampai di rentang di bawah 1250.
### 6. Frekuensi Distribusi Jumlah Data port_no
![Distribusi Data port_no](Assets/Frekuensi%20jumlah%20port_no.png)<br>
Gambar di atas menampilkan grafik visualisasi disribusi data dari kolom port_no. Pada kolom ini terdapat nilai unik berjumlah 5 yaitu 1,2,3,4 dan 5. Ditemukan bahwa, distribusi jumlah data terbanyak pada port_no 2 dengan jumlah hampir 30000, lalu diikuti dengan port_no 1 dengan jumlah hampi 30000 juga. Sedangkan jumlah distribusi data paling sedikit adalah port_no 5 dengan jumlah di bawah 5000.
### 7. Distribusi Data port_no Berdasarkan label
![Distribusi Data port_no Berdasarkan label](Assets/Distribusi%20port_no%20terhadap%20label.png)<br>
Gambar di atas menampilkan dua histogram yang berbeda, dimana grafik sebelah kiri merupakan distribusi data port_no terhadap label Normal dan sebelah kanan merupakan distribusi data port_no terhadap label Attack. Dimulai dari sebelah kanan, ditemukan bahwa Normal Traffic paling banyak ada pada port_no 1 sebanyak hampir 17500 diikuti dengan port_no 2 dengan perbedaan sangat tipis. Sedangkan Normal Traffic paling sedikit ada pada port_no 5 dengan jumlah di bawah 2500. Lalu, untuk grafik sebelah kanan, ditemukan bahwa Attack Traffic paling banyak dilakukan ada pada port_no 1 dengan jumlah di atas 10000 lalu diikuti port_no 2 dengan perbedaan sangat tipis. Sedangkan Attack Traffic paling sedikit ada pada port_no 0 di bawah rentang 2000.
### 8. Frekuensi Distribusi Jumlah Data Protocol
![Distribusi Data Protocol](Assets/Frekuensi%20jumlah%20total%20Protocol.png)<br>
Gambar di atas menampilkan grafik visualisasi jumlah distribusi data dari kolom Protocol. Pada kolom ini terdapat nama unik berjumlah 3 yaitu, ICMP, UDP, dan TCP. Ditemukan bahwa, distribusi jumlah data terbanyak pada Protocol ICMP dengan jumlah di sekitar 40000, kemudian Protocol UDP dengan jumlah di sekitar di antara 30000 - 35000. Yang paling sedikit adalah Protocol TCP dengan jumlah di sekitar rentang di antara 25000 - 30000.
### 9. Frekuensi Distribusi Jumlah Data Label
![Distribusi Data Label](Assets/Distribusi%20jumlah%20label%20attack%20dan%20normal.png)<br>
Gambar di atas menampilkan grafik visualisasi jumlah distribusi data dari kolom label. Pada kolom ini terdapat nomor unik berjumlah 2 yaitu 0 dan 1. Label 0 yang berarti Normal dan label 1 yang berarti Attack. Ditemukan bahwa, distribusi jumlah data terbanyak pada label 0 dengan jumlah di sekitar rentang 60000 lebih. Sedangkan distribusi jumlah data tersedikit pada label 1 dengan jumlah di sekitar rentang 40000. Ini dapat memberikan kesimpulan bahwa terjadi imbalanced data. Berikut adalah grafik pie chartnya: <br>
![Distribusi Data Label Pie Chart](Assets/Pie%20chart%20Distribusi%20label.png)<br>
### 10. 




## 💡 Key Insights
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