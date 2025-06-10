# Adult Veri Seti ile Gelir Sınıflandırması Projesi

## Proje Hakkında

Bu proje, UCI Makine Öğrenmesi Veri Deposu'ndan alınan Adult veri setini kullanarak bireylerin demografik özelliklerine dayalı olarak yıllık gelirlerinin 50K dolar üzerinde olup olmadığını tahmin etmeyi amaçlamaktadır.

## Veri Seti Özellikleri

Veri seti 15 özellik ve 48,842 gözlem içermektedir. Özellikler:
- **Demografik bilgiler**: yaş, cinsiyet, ırk
- **Eğitim bilgileri**: eğitim seviyesi, eğitim yılı
- **Mesleki bilgiler**: çalışma sınıfı, meslek, haftalık çalışma saati
- **Aile bilgileri**: medeni durum, ilişki durumu
- **Finansal bilgiler**: sermaye kazancı, sermaye kaybı
- **Hedef değişken**: gelirin 50K üzeri olup olmaması

## Gerçekleştirilen İşlemler

### 1. Veri Yükleme ve Keşif
- Veri seti UCI deposundan direkt olarak yüklendi
- İlk 30 gözlem incelenerek veri yapısı anlaşıldı

### 2. Eksik Veri Analizi ve Doldurma
- `workclass`, `occupation` ve `native-country` sütunlarında eksik veriler tespit edildi
- Kategorik değişkenler mod (en sık tekrar eden değer) ile dolduruldu
- Bazı eksikler "Bilinmiyor" etiketi ile işaretlendi

### 3. Veri Dönüşümleri
- **Label Encoding**: `income`, `sex`, `race` sütunları sayısallaştırıldı
- **One-Hot Encoding**: `workclass` ve `relationship` sütunları dönüştürüldü
- **Ordinal Encoding**: `education` ve `marital-status` sıralı kategorik değişkenlere uygulandı
- **Frequency Encoding**: `occupation` ve `native-country` sütunları frekanslarına göre kodlandı

### 4. Veri Ölçeklendirme
- Sayısal değişkenler (`age`, `fnlwgt`, `education-num`, `capital-gain`, `capital-loss`, `hours-per-week`) StandardScaler ile standartlaştırıldı

### 5. Veri Bölme
- Veri seti %80 eğitim, %20 test olarak ayrıldı

### 6. Modelleme ve Değerlendirme
- Lojistik Regresyon modeli uygulandı
- Model performansı F1 skoru ve doğruluk oranı ile değerlendirildi
