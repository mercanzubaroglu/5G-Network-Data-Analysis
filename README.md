# 5G Network Data Analysis / 5G Ağ Veri Analizi

## Dataset

The dataset used in this project is the **5G Network Data** available on Kaggle. It contains information about network performance metrics such as download speed, upload speed, signal strength, and connection drop rates, among others.
Bu projede kullanılan veri seti, Kaggle'da bulunan **5G Ağ Verileri**dir. Diğerlerinin yanı sıra indirme hızı, yükleme hızı, sinyal gücü ve bağlantı kopma oranları gibi ağ performansı ölçümleri hakkında bilgiler içerir.

You can download the dataset from the following link:
[Download 5G Network Data](https://www.kaggle.com/datasets/vinothkannaece/5g-network-data)

---

## Project Overview / Proje Hakkında

This project focuses on analyzing 5G network performance data to gain insights into key performance indicators such as download/upload speeds, signal strength, latency, device models, network types, and connection issues. By performing various statistical and machine learning analyses, the goal is to optimize network performance and predict potential connection problems.  
Bu proje, 5G ağ performans verilerini analiz etmeye odaklanır. İndirme/yükleme hızları, sinyal gücü, gecikme süresi, cihaz modelleri, ağ tipleri ve bağlantı sorunları gibi önemli performans göstergeleri incelenir. Çeşitli istatistiksel ve makine öğrenimi analizleri ile ağ performansını optimize etmek ve bağlantı problemlerini tahmin etmek amaçlanmıştır.

---

## Key Analyses / Ana Analizler

1. **Descriptive Statistics / Temel Tanımlayıcı İstatistikler**:  
   Statistical summaries (mean, median, variance, etc.) for numerical columns, providing a quick overview of network performance metrics.  
   Sayısal sütunlar için temel istatistiksel özetler (ortalama, medyan, varyans vb.) sağlanarak ağ performans metriklerinin genel bir görünümü elde edilir.

2. **Location-Based Analysis / Lokasyon Bazlı Analiz**:  
   Analyzing download speeds and signal strength based on different geographic locations, helping to identify regions with the best and worst network performance.  
   Farklı coğrafi konumlara göre indirme hızları ve sinyal gücü analiz edilir, böylece en iyi ve en kötü ağ performansına sahip bölgeler belirlenir.

3. **Device & Carrier Comparison / Cihaz & Operatör Karşılaştırması**:  
   Comparing device models and carriers in terms of download speed and signal strength. This helps to identify the best-performing devices and operators.  
   Cihaz modelleri ve operatörler, indirme hızı ve sinyal gücü açısından karşılaştırılır. Bu analiz, en iyi performans gösteren cihazlar ve operatörleri belirler.

4. **Categorical Group Analysis / Kategorik Grup Analizleri**:  
   Grouping the data by network type (e.g., 5G, LTE) and congestion level, and comparing average performance metrics such as download speed and latency.  
   Ağ tipi (örneğin, 5G, LTE) ve yoğunluk seviyelerine göre veriler gruplandırılır ve ortalama performans metrikleri karşılaştırılır.

5. **Correlation Heatmap / Korelasyon Isı Haritası**:  
   A heatmap that shows the correlations between different numerical variables, highlighting key relationships in the data.  
   Farklı sayısal değişkenler arasındaki korelasyonları gösteren bir ısı haritası, verilerdeki ana ilişkileri vurgular.

6. **Hourly Avg Download Speed / Saatlik Ortalama İndirme Hızı**:  
   Analyzing the average download speed by hour of the day to understand peak performance times.  
   Günün saatlerine göre ortalama indirme hızları analiz edilir, bu sayede performans zirve noktaları anlaşılır.

7. **Signal Strength vs. Download Speed / Sinyal Gücü & İndirme Hızı**:  
   A scatter plot visualizing the relationship between signal strength and download speed, segmented by carrier to highlight differences.  
   Sinyal gücü ile indirme hızı arasındaki ilişkiyi görselleştiren bir dağılım grafiği, operatöre göre bölümlendirilir ve farklılıklar vurgulanır.

8. **Download Speed by Network Type / Ağ Tipine Göre İndirme Hızı**:  
   A box plot to visualize the distribution of download speeds across different network types.  
   Farklı ağ tiplerinde indirme hızlarının dağılımını görselleştiren bir kutu grafiği.

9. **Performance Prediction (ML) / Performans Tahmini (Makine Öğrenimi)**:  
   Using a RandomForest model to predict dropped connections based on features like signal strength, download speed, and latency.  
   Signal strength, download speed ve latency gibi özelliklere dayalı olarak bağlantı düşmelerini tahmin etmek için RandomForest modeli kullanılır.

10. **Connection Problem Analysis / Bağlantı Problemleri Analizi**:  
    Analyzing the rate of dropped connections and their correlations with other factors like handover count and ping times.  
    Bağlantı düşme oranı ve bunların handover sayısı ve ping süresi gibi diğer faktörlerle korelasyonu analiz edilir.

---

### Dropped Connection Prediction Report / Bağlantı Düşmesi Tahmini Raporu

The Random Forest model was used to predict dropped connections. Below is the performance of the model:  
Bağlantı düşmesi tahmin etmek için Random Forest modeli kullanıldı. Aşağıda modelin başarımı verilmiştir:

| **Metric / Ölçüt**    | **False / Yanlış** | **True / Doğru** | **Macro Avg** | **Weighted Avg** |
|-----------------------|--------------------|------------------|---------------|------------------|
| **Precision / Hassasiyet** | 0.50               | 0.49             | 0.50          | 0.50             |
| **Recall / Geri Çağırma**  | 0.50               | 0.49             | 0.50          | 0.50             |
| **F1-Score**          | 0.50               | 0.49             | 0.50          | 0.50             |
| **Support / Destek**   | 5032               | 4968             | 10000         | 10000            |

#### Evaluation / Değerlendirme:
- **Accuracy (Doğruluk)**: 50%  
  The accuracy of the model is 50%, which means the model is predicting correctly half of the time. This indicates that the model has a balanced performance but might need further improvement.
  Modelin doğruluğu %50'dir, yani model tahminleri doğru yapma oranı yarı yarıya. Bu, modelin dengeli bir performansa sahip olduğunu ancak daha fazla iyileştirmeye ihtiyaç duyduğunu gösterir.
  
- **Precision (Hassasiyet)**: 50% for both False and True predictions  
  Precision indicates the percentage of true positive predictions (True connections predicted correctly) out of all positive predictions made by the model. A 50% precision shows that for every positive prediction, half are correct.
  Hassasiyet, modelin yaptığı pozitif tahminlerden doğru yapılan pozitif tahminlerin oranını gösterir. %50 hassasiyet, her pozitif tahminden yarısının doğru olduğunu gösterir.

- **Recall (Geri Çağırma)**: 50% for both False and True predictions  
  Recall refers to the model's ability to identify all true positives (True connections that were actually dropped). A 50% recall means the model is identifying half of the dropped connections.
  Geri çağırma, modelin doğru pozitif tahminleri (gerçekten düşen bağlantılar) tanıma yeteneğini ifade eder. %50 geri çağırma, modelin düşen bağlantıların yarısını doğru şekilde tespit ettiğini gösterir.

- **F1-Score**: 50% for both False and True predictions  
  The F1-Score is the harmonic mean of precision and recall. With an F1-Score of 50%, this indicates that the model's overall performance is balanced between precision and recall, but there is room for improvement in both areas.
  F1 puanı, hassasiyet ve geri çağırmanın harmonik ortalamasıdır. %50 F1 puanı, modelin genel performansının hassasiyet ve geri çağırma arasında dengeli olduğunu, ancak her iki alanda da iyileştirme yapılabileceğini gösterir.

#### Conclusion / Sonuç:
- **Model Performance**: The model shows balanced performance with an accuracy rate of 50%. However, it is crucial to improve the model's ability to correctly predict dropped connections by tuning the features, adding more data, or experimenting with more advanced machine learning models.
- **Modelin Performansı**: Model, %50 doğruluk oranı ile dengeli bir performans sergiliyor. Ancak, modelin doğru bağlantı düşüşlerini tahmin etme yeteneğini artırmak için özellikleri ayarlamak, daha fazla veri eklemek veya daha ileri makine öğrenimi modelleriyle denemeler yapmak önemlidir.

This analysis provides an initial insight into predicting dropped connections, and further optimization steps can be taken to enhance model accuracy.  
Bu analiz, bağlantı düşmelerini tahmin etme konusunda ilk içgörüyü sağlar ve model doğruluğunu artırmak için daha fazla optimizasyon adımları atılabilir.

---
