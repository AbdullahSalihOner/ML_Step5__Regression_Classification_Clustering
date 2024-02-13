### 14.Hieararchic Clusturing

Hierarchical Clustering (Hiyerarşik Kümeleme), bir unsupervised (denetimsiz) öğrenme algoritmasıdır ve veri noktalarını benzerliklerine göre gruplara (veya "kümeler") ayırmak için kullanılır. Bu algoritma, bir hiyerarşi veya ağaç yapısı oluşturarak kümeleri oluşturur.

Hiyerarşik Kümeleme'nin iki ana türü vardır: Agglomerative (Birleştirici) ve Divisive (Bölücü). Birleştirici hiyerarşik kümeleme, her veri noktasını ayrı bir küme olarak başlatır ve benzer kümeleri birleştirir. Bölücü hiyerarşik kümeleme, tüm veri noktalarını içeren tek bir küme ile başlar ve kümeyi alt kümelerine böler.

Hiyerarşik Kümeleme'nin avantajları şunlardır:

- K sayısının önceden belirlenmesi gerekmez.
- Küme sayısı ve yapı hakkında bilgi sağlayan bir dendrogram (ağaç diyagramı) oluşturur.
- Farklı küme şekillerini ve boyutlarını işleyebilir.

Ancak, Hiyerarşik Kümeleme'nin bazı dezavantajları da vardır:

- Büyük veri setleri için zaman alıcı olabilir, çünkü her veri noktası arasındaki mesafeyi hesaplar.
- Bir kez birleştirildiğinde veya bölündüğünde, kümeler daha sonra yeniden düzenlenemez.

Python'da, `scipy.cluster.hierarchy` veya `sklearn.cluster` modülleri ile Hiyerarşik Kümeleme uygulanabilir. Bu modüller, bir model oluşturur, modeli veriye uyarlar ve veri noktalarının küme etiketlerini tahmin eder.

```python
from sklearn.cluster import AgglomerativeClustering
from sklearn.datasets import load_iris
import matplotlib.pyplot as plt

# Iris veri setini yükle
data = load_iris()
X = data.data

# Modeli oluştur ve eğit
hclust = AgglomerativeClustering(n_clusters=3)
hclust.fit(X)

# Küme etiketlerini tahmin et
labels = hclust.labels_

# Sonuçları çizdir
plt.scatter(X[:, 0], X[:, 1], c=labels)
plt.show()
```

Bu kod, Iris veri setini yükler, bir Agglomerative Hierarchical Clustering modeli oluşturur ve eğitir, veri noktalarının küme etiketlerini tahmin eder ve sonuçları çizdirir.

Hierarchical Clustering'ın kullanılabileceği bazı örnek senaryolar şunlardır:

1. **Müşteri Segmentasyonu:** Müşterileri satın alma davranışlarına, demografik özelliklerine veya diğer özelliklerine göre segmentlere ayırmak için Hierarchical Clustering kullanılabilir.
2. **Genetik Sınıflandırma:** Genler veya proteinler arasındaki benzerlikleri belirlemek için Hierarchical Clustering kullanılabilir.
3. **Sosyal Ağ Analizi:** Sosyal ağlarda toplulukları tespit etmek için Hierarchical Clustering kullanılabilir.

Bu senaryoların her birinde, Hierarchical Clustering, veri noktalarını benzerliklerine göre gruplara ayırır ve bu grupları analiz etmek veya kullanmak için kullanılır.
