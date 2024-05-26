# Saudi Arabia Used Car

## **Context**

Penjualan mobil bekas di Saudi Arabia dipengaruhi dengan kondisi ekonomi termasuk pertumbuhan GDP dan tingkat pengangguran, fluktuasi harga minyak yang signifikan sebagai produsen minyak terkemuka, kebijakan pemerintah terkait impor dan pajak, serta tren konsumen terkait preferensi merek dan jenis mobil. Data-data tersebut dapat digunakan untuk mengidentifikasi pola penjualan bulanan atau tahunan, distribusi geografis penjualan, dan preferensi konsumen yang dapat memberikan wawasan mendalam tentang dinamika pasar mobil bekas di negara tersebut.
Faktor-faktor ekonomi yang terkait dengan Arab Saudi sebagai salah satu produsen minyak terbesar di dunia memiliki dampak yang signifikan terhadap pasar mobil bekas di negara tersebut. Ketersediaan bahan bakar yang lebih murah di Arab Saudi karena produksi minyak yang melimpah mendorong tingginya penggunaan kendaraan, terutama mobil. Dampak langsungnya adalah peningkatan permintaan pasar terhadap mobil, khususnya mobil bekas. Dengan demikian, kondisi ekonomi dan faktor-faktor terkait dengan produksi minyak di Arab Saudi secara langsung berkontribusi pada dinamika pasar mobil bekas di negara tersebut.

Penentuan harga mobil bekas didasarkan pada berbagai spesifikasi mobil seperti tahun pembuatan (usia mobil), total jarak tempuh, merek, dan faktor lainnya. Ketersediaan beragam mobil bekas dengan spesifikasi yang berbeda-beda membuat penentuan harga yang optimal menjadi aspek penting yang harus dipertimbangkan. Menetapkan harga yang tepat untuk mobil bekas dapat menentukan kefektifan dan keefisienan proses jual beli bagi kedua belah pihak, baik penjual maupun pembeli. Selain itu, penentuan harga ini berperan penting dalam menentukan tingkat keuntungan yang dapat diperoleh oleh penjual.

## **Problem Statement**

Tingginya permintaan mobil bekas di Arab Saudi membuat Perusahaan A sulit dalam menetapkan harga yang sesuai. Dalam persaingan yang ketat, penentuan harga mobil bekas yang tepat menjadi kunci untuk menganalisis apakah harga tersebut terlalu tinggi atau terlalu rendah. Dengan beragam pilihan mobil dan spesifikasinya, Perusahaan A ingin memiliki model bisnis yang memungkinkan mereka menetapkan harga yang kompetitif agar menarik minat banyak pelanggan. Hal ini juga memastikan pengalaman pelanggan yang optimal dalam menemukan mobil sesuai dengan spesifikasi dan harga yang diinginkan. Dengan begitu Perusahaan A dapat meningkatkan jumlah pelanggan dan pendapatan yang maksimal.

## **Goals**

Perusahaan A perlu mempunyai tools yang dapat memprediksi harga mobil bekas agar dapat membantu pelanggan menemukan mobil sesuai keinginan mereka. Kriteria yang perlu dipertimbangkan termasuk merek, tipe, jenis transmisi, asal, tahun, jarak tempuh, dan ukuran mesin. Hal ini diharapkan memberikan harga yang kompetitif namun menguntungkan. Dengan machine learning, diharapkan prediksi harga menjadi lebih efisien, menghemat waktu dan biaya.


## **Pendekatan Analisis**

Dalam pendekatan analisis ini, penting untuk melakukan proses analisis data guna mengidentifikasi pola dari berbagai fitur (kriteria) yang membedakan mobil satu dengan lainnya. Oleh karena itu, disini akan dikembangkan sebuah model regresi yang dapat membantu perusahaan dengan memiliki alat prediksi untuk harga mobil bekas dengan tingkat akurasi yang tinggi, yang akan berkontribusi pada peningkatan pendapatan perusahaan.

## **Metric Evaluation**
Evaluasi metrik yang akan digunakan adalah RMSE, MAE, dan MAPE, di mana :

RMSE adalah nilai rataan akar kuadrat dari error,
MAE adalah rataan nilai absolut dari error,
MAPE adalah rataan persentase error yang dihasilkan oleh model regresi.
Semakin kecil nilai RMSE, MAE, dan MAPE yang dihasilkan, semakin akurat model dalam memprediksi harga mobil bekas dengan mempertimbangkan limitasi fitur yang digunakan. Dua metric utama, yaitu RMSE dan MAE, memiliki perbedaan signifikan. RMSE lebih sensitif terhadap kesalahan besar karena menggunakan kuadrat dari kesalahan, sedangkan MAE menggunakan nilai absolut kesalahan. Dalam konteks prediksi harga mobil bekas, kesalahan besar dapat memiliki dampak finansial yang besar, terutama jika model memprediksi harga yang jauh dari nilai sebenarnya. Oleh karena itu, untuk kasus ini, RMSE lebih relevan karena memberikan perhatian khusus terhadap kesalahan besar yang dapat menyebabkan kerugian yang signifikan bagi pengguna model, terutama jika digunakan untuk menentukan harga jual mobil bekas. Sehingga, RMSE memberikan gambaran yang lebih akurat tentang seberapa baik model memprediksi harga mobil bekas.

## **Data Understanding**
Dataset yang digunakan berisi 5624 catatan mobil bekas yang dikumpulkan dari syarah.com. Setiap baris mewakili mobil bekas. Informasi lain mengenai setiap mobil adalah nama merek, model, tahun pembuatan, asal, pilihan, kapasitas mesin, jenis transmisi, jarak tempuh yang ditempuh mobil, harga wilayah, dan nego.

**Attributes Information**

| **Feature** | **Description** |
| --- | --- |
| Type | Jenis mobil bekas
| Region | Wilayah tempat mobil bekas ditawarkan untuk dijual
| Make | Nama perusahaan
| Gear_Type | Ukuran jenis gigi mobil bekas
| Origin | Asal mobil bekas
| Options | Pilihan mobil bekas
| Year | Tahun pembuatan
| Engine_Size | Ukuran mesin mobil bekas
| Mileage | Jarak tempuh mobil bekas
| Negotiable | True, kalau harga 0 berarti bisa nego
| Price | Harga mobil bekas (dalam Riyal)


## **Step**
- Data Pre-processing:
  - Feature Engineering
  - Multicollinearity
  - Data splitting
  - Train and test splitting
  - Encoding and scaling
   
- Training Models
  - Pilih model benchmark
  - Mempredisksi data test
  - Model terpilih
  - Hyperparameter tuning
  - Performa comparison
  - Feature Importance


## **Kesimpulan**

Berdasarkan pemodelan yang telah dilakukan, berikut adalah beberapa kesimpulan utama dari proyek ini:

1. **Model Terbaik**: Model XGBoost Regressor dengan hyperparameter tuning pada:
   1. colsample_bytree : 1
   2. gamma : 0.01 
   3. learning_rate : 0.1 
   4. max_depth : 7
   5. min_child_weight : 5 
   6. n_estimators : 100 
   7. subsample : 0.8
   8. preprocessing__Scalling: MinMaxScaler

      Score terbaik pada Tuningan model XGBoost disini adalah `-25439.082717200603` secara RMSE<br>

2. **Evaluasi Model**:
   - Prediksi model mungkin meleset lebih jauh karena adanya bias yang cukup tinggi, disebabkan oleh keterbatasan fitur (e.g tidak adanya kondisi mesin, garansi, dan status mobil klasik) dan beberapa data yang mungkin dianggap outlier namun tidak dibuang karena mempertimbangkan banyaknya data yang diperlukan (e.g. Harga mobil yang lebih dari 500.000 SAR)

3. **Limitasi dan Implikasi**: 
   - Model memiliki limitasi yang signifikan pada data testing baru. Data harus disesuaikan dengan batasan yang telah ditentukan agar prediksi dapat dipercaya.
   - Saat digunakan pada data yang tidak memenuhi batasan ini, hasil prediksi bisa kurang akurat.

4. **Analisis Residual**: Model memprediksi data sebagai overprice sebanyak 422 data dan underprice sebanyak 326 data. Hal ini berguna dalam menentukan strategi penjualan dan pembelian mobil bekas untuk mencari keuntungan. Namun model prediksi harga mobil bekas disini dapat dianggap memiliki akurasi yang cukup baik. Hal ini ditunjukkan dengan jumlah prediksi harga yang akurat (overprice atau underprice yang masih masuk akal) yang lebih banyak daripada jumlah prediksi harga yang tidak akurat.

5. **Fitur Tambahan dan Pengaruhnya**: 
   - Fitur tambahan seperti `harga rata-rata` sangat berpengaruh pada prediksi harga 
   - Bias model masih tinggi karena terbatasnya fitur yang mewakili variasi spesifikasi mobil bekas seperti Option dan Original

Dengan demikian, meskipun model saat ini sudah cukup baik, masih terdapat ruang untuk peningkatan akurasi dan pengurangan bias dengan menambahkan fitur yang lebih representatif.


## **Rekomendasi**

- Terkait dengan limitasi untuk dalam pemodelan ini, sebaiknya jumlah data diperbanyak menjadi lebih dari dari 5000an (jumlah data yang sudah dibersihkan), agar model dapat memprediksi harga lebih akurat dari banyaknya variasi data juga.

- Jika ada penambahan banyak data, dapat dicoba dengan menggunakan model yang lebih kompleks, seperti neural networks. 

- Penambahan feature untuk melengkapi informasi yang merepresentasikan variasi spesifikasi mobil seperti, apakah mobil memiliki garansi atau tidak, jenis mobil seperti mobil sport atau tidak, daln lainnya yang mempengarahui dalam menentukan harga mobil bekas. 

- Penggunaan model yang lain dengan target baru untuk  mengklasifikasikan apakah mobil yang terjual ini menguntungkan bagi perusahaan atau tidak. Model klasifikasi ini berguna bagi perusahaan untuk memotong cost servis mobil dengan kondisi sangat buruk, atau sebagai bahan pertimbangan mobil tetap diiklankan atau tidak (Marketing Analyst).

- Mengecek prediksi mana saja yang memiliki nilai error yang tinggi. Kita dapat mengelompokkan error tersebut ke dalam grup overestimation dan underestimation, lalu memilih 5% error paling ekstrim saja untuk tiap grup. Nantinya pengelompokkan akan menjadi 3 grup, yaitu overestimation (5%), underestimation (5%), dan grup mayoritas yang error-nya mendekati nilai mean (90%). Setelahnya kita bisa mengecek hubungan antara error tersebut dengan tiap variabel independen. Pada akhirnya kita dapat mengetahui sebenarnya variabel mana saja dan aspek apa yang menyebabkan model menghasilkan error yang tinggi, sehingga kita bisa melakukan training ulang dengan penerapan feature engineering lainnya.

- Dengan menunjukkan harga mana saja yang overprice dan underprice akan lebih baik juga bagi perusahaan untuk memberikan pertimbangan khusus harga mana yang dirasa overprice atau underprice yang masuk akal, dengan begitu perusahaan akan mencapai keuntungan dan bagi pelanggan menemukan harga yang sesuai dengan kriteria atau spesifikasi mobilnya. 

