### 13.K-Means Clusturing

K-Means Clustering, bir unsupervised (denetimsiz) öğrenme algoritmasıdır ve veri noktalarını benzerliklerine göre gruplara (veya "kümelere") ayırmak için kullanılır. Algoritma, her bir kümenin merkezini (veya "merkezini") hesaplar ve her veri noktasını en yakın merkeze göre atar.

K-Means Clustering'in temel adımları şunlardır:

1. K merkezini rastgele başlatın.
2. Her veri noktasını en yakın merkeze göre atayın.
3. Her kümenin merkezini, kümedeki tüm veri noktalarının ortalaması olarak güncelleyin.
4. Atama değişiklikleri olana kadar 2. ve 3. adımları tekrarlayın.

K-Means Clustering'in avantajları şunlardır:

- Basit ve kolay uygulanabilir.
- Büyük veri setleri için hızlı ve verimli.

Ancak, K-Means Clustering'in bazı dezavantajları da vardır:

- K sayısının önceden belirlenmesi gerekiyor.
- Başlangıç merkezlerine duyarlıdır ve farklı başlangıç noktaları farklı sonuçlara yol açabilir.
- Küme şekilleri ve boyutlarına duyarlıdır, ve genellikle yuvarlak kümeleri varsayar.

Python'da, `sklearn.cluster` modülündeki `KMeans` sınıfı ile K-Means Clustering uygulanabilir. Bu sınıf, bir model oluşturur, modeli veriye uyarlar ve veri noktalarının küme etiketlerini tahmin eder.

```python
from sklearn.cluster import KMeans
from sklearn.datasets import load_iris
import matplotlib.pyplot as plt

# Iris veri setini yükle
data = load_iris()
X = data.data

# Modeli oluştur ve eğit
kmeans = KMeans(n_clusters=3, random_state=42)
kmeans.fit(X)

# Küme etiketlerini tahmin et
labels = kmeans.predict(X)

# Sonuçları çizdir
plt.scatter(X[:, 0], X[:, 1], c=labels)
plt.show()
```

Bu kod, Iris veri setini yükler, bir K-Means Clustering modeli oluşturur ve eğitir, veri noktalarının küme etiketlerini tahmin eder ve sonuçları çizdirir.

K-Means Clustering'ın kullanılabileceği bazı örnek senaryolar şunlardır:

1. **Müşteri Segmentasyonu:** Müşterileri satın alma davranışlarına, demografik özelliklerine veya diğer özelliklerine göre segmentlere ayırmak için K-Means Clustering kullanılabilir.
2. **Anomali Tespiti:** Veri noktalarını normal ve anormal kümeler olarak ayırmak için K-Means Clustering kullanılabilir.
3. **Görüntü Sıkıştırma:** Bir görüntüdeki renkleri kümelere ayırmak için K-Means Clustering kullanılabilir, bu da görüntünün sıkıştırılmasını sağlar.

Bu senaryoların her birinde, K-Means Clustering, veri noktalarını benzerliklerine göre gruplara ayırır ve bu grupları analiz etmek veya kullanmak için kullanılır.
