# Laporan Proyek Machine Learning - Musfirotul Khusna

## Domain Proyek

**Latar Belakang**
Klasifikasi gender berdasarkan fitur wajah merupakan topik penting dalam bidang pengenalan pola dan visi komputer (Sofwan Alfaritsi, 2024). Dengan kemajuan teknologi dan meningkatnya kebutuhan akan sistem identifikasi otomatis, kemampuan untuk menentukan gender seseorang melalui analisis fitur wajah menjadi semakin relevan dalam berbagai aplikasi, seperti keamanan, interaksi manusia-komputer, dan pemasaran yang ditargetkan (Hanifa Salsabila, 2021).

Dataset yang digunakan dalam penelitian ini mencakup informasi tentang berbagai fitur wajah, termasuk panjang rambut, lebar dan tinggi dahi, lebar dan panjang hidung, ketebalan bibir, serta jarak antara hidung dan bibir. Fitur-fitur ini dipilih karena menunjukkan perbedaan yang signifikan antara pria dan wanita, sehingga menjadi indikator yang tepat untuk proses klasifikasi gender.


**Tujuan Proyek**
Tujuan utama dari penelitian ini adalah untuk mengembangkan model klasifikasi yang dapat memprediksi gender seseorang berdasarkan fitur-fitur wajah yang tersedia dalam dataset. Dengan memanfaatkan teknik pembelajaran mesin seperti Random Forest, Support Vector Machine (SVM), dan K-Nearest Neighbors (KNN), proyek ini bertujuan untuk mengevaluasi efektivitas masing-masing metode dalam konteks klasifikasi gender.

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
- Membandingkan beberapa algoritma seperti Logistic Regression, K-Nearest Neighbors (KNN), Decision Tree, Random Forest, dan Gradient Boosting untuk mengidentifikasi model dengan performa terbaik.
- Menyediakan evaluasi model yang bisa dijadikan baseline bagi pengembangan sistem klasifikasi gender secara otomatis.

    ### Solution statements
    - Menerapkan dan membandingkan lima algoritma klasifikasi (Logistic Regression, KNN, DecisionTreeClassifier, RandomForestClassifier, GradientBoostingClassifier) terhadap dataset gender. Setiap model dievaluasi berdasarkan akurasi pada data training dan testing, serta metrik precision, recall, dan f1-score.
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
## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Anda perlu menjelaskan tahapan dan parameter yang digunakan pada proses pemodelan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan kelebihan dan kekurangan dari setiap algoritma yang digunakan.
- Jika menggunakan satu algoritma pada solution statement, lakukan proses improvement terhadap model dengan hyperparameter tuning. **Jelaskan proses improvement yang dilakukan**.
- Jika menggunakan dua atau lebih algoritma pada solution statement, maka pilih model terbaik sebagai solusi. **Jelaskan mengapa memilih model tersebut sebagai model terbaik**.

## Evaluation
Pada bagian ini anda perlu menyebutkan metrik evaluasi yang digunakan. Lalu anda perlu menjelaskan hasil proyek berdasarkan metrik evaluasi yang digunakan.

Sebagai contoh, Anda memiih kasus klasifikasi dan menggunakan metrik **akurasi, precision, recall, dan F1 score**. Jelaskan mengenai beberapa hal berikut:
- Penjelasan mengenai metrik yang digunakan
- Menjelaskan hasil proyek berdasarkan metrik evaluasi

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.

