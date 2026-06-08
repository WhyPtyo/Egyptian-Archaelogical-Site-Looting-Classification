# Egyptian Archaeological Site Looting Classification
Sistem klasifikasi citra satelit (Looted vs NotLooted) untuk deteksi penjarahan situs arkeologi di Mesir. Membandingkan algoritma klasik (Ekstraksi Fitur + PCA + SVM) dengan Convolutional Neural Network (CNN). Dibuat oleh Kelompok 1 Sains Data 2024E UNESA.

Sebuah proyek *Machine Learning* dan *Deep Learning* untuk mendeteksi aktivitas penjarahan dan penggalian ilegal pada situs arkeologi kuno di Mesir berdasarkan citra satelit[cite: 2, 3]. Proyek ini merupakan tugas untuk mata kuliah Pembelajaran Mesin Dasar[cite: 3].

## 📌 Deskripsi Proyek
Situs arkeologi seringkali menghadapi ancaman penjarahan yang merusak warisan budaya[cite: 3]. Mengingat luasnya gurun pasir di Mesir, pemantauan manual sangat tidak efisien[cite: 3]. Oleh karena itu, proyek ini memanfaatkan citra satelit untuk mengklasifikasikan area secara otomatis menjadi dua kategori: **Looted** (mengalami penjarahan) dan **NotLooted** (aman)[cite: 2, 3].

Penelitian ini melakukan studi komparatif antara dua paradigma kecerdasan buatan:
1. **Machine Learning Klasik (SVM):** Menggunakan *handcrafted feature extraction* yang mengintegrasikan Histogram of Oriented Gradients (HOG), Gray-Level Co-occurrence Matrix (GLCM), dan Color Histogram[cite: 3]. Fitur ini kemudian direduksi menggunakan Principal Component Analysis (PCA) menjadi 100 komponen utama[cite: 2, 3].
2. **Deep Learning (CNN):** Mengekstrak peta fitur spasial hierarkis secara otomatis (*end-to-end*)[cite: 3].

## 📊 Dataset

Dataset: https://www.kaggle.com/datasets/abdelazizamr837/egyptian-archaeological-site-looting/data
Dataset yang digunakan adalah "Egyptian Archaeological Site Looting" yang bersumber dari Kaggle[cite: 2, 3].
* **Total Data:** 322 citra satelit beresolusi asli 256x256 piksel[cite: 2, 3].
* **Distribusi Kelas:** Seimbang (*balanced*), terdiri dari 176 citra *Looted* dan 146 citra *NotLooted*[cite: 2, 3].
* **Pembagian Data:** 80% data latih (257 citra) dan 20% data uji (65 citra) menggunakan *stratified random sampling*[cite: 2, 3].

## 🏆 Hasil dan Analisis
Untuk memastikan reproduktibilitas dan menghindari instabilitas metrik, pelatihan model dilakukan dengan mengunci lingkungan komputasi secara deterministik[cite: 3]. Hasil eksperimen menunjukkan:
* **Akurasi CNN:** 70,77%[cite: 2, 3]
* **Akurasi SVM:** 66,15%[cite: 2, 3]

**Insight Utama:**
* Arsitektur CNN terbukti lebih tangguh dan superior dalam memetakan fitur spasial kompleks pada citra satelit beresolusi rendah dibandingkan algoritma klasik[cite: 3].
* Reduksi dimensi yang masif menggunakan PCA pada model SVM terbukti menghilangkan detail visual samar, membuat model ini rentan terhadap alarm palsu (*False Positive*) saat membedakan kawah galian dengan kontur pasir alami[cite: 3].

## 🛠️ Teknologi yang Digunakan
* **Bahasa:** Python
* **Library Ekstraksi Fitur:** OpenCV, Scikit-Image (HOG, GLCM)
* **Library Pemodelan:** Scikit-Learn (PCA, SVM), TensorFlow / Keras (CNN)
* **Visualisasi & UI:** Matplotlib, Seaborn, IPyWidgets

## 👥 Tim Pengembang (Kelompok 1)
Proyek ini dikembangkan oleh mahasiswa Program Studi Sains Data (Kelas 2024E), Universitas Negeri Surabaya[cite: 3]:
* **Wahyu Prasetyono** (24031554133)[cite: 2, 3]
* **Danis Setyansyah** (24031554143)[cite: 2, 3]
* **Davan Juheins Tololiu** (24031554157)[cite: 2, 3]

**Dosen Pengampu:** Riskyana Dewi Intan Puspitasari, S.Si., M.Kom.[cite: 3]
