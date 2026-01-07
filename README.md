# 📊 Psikolojik Sağlık Geçmişi Sınıflandırma Sistemi

**Veri Madenciliği Dersi – Digital Nomads**

Bu proje, bireylerin **depresyon ve ruhsal hastalık geçmişine sahip olup olmadığını**
(**History of Mental Illness – 0 / 1**) tahmin etmeyi amaçlayan
**ikili sınıflandırma (Binary Classification)** problemine odaklanmaktadır.

Çalışmada, **davranışsal, yaşam tarzı ve sosyo-ekonomik veriler** kullanılarak
veri madenciliği ve makine öğrenmesi yöntemlerinin performansı analiz edilmiştir.

> ⚠️ Bu çalışma **klinik veya tıbbi tanı koyma amacı taşımaz**.
> Ruh sağlığı alanında **tarama (screening)** ve **karar destek sistemlerinin**
> akademik olarak nasıl tasarlanabileceğini incelemektedir.

---

## 📊 Veri Seti

* Kaynak: **Kaggle – Depression Dataset (Synthetic)**
* Toplam gözlem: **413.768**
* Toplam özellik: **15**
* Hedef değişken: **History of Mental Illness (0 / 1)**

Veri seti, gerçek hasta verisi içermeyen **sentetik** bir yapıdadır ve
eğitsel analizler için uygundur.

Kullanılan temel değişkenler:

* Yaş
* Medeni durum
* Eğitim seviyesi
* Çocuk sayısı
* Sigara kullanımı
* Fiziksel aktivite
* Çalışma durumu
* Yıllık gelir

---

## 🎯 Projenin Amacı

* Ruhsal hastalık geçmişi olan bireyleri sınıflandırmak
* Özellik seçimi yöntemlerinin model performansına etkisini incelemek
* PCA sonrası performans değişimini analiz etmek
* Sınıf dengesizliği probleminin etkilerini değerlendirmek
* Tek model yerine **sistem bazlı karar yapısı** geliştirmek

---

## ⚠️ Temel Problemler

Veri analizi sonucunda iki ana sınırlayıcı faktör tespit edilmiştir:

* **Sınıf dengesizliği (Class Imbalance)**
* **Sınıflar arası yüksek benzerlik (Low Separability)**

Bu nedenle:

* Accuracy tek başına yeterli değildir
* **Recall ve F1-score** metrikleri öncelikli değerlendirilmiştir

---

## 🛠 Kullanılan Yöntemler

### 🔹 Veri Ön İşleme

* Label Encoding
* Hedef dağılım analizi
* Outlier incelemesi
* Eksik değer kontrolü

### 🔹 Özellik Seçimi

* Chi-Square
* Mutual Information
* VarianceThreshold
* SelectKBest (k = 10, 30)

### 🔹 Boyut İndirgeme

* PCA (farklı `n_components` değerleri ile)

### 🔹 Kullanılan Modeller

* Logistic Regression
* Decision Tree Classifier
* K-Nearest Neighbors (KNN)
* Gaussian Naive Bayes
* Özellik seçimi + PCA + Model kombinasyonları

---

## 🧩 İki Aşamalı Sınıflandırma Yaklaşımı

Gerçek hayattaki tarama sistemlerinden ilham alınarak
**iki aşamalı bir sınıflandırma yapısı** tasarlanmıştır:

**Aşama 1**

* Düşük threshold
* Amaç: Potansiyel vakaları kaçırmamak

**Aşama 2**

* Recall ve Precision dengesi
* Threshold istatistiksel olarak belirlenmiştir

Bu yaklaşım, tek bir model yerine
**sistem bazlı karar verme anlayışını** yansıtır.

---

## 📈 Sonuçların Özeti

* Baz modellerde Recall sistematik olarak düşüktür
* Sınıf dengesizliği temel sınırlayıcı faktördür
* PCA bazı modellerde sınırlı iyileşme sağlamıştır
* Performans sınırları modelden çok **verinin doğasından** kaynaklanmaktadır

---

## 📁 Proje Yapısı ve Ekip

Proje üç ekip üyesi tarafından yürütülmüştür ve
her üye kendi Jupyter Notebook dosyasında çalışmıştır:

| Üye         | Katkılar                                         |
| ----------- | ------------------------------------------------ |
| **Wisam**   | Feature Engineering, PCA, Logistic Regression    |
| **Mustafa** | KNN, GaussianNB, Threshold Analizi               |
| **Cüneyd**  | Baz Modeller, Logistic Regression, Decision Tree |

**Grup Adı:** DigitalNomads

---

## 🧰 Kullanılan Teknolojiler

* Python 3.x
* Pandas, NumPy
* Scikit-learn
* Matplotlib, Seaborn
* Jupyter Notebook

---

## 🔧 Nasıl Çalıştırılır?

```bash
git clone <repo-link>
cd PsikolojikSaglikGecmisi_SiniflandirmaSistemi
jupyter notebook
```

Notebook dosyalarından herhangi biri açılarak çalışmalar incelenebilir.

---

## 📄 Lisans

Bu proje **yalnızca akademik amaçlıdır**.
Ticari kullanım için uygun değildir.
