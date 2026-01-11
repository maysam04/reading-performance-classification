# Okuma Performansı ve Anlama Seviyesi Analizi

## Proje Amacı

Bu projenin amacı, bireylerin okuma alışkanlıkları, çevresel koşulları ve kişisel durumları gibi çeşitli faktörlerin **okuduğunu anlama seviyesi (COMPREHENSION_LEVEL)** üzerindeki etkisini incelemektir. Çalışmada makine öğrenmesi yöntemleri kullanılarak bir sınıflandırma modeli oluşturulmuştur.

---

## Veri Seti Hakkında

Veri seti, okuma davranışını ve bilişsel durumu etkileyebilecek aşağıdaki türden değişkenleri içermektedir:

* Demografik bilgiler (AGE_CATEGORY, GENDER, MAJOR)
* Okuma süresi ve mola bilgileri (MINUTES_READING, MINUTES_BREAK)
* Dikkat ve zihinsel durum (FOCUS_LEVEL, MENTAL_FATIGUE, MOOD)
* İçerik ve ortam bilgileri (READING_GENRE, CONTENT_LEVEL_ENUM, DEVICE, LOCATION)
* Hedef değişken: **COMPREHENSION_LEVEL** (Low, Medium, High)

---

## Kullanılan Yöntemler

Projede aşağıdaki adımlar izlenmiştir:

1. **Veri Ön İşleme**

   * Kategorik değişkenler `get_dummies` yöntemi ile sayısallaştırılmıştır.
   * Sayısal değişkenler `StandardScaler` kullanılarak ölçeklendirilmiştir.

2. **Keşifsel Veri Analizi (EDA)**

   * Hedef değişkenin dağılımı görselleştirilmiştir.
   * Bazı değişkenler ile anlama seviyesi arasındaki ilişkiler incelenmiştir.

3. **Modelleme**

   * Logistic Regression modeli kullanılmıştır.
   * Modelin yakınsamaması (convergence warning) problemi, ölçeklendirme ve iterasyon sayısının artırılması ile giderilmiştir.

4. **Model Değerlendirme**

   * Accuracy
   * Precision, Recall, F1-score
   * Confusion Matrix

---

## Model Sonuçları (Özet)

* Model genel olarak **High** sınıfını tahmin etmede daha başarılıdır.
* **Low** ve **Medium** sınıflarında veri dengesizliği nedeniyle performans düşüktür.
* Accuracy yaklaşık %55–62 aralığındadır.

Bu durum, veri setinin küçük ve dengesiz olmasından kaynaklanmaktadır.

---

## Karşılaşılan Problemler ve Çözümler

* **ConvergenceWarning**:

  * Sayısal veriler ölçeklendirilmiştir.
  * `max_iter` değeri artırılmıştır.

* **Sınıf Dengesizliği**:

  * Sonuçlar yorumlanırken yalnızca accuracy değil, macro ve weighted ortalamalar da dikkate alınmıştır.

---

## Kullanılan Kütüphaneler

* pandas
* numpy
* matplotlib / seaborn
* scikit-learn

---

## Sonuç

Bu çalışma, okuma performansını etkileyen faktörlerin makine öğrenmesi ile analiz edilebileceğini göstermektedir. Daha dengeli ve büyük bir veri seti ile model başarımı artırılabilir.

---

## Not

Bu proje bir **ders kapsamında** hazırlanmıştır ve eğitim amaçlıdır.
