# 🎬 TMDB Movie Dataset - Exploratory Data Analysis (EDA)

## 📌 Project Overview

Proyek ini berfokus pada **Exploratory Data Analysis (EDA)** terhadap dataset perfilman global TMDB (~44k records) untuk memahami karakteristik industri film, tren produksi, dinamika finansial, serta pola kualitas dan popularitas. Analisis dilakukan untuk menemukan pola, hubungan antar fitur, serta memperoleh *insight* yang mendalam sebagai landasan sebelum membangun sistem rekomendasi berbasis NLP (*metadata soup*).

---

## 🎯 Objectives

Tujuan dari proyek ini adalah:

- Memahami struktur, fitur, dan cakupan data industri perfilman global.
- Menganalisis tren pertumbuhan produksi film dari dekade ke dekade.
- Mengeksplorasi korelasi finansial antara anggaran (*budget*) dan pendapatan (*revenue*) film.
- Mengidentifikasi film-film paling menguntungkan (*top profit-generators*) dan anomali pasar (*outlier*).
- Menganalisis hubungan antara skor popularitas (*popularity*) dan kualitas rating penonton (*vote_average*).
- Memetakan dominasi rumah produksi (*production companies*) dan bahasa utama (*spoken languages*).

---

## 📂 Dataset Features

Dataset terdiri dari beberapa fitur utama berikut:

| Feature | Description |
|----------|-------------|
| adult     | Usia untuk Film |
| belongs_to_collection | Koleksi film franchise |
| budget | Anggaran pembuatan film (USD) |
| genres | Genre film (format *list*) |
| homepage | Tautan URL dari film tersebut |
| id    | Nomor Unik Dataset |
| imdb_id | Nomor Pengenal Unik bersumber dari IMDB |
| original_languages | Kode bahasa asli film pertama kali dirilis |
| original_title | Judul asli film dalam bahasa lokal tempat film dirilis |
| overview | Sinopsis / ringkasan cerita film |
| popularity | Skor popularitas film di platform TMDB |
| poster_path | String jalur direktori atau URL path menuju file gambar poster film |
| production_companies | Perusahaan rumah produksi (format *list*) |
| production_countries | Daftar negara tempat perusahaan produksi film berkendudukan |
| release_date | Berisi tanggal resmi penanyangan film perdana |
| revenue | Pendapatan kotor film (USD) |
| runtime | Durasi film |
| spoken_languages | Bahasa yang digunakan (format *list*) |
| status | Menunjukkan status distribusi dari film |
| tagline | Kalimat promosi yang sering muncul di poster film |
| title | Judul film |
| video | Berisi nilai boolean yang mengidikasikan apakah ada teaser atau video promosi komersial |
| vote_average | Rata-rata rating penonton (skala 0–10) |
| vote_count | Jumlah total penilai / *votes* |

---

# 📊 Exploratory Data Analysis

## 1. Tren Produksi Film dari Tahun ke Tahun

![Tren Produksi](Assets/Tren%20Jumlah%20Produksi%20Film%20dari%20Tahun%20ke%20Tahun.png)

### Insight & Cara Membaca Grafik
- Grafik garis (*line plot*) di atas menunjukkan jumlah produksi film setiap tahunnya dari dekade 1920 hingga 2020.
- **Cara Membaca:** Sumbu X merepresentasikan tahun rilis, sementara sumbu Y menunjukkan total volume film yang dirilis pada tahun tersebut. 
- Industri film menunjukkan pertumbuhan yang stabil dan landai hingga akhir abad ke-20, sebelum mengalami lonjakan eksponensial yang sangat tajam pada awal tahun 2000-an.
- Lonjakan ini merefleksikan era digitalisasi sinema, kemudahan teknologi *editing* komputer, serta masifnya ekspansi industri perfilman global.

---

## 2. Korelasi Budget dan Revenue

![Budget vs Revenue](Assets/Korelasi%20antara%20Budget%20dan%20Revenue%20Film.png)

### Insight & Cara Membaca Grafik
- Grafik *scatter plot* dengan garis regresi linear (*trendline* merah) memetakan hubungan finansial dari 5.362 film dengan data finansial valid.
- **Cara Membaca:** Sumbu X adalah besaran modal (*budget*), dan sumbu Y adalah total pendapatan (*revenue*). Garis merah menanjak ke kanan atas menunjukkan angka korelasi Pearson sebesar **0.73**, yang membuktikan adanya hubungan positif yang kuat antara modal besar dan pendapatan tinggi.
- Sebaran titik di area anggaran rendah sangat padat, namun ketika modal melampaui \$150 juta, sebaran titik menjadi sangat liar (risiko tinggi: bisa sukses besar atau gagal total).
- Terdapat *outlier* raksasa di bagian atas (menembus angka pendapatan mendekati 3 miliar USD) yang diisi oleh film-film *blockbuster* dunia seperti *Avatar*.

---

## 3. Top 10 Film Paling Menguntungkan

![Top 10 Profit](Assets/Top%2010%20Film%20Paling%20Menguntungkan%20Sepanjang%20Masa.png)

### Insight & Cara Membaca Grafik
- Grafik batang horizontal (*horizontal bar chart*) merangking 10 film dengan keuntungan bersih (*profit* = *revenue* - *budget*) tertinggi sepanjang masa.
- **Cara Membaca:** Panjang batang menunjukkan total keuntungan bersih dalam skala Miliar USD. 
- *Avatar* mendominasi peringkat pertama dengan keuntungan bersih yang sangat jauh melampaui film-film lainnya, disusul ketat oleh *Star Wars: The Force Awakens* di posisi kedua.
- Grafik ini menegaskan bahwa film-film pemegang rekor profit tertinggi didominasi oleh waralaba (*franchise*) berskala global dengan daya tarik penonton massal lintas negara.

---

## 4. Popularitas vs Rating (Min. 500 Votes)

![Popularity vs Rating](Assets/Korelasi%20antara%20popularitas%20dan%20rating%20film%20(min.%20500%20votes).png)

### Insight & Cara Membaca Grafik
- Grafik penyebaran ini membandingkan skor popularitas (*popularity*) melawan rata-rata rating penonton (*vote_average*) dengan filter minimal 500 penilai untuk menghindari bias statistik.
- **Cara Membaca:** Sumbu X adalah skor popularitas, dan sumbu Y adalah tingkat kepuasan penonton (skor 0-10). Titik-titik dengan rating tertinggi (di atas 8.5) justru menumpuk di zona popularitas yang rendah (di bawah 50).
- Contoh anomali kualitas tinggi adalah *Dilwale Dulhania Le Jayenge* (meraih rating 9.1) dan *The Shawshank Redemption*, yang membuktikan bahwa film mahakarya sering kali bersifat *segmented* (*cult classic*) dan tidak selalu identik dengan film terpopuler.
- Sebaliknya, titik anomali di sisi kanan ekstrem (popularitas >500 dengan rating moderat sekitar 6.4) dipegang oleh film viral seperti *Minions*, yang sukses besar secara *hype* dan pemasaran namun memiliki kualitas cerita standar.

---

# 🌍 Kategorial & Demografi Industri Film

## 1. Top 10 Rumah Produksi & Bahasa Utama

![Companies & Languages](Assets/Distribusi%20Rumah%20Film%20dan%20Bahasa%20Paling%20Banyak%20digunakan%20di%20Film.png)

### Insight & Cara Membaca Grafik
- Grafik batang ganda ini memetakan hegemoni studio Hollywood dan distribusi bahasa global dalam industri perfilman.
- **Cara Membaca:** Sumbu horizontal menunjukkan frekuensi kemunculan dalam dataset. 
- Di sisi kiri, rumah produksi raksasa seperti Warner Bros dan Universal Pictures mendominasi jumlah rilis film terbanyak secara global.
- Di sisi kanan, bahasa Inggris (`en`) memimpin secara mutlak, diikuti oleh bahasa utama Eropa seperti Prancis (`Français`), Jerman (`Deutsch`), Spanyol (`Español`), serta Jepang (`日本語`) yang mewakili kekuatan industri anime dunia.

---

# 📌 EDA Summary

Berdasarkan hasil Exploratory Data Analysis pada dataset TMDB, diperoleh beberapa temuan penting:

- Produksi film global mengalami lonjakan eksponensial sejak awal tahun 2000-an seiring perkembangan era digital.
- Terdapat korelasi positif yang kuat (**r = 0.73**) antara anggaran (*budget*) dan pendapatan (*revenue*), di mana modal besar menjadi penggerak utama *box office*.
- *Avatar* dan *Star Wars: The Force Awakens* tercatat sebagai film pencetak profit bersih tertinggi di dunia.
- Popularitas tinggi tidak menjamin kualitas rating yang tinggi; film-film dengan rating tertinggi sering kali berasal dari segmen penonton khusus (*niche*), sementara film terpopuler didorong oleh faktor *hype* (*Minions*).
- Dominasi industri film masih dipegang oleh studio besar Hollywood dengan bahasa pengantar utama bahasa Inggris.

---

# 🚀 Next Step

Tahapan selanjutnya yang dapat dilakukan untuk pengembangan sistem rekomendasi berbasis NLP adalah:

- *Data Preprocessing & Text Cleaning* (penggabungan kolom teks `overview`, `tagline`, dan `genres` menjadi *metadata soup*).
- *Vectorization* menggunakan TF-IDF (*Term Frequency-Inverse Document Frequency*).
- Menghitung kemiripan antar film menggunakan *Cosine Similarity*.
- Membangun fungsi sistem rekomendasi film interaktif.

---

## 🛠️ Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

---

## 👨‍💻 Author

**Muhammad Andi Ubaidillah**