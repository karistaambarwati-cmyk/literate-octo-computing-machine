# Proyek UTS Data Mining: Klasifikasi Kualitas Wine

Analisis ini merupakan bagian dari Ujian Tengah Semester (UTS) Mata Kuliah Data Mining. Proyek ini berfokus pada pembangunan model *Machine Learning* untuk memprediksi kualitas *wine* (anggur) berdasarkan atribut kimiawinya.

Notebook utama untuk proyek ini adalah `UTS_Karista Ambarwati_4111422008.ipynb`.

## 1️⃣ Konteks Proyek (Context)

Industri *wine* sangat bergantung pada kualitas rasa dan aroma. Secara tradisional, penilaian ini dilakukan oleh ahli pencicip (*wine tasters*), sebuah proses yang bisa jadi bersifat subjektif, memakan waktu, dan mahal.

Proyek ini mengimplementasikan pendekatan Data Mining untuk menciptakan model prediktif yang objektif. Dengan menganalisis parameter kimiawi (seperti keasaman, kadar alkohol, dan gula), kita dapat membangun sistem untuk mengklasifikasikan kualitas *wine* secara otomatis.

## 2️⃣ Pernyataan Masalah (Problem Statement)

Tantangan utama dalam proyek ini adalah:

* **Subjektivitas Penilaian:** Penilaian manual oleh manusia rentan terhadap bias dan inkonsistensi.
* **Kebutuhan Klasifikasi:** Diperlukan sebuah model yang andal untuk mengklasifikasikan *wine* ke dalam kategori kualitas tertentu (misalnya 'baik' atau 'buruk') berdasarkan data fisik-kimia.
* **Optimasi Model:** Banyak model *machine learning* yang tersedia. Perlu dilakukan pemilihan dan *tuning* model untuk mendapatkan performa terbaik.

## 3️⃣ Tujuan Proyek (Objective)

Tujuan utama dari proyek ini adalah:

* Melakukan *Exploratory Data Analysis (EDA)* untuk memahami karakteristik dataset *wine*.
* Melakukan *Data Preprocessing* agar data siap digunakan untuk pemodelan.
* Membangun dan melatih beberapa model klasifikasi.
* Memilih model terbaik (dalam hal ini **Random Forest**) dan melakukan *hyperparameter tuning* untuk optimasi.
* Mengevaluasi performa model *tuned* menggunakan metrik yang relevan (seperti *accuracy*, *precision*, *recall*, dan *confusion matrix*).
* Menyimpan model final yang telah dilatih dan hasil prediksinya.

## 4️⃣ Dataset dan Variabel-Variabel Kunci

Dataset yang digunakan (kemungkinan besar *Wine Quality Dataset* dari UCI) berisi berbagai pengukuran kimiawi untuk setiap sampel *wine*.

* **Variabel Fitur (Input):**
    * `fixed acidity`
    * `volatile acidity`
    * `citric acid`
    * `residual sugar`
    * `chlorides`
    * `free sulfur dioxide`
    * `total sulfur dioxide`
    * `density`
    * `pH`
    * `sulphates`
    * `alcohol`
* **Variabel Target (Output):**
    * `quality` (Biasanya berupa skor yang kemudian dikategorikan, misal menjadi 'good' dan 'bad').

## 5️⃣ Metodologi dan Alur Kerja

Proyek ini mengikuti alur kerja Data Mining yang standar:

1.  **Import Library:** Memuat pustaka yang diperlukan (`pandas`, `numpy`, `sklearn`, `matplotlib`, `seaborn`, `joblib`).
2.  **Data Loading:** Memuat dataset ke dalam DataFrame `pandas`.
3.  **Exploratory Data Analysis (EDA):**
    * Memeriksa informasi dasar (`.info()`, `.describe()`.
    * Mengecek nilai yang hilang (`.isnull().sum()`).
    * Visualisasi data untuk memahami korelasi dan distribusi (misalnya menggunakan `heatmap` dan `countplot`).
4.  **Data Preprocessing:**
    * **Penanganan Variabel Target:** Mengubah variabel `quality` (yang mungkin numerik 1-10) menjadi variabel kategorikal biner (misal 0 = 'buruk', 1 = 'baik').
    * **Pemisahan Data:** Membagi dataset menjadi fitur (`X`) dan target (`y`).
    * **Feature Scaling:** Menerapkan `StandardScaler` pada fitur (`X`) untuk menstandarisasi rentang data.
    * **Train-Test Split:** Membagi data menjadi 80% data latih dan 20% data uji.
5.  **Pemodelan dan Evaluasi:**
    * Melatih model dasar **Random Forest Classifier**.
    * Mengevaluasi performa model dasar.
6.  **Hyperparameter Tuning:**
    * Menggunakan `GridSearchCV` atau `RandomizedSearchCV` untuk mencari kombinasi *hyperparameter* terbaik untuk model Random Forest.
    * Melatih model `best_rf` (model Random Forest terbaik) menggunakan parameter hasil *tuning*.
7.  **Evaluasi Akhir:**
    * Mengukur performa model *tuned* pada data uji.
    * Menghasilkan `classification_report` dan `confusion_matrix`.
8.  **Penyimpanan Hasil:**
    * Menyimpan model *tuned* ke dalam file (`model_RF_tuned.pkl`) menggunakan `joblib`.
    * Menyimpan hasil prediksi dari data uji ke dalam file CSV (`hasilprediksi_008.csv`).

## 6️⃣ Hasil Proyek (Results)

Proyek ini berhasil menghasilkan dua *artifacts* utama:

1.  **Model Machine Learning (`model_RF_tuned.pkl`):**
    * Sebuah model *Random Forest Classifier* yang telah dioptimalkan (*tuned*).
    * Model ini siap digunakan untuk memprediksi kualitas *wine* baru berdasarkan data kimianya.
2.  **File Prediksi (`hasilprediksi_008.csv`):**
    * Sebuah file CSV yang berisi hasil prediksi model pada data uji.
    * File ini dapat digunakan untuk analisis lebih lanjut atau perbandingan dengan nilai aktual.

## 7️⃣ Kesimpulan (Conclusion)

Proyek ini berhasil mendemonstrasikan penerapan *pipeline* Data Mining secara lengkap, mulai dari pembersihan data, eksplorasi, *preprocessing*, *feature scaling*, pembangunan model, hingga *hyperparameter tuning* dan evaluasi.

Model Random Forest yang telah di-*tuning* menunjukkan performa yang baik (berdasarkan metrik evaluasi yang dihasilkan dalam notebook) dan berhasil disimpan untuk penggunaan di masa depan.

## 8️⃣ Cara Menjalankan (How to Use)

1.  Pastikan Anda memiliki *environment* Python dengan pustaka yang tercantum dalam notebook (seperti `scikit-learn`, `pandas`, `joblib`).
2.  Tempatkan dataset (misal: `wine_quality.csv`) dalam direktori yang sama.
3.  Jalankan sel-sel di dalam notebook `UTS_Karista Ambarwati_4111422008.ipynb` secara berurutan.
4.  Setelah eksekusi selesai, file `model_RF_tuned.pkl` dan `hasilprediksi_008.csv` akan dibuat di direktori Anda.
