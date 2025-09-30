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
## V
## 📊 Insight

- **Most Cheapest tickets price is Airlines from Chennai to Hyderabad**      =    1105.00 
- **Most expensive tickets price is Vistara Airlines Kolkata to Delhi**      =  123071.00
- **Average ticket price**                                                   =   20889.66
- **Most flights with departure times are at Morning**
- **Most flight with arrival times are at Night**
- **The flight with the most destination cities is Mumbai**
- **The flight with the most source cities is Delhi**
- **Vistara airlines is the airline with the highest average economy and business class ticket prices**
- **Based on departure time the highest ticket prices are found at night**
- **Based on arrival time the highest ticket prices are found at evening**
- **Based on source city the highest average ticket price are found in Chennai City**
- **Based on destination city the highest average ticket price are found in Kolkata City**
- **The highest average ticket price when purchasing was found 2 days before departure at a price 30211** 


---

## 🚀 Usage

- Exploratory Data Analysis (EDA)  
- Data visualization of airlines, routes, and pricing    

---

## 📌 Notes
- Dataset has been cleaned and preprocessed.  
- Suitable for machine learning tasks such as regression and classification.  
