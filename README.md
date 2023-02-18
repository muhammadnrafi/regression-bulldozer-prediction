# Regression: Bluebook Bulldozer Price Prediction
## Using Random Forest Regressor
**[EN]**  
In this project, I tested how well bulldozer prices might be predicted using machine learning.

Because we'll utilize the Randomforest Regressor algorithm to calculate or forecast a value in numerical form, this project involves a regression problem.

**[ID]**  
Pada projek ini saya melakukan sebuah eksperimen dengan menggunakan machine learning untuk memprediksi harga dari bulldozers. 

Dengan demikian projek ini masuk kedalam permasalahan regresi, karena kita akan menentukan atau memperdiksi sebuah nilai dalam bentuk numerik dengan menggunakan algoritma Randomforest Regressor.

# Problem Definition
**[EN]**  
How well can we predict the future sale price of a bulldozer, given its characteristics previous examples of how much similar bulldozers have been sold for?

**[ID]**  
Seberapa baik kita dapat memprediksi harga jual bulldozer di masa depan, mengingat karakteristiknya contoh sebelumnya berapa banyak bulldoser serupa yang telah dijual?

# Data
**[EN]**  
You can see it's a time series problem by looking at the [dataset from Kaggle](https://www.kaggle.com/c/bluebook-for-bulldozers/data). This indicates that the dataset has a time attribute.
In this instance, the relevant information is bulldozer sales history. include information on the model kind, size, sale date, and more.
Three datasets are present:
1. **Train.csv** - Historical bulldozer sales examples from the year 2000 to 2011 (almost 400,000 examples with more than 50 variables, including the **target variable** "SalePrice").
2. **Valid.csv** - Historical bulldozer sales samples from January 1 2012 to April 30 2012. This file contains about 12,000 examples with the same characteristics as **Train.csv**.
3. **Test.csv** - Historical bulldozer sales samples from May 1, 2012, to November 2012 (almost 12,000 examples; the 'SalePrice' variable is absent because this is what we'll be attempting to forecast).

**[ID]**  
Berdasarkan dataset yang digunakan, diketahui bahwa dataset berupa timeseries [dataset dari Kaggle] (https://www.kaggle.com/c/bluebook-for-bulldozers/data). Ini menunjukkan bahwa dataset memiliki atribut waktu.
Dalam kasus ini, informasi yang relevan adalah riwayat penjualan bulldozer. termasuk informasi tentang jenis model, ukuran, tanggal penjualan, dan banyak lagi.
Ada tiga dataset yang hadir:
1. **Train.csv** - Contoh penjualan bulldozer bersejarah dari tahun 2000 hingga 2011 (hampir 400.000 contoh dengan lebih dari 50 variabel, termasuk variabel **target** "SalePrice").
2. **Valid.csv** - Sampel penjualan bulldozer bersejarah dari 1 Januari 2012 hingga 30 April 2012. File ini berisi sekitar 12.000 contoh dengan karakteristik yang sama dengan **Train.csv**.
3. **Test.csv** - Sampel penjualan bulldozer bersejarah dari 1 Mei 2012, hingga November 2012 (hampir 12.000 contoh; variabel 'SalePrice' tidak ada karena ini adalah apa yang akan kami coba memprediksi).

# Evaluation
**[EN]**  
Root mean squared log error (RMSLE) has been chosen by Kaggle as the evaluation statistic for this particular issue. (https://www.kaggle.com/c/bluebook-for-bulldozers/overview/evaluation). The objective will be to reduce this value as much as feasible, as is the case with many regression analyses.

We'll compute the RMSLE and then compare our results to others on the [Kaggle leaderboard](https://www.kaggle.com/c/bluebook-for-bulldozers/leaderboard) to see how well our model is performing.

**[ID]**  
Root mean squared log error (RMSLE) telah dipilih oleh Kaggle sebagai statistik evaluasi untuk masalah ini. (https://www.kaggle.com/c/bluebook-for-bulldozers/overview/evaluation). Tujuannya adalah untuk mengurangi nilai ini sebanyak mungkin, seperti yang terjadi dengan banyak analisis regresi.

Kami akan menghitung RMSLE dan kemudian membandingkan hasil kami dengan yang lain di [Kaggle leaderboard] (https://www.kaggle.com/c/bluebook-for-bulldozers/leaderboard) untuk melihat seberapa baik model tersebut menghasilkan prediksi.

# Features / Fitur
**[EN]**  
Different elements of the data are called features. You should start learning as much as you can about the data throughout this step.


To accomplish this, one of the most popular methods is to build a **data dictionary**.


Kaggle offers a data dictionary for this dataset that describes what each attribute in the dataset implies. From the Kaggle competition page, you can [immediately download this file]. (account required) or view it on Google Sheets. (https://www.kaggle.com/c/bluebook-for-bulldozers/download/Bnl6RAHA0enbg0UfAvGA%2Fversions%2FwBG4f35Q8mAbfkzwCeZn%2Ffiles%20Data%20Dictionary.xlsx)


Now that you are aware of everything, let's get going!


We'll import the dataset first, then we'll start investigating. Building a baseline model and comparing it to the competition will be our first objective because we are aware of the assessment measure we're seeking to minimize.

**[ID]**  
Elemen-elemen yang berbeda dari data disebut fitur. Anda harus mulai mempelajari sebanyak mungkin tentang data selama langkah ini.


Untuk mencapai ini, salah satu metode yang paling populer adalah membangun kamus **data**.


Kaggle menawarkan kamus data untuk dataset ini yang menggambarkan apa yang diartikan oleh setiap atribut dalam dataset. Dari halaman persaingan Kaggle, Anda dapat [mengunduh file ini segera]. (akun diperlukan) atau menontonnya di Google Sheets. (https://www.kaggle.com/c/bluebook-for-bulldozers/download/Bnl6RAHA0enbg0UfAvGA%2Fversions%3FwBG4f35Q8mAbfkzwCeZn%4Ffiles%10Data%20Dictionary.xlsx)


Sekarang Anda sudah menyadari segalanya, mari kita mulai!


Kami akan mengimpor dataset pertama, kemudian kami akan mulai menyelidiki. Membangun model baseline dan membandingkannya dengan kompetisi akan menjadi tujuan pertama kami karena kami menyadari ukuran penilaian yang kami ingin meminimalkan.


# Conclusion
**[EN]**
So, the project has resulted in the ‘RMSLE’ level on Training data from 0.25 to 0.13, and has successfully lowered the level of ‘RMLE’ on data validation from 0.29 to 0.24.

- If viewed from the results, the model produced on this project can be said to be quite good, while for the test data the author can not determine the result of its 'RMSLE' level. So, to continue to analyze whether the model is successful or not, you can do an analysis of the feature importance on the model.

- Feature importance is used to know what features have an influence in determining the prediction of the **target variable** in this case `SalePrice`

Based on the feature importance results obtained, that Top 5 features that have the greatest influence on the model are ‘YearMade’, ‘ProductSize’, ‘fiSecondaryDesc’, ‘Enclosure’, and ‘saledate’.

**[ID]**
- Jadi, projek ini telah menghasilkan tingkat `RMSLE` pada Training data dari 0.25 menjadi 0.13, dan berhasil menurunkan tingkat `RMSLE` pada validation data dari 0.29 menjadi 0.24.

- Jika dilihat dari hasil tersebut, model yang dihasilkan pada projek ini dapat dibilang cukup baik, sedangnkan untuk data test penulis tidak dapat menentukan hasil dari tingkat `RMSLE` nya. Sehingga, untuk melanjutkan analisa apakah berhasil atau tidaknya model yang dibuat, dapat melakukan analisa terhadap feature importance pada model tersebut.

- Feature importence digunakan untuk mengetahui features apa yang memiliki pengaruh dalam menentukan prediksi terhadap **target variable** dalam hal ini `SalePrice`

- Berdasarkan hasil feature importance yang didapatkan, bahwa Top 5 feature yang memiliki pengaruh terbesar pada model adalah `YearMade`, `ProductSize`, `fiSecondaryDesc`, `Enclosure`, dan `saledate`.
