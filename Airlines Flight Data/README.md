# Airlines Flight Data ✈️

Repository ini berisi kumpulan data yang digunakan untuk melakukan Exploratory Data Analyst (EDA) penerbangan maskapai. Kumpulan data ini menyediakan informasi detail tentang maskapai, rute, jadwal, dan harga tiket. Kumpulan data ini cocok untuk analisis, visualisasi, dan pemodelan prediktif.

---

## 📂 Dataset Features

Dataseet ini berisi beberapa fitur sebagai berikut:

1. **Airline**  
   Nama perusahaan dari maskapai.  
   *Type:* Categorical (6 unique airlines)

2. **Flight**  
   Nomor Penerbangan dari Maskapai.  
   *Type:* Categorical

3. **Source City**  
   Kota dari tempat keberangkatan pesawat.  
   *Type:* Categorical (6 unique cities)

4. **Departure Time**  
   Waktu keberangkatan dari kota asal.  
   *Type:* Categorical (6 unique labels)

5. **Stops**  
   Jumlah pemberhentian (transit) antara kota asal ke kota tujuan.  
   *Type:* Categorical (3 values)

6. **Arrival Time**  
   Waktu kedatangan di kota tujuan.  
   *Type:* Categorical (6 unique labels)

7. **Destination City**  
   Kota tujuan pesawat dimana akan melakukan landing.  
   *Type:* Categorical (6 unique cities)

8. **Class**  
   Kursi class (Business atau Economy).  
   *Type:* Categorical (2 values)

9. **Duration**  
   Waktu perjalanan yang ditempuh dari kota asal ke kota tujuan.  
   *Type:* Continuous

10. **Days Left**  
    Pembelian tiket dari hari tersisa sebelum keberangkatan (trip date − booking date).  
    *Type:* Derived numerical feature

11. **Price**  
    Harga tiket dari penerbangan tertentu.  
    *Type:* Target variable (continuous)

---
## 📊 Visualisasi
### 1. Frekuensi Jumlah Penerbangan
![Frekuensi Penerbangan](Assets/Frekuensi%20Maskapai.png)<br>
Grafik di atas menunjukkan frekuensi penerbangan dari berbagai maskapai yang ada di datasheet ini, dari grafik ini dapat diliat kalo jumlah penerbangan terbanyak adalah maskapai Vistara sedangkan jumlah penerbangan tersedikit adalah maskapai Spicejet.
### 2. Frekuensi Jumlah Waktu Kedatangan dan Waktu Keberangkatan
![Frekuensi waktu kedatangan dan waktu keberangkatan](Assets/Frekuensi%20Departure%20dan%20Arrival%20Time.png)<br>
Gambar di atas menunjukkan dua grafik yang berbeda, sebelah kiri menunjukkan frekuensi jumlah keberangkatan dari sebuah penerbangan dan sebelah kanan menunjukkan frekuensi jumlah kedatangan dari sebuah penerbangan. Pada grafik tersebut didapatkan bahwa pada waktu keberangkatan terbanyak terjadi di Pagi hari atau **MORNING** dan waktu keberangkatan tersedikit adalah pada waktu Tengah malam. Untuk grafik waktu kedatangan terbanyak terjadi di malam hari sedangkan waktu kedatangan tersedikit terjadi di tengah malam.
### 3. Frekuensi Jumlah Kota Tujuan dan Kota Asal dari Sebuah Penerbangan
![Frekuensi Jumlah Kota Tujuan dan Kota Asal dari Sebuah Penerbangan](Assets/Frekuensi%20Penerbangan%20dari%20kota%20asal%20dan%20tujuan.png)<br>
Gambar di atas menunjukkan dua grafik yang berbeda, sebelah kiri menunjukkan penerbangan dengan kota tujuan terbanyak dan grafik sebelah kanan menunjukkan penerbangan dengan kota asal terbanyak dari sebuah penerbangan. Pada grafik tersebut didapatkan bahwa kota tujuan dengan jumlah penerbangan terbanyak adalah Mumbai dan kota tujuan dengan jumlah penerbangan tersedikit adalah Chennai. Untuk gambar grafik sebelah kanan, kota asal terbanyak dari berbagai penerbangan adalah Delhi sedangkan kota asal tersedikit dari penerbangan adalah Chennai.

### 4. Grafik Harga Tiket Maskapai
![Harga Tiket Maskapai](Assets/Rata-rata%20Harga%20tiket%20dari%20berbagai%20maskapai.png)<br>
Gambar di atas menunjukkan harga tiket berbagai maskapai. Harga tiket termahal dari ekonomi dan bisnis adalah maskapai Vistara diikuti dengan maskapai Air_India, sedangkan harga tiket termurah adalah maskapai AirAsia.

## 💡 Insight

- **Harga tiket termurah adalah dari Chennai ke Hyderabad dengan harga 1105.00** 
- **Harga tiket termahal adalah maskapai Vistara Airlines dari Kolkata ke Delhi dengan harga 123071.00**
- **Harga rata-rata tiket adalah 20889.66**
- **Penerbangan terbanyak dengan waktu keberangkatan adalah di pagi hari**
- **Penerbangan terbanyak tiba pada malam hari**
- **Penerbangan dengan kota tujuan terbanyak adalah Mumbai**
- **Penerbangan dengan kota asal terbanyak adalah Delhi**
- **Maskapai penerbangan Vistara adalah maskapai penerbangan dengan harga tiket kelas ekonomi dan bisnis rata-rata tertinggi**
- **Berdasarkan waktu keberangkatan, harga tiket tertinggi ditemukan pada malam hari**
- **Berdasarkan waktu kedatangan, harga tiket tertinggi ditemukan pada malam hari**
- **Berdasarkan kota asal, harga tiket rata-rata tertinggi ditemukan di Kota Chennai**
- **Berdasarkan kota tujuan, harga tiket rata-rata tertinggi ditemukan di Kota Kolkata**
- **Harga tiket rata-rata tertinggi saat pembelian ditemukan 2 hari sebelum keberangkatan dengan harga 30211** 


---

## 🚀 Usage

- Exploratory Data Analysis (EDA)  
- Visualisasi data maskapai penerbangan, rute, dan harga   

---

## 📌 Notes
- Dataset telah dibersihkan dan diproses terlebih dahulu.  
- Cocok untuk tugas pembelajaran mesin seperti regresi dan klasifikasi.  
