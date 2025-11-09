# 🧠 Machine Learning to Predict the Number of Promotions

## 📌 Pengertian Proyek
Proyek ini bertujuan untuk membangun model *machine learning* yang dapat memprediksi jumlah promosi (`num_promotions`) yang diterima pelanggan berdasarkan data demografis, perilaku belanja, dan pengeluaran mereka.  
Pendekatan ini termasuk dalam **supervised learning (classification)** dengan target berupa jumlah promosi dalam kategori diskrit (0–6).  

---

## 🧾 Deskripsi Proyek
Notebook ini menampilkan alur lengkap mulai dari pemuatan data, pembersihan data, penanganan nilai hilang dan outlier, encoding variabel kategorikal, normalisasi, hingga pelatihan model *neural network* dengan beberapa arsitektur berbeda.  
Tujuan utama adalah mendapatkan model dengan **akurasi validasi terbaik** untuk memprediksi promosi pelanggan secara tepat.

Proyek ini juga membandingkan beberapa arsitektur jaringan saraf:
1. **Complex Neural Network** – dengan *Batch Normalization* dan *Dropout* untuk regularisasi.
2. **Simpler Neural Network** – versi ringan dengan lapisan lebih sedikit.
3. **Deeper Neural Network** – versi dalam dengan lebih banyak neuron.

---

## 📊 Dataset
- **Train Dataset:** `train.csv` (3.436 baris, 17 kolom)  
- **Test Dataset:** `test_features.csv` (381 baris, 17 kolom)

### Fitur utama:
- `income` — Pendapatan tahunan
- `num_toddlers`, `num_teens` — Jumlah anak balita dan remaja
- `year_of_birth` — Tahun kelahiran
- `education_level`, `marital_status` — Data kategorikal
- `study_expenses`, `food_expenses`, `transportation_expenses`, `entertainment_expenses` — Total pengeluaran per kategori
- `discount_activities`, `online_activities`, `offline_activities` — Aktivitas pelanggan dalam promosi
- `complaints` — Indikator keluhan pelanggan
- **Target:** `num_promotions` (0–6)

---

## ⚙️ Tools dan Teknologi
- **Python**  
- **Pandas**, **NumPy** → Analisis dan manipulasi data  
- **Matplotlib**, **Seaborn** → Visualisasi data  
- **Scikit-learn** → Preprocessing, encoding, scaling, imputasi, dan split data  
- **TensorFlow / Keras** → Pembangunan dan pelatihan model Neural Network  
- **Pipeline** & **ColumnTransformer** → Pengolahan data terstruktur  

---

## 🔍 Tahapan Analisis
1. **Pemuatan Data**  
   - Dataset `train.csv` dan `test_features.csv` dibaca menggunakan `pandas`.
2. **Pemeriksaan dan Pembersihan Data**  
   - Menangani *missing values* dengan `SimpleImputer` (median dan modus).
   - Menghapus kolom `enrollment_date` karena memiliki terlalu banyak nilai kosong.
3. **Identifikasi dan Penanganan Outlier**  
   - Outlier dideteksi menggunakan metode **IQR (Interquartile Range)**, kemudian disesuaikan agar berada dalam batas wajar.
4. **Encoding**  
   - Fitur kategorikal (`education_level`, `marital_status`) diubah menjadi numerik menggunakan **LabelEncoder**.
5. **Normalisasi**  
   - Fitur numerik diskalakan menggunakan **StandardScaler** untuk mempercepat konvergensi model.
6. **Pembagian Data**  
   - Data dilatih dan divalidasi menggunakan **train-test split (80:20)**.
7. **Pelatihan Model**  
   - Model dilatih menggunakan arsitektur berbeda (3 variasi neural network) dengan **EarlyStopping** dan **ReduceLROnPlateau** untuk menghindari overfitting.
8. **Evaluasi dan Validasi**  
   - Akurasi validasi digunakan untuk membandingkan performa antar model.

---

## 📈 Hasil Akhir Analisis
Tiga model diuji:
1. **Model 1 – Complex NN:** menggunakan BatchNormalization & Dropout (akurasi validasi ~29–35%)  
2. **Model 2 – Simple NN:** arsitektur lebih ringan dengan Dropout moderat  
3. **Model 3 – Deep NN:** arsitektur dalam dengan neuron besar dan Dropout tinggi  

Model 1 menunjukkan **stabilitas dan generalisasi terbaik**, meskipun hasil keseluruhan menunjukkan tantangan dalam prediksi akurat untuk variabel multi-kelas dengan distribusi tidak seimbang.

---

## 💡 Insight dan Manfaat
- **Insight utama:** Fitur seperti `income`, `discount_activities`, `online_activities`, dan `food_expenses` memiliki pengaruh signifikan terhadap prediksi jumlah promosi.  
- **Manfaat bisnis:**  
  - Membantu perusahaan memahami pola pelanggan yang cenderung menerima promosi lebih sering.  
  - Dapat digunakan untuk strategi *targeted marketing* dan retensi pelanggan yang lebih efektif.  
  - Proses *preprocessing pipeline* yang dibuat bisa digunakan ulang untuk data baru.

---

## 🧩 Kesimpulan Akhir
- Proyek ini berhasil membangun sistem prediksi berbasis **Deep Learning** untuk memperkirakan jumlah promosi pelanggan.  
- Proses analisis mencakup tahapan lengkap *data cleaning*, *feature engineering*, *modeling*, dan *evaluation*.  
- Hasil menunjukkan bahwa model neural network dengan **Batch Normalization dan Dropout** memberikan kinerja paling stabil.  
- Pipeline dan arsitektur yang digunakan dapat menjadi dasar untuk proyek prediksi perilaku pelanggan di masa depan.

---

📍 **Disusun oleh:**  
**Rehana Putri Salsabilla** – NRP 5027221015  
Kelas: AI B  
