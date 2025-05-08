# Laporan Proyek Machine Learning - Musfirotul Khusna

## Domain Proyek

**Latar Belakang**
Klasifikasi gender berdasarkan fitur wajah merupakan topik penting dalam bidang pengenalan pola dan visi komputer (Sofwan Alfaritsi, 2024). Dengan kemajuan teknologi dan meningkatnya kebutuhan akan sistem identifikasi otomatis, kemampuan untuk menentukan gender seseorang melalui analisis fitur wajah menjadi semakin relevan dalam berbagai aplikasi, seperti keamanan, interaksi manusia-komputer, dan pemasaran yang ditargetkan (Hanifa Salsabila, 2021).

Dataset yang digunakan dalam penelitian ini mencakup informasi tentang berbagai fitur wajah, termasuk panjang rambut, lebar dan tinggi dahi, lebar dan panjang hidung, ketebalan bibir, serta jarak antara hidung dan bibir. Fitur-fitur ini dipilih karena menunjukkan perbedaan yang signifikan antara pria dan wanita, sehingga menjadi indikator yang tepat untuk proses klasifikasi gender.


**Tujuan Proyek**
Tujuan utama dari penelitian ini adalah untuk mengembangkan model klasifikasi yang dapat memprediksi gender seseorang berdasarkan fitur-fitur wajah yang tersedia dalam dataset. Dengan memanfaatkan teknik pembelajaran mesin seperti Logistic Regression, Random Forest, Decision Tree, dan K-Nearest Neighbors (KNN), proyek ini bertujuan untuk mengevaluasi efektivitas masing-masing metode dalam konteks klasifikasi gender.

**Signifikansi Proyek**
Proyek ini memiliki signifikansi dalam pengembangan sistem identifikasi otomatis yang lebih akurat dan efisien. Dengan memahami fitur-fitur wajah yang paling berpengaruh dalam menentukan gender, sistem dapat dioptimalkan untuk berbagai aplikasi praktis. Selain itu, proyek ini juga memberikan kontribusi dalam pemahaman lebih lanjut mengenai perbedaan morfologi wajah antara pria dan wanita, yang dapat berguna dalam bidang antropologi dan forensik.

**Daftar Pustaka (Format APA)**:
Hanifa Salsabila, E. R. (2021). Klasifikasi Gender Berdasarkan Citra Wajah Menggunakan Metode Local Binary Pattern dan K-Nearest Neighbor. Jurnal Tugas Akhir Fakultas Informatika, 3137-3146.
Sofwan Alfaritsi, M. H. (2024). IMPLEMENTASI KLASIFIKASI JENIS KELAMIN MENGGUNAKAN PSO DAN EKSTRAKSI FITUR CNN. SENAFTI (Seminar Nasional Mahasiswa Fakultas Teknologi Informasi), 803-810.

## Business Understanding

Proses klarifikasi masalah dalam proyek ini bertujuan untuk memahami tantangan dan kebutuhan utama dalam mengembangkan sistem klasifikasi gender berdasarkan fitur wajah. Analisis ini menjadi dasar dalam merumuskan pernyataan masalah, tujuan, serta solusi yang akan dikembangkan dalam proyek.

Bagian laporan ini mencakup:

### Problem Statements

Menjelaskan pernyataan masalah latar belakang:
- Bagaimana cara mengklasifikasikan jenis kelamin (gender) berdasarkan fitur-fitur yang tersedia dalam dataset dengan tingkat akurasi yang tinggi?
- Algoritma klasifikasi mana yang memberikan performa terbaik dalam memprediksi gender berdasarkan data yang dimiliki?
- Apakah pemodelan machine learning yang diterapkan dapat digunakan sebagai baseline untuk pengembangan aplikasi berbasis klasifikasi gender?

### Goals

Menjelaskan tujuan dari pernyataan masalah:
- Mengembangkan model klasifikasi berbasis machine learning yang dapat mengidentifikasi gender secara akurat berdasarkan data fitur.
- Membandingkan beberapa algoritma seperti Logistic Regression, K-Nearest Neighbors (KNN), Decision Tree, dan Random Forest untuk mengidentifikasi model dengan performa terbaik.
- Menyediakan evaluasi model yang bisa dijadikan baseline bagi pengembangan sistem klasifikasi gender secara otomatis.

    ### Solution statements
    - Menerapkan dan membandingkan empat algoritma klasifikasi (Logistic Regression, KNN, DecisionTreeClassifier, RandomForestClassifier) terhadap dataset gender. Setiap model dievaluasi berdasarkan akurasi pada data training dan testing, serta metrik precision, recall, dan f1-score.
    - Melakukan visualisasi dan analisis confusion matrix serta classification report untuk mengidentifikasi potensi bias atau ketidakseimbangan prediksi antar gender.
    - Menggunakan metrik akurasi (accuracy), macro average, dan weighted average F1-Score sebagai indikator performa yang terukur dari tiap model, serta mempertimbangkan overfitting dari model berdasarkan perbedaan akurasi training dan testing.

## Data Understanding
Dataset yang digunakan dalam proyek ini diambil dari Kaggle (https://www.kaggle.com/datasets/elakiricoder/gender-classification-dataset/data
). Dataset ini berisi data yang digunakan untuk mengklasifikasikan gender (pria atau wanita) berdasarkan ciri-ciri wajah yang terukur. Terdapat 7 fitur dan satu kolom label yang berfungsi untuk memprediksi gender.

Selanjutnya uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

### Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
- long_hair: Merupakan kolom yang berisi nilai 0 atau 1, di mana 1 menunjukkan "rambut panjang" dan 0 menunjukkan "bukan rambut panjang".
- forehead_width_cm: Lebar dahi dalam satuan sentimeter (cm).
- forehead_height_cm: Tinggi dahi dalam satuan sentimeter (cm).
- nose_wide: Merupakan kolom yang berisi nilai 0 atau 1, di mana 1 menunjukkan "hidung lebar" dan 0 menunjukkan "bukan hidung lebar".
- nose_long: Merupakan kolom yang berisi nilai 0 atau 1, di mana 1 menunjukkan "hidung panjang" dan 0 menunjukkan "bukan hidung panjang".
- lips_thin: Merupakan kolom yang berisi nilai 0 atau 1, di mana 1 menunjukkan "bibir tipis" dan 0 menunjukkan "bukan bibir tipis".
- distance_nose_to_lip_long: Merupakan kolom yang berisi nilai 0 atau 1, di mana 1 menunjukkan "jarak antara hidung dan bibir panjang" dan 0 menunjukkan "jarak antara hidung dan bibir pendek".
- gender: Kolom label yang berisi "Male" atau "Female", yang menunjukkan jenis kelamin individu.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Distribusi Gender :Untuk mengetahui distribusi data berdasarkan gender, kita dapat menggunakan bar chart dan pie chart untuk memvisualisasikan frekuensi masing-masing kategori gender.
![alt text](https://github.com/Musfirotul17/mlterapan_satu/blob/main/visualisasi%20pie%20dan%20bar%20chart.png?raw=true)
Terdapat lebih banyak data untuk Male (1783) dibandingkan Female (1450).
- Distribusi Fitur Berdasarkan Gender : Untuk melihat perbedaan distribusi masing-masing fitur berdasarkan gender, kita dapat menggunakan count plot yang menunjukkan jumlah kategori untuk setiap kolom dibandingkan dengan gender.
![alt text](https://github.com/Musfirotul17/mlterapan_satu/blob/main/forehead%20height%20bar%20chart.png?raw=true)
![alt text](https://github.com/Musfirotul17/mlterapan_satu/blob/main/forehead%20with%20cm%20bar%20chart.png?raw=true)
![alt text](https://github.com/Musfirotul17/mlterapan_satu/blob/main/hair%20bar%20chart.png?raw=true)
![alt text](https://github.com/Musfirotul17/mlterapan_satu/blob/main/lips%20thin.png?raw=true)
![alt text](https://github.com/Musfirotul17/mlterapan_satu/blob/main/nose%20bar%20chart.png?raw=true)
![alt text](https://github.com/Musfirotul17/mlterapan_satu/blob/main/nose%20long%20bar%20chart.png?raw=true)
![alt text](https://github.com/Musfirotul17/mlterapan_satu/blob/main/nose%20to%20lips.png?raw=true)
Visualisasi ini memberikan wawasan mengenai distribusi fitur-fitur seperti panjang rambut, lebar dahi, hidung lebar, dan lainnya untuk masing-masing gender. Hal ini sangat berguna untuk mengevaluasi pola dan hubungan antara fitur dan gender.
**Kesimpulan Awal dari EDA:**
- Kolom gender menunjukkan distribusi yang lebih banyak untuk Male daripada Female.
- Setiap fitur seperti long_hair, nose_wide, dan distance_nose_to_lip_long memiliki distribusi yang berbeda pada masing-masing gender. Misalnya, "long hair" cenderung lebih banyak ditemukan pada Female, sementara "wide nose" lebih sering muncul pada Male.

## Data Preparation
1. Memisahkan fitur (input) dan target (output)
Proses: Menyalin DataFrame asli, lalu memisahkan kolom-kolom fitur (X) dari target (y), yaitu kolom gender.
Alasan: Pemisahan ini penting agar fitur dan label diproses secara terpisah, sesuai kebutuhan algoritma supervised learning.
2. Membagi dataset menjadi data latih dan data uji
Proses: Dataset dibagi menjadi 80% untuk training dan 20% untuk testing.
Alasan: Untuk menghindari overfitting dan mengukur performa model secara objektif menggunakan data yang belum pernah dilatih.
3. Mengubah label kategori ‘gender’ menjadi bentuk numerik
Proses: Label gender diubah dari bentuk string (seperti 'Male', 'Female') menjadi angka menggunakan LabelEncoder.
Alasan: Algoritma machine learning hanya bisa menerima data numerik, jadi kolom kategori perlu dikodekan terlebih dahulu.
4.  Melakukan standarisasi menggunakan MinMaxScaler
Proses: Semua fitur diubah ke rentang 0–1 menggunakan MinMaxScaler.
Alasan: Scaling diperlukan agar fitur yang memiliki skala berbeda tidak mendominasi proses pelatihan model, terutama penting untuk algoritma yang berbasis jarak atau bobot.

## Modeling
Pada tahap ini, dilakukan pemodelan untuk menyelesaikan masalah klasifikasi gender berdasarkan fitur wajah menggunakan empat algoritma machine learning, yaitu: Logistic Regression, K-Nearest Neighbors (KNN), Decision Tree, dan Random Forest. Semua model dilatih menggunakan data latih (x_train, y_train) yang telah dipisahkan sebelumnya.

1. Logistic Regression
Kelebihan:
-Model yang sederhana dan mudah diinterpretasikan.
-Cepat dalam pelatihan dan prediksi.
Kekurangan:
-Cenderung memiliki performa rendah untuk data yang tidak linear.
-Sensitif terhadap fitur yang saling berkorelasi.

2. K-Nearest Neighbors (KNN)
Kelebihan:
-Tidak memerlukan proses pelatihan (lazy learner).
-Sederhana dan cocok untuk data dengan distribusi yang jelas.
Kekurangan:
-Waktu prediksi bisa lambat karena menghitung jarak dengan seluruh data latih.
-Sensitif terhadap pemilihan nilai k dan skala fitur.

3. Decision Tree
Kelebihan:
-Mudah diinterpretasikan (berbentuk pohon keputusan).
-Dapat menangani data numerik dan kategorikal.
-Tidak membutuhkan normalisasi data.
Kekurangan:
-Rentan terhadap overfitting terutama jika tidak dilakukan pruning.

4. Random Forest
Kelebihan:
-Mengatasi overfitting dari decision tree dengan teknik ensemble.
-Lebih stabil dan akurat dalam banyak kasus klasifikasi.
Kekurangan:
-Interpretasi lebih sulit dibanding decision tree tunggal.
-Memerlukan sumber daya komputasi lebih besar.

Pemilihan Model Terbaik
Setelah dilakukan pelatihan keempat model, dilakukan evaluasi terhadap performa masing-masing model menggunakan metrik evaluasi seperti akurasi, precision, recall, dan F1-score. Model terbaik dipilih berdasarkan hasil metrik evaluasi pada data uji. Jika hasil menunjukkan bahwa misalnya salah satu algritma memiliki nilai F1-score tertinggi, maka model tersebut dipilih sebagai model terbaik.Berdasarkan hasil evaluasi, model RandomForest memberikan hasil akurasi dan F1-score tertinggi dibandingkan model lainnya. Oleh karena itu, model ini dipilih sebagai solusi terbaik dalam klasifikasi gender pada dataset ini karena mampu mengatasi overfitting dan menangkap kompleksitas data lebih baik.


## Evaluation
Untuk mengevaluasi performa model klasifikasi yang digunakan, beberapa metrik evaluasi berikut diterapkan:

✅ Metrik Evaluasi yang Digunakan
Accuracy
Mengukur proporsi prediksi yang benar dari keseluruhan prediksi.

Accuracy
=
𝑇
𝑃
+
𝑇
𝑁
𝑇
𝑃
+
𝑇
𝑁
+
𝐹
𝑃
+
𝐹
𝑁
Accuracy= 
TP+TN+FP+FN
TP+TN
​
 
Precision
Mengukur ketepatan prediksi positif dari seluruh prediksi positif.

Precision
=
𝑇
𝑃
𝑇
𝑃
+
𝐹
𝑃
Precision= 
TP+FP
TP
​
 
Recall (Sensitivity)
Mengukur seberapa baik model menangkap semua data yang relevan (positif).

Recall
=
𝑇
𝑃
𝑇
𝑃
+
𝐹
𝑁
Recall= 
TP+FN
TP
​
 
F1-Score
Merupakan rata-rata harmonis dari precision dan recall.

F1
=
2
×
Precision
×
Recall
Precision
+
Recall
F1=2× 
Precision+Recall
Precision×Recall
​
 📌 Hasil Evaluasi Model
Model	Train Accuracy	Test Accuracy	Precision (avg)	Recall (avg)	F1 Score (avg)
Logistic Regression	95.01%	95.98%	0.96	0.96	0.96
K-Nearest Neighbors	97.25%	94.13%	0.94	0.94	0.94
Decision Tree	99.77%	94.74%	0.95	0.95	0.95
Random Forest	99.77%	95.52%	0.96	0.96	0.96

📈 Analisis Hasil Evaluasi
Logistic Regression menunjukkan generalisasi yang sangat baik dengan test accuracy tertinggi (95.98%), meskipun training accuracy-nya lebih rendah dari model lain.

K-Nearest Neighbors sedikit overfit (97.25% train vs 94.13% test), namun performanya masih solid.

Decision Tree memperlihatkan overfitting yang tinggi, dengan training accuracy hampir sempurna (99.77%) namun test accuracy menurun menjadi 94.74%.

Random Forest mengatasi overfitting yang dialami oleh Decision Tree, dengan test accuracy yang lebih stabil (95.52%) dan performa metrik lainnya yang seimbang.

✅ Kesimpulan Pemilihan Model Terbaik
Berdasarkan hasil evaluasi, Random Forest Classifier dipilih sebagai model terbaik karena:

Memiliki kombinasi train-test accuracy yang stabil.

Nilai precision, recall, dan F1-score tinggi dan seimbang.

Memiliki kemampuan generalization yang baik, sekaligus meminimalkan overfitting yang dialami oleh Decision Tree.




**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.

