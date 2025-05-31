# Laporan Proyek Machine Learning - M. Reza Fahlevi

## Domain Proyek : Sosial

![Types Of Personality](https://i.pinimg.com/736x/0b/17/f4/0b17f428ef7d798e5c8b4e7f4c547237.jpg)

Memahami perilaku dan kecerdasan manusia adalah umumnya dikendalikan dan diawasi oleh aspek psikologis tentang bagaimana orang berpikir dan mempersepsikan apa pun atau tindakan apa pun. Sebagai contoh, situasi dan kondisi dapat bervariasi tetapi mengarah pada kesimpulan indikator kepribadian. Ada berbagai indikator tipe kepribadian yang membantu dalam mengidentifikasi kepribadian manusia dengan menggunakan faktor psikologis manusia. Di era teknologi saat ini, Machine Learning dan Deep Learning telah muncul sebagai teknik yang berharga dan bermanfaat untuk memprediksi temuan yang akurat dan melakukan tugas-tugas yang terperinci dan kompleks dengan efisiensi, dan akurasi.
[_(Hira Shafi et al., 2021)_](https://jisrc.szabist.edu.pk/ojs/index.php/jisrc/article/view/42). Indikator Tipe Myers-Briggs (MBTI) adalah indikator persepsi individu tentang dunia dan proses pengambilan keputusan. Katherine Cook dan putrinya, Isabel Briggs Myers, adalah orang pertama yang menemukan metode ini, yang merupakan pengembangan dari teori kepribadian yang sebelumnya dikemukakan oleh Carl Gustav Jung. MBTI telah berfungsi sebagai instrumen yang digunakan orang dalam upaya untuk lebih memahami keyakinan dan motivasi mereka sendiri. Meskipun reliabilitas dan validitas MBTI sering dikritik, MBTI tetap menjadi ukuran kepribadian yang paling banyak digunakan. [_(Mawadatul Maulidah et al., 2023)_](https://researchhub.id/index.php/jitek/article/view/1292).

Melalui analisis ini, diharapkan dapat ditemukan model klasifikasi kepribadian yang akurat dan mudah diimplementasikan di berbagai konteks. Pemahaman terhadap tipe kepribadian sangat penting karena dapat memengaruhi cara seseorang berpikir, belajar, bekerja, dan berinteraksi.

Model ini dapat dimanfaatkan di berbagai sektor, seperti pendidikan untuk menyesuaikan metode pembelajaran, rekrutmen untuk mencocokkan kandidat dengan posisi kerja, serta layanan kesehatan mental untuk deteksi dini kondisi psikologis. Dengan bantuan machine learning, pemetaan kepribadian dapat dilakukan secara lebih efisien dan berdampak nyata dalam pengambilan keputusan yang lebih personal dan tepat sasaran.

## Business Understanding

### Problem Statements

Berdasarkan latar belakang yang telah diuraikan, maka rumusan masalah dalam penelitian ini adalah sebagai berikut:

- Fitur apa saja yang paling berpengaruh terhadap tipe kepribadian seseorang?

- Model machine learning apa yang paling efektif dalam mengklasifikasikan tipe kepribadian individu?

### Goals
tujuan untuk menyelesaikan permasalahan diatas adalah:

- Mengidentifikasi fitur-fitur yang memiliki korelasi paling signifikan terhadap tipe kepribadian.

- Membangun model machine learning yang mampu mengklasifikasikan tipe kepribadian secara akurat berdasarkan fitur-fitur yang tersedia dalam dataset.

### Solution statements

Untuk mencapai tujuan tersebut, solusi yang diusulkan dalam penelitian ini mencakup langkah-langkah berikut:

- Melakukan eksplorasi data (exploratory data analysis) dan visualisasi data guna memahami distribusi, karakteristik data, serta mengidentifikasi korelasi antar fitur dan hubungannya dengan variabel target, yaitu tipe kepribadian.

- Mengimplementasikan berbagai algoritma machine learning untuk membangun model klasifikasi dan mengevaluasi kinerjanya.

- Melakukan evaluasi secara komprehensif terhadap kinerja model-model tersebut, serta membandingkan performanya berdasarkan metrik evaluasi pada data pengujian untuk menentukan model terbaik.


## Data Understanding
Dari website kaggle dapat diketahui kumpulan data sintetis ini dirancang untuk mengeksplorasi dan memprediksi tipe kepribadian Myers-Briggs Type Indicator (MBTI) berdasarkan kombinasi faktor demografis, area minat, dan skor kepribadian. Dataset ini mencakup 43744 baris dan 9 kolom. Dataset ini dapat digunakan untuk mempelajari korelasi antara dimensi kepribadian yang berbeda dan faktor eksternal seperti usia, jenis kelamin, pendidikan, dan minat.

**Informasi Datasets**

| Jenis | Keterangan |
| ------ | ------ |
| Title | Predict People Personality Types |
| Source | [Kaggle](https://www.kaggle.com/datasets/stealthtechnologies/predict-people-personality-types) |
| Owner | [Umair Zia](https://www.kaggle.com/stealthtechnologies) |
| License | MIT |
| Tags | Education, Demographics, Social Science, Beginner
| Usability | 10.00 |

### Variabel-variabel pada dataset Predict People Personality Types adalah sebagai berikut:
- Age: Usia
- Gender: Jenis kelamin
- Education: Tingkat pendidikan
    - Education = 1 → Minimal lulusan sarjana (graduate-level atau lebih tinggi)
    - Education = 0 → Lulusan di bawah sarjana (undergraduate, SMA, atau tidak berpendidikan)
- Introversion Score: Skor kecenderungan introvert
- Sensing Score	Skor: kecenderungan sensing
- Thinking Score: Skor kecenderungan berpikir
- Judging Score: Skor kecenderungan menilai
- Interest: Minat pribadi (misalnya: Arts, Sports, Others)
- Personality: Tipe kepribadian MBTI

### Exploratory Data Analysis - Deskripsi Variabel 

| #  | Column                            | Non-Null Count | Dtype   |
|----|------------------------------------|----------------|---------|
| 0  | Age                             | 43744 non-null   | float64 |
| 1  | Gender                          | 43744 non-null   | object  |
| 2  | Education                       | 43744 non-null   | int64   |
| 3  | Introversion Score              | 43744 non-null   | float64 |
| 4  | Sensing Score                   | 43744 non-null   | float64 |
| 5  | Thinking Score                  | 43744 non-null   | float64 |
| 6  | Judging Score                   | 43744 non-null   | float64 |
| 7  | Interest                        | 43744 non-null   | object  |
| 8  | Personality                     | 43744 non-null   | object  |

Dari table diatas dapat diketahui bahwa terdapat:

- 1 kolom integer
- 3 kolom object
- 5 kolom float

|Age	| Education	| Introversion | Score	| Sensing Score	| Thinking Score	| Judging Score|
|-----|-----------|--------------|--------|---------------|-----------------|--------------|
|count|	43744.000000	|43744.000000	|43744.000000	|43744.000000|	43744.000000|	43744.000000|
|mean	|27.437203	|0.229014	4.588349	|5.780074	|5.419131	|5.391041|
|std	|4.893805	|0.420203	2.902628	|1.241648	|2.900785	|1.442413|
|min	|18.000000	|0.000000	0.000150	|0.000000	|0.000320	|0.000000|
|25%	|24.000000	|0.000000	2.067020	|4.953340	|2.895750	|4.511842|
|50%	|27.000000	|0.000000	4.261680	|6.162928	|5.769870	|5.771635|
|75%	|30.000000	|0.000000	7.085002	|6.622978	|7.923503	|6.409583|
|max	|52.000000	|1.000000	9.999920	|9.803837	|9.999770	|10.000000|

Table diatas memberikan informasi statistik pada masing-masing kolom, antara lain:

- Count adalah jumlah sampel pada data.
- Mean adalah nilai rata-rata.
- Std adalah standar deviasi.
- Min yaitu nilai minimum setiap kolom.
- 25% adalah kuartil pertama. Kuartil adalah nilai yang menandai batas interval - dalam empat bagian sebaran yang sama.
- 50% adalah kuartil kedua, atau biasa juga disebut median (nilai tengah).
- 75% adalah kuartil ketiga.
- Max adalah nilai maksimum.

**Mengecek duplikat**
| Data Dupliat                        |
|-------------------------------------|
| 1028                               |

Terdapat 1028 duplikat pada dataset

**Mengecek Outlier**
- Berikut adalah visualisasi data numerik menggunakan boxplot untuk mengecek outlier
    ![alt text](https://github.com/Lucknutgacor999/Predicitve_analytics/blob/main/resource/boxplot%20outlier%20age.png?raw=true) 
    ![alt text](https://github.com/Lucknutgacor999/Predicitve_analytics/blob/main/resource/Boxplot%20Outlier%20IS.png?raw=true) 
    ![alt text](https://github.com/Lucknutgacor999/Predicitve_analytics/blob/main/resource/Boxplot%20Outlier%20TS.png?raw=true) 
    ![alt text](https://github.com/Lucknutgacor999/Predicitve_analytics/blob/main/resource/boxplot%20outlier%20JS.png?raw=true) 
    ![alt text](https://github.com/Lucknutgacor999/Predicitve_analytics/blob/main/resource/boxplot%20outlier%20SS.png?raw=true)

Dari visualisasi pada boxplot dapat diketahui terdapat 3 kolom yang memiliki nilai outlier 

**Mengecek Missing Values**

  | Column                              | Value |
  |-------------------------------------|-------|
  | Age                                 | 0     |
  | Gender                              | 0     |
  | Education                           | 0     |
  | Introversion Score                  | 0     |
  | Sensing Score                       | 0     |
  | Thinking Score                      | 0     |
  | Judging Score                       | 0     |
  | Interest                            | 0     |
  | Personality                         | 0     |

- Pada tabel diatas didapati bahwa tidak terdapat missing value pada dataset.

| Jumah Baris                           | Jumlah Kolom |
|---------------------------------------|--------------|
| 43744                                  | 9   |

## Data Preparation

### Exploratory Data Analysis - Menangani Duplikat dan Outliers

| #  | Column                            | Non-Null Count | Dtype   |
|----|------------------------------------|----------------|---------|
| 0  | Age                             |  43744 non-null   | int64 |

- Mengganti tipe data age dari float ke integer dilakukan karena usia secara logis direpresentasikan sebagai bilangan bulat—tidak masuk akal untuk menyatakan usia seseorang sebagai 25.7 tahun dalam konteks kebanyakan analisis atau pemodelan. Selain itu, konversi ini membantu menyederhanakan data, mengurangi kompleksitas, dan menghindari potensi kesalahan pembulatan atau interpretasi saat model machine learning memproses fitur tersebut.

- Sebanyak 1028 data akan dihapus karena duplikat bertujuan untuk memastikan model machine learning belajar dari pola yang sebenarnya, bukan dari data yang berulang secara tidak wajar. Ini membantu mencegah bias, overfitting, serta meningkatkan akurasi dan generalisasi model, sekaligus menghemat waktu dan sumber daya komputasi.

**Menangani Outlier** 

- Untuk mengetahui apakah data dapat dikatakan outlier dapat dilihat menggunakan teknik visualisasi, yaitu jenis boxplot.
  
  ![alt text](https://github.com/Lucknutgacor999/Predicitve_analytics/blob/main/resource/boxplot%20outlier%20JS.png?raw=true)
     
   - Pada gambar terlihat, apabila data melebihi rentang Minimum atau Maximum, maka dapat dikatakan outlier.

- Outlier merupakan rentang nilai yang melebihi batas Minimum dan Maximum. Berdasarkan hasil dari visualisasi boxplot yang dilakukan dapat dilihat:

   ![alt text](https://github.com/Lucknutgacor999/Predicitve_analytics/blob/main/resource/boxplot%20outlier%20SS.png?raw=true)

   ![alt text](https://github.com/Lucknutgacor999/Predicitve_analytics/blob/main/resource/boxplot%20outlier%20JS.png?raw=true)  
        
- Berdasarkan visualisasi yang ditampilkan, dapat disimpulkan bahwa fitur age, judging_score, dan sensing_score mengandung outlier, yang ditunjukkan oleh adanya nilai-nilai data yang berada di luar rentang maksimum normal. Setelah memastikan keberadaan outlier, dilakukan penanganan menggunakan metode IQR (Interquartile Range), yaitu dengan mengganti nilai-nilai outlier menggunakan batas bawah (lower bound) dan batas atas (upper bound) sesuai hasil perhitungan IQR. Pendekatan ini bertujuan untuk menjaga distribusi data tetap representatif tanpa menghapus baris data yang ada.

   ![alt text](https://github.com/Lucknutgacor999/Predicitve_analytics/blob/main/resource/age%20after%20outlier_rv.png?raw=true) 

   ![alt text](https://github.com/Lucknutgacor999/Predicitve_analytics/blob/main/resource/SS%20after%20outlier_rv.png?raw=true) 
    
   ![alt text](https://github.com/Lucknutgacor999/Predicitve_analytics/blob/main/resource/JS%20after%20outlier_rv.png?raw=true)

  dari visualisasi diatas dapat disimpulkan bahwa masalah outlier telah diselesaikan karena outlier sudah berhasil diubah.

### Exploratory Data Analysis - Univariate Analysis

- univariate analysis bertujuan untuk memvisualisasikan dan menganalisis setiap fitur atau variabel secara individual dalam dataset, sehingga dapat memberikan pemahaman mendalam tentang distribusi dan karakteristik data pada masing-masing fitur tersebut.

**Univariate Analysis - Fitur Kategori**

![alt text](https://github.com/Lucknutgacor999/Predicitve_analytics/blob/main/resource/univariate%20gender.png?raw=true)

Distribusi gender pada dataset menunjukkan bahwa individu didominasi oleh jenis kelamin laki-laki dengan jumlah 23.598 orang, sedangkan individu perempuan berjumlah 19.118 orang.

![alt text](https://github.com/Lucknutgacor999/Predicitve_analytics/blob/main/resource/univariate%20interest.png?raw=true)

Pada variabel Interest, mayoritas individu tercatat dalam kategori Unknown sebanyak 15.087 orang, yang berarti lebih dari sepertiga data tidak memiliki informasi minat yang jelas. Sementara itu, minat lainnya tersebar pada bidang Arts (8.249), Sports (6.774), Others (6.654), dan Technology (5.952).

![alt text](https://github.com/Lucknutgacor999/Predicitve_analytics/blob/main/resource/univariate%20personalitas.png?raw=true)

Variabel Personality menunjukkan distribusi yang relatif seimbang untuk hampir semua kelas tipe MBTI, dengan masing-masing tipe memiliki 2.734 data poin, kecuali tipe ISTJ, yang hanya berjumlah 1.706 data poin.

**Univariate Analysis - Fitur Numerik**

![alt text](https://github.com/Lucknutgacor999/Predicitve_analytics/blob/main/resource/numerical.png?raw=true)

Pada histogram diatas dapat disimpulkan bahwa:

- Distribusi usia pada dataset menunjukkan bahwa individu didominasi oleh kelompok usia muda, dengan puncak tertinggi pada rentang 24-26 tahun yang mencapai sekitar 3.500+ individu. Distribusi membentuk kurva normal dengan ekor panjang ke kanan, menunjukkan mayoritas individu berusia produktif muda (19-35 tahun) dengan sangat sedikit yang berusia di atas 35 tahun.

- Distribusi pendidikan pada dataset menunjukkan ketimpangan yang sangat ekstrem, dimana hampir seluruh individu memiliki tingkat pendidikan rendah (nilai mendekati 0) dengan jumlah mencapai 33.000+ individu, sedangkan individu berpendidikan tinggi (nilai 1) hanya berjumlah sekitar 10.000 individu. Hal ini mengindikasikan adanya bias pendidikan yang sangat signifikan dalam dataset.

- Introversion Score Menunjukkan distribusi yang relatif merata di seluruh spektrum (0-10) dengan slight peak di nilai tengah, mengindikasikan keseimbangan antara individu introvert dan ekstrovert

- Sensing Score Didominasi oleh individu dengan preferensi sensing (nilai 6-7) mencapai 3.500+ individu, menunjukkan mayoritas cenderung praktis dan detail-oriented

- Thinking Score Distribusi condong ke nilai tinggi (6-10) dengan puncak di nilai 8-10, mengindikasikan mayoritas individu memiliki preferensi pengambilan keputusan berbasis logika

- pada Judging Score Mayoritas individu memiliki preferensi judging (nilai 6-7) dengan jumlah 3.500+ individu, menunjukkan kecenderungan terstruktur dan terencana dalam hidup

### Exploratory Data Analysis - Multivariate Analysis

multivariate analysis bertujuan untuk memvisualisasikan data guna memahami hubungan antara dua atau lebih fitur dalam dataset. Teknik ini membantu mengidentifikasi pola, korelasi, atau interaksi antar fitur yang dapat memberikan wawasan lebih mendalam tentang struktur data.

**Multivariate Analysis**

![alt text](https://github.com/Lucknutgacor999/Predicitve_analytics/blob/main/resource/multivariate%20age%20new.png?raw=true)

![alt text](https://github.com/Lucknutgacor999/Predicitve_analytics/blob/main/resource/multivariate%20education%20new.png?raw=true)

![alt text](https://github.com/Lucknutgacor999/Predicitve_analytics/blob/main/resource/multivariate%20TS%20new.png?raw=true)

![alt text](https://github.com/Lucknutgacor999/Predicitve_analytics/blob/main/resource/multivariate%20SS%20new.png?raw=true)

![alt text](https://github.com/Lucknutgacor999/Predicitve_analytics/blob/main/resource/multivariate%20JS%20new.png?raw=true)

![alt text](https://github.com/Lucknutgacor999/Predicitve_analytics/blob/main/resource/multivariate%20IS%20new.png?raw=true)

Pada visualisasi terhadap fitur, dapat disimpulkan:

- Semua tipe kepribadian menunjukkan distribusi usia yang konsisten dengan median 25-29 tahun dan rentang 19-39 tahun. Tipe ISTJ memiliki median tertinggi sekitar 30 tahun, mengindikasikan dataset didominasi dewasa muda di semua kategori kepribadian.
- Terdapat bias pendidikan ekstrem dimana hanya 8 tipe kepribadian (ENTP, INTP, ESFP, ISFP, INFP, ESTP, ENFP, ISTP) memiliki individu berpendidikan tinggi, sedangkan 8 tipe lainnya seluruhnya berpendidikan rendah.
- Introversion: Tipe Introvert memiliki median 2-3, tipe Ekstrovert median 7-8
- Sensing: Tipe Sensing memiliki median 6-7, tipe Intuitive median 4-5
- Thinking: Tipe Thinking memiliki median 8-9, tipe Feeling median 2-4
- Judging: Tipe Judging memiliki median 6-7, tipe Perceiving median 4-5

untuk lebih jelasnya kita akan melihat dengan correlation matrix pada gambar dibawah.

![alt text](https://github.com/Lucknutgacor999/Predicitve_analytics/blob/main/resource/korelasi.png?raw=true)

Berdasarkan correlation matrix untuk fitur numerik, kesimpulan yang dapat diambil adalah

Korelasi Antar Variabel:
Matrix menunjukkan korelasi yang sangat lemah antar semua variabel dengan nilai berkisar -0.3 hingga 0.17. Korelasi terkuat adalah:

- Age vs Sensing Score: 0.17 (korelasi positif lemah - individu lebih tua cenderung sedikit lebih sensing)
- Education vs Judging Score: -0.3 (korelasi negatif lemah - individu berpendidikan tinggi cenderung sedikit kurang judging)

Karakteristik Umum:
Mayoritas korelasi berada di rentang -0.02 hingga 0.02, yang menunjukkan tidak ada hubungan linear yang signifikan antar variabel. Hal ini mengindikasikan bahwa:

- Faktor demografis (usia, pendidikan) tidak berpengaruh kuat terhadap skor kepribadian
- Dimensi kepribadian (introversion, sensing, thinking, judging) relatif independen satu sama lain
- Dataset memiliki variabel yang sebagian besar tidak saling berkorelasi, yang baik untuk analisis multivariat

Kesimpulan:
Tidak ada multikolinearitas yang signifikan dalam dataset, memungkinkan penggunaan semua variabel untuk pemodelan tanpa masalah redundansi.

## Data Preparation

Pada bagian ini ada tiga tahap persiapan data yang dilakukan, yaitu:

- Encoding fitur kategori.
- Pembagian dataset dengan fungsi train_test_split dari library sklearn.
- Standarisasi.

**Encoding fitur kategori**

pada dataset kita terdapat 2 fitur categorical yang akan diubah menjadi data numerik yaitu: 

- fitur gender dan interest akan diubah menggunakan LabelEncoder.

Fitur kategori perlu diubah menjadi data numerik karena sebagian besar algoritma machine learning tidak dapat bekerja secara langsung dengan data non-numerik.

**Train-Test-Split**

Sebelum melakukan train-test-split, langkah awalnya adalah memisahkan antara fitur dan label. Variabel x digunakan untuk menyimpan fitur yang terdiri dari:

- age
- gender
- education
- Introversion Score
- Sensing Score
- Thinking Score
- Judging Score
- Interest	

Sedangkan variabel y digunakan untuk menyimpan label yaitu personality.

Selanjutnya, dilakukan train-test-split dengan pembagian data sebesar 80:20 antara data latih (train) dan data uji (test). Dari total 42716 data, setelah dilakukan pembagian, data terbagi menjadi 34172 untuk data latih dan 8544 untuk data uji.

**Standarisasi**

Algoritma machine learning memiliki performa lebih baik dan konvergen lebih cepat ketika dimodelkan pada data dengan skala relatif sama atau mendekati distribusi normal. Proses scaling dan standarisasi membantu untuk membuat fitur data menjadi bentuk yang lebih mudah diolah oleh algoritma. 

Selanjutnya dilakukan standarisasi dengan StandartScaler pada 5 fitur yaitu:

- age	
- Introversion Score
- Sensing Score
- Thinking Score
- Judging Score

**Jadi mengapa perlu dilakukan data prepration?**

- Data kategorikal perlu diubah ke dalam format numerik melalui proses encoding, karena mayoritas algoritma machine learning tidak mampu memproses data non-numerik secara langsung.

- Pemisahan data menjadi set pelatihan dan pengujian penting untuk mengukur performa model pada data yang belum pernah dilihat sebelumnya, sehingga memberikan evaluasi yang lebih realistis terhadap kemampuan generalisasi model.

- Standarisasi fitur membantu menyamakan skala data, yang membuat algoritma machine learning bekerja lebih efisien dan mempercepat proses konvergensi, terutama ketika data memiliki distribusi yang mendekati normal.

## Modeling

Model machine learning yang digunakan untuk masalah ini terdiri dari 3 model yaitu:

**1. K-Nearest Neighbor**

- **Cara Membuat Model**:

  1.   ```from sklearn.neighbors import KNeighborsClassifier```

       - Mengimpor class `KNeighborsClassifier` dari pustaka scikit-learn.

  2.   ```KNN = KNeighborsClassifier()```

       - Membuat objek dari class `KNeighborsClassifier` dengan parameter default.

  3.   ```knn.fit(X_train, y_train)```

       - Memanggil metode fit untuk melatih model `KNeighborsClassifier` menggunakan data pelatihan `X_train` dan `y_train`.

       - `X_train`: Matriks fitur yang digunakan dalam pelatihan model.

       - `y_train`: Label target untuk data pelatihan.

- **Cara Kerja Model**:
  - K-Nearest Neighbors bekerja dengan mencari sejumlah tetangga terdekat dalam ruang fitur yang memiliki nilai target serupa. Setelah tetangga ditemukan, model akan menggunakan nilai rata-rata dari tetangga tersebut untuk membuat prediksi nilai target untuk data baru.

---

**2. Logistic Regression**

- **Cara Membuat Model**:

  1.   ```from sklearn.linear_model import LogisticRegression```

       - Mengimpor class `LinearRegression` dari pustaka scikit-learn.

  2.   ```LogisticRegression(multi_class='multinomial', max_iter=1000, random_state=42)```

       - Membuat objek dari class `LogisticRegression` dengan parameter yang ditentukan.

          - **Penjelasan Parameter**:

            - `multi_class='multinomial'`: Menentukan pendekatan klasifikasi multikelas. Dengan opsi 'multinomial', model menghitung probabilitas untuk semua kelas sekaligus menggunakan regresi logistik multinomial (softmax), bukan membuat model biner satu per satu seperti pada pendekatan one-vs-rest.

            - `max_iter=1000`: Jumlah maksimum iterasi yang diperbolehkan untuk algoritma optimisasi selama pelatihan. Nilai ini membantu model untuk mencapai konvergensi, terutama pada data yang kompleks atau banyak fitur.

            - `random_state=42`: Nilai acak yang digunakan untuk memastikan hasil yang konsisten dan dapat direproduksi. Angka 42 dipilih sebagai seed, sehingga proses yang melibatkan randomisasi (seperti pengaturan bobot awal) menghasilkan hasil yang sama setiap kali model dilatih.

  3.   ```logistic_regressor.fit(X_train, y_train)```

       - Melatih model LogisticRegression menggunakan data pelatihan X_train dan label target y_train.

       - `X_train`: Matriks fitur untuk melatih model.

       - `y_train`: Nilai target yang sesuai dengan data fitur dalam `X_train`.

- **Cara Kerja Model**:
  - Logistic Regression digunakan untuk masalah klasifikasi, bukan regresi. Model ini menghitung probabilitas suatu data termasuk dalam suatu kelas menggunakan fungsi sigmoid, yang membatasi output antara 0 dan 1.

---

**3. RandomForestClassifier** 

- **Cara Membuat Model**: 

  1.   ```from sklearn.ensemble import RandomForestClassifier``` 

       - Mengimpor class `RandomForestClassifier` dari pustaka scikit-learn.

  2.   ```RF = RandomForestClassifier(n_estimators=50, max_depth=16, random_state=42, n_jobs=-1)``` 

       - Membuat objek dari class `RandomForestClassifier` dengan parameter yang ditentukan.

          - **Penjelasan Parameter**:

              - `n_estimators=50`: Menentukan jumlah pohon keputusan yang digunakan dalam hutan (forest).

              - `max_depth=16`: Menentukan kedalaman maksimum pohon-pohon keputusan dalam hutan untuk menghindari overfitting.

              - `random_state=42`: Seed generator untuk memastikan hasil dapat diulang.

              - `n_jobs=-1`: Menentukan jumlah core yang digunakan. Jika diatur ke -1, model akan menggunakan semua core yang tersedia.

  3.   ```RF.fit(X_train, y_train)``` 

       - Memanggil metode fit untuk melatih model `RandomForestClassifier` menggunakan data pelatihan `X_train` dan `y_train`.

       - `X_train`: Matriks fitur yang digunakan untuk pelatihan.

       - `y_train`: Nilai target yang sesuai dengan `X_train`.

- **Cara Kerja Model**: 
  - Random Forest bekerja dengan membangun banyak pohon keputusan (decision trees) secara acak dan menggabungkan hasilnya untuk membuat prediksi. Setiap pohon dilatih pada subset acak dari data pelatihan dan subset acak dari fitur, sehingga mengurangi overfitting. Hasil dari semua pohon kemudian diambil rata-ratanya (regresi) atau suara mayoritas (klasifikasi) untuk menghasilkan prediksi akhir.

---

**Kelebihan dan Kekurangan 3 model tersebut?**.

- **Random Forest**
  - **Kelebihan:**
    - Menggabungkan hasil dari banyak pohon keputusan untuk menghasilkan prediksi yang lebih akurat dan robust.
    - Memiliki mekanisme built-in untuk menangani overfitting.
    - Dapat menangani data yang hilang dengan baik.

  - **Kekurangan:**
    - Lebih lambat dalam pelatihan dan prediksi dibandingkan model sederhana seperti linear regression.
    - Model yang dihasilkan sulit untuk diinterpretasikan secara langsung.
    - Memerlukan lebih banyak memori dibandingkan model yang lebih sederhana.

- **Logistic Regression**
  - **Kelebihan:**
    - Sederhana, cepat, dan efisien untuk klasifikasi biner dan multikelas pada dataset kecil hingga menengah.
    - Hasil model mudah diinterpretasikan karena koefisien menunjukkan pengaruh masing-masing fitur.
    - Tidak membutuhkan banyak resource dan konvergen dengan cepat saat pelatihan.
    - Memberikan output probabilistik, sehingga berguna untuk analisis risiko atau ambang klasifikasi yang fleksibel.

  - **Kekurangan:**
    - Tidak cocok untuk data non-linear kecuali dilakukan transformasi fitur atau digunakan teknik tambahan seperti polynomial features.
    - Performa menurun jika terdapat multikolinearitas antar fitur.
    - Sensitif terhadap outlier dan fitur yang tidak diskalakan.
    - Asumsinya bahwa hubungan antara fitur dan logit target adalah linear bisa membatasi fleksibilitas model.

- **K-Nearest Neighbors (KNN)**
  - **Kelebihan:**
    - Sangat mudah dipahami dan diimplementasikan karena merupakan metode berbasis instance (lazy learner).
    - Cocok untuk data yang distribusinya tidak diketahui dan tidak memerlukan pelatihan eksplisit.
    - Dapat digunakan baik untuk klasifikasi maupun regresi.
    - Tidak membuat asumsi khusus terhadap distribusi data (non-parametrik).

  - **Kekurangan:**
    - Waktu prediksi lambat karena membutuhkan pencarian tetangga terdekat di seluruh data setiap kali - - - prediksi dilakukan.
    - Sensitif terhadap skala data—fitur perlu dinormalisasi agar hasil tidak bias.
    - Rentan terhadap noise dan outlier, terutama jika nilai K terlalu kecil.
    - Kurang efektif untuk dataset besar karena kebutuhan komputasi tinggi saat prediksi.

## Evaluation
Untuk mengevaluasi kinerja model klasifikasi dalam memprediksi tipe kepribadian berdasarkan fitur-fitur yang tersedia, digunakan salah satu metrik klasifikasi, yaitu Accuracy, Metrik ini digunakan untuk menilai seberapa baik model dalam membedakan kelas target secara akurat.

**Evaluasi Model Machine Learning**
Model Accuracy Comparison:
|          |RandomForest       |KNN    |LogReg|
|----------|-------------------|-------|------|
|train_acc |0.99207            |0.842649  |0.782249|
|test_acc  |0.898759           |0.754096  |0.784293|

- Performa Model pada Training Set:
Random Forest menunjukkan performa terbaik dengan akurasi 99.21%, diikuti KNN dengan 84.26%, dan Logistic Regression dengan 78.22%. Random Forest hampir mencapai akurasi sempurna pada data training.
- Performa Model pada Test Set:
Random Forest tetap mempertahankan posisi terbaik dengan akurasi 89.88%, diikuti Logistic Regression dengan 78.43%, dan KNN dengan 75.41%. Menariknya, Logistic Regression berhasil melampaui KNN pada test set.


## Kesimpulan
Dari hasil analisis dan evaluasi yang telah dilakukan, dapat disimpulkan bahwa model yang diusulkan berhasil menjawab kedua rumusan masalah yang diajukan. Pertama, melalui analisis multivariate, model mengidentifikasi bahwa Education adalah fitur yang paling berpengaruh terhadap personalitas seorang individu. Kedua, model mampu mengklasifikasi personalitas individu berdasarkan fitur-fitur tersebut dengan akurasi yang baik. Dalam pencapaian goals, model yang dikembangkan mencapai tujuan yang diharapkan, yaitu mengetahui fitur yang paling berkorelasi dengan personalitas dan membuat model machine learning yang dapat mengklasifikasikan personalitas individu secara akurat. Hasil evaluasi menunjukkan bahwa model Random Forest memiliki kesalahan akurasi yang tinggi baik pada data latih maupun data test, menandakan bahwa mereka efektif dalam melakukan klasifikasi. Dampak dari solusi yang diterapkan, termasuk analisis visualisasi data dan penerapan berbagai algoritma machine learning, berdampak positif dalam memberikan pemahaman yang lebih mendalam tentang hubungan antar fitur dan personalitas. Ini tidak hanya membantu dalam memahami struktur data, tetapi juga dalam pengambilan keputusan strategis di berbagai sektor. Misalnya, perusahaan rekrutmen dapat menggunakan informasi ini untuk mencocokkan kandidat dengan posisi kerja yang sesuai berdasarkan tipe kepribadian mereka, sehingga meningkatkan produktivitas dan kepuasan kerja. Selain itu, platform e-learning dapat menyesuaikan gaya penyampaian materi berdasarkan personalitas pengguna, membuat proses belajar menjadi lebih efisien dan menyenangkan.

## Referensi

A Machine Learning Approach for Personality Type Identification using MBTI Framework [_( Link Google Scholar )_](https://jisrc.szabist.edu.pk/ojs/index.php/jisrc/article/view/42)

KLASIFIKASI KEPRIBADIAN MENGGUNAKAN ALGORITMA MACHINE LEARNING [_( Link Google Scholar )_](https://researchhub.id/index.php/jitek/article/view/1292)
