# Car-Price-Prediction-Transformer-Models
# İkinci El Araç Fiyat Tahmini: Zaman Serisi Tabanlı Transformatör Yaklaşımları

Bu proje, Türkiye'nin önde gelen ikinci el araç platformu **arabam.com**'dan elde edilen veriler üzerinden, ileri düzey bir fiyat tahmin sistemi geliştirmeyi amaçlamaktadır. Proje, geleneksel yöntemlerin ötesine geçerek, doğal dil işleme alanında devrim yaratan **transformatör modellerini** kullanmaktadır. Araçların kilometresi, yaşı, markası, modeli, motor özellikleri, yakıt tüketimi gibi birçok faktör analiz edilerek, ikinci el araç fiyatlarını etkileyen tüm unsurlar değerlendirilmiştir.

## Proje Amacı

Bu projenin temel amacı, ikinci el araç piyasasındaki dinamikleri öğrenerek, adil ve güvenilir bir fiyat tahmin modeli ortaya çıkarmaktır. Bu sayede, hem alıcılar hem de satıcılar için daha şeffaf bir pazar ortamı oluşturulması hedeflenmektedir.

## Kullanılan Teknolojiler

- **Veri Toplama:** Python ve BeautifulSoup kütüphanesi kullanılarak **arabam.com** üzerinden veri toplanmıştır.
- **Veri Ön İşleme:** Pandas kütüphanesi ile veri temizleme, eksik veri doldurma ve kategorik verilerin numerik hale getirilmesi işlemleri gerçekleştirilmiştir.
- **Modeller:** 
  - **Klasik Modeller:** Doğrusal Regresyon, Ridge Regresyonu, Lasso Regresyonu, Rastgele Orman Regresyonu, XGBoost.
  - **Derin Öğrenme Modelleri:** FCNN (Fully Connected Neural Network), TabTransformer, FTTransformer, Gated Tab Transformer.
- **Performans Metrikleri:** MAPE, MAE, MSE, RMSE ve R² skorları kullanılarak modellerin performansı değerlendirilmiştir.

## Veri Seti

Veri seti, **arabam.com** üzerinden toplanan ikinci el araç ilanlarından oluşmaktadır. Her bir araç için aşağıdaki özellikler toplanmıştır:

- Marka
- Model
- Yıl
- Kilometre
- Yakıt Tipi
- Vites Tipi
- Motor Gücü
- Motor Hacmi
- Renk
- Kasa Tipi
- Fiyat

## Model Performansı

Proje kapsamında test edilen modeller arasında en iyi performansı **FTTransformer** modeli göstermiştir. Aşağıda modellerin performans metrikleri yer almaktadır:

| Model                  | MAE       | MSE           | RMSE      | MAPE     | R²        |
|------------------------|-----------|---------------|-----------|----------|-----------|
| Linear Regresyon       | 228603.38 | 1.595249e+11  | 399405.71 | 34.64%   | 0.620508  |
| Random Forest          | 94320.64  | 5.231751e+10  | 228730.21 | 11.21%   | 0.894179  |
| XGBoost                | 95849.04  | 5.362738e+10  | 231575.87 | 11.62%   | 0.904842  |
| FCNN                   | 242786.27 | 1.599375e+11  | 399921.92 | 33.09%   | 0.627151  |
| TabTransformer         | 115476.23 | 7.221381e+10  | 268726.27 | 13.60%   | 0.882044  |
| **FTTransformer**      | **83878.88** | **3.899606e+10** | **197474.21** | **10.35%** | **0.937289** |
| GatedTab Transformer   | 99368.16  | 6.684354e+10  | 258541.18 | 11.71%   | 0.892506  |

## Sonuçlar

En iyi performansı gösteren **FTTransformer** modeli, %93.7 R² skoru ile ikinci el araç fiyat tahmininde oldukça başarılı sonuçlar vermiştir. Model, yüksek fiyatlı araçlarda biraz daha yüksek hata payı gösterse de, genel olarak başarılı bir tahmin performansı sergilemiştir.

## Kurulum

Projeyi yerel makinenizde çalıştırmak için aşağıdaki adımları izleyebilirsiniz:

1. **Gereksinimler:** Projeyi çalıştırmak için gerekli kütüphaneleri yükleyin:
   ```bash
   pip install -r requirements.txt
