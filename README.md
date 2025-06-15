# 🎬 Analisis Visual dan Prediksi AI pada Dataset Netflix Shows

Repositori ini memuat proyek eksplorasi data dan penerapan AI untuk menganalisis tren tayangan Netflix berdasarkan genre, rating, dan tahun rilis. Proyek ini menyajikan visualisasi interaktif dan model prediktif untuk memahami pola konsumsi konten serta memproyeksikan tren di masa mendatang.

---

## 🎯 Tujuan Proyek

Proyek ini dirancang untuk:

- Mengidentifikasi genre tayangan paling dominan sepanjang waktu dalam katalog Netflix.
- Menelusuri tren perkembangan genre dari tahun ke tahun.
- Memprediksi genre-genre yang akan meningkat popularitasnya hingga lima tahun ke depan (2022–2026).
- Membangun model klasifikasi untuk memprediksi rating tayangan berdasarkan genre dan tipe konten.
- Menampilkan perbandingan antara rating aktual dan hasil prediksi sebagai evaluasi model AI.
- Menganalisis hubungan antara genre dan klasifikasi rating untuk melihat pola keterkaitan atau dominasi.

---

## 📊 Deskripsi Dataset

- **Sumber**: [Netflix Shows Dataset – Kaggle](https://www.kaggle.com/datasets/shivamb/netflix-shows)
- **Nama file**: `Dataset Netflix Shows.csv`
- Dataset berisi informasi berbagai tayangan Netflix, seperti:
  - `type` – Jenis tayangan (Movie / TV Show)
  - `listed_in` – Genre (bisa lebih dari satu per tayangan)
  - `release_year` – Tahun rilis tayangan
  - `rating` – Klasifikasi usia (TV-MA, PG, dll)

Data telah diproses agar siap dianalisis:
- Menghapus data kosong
- Mengekstraksi genre menjadi baris terpisah
- Mengambil top 10 genre dan rating terpopuler

---

## 🧠 Model AI yang Digunakan

### 1. Prediksi Genre Populer
- **Model**: `LinearRegression`
- **Tujuan**: Memprediksi jumlah tayangan setiap genre dari tahun 2022 hingga 2026
- **Input**: Data jumlah tayangan per genre dari tahun 2000-an ke 2021

### 2. Prediksi Rating Tayangan
- **Model**: `RandomForestClassifier`
- **Tujuan**: Memprediksi rating tayangan berdasarkan genre dominan dan tipe (Movie/TV)
- **Evaluasi**: Confusion Matrix dan histogram prediksi vs aktual

### 3. Korelasi Genre dan Rating
- **Metode**: Statistik pengelompokan dan visualisasi bertumpuk (tanpa model AI)
- **Tujuan**: Melihat distribusi rating dalam tiap genre dan mendeteksi dominasi atau kecenderungan tertentu

---

## 📈 Visualisasi Interaktif

Terdapat **7 visualisasi interaktif** yang dihasilkan:

1. Bar chart horizontal: Top 10 genre terpopuler secara keseluruhan
2. Bar chart bertumpuk: Distribusi genre per tahun
3. Line chart: Prediksi genre terpopuler untuk 2022–2026
4. Bar chart vertikal: 10 rating tayangan terbanyak
5. Confusion Matrix: Evaluasi akurasi prediksi rating tayangan
6. Histogram: Distribusi rating aktual vs prediksi oleh model AI
7. Bar chart bertumpuk: Korelasi antara genre dan rating

> Semua output grafik disimpan dalam folder `/Images`.

---

## ✅ Hasil dan Insight

- **Genre Terpopuler**: Genre seperti *International Movies*, *Dramas*, dan *Comedies* menjadi tiga besar secara konsisten dari tahun ke tahun.
- **Tren Genre**: Tayangan bertema internasional dan drama menunjukkan tren meningkat dari tahun ke tahun, terutama sejak 2016.
- **Prediksi Genre 2022–2026**: *International Movies* diperkirakan tetap dominan, disusul oleh *Dramas* dan *Comedies*. Beberapa genre seperti *Children & Family Movies* dan *Action & Adventure* menunjukkan tren menurun.
- **Prediksi Rating**: Model Random Forest mampu mengklasifikasikan rating dengan akurasi cukup baik. Namun, model cenderung **overpredict** pada rating populer seperti `TV-MA` dan `TV-14`.
- **Korelasi Genre–Rating**: Genre seperti *Horror* dan *Crime* lebih sering diasosiasikan dengan rating tinggi (TV-MA), sedangkan genre *Children & Family* sangat dominan di rating rendah (G dan PG).
- **Ketimpangan Data**: Performa model dipengaruhi oleh ketidakseimbangan jumlah data per rating, yang menyebabkan prediksi cenderung berat ke rating populer.

---

## ▶️ Cara Menjalankan Proyek

1. **Clone repositori**
```bash
git clone https://github.com/7Riv/Visualisasi_Data
cd Visualisasi_Data

```
2. **(Opsional) Buat virtual environment**
```bash
python -m venv venv
source venv/bin/activate    # macOS/Linux
venv\Scripts\activate       # Windows
```
3. **Install dependensi**
```bash
pip install -r requirements.txt
```
5. **Jalankan notebook**
```bash
jupyter notebook NetflixShows.ipynb
```
