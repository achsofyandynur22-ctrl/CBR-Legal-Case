
# CBR Legal Case Retrieval System

## Deskripsi Proyek

Proyek ini merupakan implementasi **Case-Based Reasoning (CBR)** untuk pencarian kasus hukum serupa menggunakan dokumen putusan pengadilan Indonesia. Sistem memanfaatkan metode **TF-IDF (Term Frequency-Inverse Document Frequency)** dan **Cosine Similarity** untuk menemukan kasus yang memiliki tingkat kemiripan tertinggi terhadap suatu query.

## Latar Belakang

Jumlah putusan hukum yang tersedia pada Direktori Putusan Mahkamah Agung terus meningkat setiap tahun. Banyaknya dokumen tersebut menyebabkan proses pencarian kasus yang relevan menjadi sulit apabila dilakukan secara manual.

Case-Based Reasoning (CBR) merupakan pendekatan kecerdasan buatan yang menyelesaikan masalah baru berdasarkan pengalaman dari kasus-kasus sebelumnya yang memiliki karakteristik serupa.

## Tujuan

1. Membangun basis kasus (Case Base) dari kumpulan putusan hukum.
2. Merepresentasikan kasus hukum dalam bentuk fitur terstruktur.
3. Mengimplementasikan metode TF-IDF dan Cosine Similarity untuk pencarian kasus serupa.
4. Mengevaluasi performa sistem retrieval menggunakan beberapa metrik evaluasi.

## Dataset

| Informasi | Keterangan |
|------------|------------|
| Domain | Hukum |
| Jenis Perkara | Pidana Khusus (Narkotika) |
| Jumlah Kasus | 30 Putusan |
| Format Awal | PDF |
| Format Hasil | TXT dan CSV |
| Sumber Data | Direktori Putusan Mahkamah Agung RI |

## Metodologi

### 1. Case Base Construction

- Mengumpulkan 30 dokumen putusan hukum.
- Mengonversi PDF menjadi teks.
- Menyimpan hasil ekstraksi ke dalam basis kasus.

### 2. Case Representation

Setiap kasus direpresentasikan menggunakan atribut:

- case_id
- nomor_putusan
- tahun
- pengadilan
- jenis_perkara
- pihak
- pasal
- ringkasan_fakta
- text

### 3. Case Retrieval

Proses retrieval dilakukan menggunakan:

- TF-IDF Vectorization
- Cosine Similarity

Sistem akan mengembalikan Top-K kasus yang memiliki kemiripan tertinggi dengan query.

### 4. Case Reuse

Kasus dengan nilai similarity tertinggi digunakan sebagai rekomendasi solusi untuk kasus baru.

### 5. Evaluation

Evaluasi dilakukan menggunakan:

- Precision@K
- Recall@K
- Mean Average Precision (MAP)
- Accuracy
- F1-Score

## Siklus Case-Based Reasoning

Retrieve → Reuse → Revise → Retain

### Implementasi

- Retrieve : TF-IDF + Cosine Similarity
- Reuse : Menggunakan solusi dari kasus paling mirip
- Revise : Evaluasi hasil retrieval
- Retain : Menambahkan kasus baru ke basis kasus

## Arsitektur Sistem

PDF Putusan
↓
Ekstraksi Teks
↓
TXT
↓
Case Representation
↓
TF-IDF Vectorization
↓
Cosine Similarity
↓
Top-K Retrieval
↓
Prediksi Solusi
↓
Evaluasi Sistem

## Struktur Folder

CBR-Legal-Case/

├── data/

│   ├── raw/

│   ├── processed/

│   ├── eval/

│   └── results/

├── notebooks/

├── README.md

├── requirements.txt

└── .gitignore

## Teknologi yang Digunakan

- Python
- Pandas
- NumPy
- Scikit-Learn
- Matplotlib
- PyPDF2
- Google Colab

## Penulis

Ach Sofyan Daynur

NIM: 202110370311155

Universitas Muhammadiyah Malang
