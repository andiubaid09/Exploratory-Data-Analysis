# 🎬 MovieLens Exploratory Data Analysis (EDA) Report

Dokumen ini menyajikan laporan analisis data eksploratori (*Exploratory Data Analysis*) mendalam pada dataset MovieLens. Analisis ini mencakup prapemrosesan data, profil statistik genre, evaluasi perilaku rating pengguna, serta panduan komprehensif cara membaca dan menginterpretasikan setiap visualisasi yang dihasilkan.

---

## 📌 Executive Summary

Analisis dilakukan pada dataset interaksi film dan pengguna MovieLens setelah melalui tahap pembersihan data (*data cleaning*) dan rekayasa fitur (*feature engineering*). 

**Temuan Utama:**
1. **Dominasi Genre Skenario:** Genre `Drama`, `Action`, dan `Comedy` mendominasi total interaksi rating dan jumlah produksi film secara masif.
2. **Kualitas Niche vs Aksesibilitas Massa:** Genre *niche* seperti `Film-Noir` (3.78), `Documentary` (3.65), dan `War` (3.63) mencatatkan rata-rata rating tertinggi, sedangkan genre massa populer seperti `Horror` (3.22) dan `Comedy` (3.38) mencatatkan rata-rata kepuasan penonton terendah.
3. **Positivity Bias Penonton:** Penonton cenderung memberikan penilaian positif, di mana mayoritas rating terkonsentrasi pada skor 4.0, 3.5, dan 3.0. Nilai angka bulat lebih disukai daripada nilai pecahan.
4. **Distribusi Keaktifan Ekstrem (Long-Tail):** Sebagian besar pengguna bersikap pasif (1–5 rating), sementara kelompok *power users* minoritas menyumbang hingga >1.100 rating per individu, memicu potensi bias pada model preferensi.

---

## 📊 Statistik & Analisis Genre Film

Tabel berikut menunjukkan statistik ringkasan total film, jumlah interaksi rating, dan rata-rata skor rating untuk seluruh 18 genre bersih:

| Genre | Total Film (`total_movies`) | Total Rating (`total_ratings`) | Rata-Rata Rating (`mean_ratings`) |
| :--- | :---: | :---: | :---: |
| **Drama** | 9,575 | 435,223 | 3.637073 |
| **Action** | 3,054 | 342,034 | 3.468412 |
| **Comedy** | 6,547 | 318,370 | 3.384328 |
| **Thriller** | 4,147 | 289,894 | 3.499857 |
| **Adventure** | 1,641 | 274,417 | 3.524505 |
| **Sci-Fi** | 1,623 | 201,519 | 3.483198 |
| **Crime** | 1,968 | 167,072 | 3.619568 |
| **Romance** | 2,749 | 153,059 | 3.502042 |
| **Fantasy** | 1,294 | 137,944 | 3.526504 |
| **Mystery** | 1,168 | 137,944 | 3.526504 |
| **Animation** | 1,430 | 90,036 | 3.602903 |
| **Children** | 1,312 | 83,832 | 3.468723 |
| **Horror** | 2,529 | 76,464 | 3.217612 |
| **War** | 547 | 39,617 | 3.632923 |
| **Documentary** | 2,635 | 21,480 | 3.653399 |
| **Musical** | 258 | 18,626 | 3.443735 |
| **Western** | 147 | 10,315 | 3.644450 |
| **Film-Noir** | 18 | 4,966 | 3.779903 |

### 💡 Insight Akademis dari Data Genre:
* **Drama sebagai Tulang Punggung Industri:** Dengan 9.575 judul film dan >435 ribu rating, Drama menjadi fondasi utama interaksi pengguna dan pasar film.
* **Paradoks Genre Populer:** `Action` dan `Comedy` memiliki pangsa volume besar, namun rata-rata kepuasan penontonnya berada di bawah rentang rata-rata global (<3.50).
* **Efek Khusus Genre Niche (Film-Noir & Documentary):** Jumlah filmnya relatif sedikit, namun basis penontonnya sangat terdedikasi sehingga menghasilkan rata-rata skor kepuasan tertinggi (3.65 - 3.78).

---

## 📈 Cara Membaca & Interpretasi Visualisasi

### 1. Distribusi Frekuensi Nilai Rating Penonton
![Distribusi Frekuensi Nilai Rating Penonton](/MoviesLens/Assets/Distribusi%20Frekuensi%20Nilai%20Rating%20Penonton.png)

* **Cara Membaca Grafik:**
  * **Sumbu X:** Menampilkan nilai pecahan rating dari $0.5$ hingga $5.0$.
  * **Sumbu Y:** Menunjukkan total volume rating yang diberikan pengguna (dalam ribuan / $K$).
  * **Tinggi Batang:** Mewakili frekuensi penggunaan skor rating tersebut oleh penonton.
* **Analisis & Insight:**
  * **Puncak Tertinggi pada Skor 4.0:** Batang skor $4.0$ adalah yang paling tinggi ($~240K$ rating), diikuti oleh skor $3.5$ dan $3.0$. Ini membuktikan adanya ***Positivity Bias***, di mana pengguna lebih terdorong untuk memberi ulasan setelah menonton film yang mereka nikmati.
  * **Bias Angka Bulat (*Whole-Number Preference*):** Terlihat pola gergaji di mana batang angka bulat ($3.0$, $4.0$, $5.0$) secara konsisten lebih tinggi dibanding angka setengah di sebelahnya ($2.5$, $3.5$, $4.5$).
  * **Rating Rendah Sangat Langka:** Skor $0.5$, $1.0$, dan $1.5$ masing-masing hanya mencatatkan $<25K$ interaksi. Penonton jarang menyelesaikan atau memberikan rating pada film yang menurut mereka buruk.

---

### 2. Top 10 Genre Film dengan Interaksi Rating Terbanyak
![Top 10 Genre Film dengan Interaksi Rating Terbanyak](/MoviesLens/Assets/Top%2010%20Genre%20Film%20dengan%20Intreaksi%20Rating%20Terbanyak.png)

* **Cara Membaca Grafik:**
  * **Sumbu Y:** Menampilkan 10 genre teratas yang sudah dibersihkan dari anomali.
  * **Sumbu X:** Menunjukkan total akumulasi volume rating (dalam ribuan / $K$).
  * **Panjang Batang Horizontal:** Mengindikasikan tingkat popularitas dan jangkauan pasar genre tersebut.
* **Analisis & Insight:**
  * **Trio Dominan:** `Drama` ($~435K$), `Action` ($~342K$), dan `Comedy` ($~318K$) membentuk kelompok genre dengan tingkat interaksi terbesar.
  * **Genre Kategori Tengah:** `Thriller` ($~290K$) dan `Adventure` ($~274K$) menjadi jembatan antara narasi aksi dan drama komersial.
  * **Mystery di Urutan Ke-10:** Meskipun berada di posisi ke-10 ($~91.5K$), genre `Mystery` tetap memiliki retensi penonton yang kuat dengan rata-rata skor tinggi ($3.64$).

---

### 3. Tren Jumlah Judul Film yang Dirilis per Tahun (2000 - 2024)
![Tren Jumlah Judul Film yang Dirilis per Tahun (2000 - 2024)](/MoviesLens/Assets/Tren%20Jumlah%20Judul%20Film%20yang%20Dirilis%20per%20Tahun%20(2000%20-%202023).png)

* **Cara Membaca Grafik:**
  * **Sumbu X:** Garis waktu tahun rilis film dari tahun 2000 hingga 2023.
  * **Sumbu Y:** Jumlah judul film unik yang diproduksi pada tahun tersebut.
  * **Arah Garis Merah:** Mengindikasikan laju pertumbuhan atau penurunan volume produksi film harian/tahunan.
* **Analisis & Insight:**
  * **Fase Pertumbuhan (2000–2015):** Produksi film tumbuh secara konsisten dari $~630$ judul pada tahun 2000 hingga mencapai puncaknya di atas $1.350$ judul film pada tahun 2015.
  * **Era Puncak (2015–2017):** Industri berada pada volume produksi tertinggi ($>1.300$ film/tahun), terdorong oleh demokratisasi peralatan produksi digital dan platform independen.
  * **Penurunan Tajam Pasca-2018 & Efek Pandemi:** Terjadi penurunan drastis mulai tahun 2019 dan berlanjut hingga 2023. Penurunan pada 2020–2022 sangat mencerminkan hambatan produksi global akibat pandemi COVID-19 serta perubahan peta distribusi bioskop ke platform *streaming*.

---

### 4. Hubungan Popularitas Film (Jumlah Rating) vs Rerata Skor Rating
![Hubungan Popularitas Film (Jumlah Rating) vs Rerata Skor Rating](/MoviesLens/Assets/Hubungan%20Popularitas%20Film%20(Jumlah%20Rating)%20vs%20Rerata%20Skor%20Rating.png)

* **Cara Membaca Grafik:**
  * **Sumbu X:** Jumlah total rating yang diterima oleh sebuah film (Popularitas/Tingkat Visibilitas).
  * **Sumbu Y:** Rata-rata skor rating film tersebut ($1.5 - 4.5$).
  * **Setiap Titik Ungu:** Mewakili satu judul film unik.
* **Analisis & Insight:**
  * **Pola Corong Terbuka (*Funnel Pattern*):** Pada film dengan popularitas rendah ($<1.000$ rating), sebaran skor rating sangat luas ($1.5$ hingga $4.5$).
  * **Efek Konvergensi Kualitas Blockbuster:** Semakin ke kanan (film semakin populer dengan $>3.000$ rating), variasi skor menyempit dan mengumpul pada angka tinggi ($3.6 - 4.2$).
  * **Kesimpulan:** Film yang sangat populer hampir selalu memiliki kualitas yang diakui publik secara luas (*high acclaim*). Film dengan kepuasan buruk tidak pernah mencapai tingkat popularitas tinggi di kanan grafik.

---

### 5. Distribusi Jumlah Rating per Pengguna (Skala Logaritmik)
![Distribusi Jumlah Rating per Pengguna (Skala Logaritmik)](/MoviesLens/Assets/Distribusi%20Jumlah%20Rating%20per%20Pengguna%20(Skala%20Logaritmik).png)

* **Cara Membaca Grafik:**
  * **Sumbu X:** Jumlah rating yang diberikan oleh satu pengguna dalam skala logaritmik ($10^0 = 1$, $10^1 = 10$, $10^2 = 100$, $10^3 = 1000$).
  * **Sumbu Y:** Frekuensi/jumlah pengguna yang berada pada tingkat keaktifan tersebut.
  * **Garis Kurva Toska (KDE):** Mengestimasikan kerapatan distribusi keaktifan.
* **Analisis & Insight:**
  * **Lonjakan pada Ambang Minimal:** Terjadi puncak tinggi pada angka $1$, $2$, dan $3$ rating ($>24.000$ pengguna hanya memberi 1 rating).
  * **Karakteristik *Power Law* / *Long-Tail*:** Distribusi miring ke kanan (*right-skewed*). Sebagian besar pengguna bersifat pasif (*casual viewers*).
  * **Tantangan Rekomendasi (*Cold-Start Problem*):** Karena mayoritas pengguna memiliki $<10$ rating, sistem rekomendasi berbasis *Collaborative Filtering* membutuhkan penanganan khusus agar rekomendasi tetap akurat untuk pengguna baru.

---

### 6. Top 10 Pengguna Paling Aktif Merating Film
![Top 10 Pengguna Paling Aktif Merating Film](/MoviesLens/Assets/User%20Paling%20Aktif%20Memberikan%20Rating.png)

* **Cara Membaca Grafik:**
  * **Sumbu Y:** ID Pengguna teratas (Format `User <ID>`).
  * **Sumbu X:** Jumlah total kontribusi rating yang telah diberikan oleh pengguna tersebut.
  * **Panjang Batang Ungu Tua:** Menunjukkan tingkat dominasi kontribusi *power user* tersebut di dalam dataset.
* **Analisis & Insight:**
  * **Outlier Keaktifan Ekstrem (`User 175325`):** Pengguna dengan ID `175325` berdiri jauh di atas pengguna lain dengan memberikan **lebih dari 1.150 rating**.
  * **Konsistensi Kontributor Utama:** Pengguna teraktif posisi 2 hingga 10 memiliki kontribusi yang relatif stabil di kisaran **300 hingga 450 rating**.
  * **Implikasi Model Rekomendasi:** Kelompok pengguna ini memberikan sinyal preferensi yang sangat kuat, namun seleranya dapat mendominasi pembentukan faktor laten pada model pemodelan matriks (*Matrix Factorization*). Pemberian bobot (*weighting/scaling*) perlu dipertimbangkan saat pelatihan model ML.

---

## 🛠️ Langkah Prapemrosesan Data yang Telah Dilakukan

1. **Pembersihan Kolom `title` & `year`:**
   * Ekstraksi tahun 4 digit menggunakan ekspresi reguler (Regex) `r'\((\d{4})\)'`.
   * Penanganan format artikel terbalik bahasa Inggris (misal: `"Amazing Spider-Man, The"` diubah menjadi `"The Amazing Spider-Man"`).
2. **Pembersihan Kolom `genres`:**
   * Menghapus anomali non-genre seperti `IMAX` dan penanda *missing value* `(no genres listed)`.
   * Memperbaiki kesalahan penggabungan teks (*concatenation error*) seperti `Comedystand-up comedy`.
3. **Pembersihan Kolom `tags`:**
   * Konversi ke *lowercase*, normalisasi ejaan, pembersihan karakter baris/simbol (`===`), serta penghapusan kata sampah sistem (`owned`, `dvd`, `watched`).
   * Mengeliminasi tag duplikat pada film yang sama.

---

## 🚀 Kesimpulan & Langkah Selanjutnya

Hasil eksplorasi ini memberikan landasan kuat untuk pengembangan tahap berikutnya:
* **Pengembangan Sistem Rekomendasi:** Menerapkan strategi pemisahan untuk *Power Users* dan penanganan *Cold-Start* bagi *Casual Users*.
* **Filter Kolaboratif & Konten:** Kombinasi fitur `genres` yang telah dibersihkan dengan pembobotan *TF-IDF* pada `tags` untuk membentuk *Content-Based Filtering* yang presisi.