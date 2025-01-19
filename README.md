# Car-Price-Prediction-Transformer-Models
# İkinci El Araç Fiyat Tahmini: Zaman Serisi Tabanlı Transformatör Yaklaşımları

Bu proje, bir ikinci el araç platformundan elde edilen veriler üzerinden, ileri düzey bir fiyat tahmin sistemi geliştirmeyi amaçlamaktadır. Proje, geleneksel yöntemlerin ötesine geçerek, doğal dil işleme alanında devrim yaratan **transformatör modellerini** kullanmaktadır. Araçların kilometresi, yaşı, markası, modeli, motor özellikleri, yakıt tüketimi gibi birçok faktör analiz edilerek, ikinci el araç fiyatlarını etkileyen tüm unsurlar değerlendirilmiştir.

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
- Seri
- Yıl
- Kilometre
- Yakıt Tipi
- Vites Tipi
- Kasa Tipi
- Renk
- Motor Hacmi
- Motor Gücü
- Çekiş
- Ortalama Yakıt Tüketimi
- Yakıt Deposu
- Fiyat



## Veri Görselleştirme

Veri seti üzerinde yapılan analizler sonucunda çeşitli grafikler oluşturulmuştur. Bu grafikler, veri setindeki trendleri ve ilişkileri anlamak için kullanılmıştır.

### 1. Yakıt Tipi Dağılımı

![yakıt_tipi](https://github.com/user-attachments/assets/8bc41b79-f824-4ab2-890d-cb7b4b4cf9ba)

Yakıt tiplerinin dağılımını gösteren pasta grafiği. En yaygın yakıt tipi **Benzin** olarak görülmektedir.

### 2. Vites Tipi Dağılımı
![vites](https://github.com/user-attachments/assets/99d6db14-2a7c-4def-b01a-837ac497f748)

Vites tiplerinin dağılımını gösteren pasta grafiği. Veri setinde en çok temsil edilen vites tipi **Düz** vites olmuştur.

### 3. Araba Markaları
![marka-adet](https://github.com/user-attachments/assets/ac95ad1f-8eb4-4b62-a54e-1231ea645ab6)

Araba markalarının dağılımını gösteren grafik. En yaygın marka **Renault** olurken, en az bulunan marka **Lada** olmuştur.

### 4. Kasa Tipleri
 ![kasa_tipi](https://github.com/user-attachments/assets/ad889046-2c49-42e7-ad59-11f8907540be)
 
Araçların kasa tiplerinin dağılımını gösteren grafik. En fazla bulunan kasa tipi **Sedan** olurken, en az rastlanan kasa tipi **Coupe** olmuştur.

### 5. Renk Dağılımı
![renkler](https://github.com/user-attachments/assets/a6b14180-c355-419c-b6bd-8030fbd86d85)

Araçların renklerinin dağılımını gösteren grafik. En çok bulunan araç rengi **Beyaz** olurken, en az bulunan renk **Pembe** olmuştur.


### 6. Marka-Fiyat Dağılımı
![marka-fiyat](https://github.com/user-attachments/assets/ba6ad975-df80-4d2d-b43a-d6b9463b0b31)

Her bir markanın fiyatlarını gösteren boxplot grafiği. En yüksek fiyatlar **Porsche** markasında görülmektedir.

### 7. Marka-Fiyat-Vites Tipi Dağılımı
![marka-fiyat-vites](https://github.com/user-attachments/assets/eb73e0d0-1798-4d16-b4be-96855e3c9364)

Marka ve vites tiplerine göre fiyatların dağılımını gösteren boxplot grafiği. Otomatik vitesli araçların fiyatları genellikle daha yüksektir.

### 8. Kasa-Vites-Fiyat Dağılımı
![kasatipi-fiyat](https://github.com/user-attachments/assets/443ceeb3-dad9-4ab0-9e40-46968c54e6e5)

Her bir kasa tipine ait araçların viteslere göre dağılımı yer verilmiştir. En yüksek fiyatlı araçlar **Otomatik** vitesli araçlar olmuştur.


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

![fttransformer-epochloss](https://github.com/user-attachments/assets/2198b484-1d57-4fc7-856d-70852dbac9f5)

### FTTransformer Epoch Size Loss Grafiği

Yukarıda FTTransformer modeline ait epoch size loss grafiğine yer verilmiştir.

![ftt-scatter1](https://github.com/user-attachments/assets/d9d85262-fc1b-477e-81fa-fb09ca5ab632)

### FTTransformer Scatter Grafiği

FTTransformer'a ait grafikte gerçek veriler ile tahmin verileri nokta grafiği ile yer verilmiştir. Linear bir çizgi beklenmektedir.



