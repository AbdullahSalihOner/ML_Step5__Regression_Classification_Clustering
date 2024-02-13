### 9.Gradient Boosting Classifier

Gradient Boosting Classifier, bir dizi zayıf öğrenici (genellikle karar ağaçları) kullanarak bir topluluk modeli oluşturan bir makine öğrenmesi algoritmasıdır. Her bir zayıf öğrenici, önceki öğrenicinin hatalarını düzeltmeye çalışır. Bu, hataların bir gradyan iniş algoritması kullanılarak azaltılmasıyla elde edilir, bu da algoritmanın adını verir.

Gradient Boosting Classifier modeli, aşağıdaki avantajlara sahiptir:

- Hem sınıflandırma hem de regresyon problemlarında kullanılabilir.
- Özelliklerin ölçeklendirilmesi gerekmez.
- Hem kategorik hem de sürekli özelliklerle çalışabilir.
- Özellik önemini belirlemek için kullanılabilir, bu da modelin yorumlanabilirliğini artırır.

Ancak, Gradient Boosting Classifier modelinin bazı dezavantajları da vardır:

- Büyük veri setleri için eğitim süresi uzun olabilir.
- Karar ağaçlarına kıyasla daha az yorumlanabilir.
- Tahminler yapmak için birçok ağacın tahminlerini birleştirmek gerektiği için tahmin süresi uzun olabilir.

Python'da, `sklearn.ensemble` modülündeki `GradientBoostingClassifier` sınıfı ile Gradient Boosting Classifier modeli oluşturulabilir ve eğitilebilir.

```python
from sklearn.ensemble import GradientBoostingClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score
from sklearn.datasets import load_iris

# Iris veri setini yükle
data = load_iris()
X = data.data
y = data.target

# Veri setini eğitim ve test setlerine ayır
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Modeli oluştur ve eğit
model = GradientBoostingClassifier(n_estimators=100, learning_rate=1.0, max_depth=1, random_state=42)
model.fit(X_train, y_train)

# Tahminler yap
y_pred = model.predict(X_test)

# Doğruluk hesapla
accuracy = accuracy_score(y_test, y_pred)

print('Accuracy:', accuracy)
```

Gradient Boosting Classifier'ın kullanılabileceği bazı örnek senaryolar şunlardır:

1. **Iris Çiçeği Sınıflandırması:** Iris çiçeğinin türünü, çiçeğin taç ve çanak yapraklarının boyutlarına göre tahmin etmek.
2. **E-posta Spam Tespiti:** Bir e-postanın spam olup olmadığını, e-postanın içeriğine göre tahmin etmek.
3. **Hastalık Teşhisi:** Bir hastanın belirli bir hastalığa sahip olup olmadığını, çeşitli sağlık göstergelerine (örneğin, yaş, kan basıncı, kolesterol seviyesi, vb.) göre tahmin etmek.

Bu senaryoların her birinde, Gradient Boosting Classifier modeli, bağımsız değişkenler ve hedef değişken arasındaki ilişkiyi modellemek için kullanılır. Ancak, Gradient Boosting modelinin performansı, ağaç sayısı ve ağaçların derinliği gibi hiperparametrelere bağlıdır, bu nedenle model seçimi ve hiperparametre ayarı önemlidir.
