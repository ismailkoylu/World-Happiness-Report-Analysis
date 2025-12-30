# 🏀 EuroLeague Player Scouting & Data Analysis System

Bu proje, **EuroLeague Live API** uç noktalarından (endpoints) gerçek zamanlı maç verilerini çekerek oyuncu performanslarını analiz eden ve takımlar için potansiyel transfer adaylarını belirleyen bir veri mühendisliği çalışmasıdır.

## 🎯 Proje Amacı
Basketbol verilerini (Play-by-Play data) ham formatta (JSON) alıp anlamlı içgörülere dönüştürmek ve **3 Sayı Performansı (3PT PPG)** yüksek olan oyuncuları tespit etmek.

## 🚀 Temel Özellikler
- **API Entegrasyonu:** `live.euroleague.net` üzerinden canlı maç verilerinin dinamik olarak çekilmesi.
- **Veri Dönüştürme (ETL):** Karmaşık JSON verilerinin Pandas DataFrame formatına dönüştürülmesi ve temizlenmesi.
- **Scouting Algoritması:**
  - Oyuncuların maç başına attığı 3 sayılık basket ortalamasının hesaplanması.
  - Belirli bir takımın (Örn: Fenerbahçe/ULK) kadrosu hariç tutularak, rakip takımlardaki en iyi şutörlerin filtrelenmesi.
- **Raporlama:** Analiz sonuçlarının karar destek mekanizmaları için sıralı bir liste halinde sunulması.

## 🛠️ Kullanılan Teknolojiler
- **Python 3.x**
- **Pandas** (Veri Manipülasyonu ve Analiz)
- **Requests** (HTTP API Çağrıları)
- **NumPy** (Sayısal İşlemler)

## 📊 Analiz Mantığı (Scouting Logic)
Proje şu adımları takip eder:
1. **Veri Toplama:** Tüm maçların "Play-by-Play" verisi API'den çekilir.
2. **Filtreleme:** Sadece belirli bir maç sayısının üzerindeki oyuncular dikkate alınır.
3. **Metrik Hesaplama:** `Total 3PT Points / Games Played` formülü ile verimlilik puanı oluşturulur.
4. **Eleme:** Halihazırda kadroda olan oyuncular listeden çıkarılır (Transfer hedefi belirlemek için).
5. **Sonuç:** Kriterlere uyan "En İyi 5 Aday" listelenir.

---

### 💻 Kurulum ve Çalıştırma

1. Repoyu klonlayın:
   ```bash
   git clone [https://github.com/KULLANICI_ADIN/EuroLeague-Player-Scouting-Analysis.git](https://github.com/KULLANICI_ADIN/EuroLeague-Player-Scouting-Analysis.git)
   
   Gerekli kütüphaneleri yükleyin:
   pip install pandas requests
   
   Notebook'u çalıştırın:
   jupyter notebook EuroLeague_API_Scouting.ipynb
