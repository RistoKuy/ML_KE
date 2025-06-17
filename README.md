# Analisis Sentimen Etika AI: Crawling dan Klasifikasi Data Twitter

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-green.svg)](https://scikit-learn.org/)
[![NLTK](https://img.shields.io/badge/NLTK-NLP-red.svg)](https://www.nltk.org/)

## 📋 Deskripsi Proyek

Proyek ini melakukan analisis sentimen terhadap tweet-tweet yang membahas **etika AI (Artificial Intelligence)** menggunakan berbagai metode machine learning. Tujuan utama adalah mengklasifikasikan sentimen masyarakat Indonesia terhadap topik etika AI menjadi kategori positif dan negatif.

## 🎯 Tujuan

- 📊 Menganalisis persepsi publik terhadap etika AI melalui data Twitter
- 🔍 Mengidentifikasi concerns utama masyarakat tentang penggunaan AI
- 📈 Memberikan insight untuk pengembangan kebijakan etika AI yang lebih baik
- 📱 Monitoring sentiment publik terhadap perkembangan teknologi AI

## 🛠️ Teknologi dan Tools

### Bahasa Pemrograman
- **Python 3.8+**

### Libraries Utama
- **Data Processing**: `pandas`, `numpy`
- **Natural Language Processing**: `nltk`, `sastrawi`
- **Machine Learning**: `scikit-learn`
- **Sentiment Analysis**: `vaderSentiment`
- **Visualization**: `matplotlib`, `seaborn`, `wordcloud`
- **Web Scraping**: `tweet-harvest` (Node.js)

### Platform
- **Jupyter Notebook**
- **Windows 11** / **Linux**

## 📁 Struktur Proyek

```
ML_KE/
├── dataMining_KompEtik.ipynb          # Notebook utama
├── README.md                          # Dokumentasi proyek
├── auth.key                          # Twitter authentication token
├── etikaAI.csv                       # Dataset hasil crawling
├── normalisasi-V1.xlsx               # File normalisasi kata
├── positive.tsv                      # Leksikon sentimen positif
├── negative.tsv                      # Leksikon sentimen negatif
├── stopword.txt                      # Daftar stopwords
├── Hasil-Akhir-Preprocessing(Setelah Stemming).csv
├── hasil_jumlah_kata.csv
├── tweet-train.csv                   # Data training
├── tweet-test.csv                    # Data testing
├── testpredict.csv                   # Hasil prediksi
└── tweets-data/
    └── etikaAI.csv                   # Raw data tweets
```

## 🚀 Instalasi dan Setup

### 1. Clone Repository
```bash
git clone <repository-url>
cd ML_KE
```

### 2. Install Dependencies

#### Untuk Windows 11:
```bash
pip install pandas numpy nltk sastrawi swifter openpyxl xlrd vaderSentiment scikit-learn matplotlib seaborn wordcloud pytz
```

#### Untuk Linux:
```bash
sudo pip3 install pandas numpy nltk sastrawi swifter openpyxl xlrd vaderSentiment scikit-learn matplotlib seaborn wordcloud pytz
```

### 3. Install Node.js (untuk tweet-harvest)
- **Windows**: Download dari [nodejs.org](https://nodejs.org/)
- **Linux**: 
```bash
sudo apt-get update
sudo apt-get install nodejs npm
```

### 4. Setup Twitter Authentication
1. Buat file `auth.key` di direktori root
2. Masukkan Twitter Bearer Token Anda ke dalam file tersebut

## 📖 Panduan Penggunaan

### 1. Jalankan Jupyter Notebook
```bash
jupyter notebook dataMining_KompEtik.ipynb
```

### 2. Eksekusi Cell secara Berurutan
1. **Setup Libraries**: Install dan import semua dependencies
2. **Data Crawling**: Crawl tweets dengan keyword "etika ai"
3. **Preprocessing**: Cleaning, tokenizing, stemming
4. **Sentiment Analysis**: Analisis menggunakan VADER
5. **Machine Learning**: Training dan evaluasi model

## 🔬 Metodologi

### 1. Data Collection
- **Source**: Twitter API via tweet-harvest
- **Keyword**: "etika ai since:2025-01-01 lang:id"
- **Limit**: 1000 tweets
- **Language**: Bahasa Indonesia

### 2. Text Preprocessing
- **Tokenizing**: Pemecahan teks menjadi token
- **Case Folding**: Konversi ke huruf kecil
- **Cleansing**: Penghapusan angka, tanda baca, whitespace
- **Stopword Removal**: Penghapusan kata-kata tidak bermakna
- **Normalisasi**: Standardisasi kata tidak baku
- **Stemming**: Konversi ke kata dasar (Sastrawi)

### 3. Feature Engineering
- **TF-IDF Vectorization**: Transformasi teks ke representasi numerik
- **Train-Test Split**: 80% training, 20% testing

### 4. Machine Learning Models
- **SVM (Support Vector Machine)**: Kernel linear
- **Random Forest**: Ensemble learning
- **Naive Bayes**: MultinomialNB

### 5. Evaluation Metrics
- **Accuracy Score**
- **Confusion Matrix**
- **Classification Report** (Precision, Recall, F1-Score)

## 📊 Hasil dan Visualisasi

### Model Performance
- Akurasi model SVM, Random Forest, dan Naive Bayes
- Confusion matrix untuk setiap model
- Visualisasi heat map performa klasifikasi

### Sentiment Distribution
- Distribusi sentimen positif vs negatif
- Word cloud kata-kata dominan
- Analisis frekuensi kata

## 📈 Contoh Output

```
Data training: 800 samples
Data testing: 200 samples

SVM Accuracy: XX.XX%
Random Forest Accuracy: XX.XX%
Naive Bayes Accuracy: XX.XX%

Distribusi Sentimen:
- Positive: XX%
- Negative: XX%
- Neutral: XX%
```

## 🔧 Troubleshooting

### Common Issues

1. **Twitter Authentication Error**
   - Pastikan `auth.key` berisi token yang valid
   - Periksa koneksi internet

2. **NLTK Data Missing**
   ```python
   import nltk
   nltk.download('punkt')
   nltk.download('stopwords')
   nltk.download('vader_lexicon')
   ```

3. **Encoding Issues**
   - Pastikan file CSV menggunakan encoding UTF-8

## 🤝 Kontribusi

1. Fork repository
2. Buat branch fitur (`git checkout -b feature/AmazingFeature`)
3. Commit perubahan (`git commit -m 'Add some AmazingFeature'`)
4. Push ke branch (`git push origin feature/AmazingFeature`)
5. Buat Pull Request

## 📝 Pengembangan Selanjutnya

- [ ] Implementasi IndoBERT untuk akurasi lebih tinggi
- [ ] Integrasi BERTopic untuk topic modeling
- [ ] Analisis temporal perubahan sentimen
- [ ] Klasifikasi multi-class (positif, negatif, netral, mixed)
- [ ] Dashboard interaktif dengan Streamlit/Dash
- [ ] Real-time sentiment monitoring
- [ ] Ekspansi ke platform media sosial lain

## 👥 Tim Pengembang

- **Nama**: Aristo Baadi
- **Institusi**: Universitas/Perguruan Tinggi
- **Mata Kuliah**: Komunikasi Etika (KomEtik)
- **Semester**: 4

## 📞 Kontak

Untuk pertanyaan atau saran, silakan hubungi:
- Email: [email@example.com]
- LinkedIn: [linkedin-profile]
- GitHub: [github-profile]

## 🙏 Acknowledgments

- NLTK team untuk natural language processing tools
- Sastrawi untuk Indonesian stemming
- scikit-learn untuk machine learning algorithms
- VADER untuk sentiment analysis lexicon
- Tweet-harvest untuk Twitter data collection

---

**⭐ Jika proyek ini bermanfaat, jangan lupa beri star!**
