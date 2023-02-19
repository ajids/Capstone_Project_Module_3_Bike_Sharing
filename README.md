# **Bike Sharing (Capital Bikeshare)**

-Capstone Project Module 3: Capital Bikesharing Prediction

-Nama: Aji Dwi Septian

[Sumber data Bike Sharing](https://capitalbikeshare.com/system-data) 

## **Contents**

1. Business Problem Understanding
2. Data Understanding
3. Data Preprocessing
4. Modeling
5. Conclusion
6. Recommendation

****

## Business Problem Understanding
### Context

*Capital Bikesharing* adalah sebuah jaringan layanan berbagi sepeda publik yang ada di beberapa kota di Amerika Serikat. Sistem ini memungkinkan pengguna untuk meminjam sepeda dari lokasi tertentu dan mengembalikan sepeda ke lokasi lain setelah mereka selesai menggunakannya. Capital Bikeshare biasanya menggunakan stasiun sepeda dan teknologi pemantauan untuk memastikan bahwa sepeda dapat dipinjam dan dikembalikan dengan mudah.

*Capital Bikeshare* dibuat untuk menawarkan alternatif transportasi yang lebih ramah lingkungan dan efisien bagi warga kota dan turis. Sistem ini juga menyediakan opsi yang menyenangkan dan sehat bagi para penggunanya. Capital Bikeshare umumnya tersedia 24 jam sehari, 7 hari seminggu, dan memerlukan biaya sewa yang rendah.

Project ini menggunakan data kondisi cuaca, musim, tanggal, jam, dan jumlah penyewaan sepeda. Analisis data ini memungkinkan untuk mengkaji hubungan antar fitur dan menemukan metode untuk memprediksi jumlah sepeda yang diperlukan pada kondisi tertentu.


## Data Understanding
Ada perbedaan cukup signifikan antara nilai RMSE dan MAE, di mana RMSE lebih tinggi karena nilai residuals atau error-nya dikuadratkan terlebih dahulu sebelum dirata-ratakan. Hal ini menyebabkan RMSE akan memberikan "weight" yang lebih tinggi untuk nilai error yang besar, sehingga terdapat perbedaan signifikan antara nilai RMSE dan MAE karena terdapat beberapa nilai error yang besar yang dihasilkan oleh semua algoritma yang digunakan. Berdasarkan nilai ketiga matriks tersebut, XGBoost adalah model terbaik. Oleh karena itu, prediksi test set akan dilakukan dengan menggunakan model XGBoost.
- Dataset merupakan data peminjaman sepeda di sistem ***Capital Bikeshare*** dalam rentang tahun 2011-2012.
- Setiap baris data merepresentasikan informasi terkait waktu peminjaman, cuaca, dan musim yang sesuai.

Dari 12165 data yang tersedia, sebanyak 11803 data diperoleh pada hari kerja dan 362 data pada hari libur. Season fall menunjukkan tingkat persewaan tertinggi, diikuti oleh summer, spring, dan winter. Sepeda sering disewa saat cuaca cerah hingga berawan, namun sangat sedikit disewa saat cuaca buruk seperti hujan deras, bersalju, badai, dan berkabut. Jam efektif persewaan adalah antara jam 6 hingga 23, dan sering terjadi pada pukul 8, 12, 16, 17, 18, dan 19.

## Modelling
Membandingkan model dari Linear Regression, KNN Regressor, Decision Tree Regressor, Random Forest Regressor, XGBoost Regressor. Kemudian didapatkan hasil dari model terbaik yaitu XGBoost, dan selanjutnya dilakukan hyperparameter tuning.

Dapat dilihat bahwa setelah dilakukan hyperparameter tuning, model mengalami peningkatan performa.

RMSE, MAE & MAPE sebelum tuning: 40.25, 25.66, 0.41
RMSE, MAE & MAPE setelah tuning: 39.12, 24.97, 0.43

## Kesimpulan
Dari hasil pemodelan yang telah dilakukan, dapat disimpulkan bahwa fitur yang paling berpengaruh terhadap jumlah penyewaan sepeda ('Count') adalah 'Hour'. Evaluasi model menggunakan tiga matriks, yaitu RMSE, MAE, dan MAPE. Setelah dilakukan hyperparameter tuning, didapatkan nilai RMSE sebesar 39,12. Oleh karena itu, dapat disimpulkan bahwa model dapat memperkirakan jumlah penyewa sepeda dengan meleset sekitar 39 orang dari jumlah aktualnya jika digunakan untuk memperkirakan jumlah penyewaan pada rentang nilai maksimum sebesar 645. Meskipun demikian, masih terdapat bias pada data prediksi dan aktual karena fitur pada dataset masih kurang untuk merepresentasikan keadaan dimana orang akan memutuskan untuk menyewa sepeda, seperti lokasi stasiun, adanya event tertentu, dan lain-lain.

## Rekomendasi
1. Mengumpulkan lebih banyak data dapat membantu meningkatkan model, terutama jika data yang dikumpulkan lebih dari dua tahun. Dengan menggunakan data ini, keterkaitan tahun dengan Count dapat dipelajari lebih detail. Selain itu, model yang lebih kompleks dapat digunakan untuk pemodelan untuk membandingkan dan menemukan model dengan kesalahan paling kecil.
2. Penambahan fitur baru seperti fitur "Hour" yang merupakan fitur paling berpengaruh terhadap "Count". Selain itu, penambahan fitur baru seperti lokasi station dan faktor-faktor lain yang mempengaruhi keputusan orang untuk menyewa sepeda dapat meningkatkan akurasi prediksi.
3. Selain itu, model yang telah dibangun dapat digunakan untuk pengembangan lain, seperti pembuatan model untuk memprediksi harga rental atau jumlah sepeda yang masuk atau keluar dari stasiun tertentu. Analisis lokasi stasiun strategis dapat membantu dalam membuat pertimbangan untuk membuka stasiun baru di lokasi serupa.

Link drive: https://drive.google.com/drive/folders/1v69Cbid5E-xQp4lW-ck5UibNs94YCKWq?usp=sharing

