# Klasifikasi Performa Akademik Mahasiswa Berdasarkan Kebiasaan Harian

## 📌 Latar Belakang

Performa akademik merupakan hal yang sangat relevan dengan kehidupan mahasiswa. Kebiasaan sehari-hari seperti penggunaan media sosial, durasi tidur, dan aktivitas fisik dapat memengaruhi hasil belajar dan pencapaian akademik.

Project ini bertujuan untuk menganalisis dan mengklasifikasikan performa akademik mahasiswa berdasarkan kebiasaan harian menggunakan perbandingan dua algoritma Machine Learning: **Decision Tree** dan **Gaussian Naive Bayes**.

---

## 👥 Tim Peneliti

- **Anggota Kelompok:**
  - Lisa Damayanti
  - Nasya Aulia 
  - Aprilia Rachel

---


## 📊 Dataset & Fitur

Dataset yang digunakan diperoleh dari Kaggle: [Student Habits vs Academic Performance](https://www.kaggle.com/datasets/jayaantanaath/student-habits-vs-academic-performance).

### Preprocessing Target

Variabel `exam_score` dikonversi menjadi kategori variabel target `performance`:

- **Tinggi:** ≥ 70 (511 data / 51.1%)
- **Sedang:** 50–69 (358 data / 35.8%)
- **Rendah:** < 50 (131 data / 13.1%)

### Fitur yang Digunakan

- `age`, `gender`
- `study_hours_per_day`, `social_media_hours`, `netflix_hours`
- `part_time_job`, `attendance_percentage`, `sleep_hours`
- `diet_quality`, `exercise_frequency`, `parental_education_level`
- `internet_quality`, `mental_health_rating`, `extracurricular_participation`

---

## ⚙️ Pembagian Data

Data dibagi menggunakan rasio **80% Training Data** dan **20% Testing Data**.

---

## 📈 Perbandingan Hasil Evaluasi

### 1. Library Implementation (Scikit-Learn)

| **Algoritma** | **Accuracy** | **Precision** | **Recall** | **F1-Score** |
|---|---:|---:|---:|---:|
| **Decision Tree** | 70.5% | 72.6% | 70.5% | 71.0% |
| **Gaussian Naive Bayes** | **78.5%** | **79.1%** | **78.5%** | **78.3%** |

### 2. From Scratch Implementation

| **Algoritma** | **Accuracy** | **Precision** | **Recall** | **F1-Score** |
|---|---:|---:|---:|---:|
| **Decision Tree (Scratch)** | 78.5% | 79.0% | 78.5% | 78.6% |
| **Naive Bayes (Scratch)** | **80.0%** | **80.7%** | **80.0%** | **79.9%** |

---

## 🔍 Temuan Utama & Kesimpulan

- **Fitur Paling Berpengaruh:** Atribut `study_hours_per_day` memiliki korelasi paling kuat (**0.83**) terhadap `exam_score` dan menjadi *root node* pada Decision Tree.
- **Model Terbaik:** **Gaussian Naive Bayes** menunjukkan performa terbaik pada implementasi Scikit-Learn dengan accuracy **78.5%** dan F1-Score **78.3%**.
- **From Scratch:** Implementasi **Naive Bayes** menghasilkan performa terbaik dengan accuracy **80.0%** dan F1-Score **79.9%**.
- **Visualisasi ROC-AUC:** Naive Bayes mencapai nilai AUC **0.95** untuk kelas Rendah dan Tinggi, sedangkan Decision Tree mencapai **0.91** untuk kelas Rendah dan **0.88** untuk kelas Tinggi.
- **Kesimpulan:** Secara keseluruhan, **Naive Bayes** menunjukkan performa klasifikasi yang lebih baik dibandingkan Decision Tree dalam memprediksi kategori performa akademik berdasarkan kebiasaan harian mahasiswa.
