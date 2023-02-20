# purwadhika-bike-sharing-regression-model
Capstone Project Module 3 Purwadhika -  Bike Sharing Regression

Nama : Joshua Gerald Javia

# Contents
 - Business Problem Understanding
 - Data Understanding
 - Data Preprocessing (Data Cleaning, Feature Selection, Feature Engineering)
 - Modeling (Algorithm, Evaluation Metrics)
 - Conclusion
 - Recommendation / Improvement

# Business Problem & Data Understanding
Bike sharing merupakan sistem persewaan sepeda dimana sepeda dapat disewa baik oleh penyewa yang telah menjadi member maupun yang belum menjadi member. Pada beberapa sistem Bike sharing, penyewa dapat menyewa sebuah sepeda dari satu lokasi station, dan mengembalikannya pada station lain yang lokasinya berbeda namun masih dalam satu sistem.

Data yang digunakan dalam project ini adalah data kondisi cuaca, musim, tanggal dan jam, serta total penyewa. Dari data tersebut, dapat dipelajari dan dianalisis keterkaitan antar fitur, sehingga dapat diperoleh metode untuk memprediksi perkiraan sepeda yang diperlukan pada waktu dengan kondisi tertentu.

# Data Preprocessing
 - Penambahan fitur month, year, dayname yang diambil dari dteday
 - Penghapusan outlier
 - Pengapusan fitur dteday, casual, registered, atemp
 - Pengubahan tipe data untuk weathersit, season, holiday menjadi category

# Modeling
Membandingkan Linear Regression, KNN Regressor, Decision Tree Regressor, Random Forest Regressor, XGBoost Regressor.

Hasilnya adalah XGBoost merupakan model terbaik, kemudian dilakukan hyperparameter tuning.

Hasil before dan after Hyperparameter Tuning :

- MAE, MAPE & RMSE sebelum tuning: 25.774804, 0.435109, 40.800221
- MAE, MAPE & RMSE setelah tuning: 25.082641, 0.386078, 40.336543

# Conclusion
Berdasarkan pemodelan yang telah dilakukan, fitur 'Hour' merupakan fitur yang paling berpengaruh terhadap 'Count'.

Untuk matriks evaluasi yang digunakan adalah RMSE, MAE, dan MAPE. Nilai RMSE yang dihasilkan setelah hyperparameter tuning adalah 39,12. Sehingga dapat disimpulkan bahwa jika model akan digunakan untuk memperkirakan penyewa sepeda pada rentang nilai sesuai model yang dilatih (maksimal Count 645), maka perkiraan penyewa dapat meleset kurang lebih 39 orang dari total aktualnya. Namun dapat terjadi kesalahan lebih jauh juga karena masih terdapat bias yang terlihat dari visualisasi data prediksi dan aktual. Bias dapat terjadi karena masih kurangnya fitur pada dataset untuk merepresentasikan keadaan dimana orang akan memutuskan untuk menyewa sepeda, seperti lokasi station, adanya event tertentu, dan lain - lain.

# Recommendation
 1. Penambahan fitur yang lebih korelatif dengan target (`Count`) seperti diadakannya event khusus, selain itu dapat dipertimbangkan juga mengenai jarak lokasi station dengan lokasi perkantoran, sekolah, atau tempat wisata. Dimana merupakan tempat yang cukup strategis karena area-area tersebut merupakan area yang cukup padat dilalui orang-orang serta kebutuhan untuk bisa sampai tujuan tepat waktu tanpa terlambat.
 
 2. Melakukan penambahan data. Jika terdapat data lebih banyak dibandingkan dataset yang digunakan saat ini, dirasa dapat dianalisis dengan lebih baik lagi. Dapat juga digunakan model yang lebih kompleks untuk proses pemodelannya untuk dibandingan dan dicari model dengan error yang paling sedikit, serta hal tersebut dapat membantu dalam meningkatkan akurasi prediksi dari model.
 
 3. Model yang sudah dibuat juga dapat dimanfaatkan untuk melakukan pengembangan lainnya. Seperti dalam pembuatan model untuk memprediksi harga rental, atau dapat juga digunakan untuk pembuatan model dalam memprediksi total unit sepeda yang disewa pada lokasi tertentu. Dimana kedepannya dapat dianalisa sebagai pertimbangan untuk menambah stasiun sepeda di lokasi-lokasi yang strategis.

# Save Model Menggunakan PICKLE
