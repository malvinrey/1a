# Analisis Eksploratif Data (EDA) Review Aplikasi redBus

## Deskripsi Proyek

Proyek ini melakukan analisis eksploratif data (EDA) yang komprehensif pada review aplikasi redBus. Analisis meliputi preprocessing teks, tokenisasi, stemming, analisis frekuensi kata, visualisasi data, analisis korelasi, word cloud, dan pembuatan laporan ringkasan untuk memahami pola dan karakteristik review pengguna terhadap aplikasi redBus.

## Dataset

- **Sumber Data**: Review aplikasi redBus dari Google Play Store
- **Nama Aplikasi**: redBus - Bus, Ferry, Train, IRCTC Auth. Partner
- **Platform**: Google Play Store
- **Rating**: 4.6/5 bintang
- **Total Review**: 3.78 juta review
- **Download**: 50+ juta
- **Kategori**: Travel & Local

## Instalasi dan Cara Menjalankan

### **Prerequisites:**

```bash
pip install nltk PySastrawi requests beautifulsoup4 textblob wordcloud matplotlib seaborn scipy pandas numpy
```

### **Setup NLTK:**

```python
import nltk
nltk.download('punkt')
nltk.download('stopwords')
```

### **Menjalankan Notebook:**

1. Buka `scripts.ipynb` di Jupyter Notebook atau Google Colab
2. Jalankan semua cell secara berurutan
3. Hasil analisis akan tersimpan dalam file `redbus_analysis_results.md`
4. Token dari setiap review akan tersimpan dalam file `redbus_review_*.txt`

## Metodologi

### 1. Data Preprocessing

- **Case Folding**: Mengubah teks ke lowercase
- **Pembersihan Tanda Baca**: Menghilangkan karakter non-alfanumerik
- **Tokenisasi**: Menggunakan NLTK `word_tokenize` untuk memecah teks menjadi token
- **Stopwords Removal**: Menghilangkan kata-kata umum yang tidak informatif
- **Stemming**: Menggunakan PorterStemmer untuk mencari kata dasar

### 2. Exploratory Data Analysis (EDA)

- **Analisis Kualitas Data**: Missing values, duplikasi, konsistensi
- **Statistik Deskriptif**: Mean, median, distribusi data
- **Analisis Korelasi**: Hubungan antar variabel numerik
- **Visualisasi Data**: Distribusi rating, sentimen, panjang review
- **Word Cloud Analysis**: Visualisasi kata kunci berdasarkan sentimen
- **Analisis Frekuensi**: Top 100 kata paling sering muncul

### 3. Tools yang Digunakan

- `nltk`: Untuk tokenisasi teks dan stopwords
- `pandas` & `numpy`: Untuk manipulasi dan analisis data
- `matplotlib` & `seaborn`: Untuk visualisasi data
- `wordcloud`: Untuk pembuatan word cloud
- `collections.Counter`: Untuk analisis frekuensi kata
- `scipy`: Untuk analisis statistik lanjutan

## Fitur Notebook

### **Cell 1-2 - Instalasi dan Import Libraries:**

- Instalasi packages yang diperlukan (nltk, PySastrawi, wordcloud, dll.)
- Import semua library untuk manipulasi data, visualisasi, dan NLP
- Konfigurasi NLTK dan pengaturan plot

### **Cell 3-4 - Pemuatan Data:**

- Memuat dataset review redBus dengan 5 sample review
- Konversi data ke DataFrame pandas
- Preview data yang dimuat

### **Cell 5-6 - EDA pada Data Mentah:**

- Analisis informasi dasar dataset
- Statistik deskriptif untuk data numerik
- Analisis kualitas data (missing values, duplikasi)
- Visualisasi distribusi rating dan panjang review

### **Cell 7-8 - Data Preprocessing:**

- Case folding (lowercase conversion)
- Pembersihan tanda baca
- Tokenisasi menggunakan NLTK
- Penghapusan stopwords
- Stemming menggunakan PorterStemmer

### **Cell 9-10 - EDA pada Data Bersih:**

- Analisis frekuensi 100 kata teratas
- Visualisasi kata paling umum
- Pembuatan word cloud dari data bersih

### **Cell 11-12 - Analisis Statistik dan Kualitas Data:**

- Statistik deskriptif lengkap
- Analisis distribusi rating dan sentimen
- Analisis missing values dan duplikasi
- Analisis konsistensi rating vs sentimen

### **Cell 13-14 - Visualisasi Eksploratif:**

- 4 grafik visualisasi (distribusi rating, sentimen, panjang review, box plot)
- Analisis korelasi antar variabel
- Heatmap korelasi

### **Cell 15-16 - Analisis Teks Lanjutan:**

- Word cloud untuk semua review, positif, dan negatif
- Analisis frekuensi kata kunci positif dan negatif
- Perbandingan kata kunci berdasarkan sentimen

### **Cell 17-18 - Pembuatan Laporan:**

- Fungsi untuk generate laporan ringkasan EDA
- Penyimpanan laporan ke file markdown
- Rekomendasi berdasarkan temuan analisis

## Hasil Analisis

### Dataset Overview

Notebook ini menggunakan dataset sample dengan **5 review** redBus yang mencakup berbagai rating dan sentimen:

- **Review 1**: Rating 3/5 - Sentimen Campuran
- **Review 2**: Rating 1/5 - Sentimen Negatif
- **Review 3**: Rating 1/5 - Sentimen Negatif
- **Review 4**: Rating 5/5 - Sentimen Positif
- **Review 5**: Rating 4/5 - Sentimen Positif

### Analisis Preprocessing

**Proses Pembersihan Teks:**

1. **Case Folding**: Semua teks diubah ke lowercase
2. **Pembersihan Tanda Baca**: Karakter non-alfanumerik dihilangkan
3. **Tokenisasi**: Teks dipecah menjadi token menggunakan NLTK
4. **Stopwords Removal**: Kata-kata umum dihilangkan
5. **Stemming**: Kata-kata diubah ke bentuk dasar menggunakan PorterStemmer

**Hasil Preprocessing:**

- Dataset bersih siap untuk analisis frekuensi dan visualisasi
- Token yang sudah distemming untuk analisis kata kunci
- Perbandingan data sebelum dan sesudah preprocessing

## Analisis Frekuensi Kata

**Top 100 Kata Paling Sering Muncul:**

Notebook ini menganalisis frekuensi 100 kata teratas dari dataset yang sudah dibersihkan. Analisis ini mencakup:

- **Kata Kunci Positif**: Kata-kata yang sering muncul dalam review positif
- **Kata Kunci Negatif**: Kata-kata yang sering muncul dalam review negatif
- **Word Cloud**: Visualisasi kata kunci berdasarkan sentimen
- **Analisis Frekuensi**: Top 20 kata paling umum dengan visualisasi bar chart

**Fitur Analisis Frekuensi:**

1. **Counter Analysis**: Menggunakan `collections.Counter` untuk menghitung frekuensi
2. **Visualisasi Bar Chart**: Top 20 kata dengan seaborn
3. **Word Cloud Generation**: Visualisasi kata kunci yang menarik
4. **Sentiment-based Analysis**: Pemisahan kata kunci berdasarkan sentimen

## Temuan Penting

### 1. Masalah Teknis yang Dominan

**Dynamic Pricing Issues:**

- Algoritma pricing yang tidak konsisten
- Kenaikan harga yang tidak wajar setelah gagal pembayaran
- Transparansi harga yang kurang

**Bug dan Error:**

- Fitur referral code tidak berfungsi
- Help section mengalami error
- Gagal pembayaran yang sering terjadi

### 2. Masalah Customer Service

**Kebijakan Pembatalan:**

- Kebijakan yang terlalu kaku untuk situasi darurat
- Tidak ada fleksibilitas untuk reschedule
- Kerugian finansial pengguna

**Responsivitas:**

- Fitur bantuan tidak berfungsi
- Customer service kurang responsif
- Masalah teknis tidak segera ditangani

### 3. Aspek Positif yang Dihargai

**User Experience:**

- Interface yang mudah digunakan
- Proses booking yang smooth
- Fitur baru yang inovatif (train booking, metro)

**Kualitas Layanan:**

- Customer service yang helpful (ketika berfungsi)
- Aplikasi yang stabil untuk fungsi utama

## File Output

Proyek ini menghasilkan beberapa file output:

- `eda_summary_report.md`: Laporan ringkasan EDA yang dihasilkan otomatis
- `README.md`: Dokumentasi lengkap proyek
- File-file hasil analisis sebelumnya (jika ada):
  - `redbus_analysis_results.md`: Hasil analisis terstruktur lengkap
  - `redbus_review_1.txt`: Token dari review 1
  - `redbus_review_2.txt`: Token dari review 2
  - `redbus_review_3.txt`: Token dari review 3

## Visualisasi dan Statistik

### Grafik yang Dihasilkan:

1. **Distribusi Rating**: Bar chart dengan palette 'husl' menunjukkan distribusi rating
2. **Distribusi Sentimen**: Pie chart dengan warna custom untuk sentimen positif, negatif, dan campuran
3. **Distribusi Panjang Review**: Histogram dengan KDE untuk panjang review dalam karakter
4. **Box Plot Rating vs Panjang Review**: Analisis hubungan rating dengan panjang review
5. **Heatmap Korelasi**: Matriks korelasi antar variabel numerik
6. **Word Cloud**: 3 word cloud (semua review, positif, negatif)
7. **Top 20 Kata**: Bar chart kata paling sering muncul

### Statistik Deskriptif:

- **Informasi Dataset**: Info lengkap tentang struktur data
- **Statistik Numerik**: Mean, median, std dev untuk kolom numerik
- **Analisis Kualitas Data**: Missing values, duplikasi, konsistensi
- **Distribusi Rating dan Sentimen**: Count dan persentase

## Kesimpulan

Analisis review aplikasi redBus menunjukkan bahwa meskipun aplikasi memiliki rating yang baik (4.6/5) dengan basis pengguna yang besar (50+ juta download), masih terdapat beberapa area kritis yang perlu diperbaiki:

### **Masalah Utama:**

1. **Algoritma Dynamic Pricing** yang tidak konsisten dan tidak transparan
2. **Bug teknis** pada fitur referral dan help section
3. **Kebijakan pembatalan** yang terlalu kaku untuk situasi darurat
4. **Customer service** yang kurang responsif

### **Aspek Positif:**

1. **User interface** yang mudah digunakan
2. **Proses booking** yang smooth
3. **Fitur inovatif** seperti train booking dan metro tickets

## Rekomendasi

### **Untuk redBus:**

1. **Perbaiki Algoritma Pricing**: Implementasikan transparansi dalam penetapan harga
2. **Enhance Customer Service**: Perbaiki fitur bantuan dan tingkatkan responsivitas
3. **Fleksibilitas Kebijakan**: Pertimbangkan situasi darurat untuk pembatalan
4. **Bug Fixes**: Perbaiki masalah teknis dengan payment dan referral
5. **Quality Assurance**: Implementasikan testing yang lebih ketat

### **Untuk Pengguna:**

1. **Backup Plan**: Selalu siapkan alternatif jika ada masalah teknis
2. **Read Terms**: Pahami kebijakan pembatalan sebelum booking
3. **Contact Support**: Gunakan saluran komunikasi yang tersedia
4. **Monitor Pricing**: Perhatikan perubahan harga sebelum finalisasi pembayaran

### **Untuk Analisis Lanjutan:**

1. **Dataset Lebih Besar**: Gunakan dataset review yang lebih komprehensif
2. **Sentiment Analysis Tools**: Implementasikan VADER, TextBlob, atau BERT
3. **Topic Modeling**: Analisis topik menggunakan LDA atau BERTopic
4. **Time Series Analysis**: Analisis trend sentimen dari waktu ke waktu

## Struktur Proyek

```
1a/
├── scripts.ipynb                    # Notebook utama dengan EDA komprehensif
├── README.md                        # Dokumentasi proyek (file ini)
├── eda_summary_report.md           # Laporan ringkasan EDA (generated)
├── redbus_analysis_results.md       # Laporan analisis lengkap (generated)
├── redbus_review_1.txt             # Token dari review 1 (generated)
├── redbus_review_2.txt             # Token dari review 2 (generated)
├── redbus_review_3.txt             # Token dari review 3 (generated)
└── results.md                      # File hasil analisis sebelumnya
```

## Kontribusi

Jika Anda ingin berkontribusi pada proyek ini:

1. Fork repository ini
2. Buat branch fitur baru (`git checkout -b feature/AmazingFeature`)
3. Commit perubahan Anda (`git commit -m 'Add some AmazingFeature'`)
4. Push ke branch (`git push origin feature/AmazingFeature`)
5. Buat Pull Request

## Lisensi

Proyek ini menggunakan lisensi MIT. Lihat file `LICENSE` untuk detail lebih lanjut.

## Kontak

Untuk pertanyaan atau saran, silakan buat issue di repository ini.
