
# Laporan Ringkasan EDA - Review redBus

**Tanggal Analisis:** 2025-09-30 16:01:22

## 1. Ikhtisar Dataset
- **Total Review:** 5
- **Rata-rata Rating:** 2.80
- **Rata-rata Panjang Review:** 44.6 karakter

## 2. Kualitas Data
- **Missing Values:** 0
- **Data Duplikat:** 0
- **Inkonsistensi Rating-Sentimen:** 0

## 3. Temuan Utama
- Mayoritas review memberikan rating **positif** (4-5 bintang) atau **negatif** (1-2 bintang), dengan sedikit review campuran.
- Terdapat korelasi negatif antara **rating** dengan **panjang review**, menunjukkan review negatif cenderung lebih panjang.
- Kata kunci negatif yang sering muncul adalah terkait **masalah teknis** ('payment', 'app', 'ticket') dan **layanan pelanggan** ('cancel', 'reschedule').
- Kata kunci positif berfokus pada **kemudahan penggunaan** ('easy', 'smooth', 'good') dan **fitur** ('booking', 'interface').

## 4. Rekomendasi
- **Untuk Tim Produk:** Fokus pada perbaikan bug terkait proses pembayaran dan fitur referral.
- **Untuk Tim Layanan Pelanggan:** Tinjau kembali kebijakan pembatalan dan penjadwalan ulang, terutama untuk kasus darurat.
- **Untuk Analisis Lanjutan:** Lakukan analisis sentimen yang lebih mendalam menggunakan model machine learning dan analisis topik untuk mengidentifikasi masalah spesifik.
