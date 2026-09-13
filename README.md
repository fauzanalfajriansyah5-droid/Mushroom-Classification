# Mushroom Classification

## Take-Home Challenge — Machine Learning & Deep Learning

### Identitas

- **Nama:** Fauzan Al Fajriansyah
- **NIM:** 09030282630035
- **Program Studi:** Teknik Komputer
- **Perguruan Tinggi:** Universitas Sriwijaya

---

## 1. Overview

Project ini merupakan pengerjaan Take-Home Challenge dengan topik **Mushroom Classification** menggunakan Machine Learning dan Deep Learning.

Tujuan utama project adalah melakukan klasifikasi jamur berdasarkan karakteristik yang terdapat pada dataset untuk menentukan apakah jamur termasuk **Edible (e)** atau **Poisonous (p)**.

### Pertanyaan Utama

> **Can Machine Learning Identify Whether a Mushroom is Edible or Poisonous?**

Project ini mencakup proses end-to-end mulai dari memahami dataset, Exploratory Data Analysis (EDA), preprocessing, pemodelan klasifikasi, Deep Learning, evaluasi model, hyperparameter tuning, interpretasi model, hingga eksperimen regresi.

---

## 2. Dataset

Dataset yang digunakan adalah **Mushroom Classification** dengan file: **mushrooms.csv**

     Dataset terdiri dari:
     8.124 baris
     23 kolom
     Seluruh fitur pada dataset berbentuk categorical.

     Target
     Kolom target adalah:
     class

     Keterangan:
     e = Edible
     p = Poisonous

     Distribusi target:
     e = 4.208 data
     p = 3.916 data

     Sumber Dataset
     Dataset berasal dari Kaggle dengan sumber UCI ML Repository:
     https://www.kaggle.com/datasets/uciml/mushroom-classification/data

3. Repository Structure

Struktur repository dibuat sesuai dengan ketentuan pengumpulan:

Mushroom-Classification/
├── data/
│   └── mushrooms.csv
├── notebook/
│   └── Fauzan_NIM_TakeHomeML.ipynb
└── README.md

4. Methodology

    Tahapan pengerjaan project meliputi:
    1. Problem Definition
    2. Data Understanding
    3. Exploratory Data Analysis (EDA)
    4. Data Preprocessing
    5. Feature & Target Preparation
    6. Train Test Split
    7. Logistic Regression
    8. Decision Tree
    9. Random Forest
    10. Deep Learning Model
    11. Model Evaluation & Comparison
    12. Hyperparameter Tuning
    13. Model Interpretation
    14. Regression Exploration
    15. Comprehensive Analysis
    16. Final Insight
    17. Conclusion

5. Exploratory Data Analysis

    EDA dilakukan untuk memahami karakteristik dataset sebelum proses pemodelan.

    Analisis yang dilakukan meliputi:
    - Melihat distribusi target class.
    - Melihat distribusi minimal lima fitur.
    - Menganalisis hubungan fitur dengan target.
    - Menganalisis fitur odor terhadap class.
    - Menganalisis fitur bruises terhadap class.
    - Menganalisis fitur gill-size terhadap class.
    - Menganalisis fitur habitat terhadap class.
    - Memeriksa missing value.
    - Memeriksa nilai ?.
    - Memeriksa duplicate data.
    - Memeriksa fitur konstan atau tidak informatif.

    Hasil dan visualisasi EDA dapat dilihat secara lengkap pada notebook.

6. Data Preprocessing

    Tahapan preprocessing yang dilakukan:

    Missing Value dan Nilai ?
    Dataset tidak memiliki standard missing value (NaN), tetapi terdapat nilai ? pada beberapa kolom.

    Nilai ? ditangani dengan menggantinya menjadi:
    unknown
    
    Dengan cara ini, informasi bahwa suatu nilai tidak diketahui tetap dapat dipertahankan sebagai kategori.

    Duplicate
    Dilakukan pemeriksaan terhadap data duplikat. Dataset tidak memiliki duplicate berdasarkan pemeriksaan yang dilakukan.

    Constant Feature
    Fitur veil-type memiliki satu nilai unik sehingga tidak memberikan informasi pembeda dan dihapus dari proses pemodelan.

    Encoding
    Karena fitur pada dataset bersifat categorical, dilakukan One Hot Encoding.

    Encoding diterapkan menggunakan:
    - OneHotEncoder
    - ColumnTransformer
    - Pipeline

    Target kemudian dikonversi menjadi nilai numerik:
    e → 0
    p → 1

7. Feature & Target Preparation

    Feature atau variabel input:
    X = seluruh kolom kecuali class

    Target:
    y = class

    Dataset kemudian dibagi menjadi data training dan testing dengan perbandingan:
    80% training
    20% testing

    Pembagian menggunakan:
    random_state = 42
    stratify = y

8. Classification Models

    Tiga algoritma Machine Learning digunakan untuk melakukan klasifikasi.

    Logistic Regression
    Logistic Regression digunakan sebagai salah satu model baseline untuk klasifikasi biner.

    Decision Tree
    Decision Tree digunakan untuk mempelajari pola keputusan berdasarkan fitur-fitur pada dataset.

    Selain evaluasi model, training accuracy dan testing accuracy dibandingkan untuk melihat indikasi overfitting.

    Random Forest
    Random Forest digunakan karena merupakan ensemble method yang menggabungkan beberapa decision tree untuk menghasilkan        prediksi.


9. Deep Learning Model
    Untuk pendekatan Deep Learning digunakan Neural Network menggunakan MLPClassifier.

    Arsitektur yang digunakan memiliki dua hidden layer:

    Input
      ↓
    Hidden Layer 1: 64 neurons
      ↓
    Hidden Layer 2: 32 neurons
      ↓
    Output

    Parameter utama yang digunakan meliputi:
    Activation: ReLU
    Optimizer: Adam
    Learning rate: 0.001
    Batch size: 32
    Early stopping
    Validation fraction: 0.2

    Training dan validation performance divisualisasikan melalui kurva loss dan validation score.


10. Model Evaluation

    Setiap model dievaluasi menggunakan:
    Accuracy
    Precision
    Recall
    F1-Score
    Confusion Matrix

    Perbandingan performa seluruh model dapat dilihat pada bagian** Model Evaluation & Comparison** di notebook.

    Model Comparison
    Model	                Accuracy	    Precision	          Recall	       F1-Score
    Logistic Regression	Lihat notebook	Lihat notebook	Lihat notebook	Lihat notebook
    Decision Tree	      Lihat notebook	Lihat notebook	Lihat notebook	Lihat notebook
    Random Forest	      Lihat notebook	Lihat notebook	Lihat notebook	Lihat notebook
    Neural Network	Lihat notebook	Lihat notebook	Lihat notebook	Lihat notebook

    Nilai numerik hasil evaluasi mengikuti output aktual yang dihasilkan ketika notebook dijalankan.


11. Hyperparameter Tuning
    Hyperparameter tuning dilakukan pada model Random Forest menggunakan GridSearchCV.

    Parameter yang dieksplorasi meliputi:
    - n_estimators
    - max_depth
    - min_samples_split
    - min_samples_leaf

    Tujuan tuning adalah mencari kombinasi hyperparameter yang dapat meningkatkan performa model berdasarkan F1-Score.
    Performa Random Forest sebelum dan sesudah tuning dibandingkan pada notebook.


12. Model Interpretation
    Interpretasi model dilakukan menggunakan **feature importance** dari Random Forest.

    Feature importance digunakan untuk melihat fitur yang memiliki kontribusi relatif lebih besar terhadap keputusan model.
    Hasil feature importance divisualisasikan pada notebook.


13. Regression Exploration
    Selain klasifikasi, dilakukan eksperimen regresi sebagai eksplorasi tambahan.

    Target numerik eksperimental dibuat dengan nama:
    rarity_score

    Rarity score dibuat berdasarkan frekuensi kategori pada fitur.

    Eksperimen ini menggunakan:
    RandomForestRegressor

    Evaluasi regresi dilakukan menggunakan:
    - MAE (Mean Absolute Error)
    - RMSE (Root Mean Squared Error)
    - R² (R-squared)

    Rarity score pada eksperimen ini merupakan target numerik buatan untuk memenuhi eksplorasi regresi dan **bukan merupakan       ukuran biologis atau indikator keamanan jamur.**


14. Comprehensive Analysis

    Berdasarkan proses analisis, beberapa hal yang diperhatikan adalah:
    - Dataset memiliki dua kelas target, yaitu edible dan poisonous.
    - Dataset didominasi oleh fitur categorical.
    - Nilai ? perlu ditangani sebelum pemodelan.
    - Fitur konstan seperti veil-type tidak memberikan informasi yang berguna bagi model.
    - Encoding diperlukan agar fitur categorical dapat digunakan oleh model.
    - Performa model dibandingkan menggunakan beberapa metrik evaluasi.
    - Perbedaan training dan testing performance digunakan untuk melihat kemungkinan overfitting.
    - Hyperparameter tuning dilakukan untuk meningkatkan atau mempertahankan performa model.
    - Feature importance digunakan untuk membantu memahami fitur yang paling berpengaruh.
    - Deep Learning dibandingkan dengan pendekatan Machine Learning tradisional.


15. Final Insight

    Beberapa insight utama dari project ini:
    1. Dataset Mushroom Classification dapat digunakan sebagai permasalahan binary classification.
    2. Preprocessing categorical data merupakan tahap penting sebelum model dilatih.
    3. Penanganan nilai ? diperlukan agar data dapat diproses dengan baik.
    4. Random Forest dapat digunakan untuk klasifikasi sekaligus memberikan informasi feature importance.
    5. Evaluasi model tidak cukup hanya menggunakan accuracy sehingga precision, recall, F1-score, dan confusion matrix juga        digunakan.
    6. Hyperparameter tuning dapat digunakan untuk mencari konfigurasi model yang lebih baik.
    7. Deep Learning dapat dibandingkan dengan model Machine Learning tradisional untuk melihat pendekatan yang lebih sesuai        terhadap dataset.

    Hasil model pada dataset tidak boleh dianggap sebagai jaminan keamanan jamur di dunia nyata.

16. Conclusion
    Project ini menunjukkan proses lengkap penerapan Machine Learning dan Deep Learning pada dataset Mushroom Classification.

    Dataset diproses melalui tahap data understanding, EDA, preprocessing, encoding, pembagian data training dan testing,        kemudian digunakan untuk melatih Logistic Regression, Decision Tree, Random Forest, dan Neural Network.

    Setiap model dievaluasi menggunakan Accuracy, Precision, Recall, F1-Score, dan Confusion Matrix. Random Forest juga          dilakukan hyperparameter tuning dan interpretasi menggunakan feature importance.

    Selain klasifikasi, dilakukan eksperimen regresi menggunakan target numerik eksperimental berupa rarity score.

    Secara keseluruhan, Machine Learning dapat digunakan untuk mempelajari pola pada dataset dan melakukan klasifikasi           antara kelas edible dan poisonous. Namun, hasil model pada dataset ini tidak dapat dijadikan sebagai jaminan keamanan        konsumsi jamur di dunia nyata.

17. Files

    Repository ini berisi:
    - data/mushrooms.csv — dataset yang digunakan.
    - notebook/Fauzan_NIM_TakeHomeML.ipynb — notebook pengerjaan Take-Home Challenge.
    - README.md — dokumentasi project.

18. Dataset Source

    Dataset:
    Mushroom Classification — UCI ML Repository

    Kaggle:
    https://www.kaggle.com/datasets/uciml/mushroom-classification/data

