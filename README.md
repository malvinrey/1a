# Analisis Sentimen Bahasa Indonesia

## Deskripsi Proyek

Proyek ini melakukan analisis sentimen pada dataset bahasa Indonesia menggunakan dataset `kornwtp/indonlu-smsa`. Analisis meliputi tokenisasi, stemming, dan analisis frekuensi kata untuk memahami karakteristik teks dalam bahasa Indonesia.

## Dataset

- **Nama Dataset**: `kornwtp/indonlu-smsa`
- **Jenis**: Dataset sentimen bahasa Indonesia
- **Split**: Train
- **Format**: Dataset Hugging Face

## Metodologi

### 1. Preprocessing

- **Tokenisasi**: Menggunakan NLTK `word_tokenize` untuk memecah teks menjadi token
- **Stemming**: Menggunakan PySastrawi untuk stemming bahasa Indonesia
- **Analisis Frekuensi**: Menghitung frekuensi kemunculan kata

### 2. Tools yang Digunakan

- `datasets`: Untuk memuat dataset dari Hugging Face
- `nltk`: Untuk tokenisasi teks
- `PySastrawi`: Untuk stemming bahasa Indonesia
- `pandas`: Untuk manipulasi data
- `collections.Counter`: Untuk analisis frekuensi kata

## Hasil Analisis

### Contoh Teks 1 (Label: 0 - Sentimen Negatif)

**Teks Asli:**

> "warung ini dimiliki oleh pengusaha pabrik tahu yang sudah puluhan tahun terkenal membuat tahu putih di bandung . tahu berkualitas , dipadu keahlian memasak , dipadu kretivitas , jadilah warung yang menyajikan menu utama berbahan tahu , ditambah menu umum lain seperti ayam . semuanya selera indonesia . harga cukup terjangkau . jangan lewatkan tahu bletoka nya , tidak kalah dengan yang asli dari tegal !"

**Analisis:**

- **Jumlah Token**: 66 token
- **Token Unik**: 50 token
- **Token setelah Stemming**: 56 token
- **File Output**: `tokens_sample_1.txt`

**Pembahasan**: Teks ini merupakan review restoran yang membahas warung tahu di Bandung. Meskipun label menunjukkan sentimen negatif (0), isi teks sebenarnya cenderung positif dengan kata-kata seperti "berkualitas", "terjangkau", dan "tidak kalah". Hal ini menunjukkan kemungkinan ada inkonsistensi dalam labeling atau teks ini mungkin mengandung aspek negatif yang tidak terlihat jelas.

### Contoh Teks 2 (Label: 1 - Sentimen Positif)

**Teks Asli:**

> "mohon ulama lurus dan k212 mmbri hujjah partai apa yang harus diwlh agar suara islam tidak pecah-pecah"

**Analisis:**

- **Jumlah Token**: 17 token
- **Token Unik**: 17 token
- **Token setelah Stemming**: 17 token
- **File Output**: `tokens_sample_2.txt`

**Pembahasan**: Teks ini membahas topik politik dan agama. Semua token adalah unik, menunjukkan keragaman kosakata yang tinggi. Teks ini menggunakan bahasa yang lebih formal dan mengandung istilah keagamaan seperti "ulama" dan "hujjah".

### Contoh Teks 3 (Label: 0 - Sentimen Negatif)

**Teks Asli:**

> "lokasi strategis di jalan sumatera bandung . tempat nya nyaman terutama sofa di lantai 2 . paella nya enak , sangat pas dimakan dengan minum bir dingin . appetiser nya juga enak-enak ."

**Analisis:**

- **Jumlah Token**: 33 token
- **Token Unik**: 27 token
- **Token setelah Stemming**: 28 token
- **File Output**: `tokens_sample_3.txt`

**Pembahasan**: Teks ini merupakan review restoran yang membahas lokasi, suasana, dan makanan. Meskipun label menunjukkan sentimen negatif, teks ini sebenarnya sangat positif dengan kata-kata seperti "strategis", "nyaman", "enak", dan "sangat pas". Ini menunjukkan pola yang sama dengan contoh pertama.

## Analisis Frekuensi Kata

**10 Kata Teratas:**

1. `.` (8 kali) - Tanda baca titik
2. `,` (6 kali) - Tanda baca koma
3. `tahu` (5 kali) - Kata benda (makanan)
4. `yang` (4 kali) - Kata penghubung
5. `nya` (4 kali) - Kata ganti posesif
6. `di` (3 kali) - Preposisi
7. `warung` (2 kali) - Kata benda (tempat)
8. `bandung` (2 kali) - Nama kota
9. `dipadu` (2 kali) - Kata kerja
10. `menu` (2 kali) - Kata benda

**Pembahasan Frekuensi:**

- Tanda baca mendominasi frekuensi tertinggi, menunjukkan struktur kalimat yang baik
- Kata "tahu" muncul 5 kali, menunjukkan fokus pada makanan tertentu
- Kata-kata fungsional seperti "yang" dan "nya" sering muncul, khas bahasa Indonesia
- Nama kota "Bandung" muncul 2 kali, menunjukkan konteks geografis yang spesifik

## Temuan Penting

### 1. Inkonsistensi Labeling

Terdapat inkonsistensi antara label sentimen dan isi teks:

- Teks dengan label 0 (negatif) sebenarnya mengandung kata-kata positif
- Hal ini dapat mempengaruhi akurasi model sentimen

### 2. Karakteristik Bahasa Indonesia

- Penggunaan kata ganti posesif "nya" yang tinggi
- Struktur kalimat yang kompleks dengan banyak kata penghubung
- Campuran bahasa formal dan informal

### 3. Efektivitas Stemming

- Stemming PySastrawi efektif mengurangi jumlah token
- Beberapa kata mengalami perubahan signifikan (misal: "terkenal" → "kenal")

## File Output

Proyek ini menghasilkan beberapa file output:

- `tokens_sample_1.txt`: Token dari contoh teks 1
- `tokens_sample_2.txt`: Token dari contoh teks 2
- `tokens_sample_3.txt`: Token dari contoh teks 3
- `results.md`: Hasil analisis terstruktur
- `README.md`: Dokumentasi lengkap proyek

## Kesimpulan

Analisis ini menunjukkan kompleksitas preprocessing teks bahasa Indonesia dan pentingnya validasi label dalam dataset sentimen. Dataset ini memerlukan review lebih lanjut untuk memastikan konsistensi labeling, terutama untuk teks yang mengandung sentimen positif namun diberi label negatif.

## Rekomendasi

1. **Validasi Label**: Perlu dilakukan review manual terhadap label sentimen
2. **Preprocessing Lanjutan**: Pertimbangkan normalisasi teks dan handling kata tidak baku
3. **Analisis Konteks**: Perlu analisis yang lebih mendalam untuk memahami konteks sentimen
4. **Dataset Cleaning**: Bersihkan dataset dari inkonsistensi labeling sebelum digunakan untuk training model
