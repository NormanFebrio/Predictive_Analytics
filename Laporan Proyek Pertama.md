# Laporan Proyek Machine Learning - Norman Dwi Febrio

## Domain Proyek

Dalam menghadapi masalah lingkungan yang semakin meningkat dan meningkatnya permintaan akan kehidupan yang berkelanjutan, mengoptimalkan penggunaan energi dalam bangunan telah menjadi tujuan utama. Efisiensi energi tidak hanya mengurangi dampak lingkungan, tetapi juga secara signifikan menurunkan biaya operasional bagi pemilik rumah dan bisnis. Proyek ini bertujuan untuk memanfaatkan kekuatan ilmu data untuk mengembangkan model prediktif yang dapat secara akurat memperkirakan efisiensi energi bangunan.


### Mengapa dan Bagaimana Masalah Ini Harus Diselesaikan

Bangunan mengkonsumsi sebagian besar sumber daya energi dunia. Pemodelan prediktif memainkan peran penting dalam bidang efisiensi energi, yang memungkinkan arsitek, insinyur, dan pembuat kebijakan untuk membuat keputusan yang tepat. Dengan memahami hubungan antara berbagai fitur bangunan dan konsumsi energi, menjadi mungkin untuk merancang struktur yang ramah lingkungan dan layak secara ekonomi.


## Business Understanding

Di dunia yang berkembang pesat saat ini, efisiensi energi menjadi landasan pembangunan berkelanjutan. Lanskap bisnis semakin dibentuk oleh kesadaran lingkungan, tuntutan peraturan, dan konsumen yang sadar akan biaya. Dalam konteks ini, para pelaku bisnis, arsitek, dan pembuat kebijakan mencari solusi inovatif untuk mengoptimalkan penggunaan energi, terutama di sektor konstruksi di mana bangunan menyumbang sebagian besar konsumsi energi global. Proyek ini membahas masalah-masalah yang mendesak ini dengan menggunakan teknik pemodelan prediktif untuk meningkatkan pemahaman tentang efisiensi energi pada bangunan.

Dampak dari penggunaan model ini terhadap ekonomi adalah pengembang dan arsitek dapat merancang bangunan yang lebih efisien secara energi. Hal ini akan mengurangi biaya pemanasan dan pendinginan, menghasilkan penghematan yang substansial bagi pemilik bangunan dan penghuni. Selain itu, pengurangan konsumsi energi juga berpotensi meningkatkan nilai properti, menciptakan peluang investasi yang lebih baik.

Adapun dampak bagi lingkungan adalah dapat membantu memperlambat perubahan iklim global karena pengurangan emisi gas rumah kaca dari pembangkitan energi. Selain itu, penghematan energi berarti mengurangi kebutuhan akan sumber daya energi fosil, membantu pelestarian sumber daya alam yang terbatas.


### Problem Statements

Berdasarkan dari penjelasan di atas, akan dikembangkan sebuah sistem prediksi efisiensi energi pada bangunan untuk menjawab permasalahan berikut:
1. Faktor apa saja yang memiliki pengaruh terhadap efisiensi energi?
2. Berapa beban pemanasan dan pendinginan jika suatu bangunan memiliki ciri tertentu?

### Goals

Tujuan dari dibuatnya proyek ini yaitu:
1. Mengetahui faktor apa saja yang memiliki pengaruh terhadap efisiensi energi.
2. Membuat model machine learning yang dapat memprediksi beban pemanasan dan pendinginan jika suatu bangunan memiliki ciri tertentu.

### Solution Statements

Solusi yang dapat diimplementasikan untuk mencapai tujuan adalah sebagai berikut:
1. Mengembangkan beberapa model machine learning, baik menggunakan Deep Learning, K-Nearest Neighbor, Random Forest, dan Boosting Algorithm.
2. Memilih model terbaik yang telah dikembangkan dengan mempertimbangkan nilai metrik evaluasi yang didapatkan.


## Data Understanding

Dataset yang  digunakan untuk menyelesaikan proyek ini adalah dataset "Effiency Energy" yang dibuat oleh Athanasios Tsanas dan Angeliki Xifara. Mereka melakukan analisis energi menggunakan 12 bentuk bangunan yang berbeda yang disimulasikan pada Ecotect. Bangunan-bangunan tersebut berbeda dalam hal area kaca, distribusi area kaca, dan orientasi, di antara parameter lainnya. Mereka mensimulasikan berbagai pengaturan sebagai fungsi dari karakteristik yang telah disebutkan sebelumnya untuk mendapatkan 768 bentuk bangunan. Kumpulan data terdiri dari 768 sampel dan 8 fitur, yang bertujuan untuk memprediksi dua respons nilai asli.

Dataset ini memiliki total 10 variabel, 2 di antaranya adalah target. Berikut adalah penjelasan dari tiap kolom:
1. Relative_compactness: Merepresentasikan se-padat apa bangunan tersebut.
2. Surface_area: Total luas permukaan bangunan (dinding, lantai, dan atap) dalam satuan meter persegi.
3. Wall_area: Luas dinding bangunan (eksterior dan interior) dalam satuan meter persegi.
4. Roof_area: Luas atap bangunan dalam satuan meter persegi.
5. Overall_height: Ketinggian total bangunan dalam satuan meter.
6. Orientation: Arah hadap bangunan. Direpresentasikan dalam bentuk data kategorik nominal (2 - 5). 2: Utara. 3: Timur. 4: Selatan. 5: Barat.
7. Glazing_area: Luas area kaca atau jendela pada bangunan dalam satuan meter persegi.
8. Glazing_area_distribution: Persebaran letak kaca atau jendela pada bangunan. Direpresentasikan dalam bentuk data kategorik nominal (0 - 5). 0: Bangunan tersebut tidak memiliki kaca atau jendela. 1: Bangunan tersebut memiliki persebaran kaca yang merata di tiap arah (masing-masing 25%). 2: Bangunan tersebut memiliki persebaran kaca sebanyak 55% di arah utara, dan sisanya masing-masing 15%. 3: Bangunan tersebut memiliki persebaran kaca sebanyak 55% di arah timur, dan sisanya masing-masing 15%. 4: Bangunan tersebut memiliki persebaran kaca sebanyak 55% di arah selatan, dan sisanya masing-masing 15%. 5: Bangunan tersebut memiliki persebaran kaca sebanyak 55% di arah barat, dan sisanya masing-masing 15%.
9. Heating_load: Kebutuhan energi (dalam kW) untuk mempertahankan suhu di dalam bangunan pada saat pemanasan.
10. Cooling_load: kebutuhan energi (dalam kW) untuk mempertahankan suhu di dalam bangunan pada saat pendinginan.

Dataset tersebut dapat diakses melaluli link ini: https://archive.ics.uci.edu/dataset/242/energy+efficiency.

### Exploratory Data Analysis

#### Tipe Data Tiap Kolom

Tipe data dari tiap variabel pada dataset ini merupakan numerik semua (float dan integer). Namun, untuk variabel yang bertipe data integer ("Orientation" dan "Glazing_area_distribution"), merupakan variabel kategorik.

#### Missing Values

Dataset ini tidak memiliki missing values. 

#### Informasi Statistik

Dataset ini memiliki ringkasan data statistik sebagai berikut:
- Kepadatan relatif memiliki nilai rentang antara 62% sampai dengan 98% dengan nilai rata-rata 0.76 dan median 0.75. Semakin tinggi nilainya, semakin padat pula bangunannya.
- Luas total permukaan memiliki nilai rentang antara 514.5 meter persegi sampai dengan 808.5 meter persegi dengan nilai rata-rata 671.7 dan median 673.7.
- Luas dinding memiliki nilai rentang antara 245 meter persegi sampai dengan 416.5 meter persegi dengan nilai rata-rata 318.5 meter persegi dan median 318.5 meter persegi.
- Luas atap memiliki nilai rentang antara 110.25 meter persegi sampai dengan 220.5 meter persegi dengan nilai rata-rata 176.6 meter persegi dan median 183.75 meter persegi.
- Tinggi keseluruhan memiliki nilai rentang antara 3.5 meter sampai dengan 7 meter dengan nilai rata-rata 5.25 meter dan median 5.25 meter persegi.
- Luas kaca atau jendela memiliki nilai rentang antara 0% sampai dengan 40%.

#### Sebaran Data Tiap Variabel

Tujuan dari mengetahui sebaran data dari tiap variabel adalah mencari tahu data yang dikumpulkan lebih banyak tersebar di salah satu sisi atau persebaran yang normal. Berikut adalah sebaran data dari tiap variabel.

![png](output_38_0.png)

Ternyata, sebaran dari tiap atribut cenderung condong ke salah satu sisi. Dengan demikian pada tahapan normalisasi,  diperlukan penggunaan metode Standardisasi.

#### Korelasi Antar Variabel

Sebelum menggunakan atribut-atribut yang ada untuk melatih model, diperlukan mengetahui korelasi antar variabel agar variabel yang digunakan untuk melatih model adalah variabel yang memang memiliki pengaruh dengan target. Berikut adalah korelasi antar variabel.

![png](output_41_1.png)

Dari grafik heatmap di atas, dapat disimpulkan bahwa:
1. Hubungan tiap variabel, selain wall area dan glazing area, terhadap heating load dan coolling load memiliki korelasi di atas 60% semua. 
2. Surface area dan roof area berkorelasi negatif terhadap heating load dan cooling load.
3. Relative compactness, wall area, overall height, dan glazing area berkorelasi positif dengan heating load dan coolling load.
4. Relative compactness dengan surface area memiliki korelasi yang sangat tinggi dan surface area memiliki korelasi yang lebih tinggi dengan variabel lainnya daripada relative compactness. Hal ini dapat menyebabkan kolinearitas dan berdampak pada hasil prediksi model. Oleh karena itu, variabel surface area dapat dihapus untuk menghindari kolinearitas.

Setelah itu, cek korelasi variabel kategori dengan heating load dan cooling load.
    
![png](output_44_0.png)
    

Dari grafik batang di atas, dapat disimpulkan bahwa tiap kategori memiliki nilai yang tidak jauh beda. Artinya, mau bagaimanapun orientasi dari bangunan tersebut, heating load dan cooling load yang dibutuhkan sama saja. Dengan demikian, variabel ini dapat dihapus untuk mengurangi dimensionalitas.

Sedangkan untuk Glazing_area_distribution, berikut adalah diagramnya.
    
![png](output_47_0.png)
      
![png](output_48_0.png)

Selain 0, semua kategori memiliki pola yang identik. Dengan demikian, kategori ini dapat diubah menjadi kategori biner saja, yaitu 0 mewakili glazing area distribution 0, dan 1 mewakili semua glazing area distribution selain 0. Hal ini dilakukan untuk mengurangi dimensionalitas.

### Conclusion

Berdasarkan hasil ekslporasi yang didapatkan dari proses EDA, didapatkan kesimpulan:
1. Melakukan normalisasi pada tiap kolom numerik menggunakan metode standardisasi.
2. Menghapus variabel Surface_area untuk menghindari kolinearitas.
3. Menghapus variabel Orientation karena semua kategorinya memiliki nilai yang identik.
4. Melakukan binerisasi pada variabel Glazing_area_distribution. Nilai 0 untuk kategori 0, dan 1 untuk kategori selain 0.

## Data Preparation

Berdasarkan kesimpulan di atas, diperlukan beberapa tahapan pada variabel variabel dari dataset ini.

### Menghapus Kolom Surface_area dan Orientation

Tujuan dari menghapus kolom Surface_area adalah untuk menghindari dari kolinearitas yang dapat berdampak pada hasil prediksi model. Dan tujuan dari menghapus kolom Orientation adalah karena tiap kategorinya memiliki nilai yang identik.

### Melakukan Binerisasi Pada Kolom Glazing_area_distribution

Tujuan dari binerisasi ini adalah untuk mereduksi dimensionalitas dari dataset.

### Melakukan Normalisasi pada Atribut Numerik

Tujuan dilakukan normalisasi pada atribut numerik adalah agar semua atribut numerik pada dataset memiliki skala nilai yang seragam. Dengan menyeragamkan skala nilai pada seluruh atribut numerik, model yang dikembangkan dapat bekerja lebih efektif. 

Metode normalisasi yang akan digunakan pada tahapan ini adalah metode Standardisasi. Metode Standardisasi digunakan karena dataset yang digunakan saat ini memiliki sebaran nilai yang cenderung condong ke salah satu sisi. Setelah dilakukan standardisasi, variabel tersebut akan memiliki nilai rata-rata 0 dan standar deviasi 1. Adapun rumus dari Standardisasi adalah sebagai berikut.

$$ \text{Normalized Value} = \frac{\text{Value} - \text{μ}}{\text{σ}} $$

Keterangan:
- μ: Nilai rata-rata
- σ: Nilai standar deviasi

Untuk melakukannya pada notebook, bisa menggunakan `StandardScaler()` yang telah disediakan oleh modul scikit-learn.

### Melakukan Pemisahan Antara Atribut dengan Target

Pemisahan ini perlu dilakukan agar target tidak termasuk ke dalam data yang akan dilatihkan ke model.

### Melakukan Train-Test-Split

Dataset yang telah melalui beberapa tahapan kemudian dibagi menjadi subset train dan test. Hal ini dilakukan agar model dapat belajar pola dari data latih dan kemudian mengujinya menggunakan data yang belum pernah dipelajari oleh model, yaitu data uji. Karena dataset yang digunakan hanya terdiri dari 768 data, maka pembagian yang ideal adalah 80%:20%, yang mana 80% adalah data latih dan 20% adalah data uji.

Untuk melakukannya pada notebook, bisa menggunakan `train_test_split` yang telah disediakan oleh modul scikit-learn.    

### Memisahkan Variabel Target Heating Load dan Cooling Load

Karena dataset yang digunakan ini memiliki 2 target, yaitu Heating_load dan Cooling_load, maka diperlukan pemisahan dan menyimpannya dalam variabel yang berbeda. Nantinya, model akan dilatih 2 kali. Latihan yang pertama dilakukan untuk memprediksi Heating_load dan yang kedua untuk memprediksi Cooling_load.

## Modeling

Setelah selesai melakukan tahap preprocessing pada data, akhirnya dataset yang akan digunakan siap untuk diberikan pada model. Model akan mempelajari pola pada dataset dengan sendirinya.

Model yang akan digunakan untuk menyelesaikan permasalahan ini adalah Deep learning, K-Nearest Neighbor, Random Forest, dan Boosting Algorithm.


### Deep Learning

Pada model deep learning, akan menggunakan algoritma artifical neural network (ANN). Framework yang dapat digunakan untuk membuat ANN ada 2, yaitu TensorFlow dan PyTorch. Kedua framework ini memiliki kelebihan masing-masing. TensorFlow memiliki keunggulan dalam produksi, alat visualisasi (TensorBoard), dukungan perangkat keras khusus (TPUs), dan kerjasama dengan Google. PyTorch unggul dalam eksperimen penelitian, kegunaan Pythonic, fleksibilitas dengan grafik komputasi dinamis, dan popularitas dalam komunitas penelitian.

Framework yang akan digunakan pada proyek ini adalah TensorFlow. Berikut adalah ringkasan arsitektur model yang digunakan.
```
    tf.keras.layers.Dense(512, activation='relu', input_shape=[X_train.shape[1]]),
    tf.keras.layers.Dense(512, activation='relu'),
    tf.keras.layers.Dense(1)
    
    model.compile(loss="mean_absolute_error",
                      optimizer=tf.keras.optimizers.Adam(learning_rate=8e-4),
                     metrics=["mae"])
```
Penjelasan dari model tersebut adalah sebagai berikut:
- Model tersebut merupakan Artificial Neural Network dengan 3 lapisan (layers) Dense.
- Pada lapisan Dense pertama, lapisan ini merupakan lapisan masukan (input layer). Lapisan ini terdiri dari 512 neuron karena banyaknya data training yang digunakan adalah 514 data, sedangkan pemilihan banyaknya neuron disarankan agar tidak melebihi banyaknya data latih. Jika jumlah neuron melebihi banyaknya data, maka model akan berpeluang untuk overfitting.
- Pada lapisan Dense kedua, lapisan ini merupakan lapisan tersembunyi (hidden layer). Lapisan ini terdiri dari 512 neuron karena dapat menyelesaikan kompleksitas pada data latih.
- Pada lapisan ketiga, lapisan ini merupakan lapisan keluaran (output layer). Lapisan ini terdiri dari 1 neuron karena model yang akan dibuat akan digunakan untuk memprediksi nilai regresi linear.
- Fungsi aktivasi yang digunakan pada input dan hidden layer adalah Rectified Linear Unit (ReLU). Aktivasi ini digunakan karena dapat mempelajari pola-pola non-linear pada data.
- Fungsi aktivasi yang digunakan pada output layer adalah aktivasi by default (linear). Ini karena model yang dibuat akan digunakan untuk memprediksi nilai regresi linear.
- Arsitektur model tersebut di-compile dengan menggunakan kerugian mean absolute error, optimizer menggunakan Adam, dan menggunakan metrics mean absolute error.
- mean_absolute_error digunakan pada loss dan metrics karena model yang dilatih akan memprediksi nilai linear. Dengan menggunakan MAE, ini akan menampilkan nilai rata-rata kesalahan mutlak model dalam memprediksi nilai heating load maupun cooling load pada data latih.
- Optimizer yang digunakan adalah Adam karena optimizer ini dapat memberikan learning rate yang berbeda-beda untuk tiap parameter. Hal ini memungkinkan pengoptimalan yang lebih akurat dan efisien. learning rate yang digunakan adalah 8e-4 (8 * 10^-4) agar model dapat menemukan pola pada data secara perlahan dan lebih mudah untuk menemukan minimum lokal atau global.


### K-Nearest Neighbor

K-Nearest Neighbors (KNN) adalah salah satu algoritma machine learning yang digunakan untuk masalah klasifikasi dan regresi. Algoritma ini bekerja berdasarkan prinsip bahwa objek yang serupa cenderung berada dalam jarak yang dekat satu sama lain. KNN mengklasifikasikan atau memprediksi suatu data baru berdasarkan data pembelajaran (training data) yang memiliki kemiripan tertinggi dengan data baru tersebut. Algoritma ini sangat cocok jika data latih yang digunakan memiliki fitur yang sedikit.

Dalam penentuan nilai K, jika nilai K yang digunakan terlalu kecil, maka model akan overfit dan memiliki varians yang tinggi. Jika nilai K yang digunakan terlalu besar, maka model akan underfit dan memiliki bias yang tinggi. 

Untuk mendapatkan model terbaik dari algoritma ini, bisa menggunakan teknik Random Search.

`RandomizedSearchCV(estimator=KNeighborsRegressor(), param_distributions=param_dist, n_iter=15, random_state=42)`

Penjelasan dari kode di atas adalah:
- Menginisialisasi Random Search untuk mendapatkan model KNN terbaik.
- Pada parameter estimator, nilai yang diberikan adalah model KNN.
- Pada param_distributions, nilai yang diberikan adalah param_dist yang merupakan dictionary. Adapun isi dari param_dist adalah sebagai berikut: `{'n_neighbors':range(1,16), 'metric':['euclidean','manhattan','minkowski']}`
- pada n_neighbors, nilai yang digunakan adalah range(1,16). Artinya, nilai yang akan digunakan adalah angka 1 - 15 dan disimpan dalam bentuk list.
- pada metric, yang digunakan adalah 'euclidean','manhattan', dan 'minkowski'. Ketiga metric ini merupakan metode perhitungan jarak yang akan digunakan oleh model.


### Random Forest

Random forest merupakan salah satu model machine learning yang termasuk ke dalam kategori ensemble (group) learning. Ensemble model merupakan model prediksi yang terdiri dari beberapa model dan bekerja secara bersama-sama. Ide dibalik model ensemble adalah sekelompok model yang bekerja bersama menyelesaikan masalah. Sehingga, tingkat keberhasilan akan lebih tinggi dibanding model yang bekerja sendirian. Pada model ensemble, setiap model harus membuat prediksi secara independen. Kemudian, prediksi dari setiap model ensemble ini digabungkan untuk membuat prediksi akhir.

Model ensemble sendiri terdiri dari 2 teknik pendekatan, yaitu bagging dan boosting. Random forest termasuk ke dalam teknik bagging. Artinya, Random forest merupakan algoritma yang terdiri dari beberapa model, umumnya Decision Tree. Model decision tree masing-masing memiliki hyperparameter yang berbeda dan dilatih pada beberapa bagian (subset) data yang berbeda juga. Teknik pembagian data pada algoritma decision tree adalah memilih sejumlah fitur dan sejumlah sampel secara acak dari dataset yang terdiri dari n fitur dan m sampel.

Teknik Random Search akan digunakan juga pada model ini agar mendapatkan model terbaik.

`RandomizedSearchCV(estimator=rf, param_distributions=param_dist, n_iter=10, random_state=42)`

Penjelasan dari kode di atas:
- Menginisialisasi Random Search untuk mendapatkan model Random Forest terbaik.
- Pada parameter estimator, nilai yang diberikan adalah model Random Forest Regressor.
- Pada param_distributions, nilai yang diberikan adalah param_dist yang merupakan dictionary. Adapun isi dari param_dist adalah sebagai berikut: ```{
    'n_estimators': range(30, 151, 20), 'max_features': ['auto', 'sqrt', 'log2'],
    'max_depth': range(10, 101, 10), 'min_samples_split': [2, 5, 10], 'min_samples_leaf': [1, 2, 4]
  }```
- pada n_estimators, nilai yang digunakan adalah range(30, 151, 20). Artinya, jumlah pohon yang akan diujikan adalah dimulai dari 30 sampai 150 dengan jarak langkahnya adalah 20.
- pada max_features, menentukan jumlah fitur untuk di-split.
- pada max_depth, merupakan kedalaman maksimum pohon. Nilai yang digunakan adalah angka 10 sampai dengan 100 dengan kelipatan 10.
- pada min_samples_split, merupakan jumlah sample minimum yang dibutuhkan untuk split node.
- pada min_samples_leaf, merupakan jumlah sample minimum di leaf node.


### Boosting Algorithm

Boosting adalah sebuah teknik ensemble learning di machine learning yang digunakan untuk meningkatkan performa model prediksi. Tujuan utama dari teknik ini adalah menggabungkan beberapa model lemah (weak learners) menjadi satu model kuat (strong learner). Dalam konteks ini, "weak learners" adalah model prediksi yang memiliki akurasi yang sedikit lebih baik daripada tebakan acak, sedangkan "strong learner" adalah model yang memiliki akurasi prediksi yang tinggi. 

Di sini, Algoritma boosting yang  akan digunakan adalah AdaBoostRegressor, model ensemble dari scikit-learn. Teknik Random search digunakan kembali untuk mendapatkan model dengan parameter terbaik.

`RandomizedSearchCV(estimator=AdaBoostRegressor(), param_distributions=param_dist, n_iter=10, random_state=42)`

Penjelasan dari kode di atas adalah:
- Menginisialisasi Random Search untuk mendapatkan model Boosting terbaik.
- Pada parameter estimator, nilai yang diberikan adalah AdaBoostRegressor.
- Pada param_distributions, nilai yang diberikan adalah param_dist yang merupakan dictionary. Adapun isi dari param_dist adalah sebagai berikut: : `{'learning_rate': [1e-2, 5e-2, 1e-3, 5e-3, 1e-4, 5e-4], 'n_estimators': range(30, 211, 20)}`
- pada learning_rate, menentukan seberapa cepat model akan mempelajari data.
- pada n_estimators, nilai yang digunakan adalah angka dari 30 sampai dengan 210 dengan langkah 20.


## Evaluasi

Setelah semua model berhasil dilatih dan menyimpan hasil testnya dalam dataframe, sekarang saatnya mengevaluasi semua model. Metrik yang digunakan untuk menilai performa model adalah mean absolute error. Metrik ini digunakan karena dataset yang digunakan adalah dataset yang tidak memiliki outlier. Metrik ini juga lebih mudah dipahami oleh orang awam sekalipun karena nilai error yang didapatkan merupakan selisih nilai antara nilai asli dan nilai prediksi.

Adapun rumus dari mean absolute error adalah sebagai berikut:

$$ MAE = \frac{1}{n} \sum_{i=1}^{n} \left| y_i - \hat{y}_i \right| $$
Keterangan:
- y_i: Nilai asli 
- yhat_i: Nilai prediksi

Saatnya memeriksa nilai MAE dari tiap model.

![png](output_122_0.png)
    
Dari grafik di atas, ternyata Random Forest memiliki nilai MAE yang terkecil, baik dari segi Heating_load maupun Cooling_load. Artinya, model Random Forest dapat memprediksi nilai Heating_load dan Cooling_load dengan nilai error yang lebih kecil. Dengan demikian, untuk menyelesaikan permasalahan ini dapat menggunakan model Random Forest.