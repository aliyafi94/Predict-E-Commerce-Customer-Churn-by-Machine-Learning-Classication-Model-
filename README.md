# Modul-3-ML

# **E-Commerce Customer *churn***

 Perusahaan mengaggap Customer *churn* sebagai suatu hal yang sangat penting sehingga perusahaan ingin mengetahui pelanggan yang akan berpindah ke lain hati, sehingga mereka dapat melakukan pendekatan kepada pelanggan untuk menawarkan promo. Promo yang dilakukan tentu tidak diberikan kepada seluruh palanggan, melainkan yang diprioritaskan adalah pelanggan yang diprediksi akan *churn*. Hal ini dilakukan untuk melakukan efisiensi terhadap jumlah promo yang dikeluarkan. perusahaan ingin memiliki kemampuan untuk memprediksi kemungkinan pelanggan akan *churn* atau tidak, sehingga dapat memfokuskan penawaran promo pada pelanggan yang akan *churn*. Dan juga, perusahaan ingin mengetahui apa/faktor/variabel apa yang membuat pelanggan akan *churn* atau tidak, sehingga perusahaan dapat membuat rencana yang lebih baik untuk membuat pelanggan lebih setia. Kita akan membangun model klasifikasi yang akan membantu perusahaan untuk dapat memprediksi probabilitas pelanggan akan *churn* atau tidak. Pembobotan menggunakan **F2 Score** sangat cocok untuk kasus ini, lebih banyak bobot harus diberikan pada recall untuk kasus-kasus di mana *False Negative* dianggap lebih buruk daripada *False Positive*.
 
Dataset milik perusahaan E-Commerce online terkemuka. Source: [Purwadhika](https://drive.google.com/drive/folders/1PITb78NtK9Ra6wOkQdXCIgItZkj29Ves).
Dimana kita akan melakukan Data Cleaning berupa Handling Missing value dengan **KNN Imputer**, drop duplikat data, handling inconsistent data dan membiarkan outlier karena kita anggap sebagai hal yang natural. Kita juga melakukan One Hot Encoding, Robust Scaling dan Balancing Class Weight karena terjadi imbalanced pada kelas 1 yang sedikit (16.30%) dibanding kelas 0 (83.70%).

Benchmarking Model dilakukan untuk mendapatkan hasil yang terbaik, diantaranya Logistic Regression, Decision Tree, Random Forest, KNN, AdaBoost, XGBoost, GradientBoost, LightGBM, dan SVC dengan metode Cross-Validation dan Prediction F2 Score. **LightGBM** menjadi model terbaik dengan parameter `learning_rate`: `0.03`, `max_bin`: `675`, `max_depth`: `21`, `min_data_in_leaf`: `10`, `num_iterations`: `225`, `num_leaves`: `29`. Score yang dihasilkan pada Train 79.57% dan pada Test 81.98%.

Features paling berpengaruh terhadap Customer Churn yaitu `Tenure`, `Complain`, dan `NumberOfAddress`. Semakin kecil nilai `Tenure` artinya semakin baru customer berlangganan semakin besar kemungkinan Customer akan churn dan semakin lama customer berlangganan semakin betah dia terhadap layanan perusahaan sebaliknya pada `Complain` dan `NumberOfAddress`, semakin tinggi semakin cenderung untuk Churn.

Kita bisa melihat 10 Customer paling berpotensi melakukan Churn dilihat dari Probabilitas dia melakukan churn.
- 10 customer tersebut memiliki probabilitas 98.99 - 99.32% melakukan Churn.
- 10 customer tersebut memiliki `Tenure` 0 atau 1 
- 10 customer tersebut 1 bulan terakhir bertransaksi dengan kategori `Mobile Phone` dan `Laptop & Accessory`.
- 10 Customer tersebut melakukan Complain
- 10 tersebut baru saja melakukan order 0 atau 1 hari yang lalu.

untuk memudahkan perusahaan dalam melakukan prediksi terhadap customer yang akan melakukan churn atau tidak, kita buatkan WebApp dimana perusahaan hanya perlu memasukkan data customer berdasarkan kriteria customer tersebut. Link WebApp : https://aliyafi94-customer-churn-app-churn--9c58pv.streamlit.app/

Efek Model ML yang dibangun terhadap profitabilitas perusahaan 
- Sebelum pakai ML: perusahaan merugi **-29.750 USD** per bulan
- Setelah menggunakan ML: perusahaan berhasil menghasilkan profit **62.000 USD** per bulan

Untuk kedepannya perusaahaan perlu melakukan beberapa hal
untuk Business
1. perusahaan e-commerce perlu menyusun strategi agar dapat tetap menjaga kualitas produk dan pelayanan agar dapat menghindari complain yang masuk. 
1. perusahaan e-commerce perlu menyusun strategi agar dapat menciptakan loyalitas pelanggan, baik dengan melakukan inovasi pada produk yang dipasarkan dan memberikan penawaran yang menarik, sehingga tenure customer semakin tinggi.
1. perusahaan e-commerce perlu memahami Marketing Funnel. Marketing Funnel adalah sebuah konsep untuk menjelaskan tahapan yang dilalui oleh pelanggan sebelum akhirnya melakukan pembelian produk. Dengan mengetahui dan memahami Marketing Funnel, maka sebuah perusahaan akan lebih mudah untuk mengidentifikasi penyebab pelanggan membatalkan pembelian, sehingga dapat menyusun strategi untuk dapat mengatasinya.
1. Perusahaan perlu menggunakan machine learning yang sudah dibuat, agar dapat mengurangi kerugian bagi perusahaan dengan memberikan promosi tepat sasaran kepada customer yang akan melakukan churn.
1. Untuk prediksi customer selanjutnya dapat menggunakan WebApp yang sudah disediakan, guna memudahkan perusahaan dan dapat mendeteksi sedini mungkin kemungkinan customer churn.

Untuk Model
1. Mengumpulkan lebih banyak data khususnya pada minority class
1. Menambahkan parameter lain dalam hyperparameter tuning
1. Menambahkan ID customer untuk memastikan dan mengetahui data yang duplikat
1. Menambahkan feature lain seperti lama pengiriman produk, ketepatan waktu pengiriman, dan lain-lain.
1. Meminimalisir kesalahan penulisan data dan memastikan data yang diperoleh tidak ada yang kosong atau tidak terisi

**Thank You!!!**
