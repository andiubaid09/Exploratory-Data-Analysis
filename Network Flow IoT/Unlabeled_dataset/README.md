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

---

## 📊Visualisasi 
### 1. Frekuensi Distribusi Jumlah Data Protocol
![Distribusi Data Protocol](Assets/Frekuensi%20kemunculan%20protocol.png)<br>
Gambar di atas menampilkan grafik visualisasi jumlah distribusi data dari kolom Protocol. Pada kolom ini terdapat nama unik berjumlah 3 yaitu, ICMP, UDP, dan TCP. Ditemukan bahwa, distribusi jumlah data terbanyak pada Protocol ICMP dengan jumlah di sekitar 5.000.000.
### 9. Frekuensi Distribusi Jumlah Data Label
![Distribusi Data Label](Assets/Distribusi%20jumlah%20label%20attack%20dan%20normal.png)<br>
Gambar di atas menampilkan grafik visualisasi jumlah distribusi data dari kolom label. Pada kolom ini terdapat nomor unik berjumlah 2 yaitu 0 dan 1. Label 0 yang berarti Normal dan label 1 yang berarti Attack. Ditemukan bahwa, distribusi jumlah data terbanyak pada label 0 dengan jumlah di sekitar rentang 60000 lebih. Sedangkan distribusi jumlah data tersedikit pada label 1 dengan jumlah di sekitar rentang 40000. Ini dapat memberikan kesimpulan bahwa terjadi imbalanced data. Berikut adalah grafik pie chartnya: <br>
![Distribusi Data Label Pie Chart](Assets/Pie%20chart%20Distribusi%20label.png)<br>
### 10. Distribusi Data pktrate Berdasarkan Label
![Distribusi Data pktrate Berdasarkan Label](Assets/Distribusi%20pktrate%20terhadap%20label.png)<br>
Gambar di atas menampilkan grafik boxplot distribusi data pktrate berdasarkan label. Pada label 0, terdapat nilai anomali (outlier) berjumlah 1 dimana nilainya negatif yaitu di bawah -4000. Sedangkan untuk label 1 terdapat juga nilai anomali (outlier) berjumlah 14 dimana nilainya sama juga yaitu negatif. Nilainya dimulai dari di bawah -1000 sampai -4000. Hal ini janggal mengingat pktrate tidak bisa bernilai negatif. Berikut visualisasi lain dalam bentuk histogram: <br>
![Histogram Distribusi Data pktrate Berdasarkan Label](Assets/Distribusi%20grafik%20pktrate%20terhadap%20label.png)
### 11. Distribusi Data byteperflow Berdasarkan Label
![Distribusi Data Byteperflow Berdasarkan Label](Assets/Distribusi%20byteperflow%20terhadap%20label.png)<br>
Gambar di atas menampilkan grafik boxplot distribusi data byteperflow berdasarkan label. Pada label 0, terdapat nilai anomali (outlier) berjumlah 1 dimana nilainnya negatif di rentang nilai antar -1.2 - (-1.4).Sedangkan untuk label 1 terdapat nilai anomali (outlier) berjumlah 6 dimana nilainya juga negatif. Nilainya dimulai di rentang antar -0.8 - (- 1.5). Berikut tampilan visualisasi lain dalam bentuk histogram: <br>
![Histogram Distribusi Data byteperflow](Assets/Distribusi%20grafik%20byteperflow%20terhadap%20label.png)<br>
### 12. Distribusi Data pktperflow Berdasarkan Label
![Distribusi Data pktperflow Berdasarkan Label](Assets/Distribusi%20pkteperflow%20terhadap%20label.png)<br>
Gambar di atas menampilkan grafik boxplot distribusi data pktperflow berdasrkan label. Pada label 0 terdapat nilai anomali (outlier) berjumlah 1 dimana nilainya negatif di rentang nilai di bawah -120000. Sedangkan label 1 terdapat nilai anomali (outlier) berjumlah banyak sama nilainya juga negatif. Nilainya dimulai di rentang antar di bawah - 40000 hingga di -120000. Berikut tampilan visualisasi lain dalam bentuk histogram: <br>
![Distribusi Data pktperflow Berdasarkan Label](Assets/Distribusi%20grafik%20pkteperflow%20terhadap%20label.png) 

## 💡 Key Insights
- Nilai negatif dalam metrik aliran sangat terkait dengan **lalu ​​lintas serangan**.  
- Lalu lintas normal menunjukkan penggunaan bandwidth yang relatif stabil.  
- Lalu lintas serangan lebih cepat, dengan tingkat paket yang lebih tinggi dan outlier yang tidak biasa.  
- **Alamat IP sumber** tertentu mendominasi lalu lintas serangan.  
- Distribusi Data Label 0 dan 1 terjadi Imbalanced data.
- Terdapat outlier di byteperflow, pktrate, pktperflow bernilai negatif yang sangat janggal.

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