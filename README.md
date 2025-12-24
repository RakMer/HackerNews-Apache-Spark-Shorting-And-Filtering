# Hacker News – Spark & MongoDB Veri Saklama Projesi

## 📋 Proje Bilgileri

**Proje Yürütücüsü:** Baran Mert Berber  
**Süre:** 12 Hafta  
**Proje Adı:** Hacker News – Spark & MongoDB Veri Saklama ve Analiz Sistemi

## 🎯 Proje Özeti

Bu proje, Hacker News verilerini toplamak, MongoDB'de saklamak ve Apache Spark kullanarak analiz etmek için geliştirilmiş bir sistemdir. Flask tabanlı web arayüzü ile kullanıcılar verileri görselleştirebilir ve filtreleyebilir.

## 🛠️ Teknolojiler

- **Python 3.12+**
- **MongoDB Community / Atlas**
- **Apache Spark (PySpark)**
- **Flask** - Web Framework
- **Hacker News Algolia API**

### Gerekli Python Kütüphaneleri

```txt
flask==3.0.0
pyspark==3.5.0
pymongo==4.6.0
```

## 📦 Kurulum

### 1. MongoDB Kurulumu

```bash
# macOS için
brew install mongodb-community
brew services start mongodb-community
```

### 2. Python Bağımlılıklarını Kurma

```bash
cd Bitirme
pip install -r requirements.txt
```

### 3. Uygulamayı Çalıştırma

```bash
python3 app.py
```

Uygulama varsayılan olarak `http://localhost:5000` adresinde çalışacaktır.

## 📊 Özellikler

### Veri Toplama
- Hacker News Algolia API'sinden otomatik veri çekimi
- Zaman damgası tabanlı sayfalama (`created_at_i`)
- Mükerrer kayıt önleme (unique `objectID` kontrolü)
- MongoDB'ye otomatik kaydetme (`upsert=True`)

### Veri Analizi (Apache Spark)
- En popüler domain'ler
- En çok gönderi yapan yazarlar
- Toplam yazar sayısı
- Toplam gönderi sayısı
- Başlığa göre arama
- Filtreleme ve sıralama işlemleri

### Web Arayüzü (Flask)
- Arama (keyword)
- Yazara göre filtreleme
- Tarihe göre sıralama
- Haber linklerine yönlendirme
- JSON formatında REST API
- Bootstrap tabanlı responsive tasarım

## 📁 Proje Yapısı

```
Bitirme/
├── app.py                 # Flask uygulaması
├── spark_queries.py       # Spark sorguları
├── requirements.txt       # Python bağımlılıkları
├── static/
│   ├── script.js         # Frontend JavaScript
│   └── style.css         # Stil dosyası
├── templates/
│   └── index.html        # Ana sayfa
└── tests/
    └── test_app.py       # Test dosyaları
```

## 🗓️ 12 Haftalık Proje Planı

### 3-4. Hafta: Ortam Kurulumu ve Veri Çekme Testleri ✅
- [x] Python, MongoDB ve Apache Spark kurulumları
- [x] Gerekli kütüphanelerin yüklenmesi
- [x] MongoDB bağlantı testleri
- [x] Hacker News API test veri çekimi
- [x] JSON veri yapısı analizi
- [x] Örnek veri setinin MongoDB'ye kaydedilmesi

### 5-6. Hafta: Veri Toplayıcı (Collector) Geliştirme ✅
- [x] Algolia API veri çekme modülü
- [x] Zaman damgası tabanlı sayfalama
- [x] MongoDB stories koleksiyonu oluşturma
- [x] Mükerrer kayıt önleme (upsert)
- [x] Büyük veri setinin toplanması ve doğrulanması

### 7-8. Hafta: Veri Çekme Optimizasyonu ve Analitik Sorgular ✅
- [x] SparkSession oluşturma ve MongoDB entegrasyonu
- [x] DataFrame filtreleme, sıralama ve gruplama
- [x] Spark SQL sorguları:
  - [x] En popüler domain'ler
  - [x] En çok gönderi yapan yazarlar
  - [x] Toplam yazar/gönderi sayısı
  - [x] Başlığa göre arama

### 9-10. Hafta: Optimizasyon, Performans Testleri ve Arayüz Başlangıcı ✅
- [x] MongoDB okuma performans ölçümü
- [x] Spark sonuçları performans değerlendirmesi
- [x] Flask web arayüzü geliştirmeye başlama

### 11-12. Hafta: Flask Web Arayüzü ve API Katmanı ✅
- [x] Flask REST API geliştirme
- [x] JSON formatında Spark sonuçları sunumu
- [x] Arama, filtreleme ve sıralama özellikleri
- [x] Haber linklerine yönlendirme
- [x] Flask + Spark entegrasyon testleri
- [x] Bootstrap tabanlı frontend

### 13-14. Hafta: Test, Raporlama ve Sunum Hazırlığı
- [ ] Proje raporu ve sunum dökümanları
- [ ] Sistem ekran görüntüleri
- [ ] Akademik formatta PDF çıktısı

## 🚀 API Endpoints

### GET `/`
Ana sayfa

### GET `/api/statistics`
Genel istatistikler (toplam gönderi, yazar sayısı vb.)

### GET `/api/top-stories`
En popüler haberler

### GET `/api/top-authors`
En aktif yazarlar

### GET `/api/top-articles-by-points`
En çok puan alan makaleler

### GET `/api/articles`
Tüm makaleler (filtreleme ve sıralama destekli)

**Query Parameters:**
- `search`: Başlıkta aranacak kelime
- `author`: Yazara göre filtreleme
- `sort`: Sıralama kriteri (points, date)
- `order`: Sıralama yönü (asc, desc)
- `limit`: Sonuç sayısı

### POST `/api/ai-articles`
AI/Yapay Zeka ile ilgili makaleler

## 📈 Beklenen Çıktılar

- ✅ Tam çalışan Hacker News veri toplama ve analiz sistemi
- ✅ Spark ile çalışan analitik sorgular ve Flask üzerinden web erişimi
- ⏳ Tamamlanmış proje raporu ve sunum materyali

## 🔧 Notlar

### MongoDB Bağlantısı
Varsayılan bağlantı: `mongodb://localhost:27017/`
Database: `HackerNewsDB`
Collection: `HackerNews`

### Spark Konfigürasyonu
```python
spark.driver.memory: 3g
spark.executor.memory: 2g
spark.sql.adaptive.enabled: true
spark.sql.shuffle.partitions: 8
```

## 📝 Lisans

Bu proje bitirme projesi kapsamında geliştirilmiştir.

## 👤 İletişim

**Baran Mert Berber**
