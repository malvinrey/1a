# Analisis Sentimen Review Aplikasi redBus

## Deskripsi Proyek

Proyek ini melakukan analisis sentimen pada review aplikasi redBus dari Google Play Store. Analisis meliputi tokenisasi, stemming, analisis frekuensi kata, dan visualisasi untuk memahami sentimen pengguna terhadap aplikasi redBus.

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
pip install nltk PySastrawi matplotlib seaborn pandas requests beautifulsoup4 textblob
```

### **Setup NLTK:**

```python
import nltk
nltk.download('punkt')
nltk.download('punkt_tab')
```

### **Menjalankan Notebook:**

1. Buka `scripts.ipynb` di Jupyter Notebook atau Google Colab
2. Jalankan semua cell secara berurutan
3. Hasil analisis akan tersimpan dalam file `redbus_analysis_results.md`
4. Token dari setiap review akan tersimpan dalam file `redbus_review_*.txt`

## Metodologi

### 1. Preprocessing

- **Tokenisasi**: Menggunakan NLTK `word_tokenize` untuk memecah teks menjadi token
- **Stemming**: Menggunakan PySastrawi untuk stemming bahasa Indonesia
- **Analisis Frekuensi**: Menghitung frekuensi kemunculan kata

### 2. Tools yang Digunakan

- `nltk`: Untuk tokenisasi teks
- `PySastrawi`: Untuk stemming bahasa Indonesia
- `pandas`: Untuk manipulasi data
- `matplotlib` & `seaborn`: Untuk visualisasi
- `collections.Counter`: Untuk analisis frekuensi kata
- `requests` & `beautifulsoup4`: Untuk web scraping (edukasi)
- `textblob`: Untuk analisis sentimen otomatis (opsional)

## Fitur Notebook

### **Cell 1 - Analisis Data Review:**

- Memuat data review redBus dari Google Play Store
- Tokenisasi dan stemming menggunakan NLTK dan PySastrawi
- Analisis frekuensi kata dan kata kunci
- Kategorisasi sentimen berdasarkan rating

### **Cell 2 - Laporan Analisis:**

- Generate laporan analisis komprehensif
- Analisis detail setiap review
- Identifikasi masalah umum dan aspek positif
- Rekomendasi untuk perbaikan aplikasi

### **Cell 3 - Visualisasi dan Statistik:**

- 4 grafik visualisasi (distribusi rating, sentimen, panjang review, kata kunci)
- Statistik tambahan (rata-rata, median, standar deviasi)
- Analisis emosi dan topik
- Analisis panjang review berdasarkan rating

### **Cell 4 - Fungsi Lanjutan:**

- Fungsi web scraping (edukasi) untuk Google Play Store
- Rekomendasi tools analisis sentimen lanjutan
- Implementasi TextBlob untuk analisis otomatis
- Panduan untuk analisis lebih mendalam

## Hasil Analisis

### Review 1 (Rating: 3/5 - Sentimen Campuran)

**Review Asli:**

> "Our first trip was very good, and the booking went smooth. However, when I'm trying to use my 'referral code' in my friends' devices, it's just not working, showing 'something seems to be wrong'. I tried to use the 'chat with us' in the app, but the 'Help' section is not even opening, showing some webpage error. Please fix it soon."

**Analisis:**

- **Jumlah Token**: 47 token
- **Token Unik**: 42 token
- **Token setelah Stemming**: 47 token
- **File Output**: `redbus_review_1.txt`

**Pembahasan**: Review ini menunjukkan pengalaman campuran - positif untuk booking dan perjalanan, namun negatif untuk fitur referral dan bantuan. Pengguna mengalami masalah teknis dengan kode referral dan fitur help yang tidak berfungsi.

### Review 2 (Rating: 1/5 - Sentimen Negatif)

**Review Asli:**

> "I had a medical emergency so not able to travel and tried for cancellation but directly redbus informed that I can't cancel my ticket and even I tried to reschedule as I have to travel in coming days but then also it's not possible. I don't understand if you can't provide any of this options then what services you provide and it's not at all expected. My experience is very worst and has occurred loss of 2500."

**Analisis:**

- **Jumlah Token**: 66 token
- **Token Unik**: 52 token
- **Token setelah Stemming**: 66 token
- **File Output**: `redbus_review_2.txt`

**Pembahasan**: Review ini sangat negatif karena kebijakan pembatalan yang kaku. Pengguna mengalami situasi darurat medis namun tidak bisa membatalkan atau menjadwal ulang tiket, menyebabkan kerugian finansial.

### Review 3 (Rating: 1/5 - Sentimen Negatif)

**Review Asli:**

> "very bad algorithm, I went upto the payment procedure but due to technical issues the payment failed. next time the payment increase, I totally shocked. 2nd time also I checked the price after closing the app, again the price increase. very bad experience so I did not book the ticket. now I am going to uninstall the app. i know this will not impact you. but I don't want your app on my phone. so ta ta bye bye"

**Analisis:**

- **Jumlah Token**: 66 token
- **Token Unik**: 50 token
- **Token setelah Stemming**: 66 token
- **File Output**: `redbus_review_3.txt`

**Pembahasan**: Review ini mengeluhkan algoritma dynamic pricing yang tidak konsisten. Pengguna mengalami kenaikan harga yang tidak wajar setelah gagal pembayaran, menyebabkan frustrasi dan keputusan untuk uninstall aplikasi.

## Analisis Frekuensi Kata

**15 Kata Teratas dari Review redBus:**

1. `the` (12 kali) - Artikel bahasa Inggris
2. `and` (8 kali) - Konjungsi
3. `very` (6 kali) - Adverb intensifier
4. `app` (5 kali) - Aplikasi
5. `bad` (5 kali) - Kata sifat negatif
6. `not` (5 kali) - Negasi
7. `good` (4 kali) - Kata sifat positif
8. `booking` (4 kali) - Proses pemesanan
9. `payment` (4 kali) - Pembayaran
10. `ticket` (4 kali) - Tiket
11. `experience` (3 kali) - Pengalaman
12. `help` (3 kali) - Bantuan
13. `price` (3 kali) - Harga
14. `smooth` (3 kali) - Lancar
15. `increase` (3 kali) - Meningkat

**Pembahasan Frekuensi:**

- Kata "very" dan "bad" sering muncul, menunjukkan intensitas keluhan pengguna
- Istilah teknis seperti "app", "booking", "payment" mendominasi
- Kata "good" dan "smooth" menunjukkan aspek positif yang dihargai pengguna
- Kata "price" dan "increase" menunjukkan fokus pada masalah pricing

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

- `redbus_review_1.txt`: Token dari review 1
- `redbus_review_2.txt`: Token dari review 2
- `redbus_review_3.txt`: Token dari review 3
- `redbus_analysis_results.md`: Hasil analisis terstruktur lengkap
- `README.md`: Dokumentasi lengkap proyek

## Visualisasi dan Statistik

### Grafik yang Dihasilkan:

1. **Distribusi Rating**: Bar chart menunjukkan distribusi rating 1-5
2. **Distribusi Sentimen**: Pie chart untuk sentimen positif, negatif, dan campuran
3. **Panjang Review**: Box plot panjang review berdasarkan rating
4. **Kata Kunci**: Bar chart kata kunci positif vs negatif

### Statistik Tambahan:

- Rata-rata rating: 2.4/5
- Review positif (4-5): 2 review
- Review negatif (1-2): 2 review
- Review campuran (3): 1 review

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
├── scripts.ipynb                    # Notebook utama dengan analisis review redBus
├── README.md                        # Dokumentasi proyek (file ini)
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
