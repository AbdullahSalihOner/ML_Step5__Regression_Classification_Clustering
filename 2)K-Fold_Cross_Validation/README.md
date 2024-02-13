### 10.K-Fold Cross Validation

K-Fold Cross Validation, bir makine öğrenmesi modelinin performansını değerlendirmek için kullanılan bir tekniktir. Bu teknik, veri setini "K" sayıda eşit büyüklükteki alt küme (veya "fold") olarak bölme ve modeli bu "K" alt küme üzerinde "K" kez test etme ve eğitme prensibine dayanır.

Her bir iterasyonda, model, "K-1" alt küme üzerinde eğitilir ve kalan alt küme üzerinde test edilir. Bu işlem, her alt kümenin tam olarak bir kez test seti olarak kullanıldığı "K" iterasyon boyunca devam eder. Sonuç olarak, "K" farklı modelin performansı elde edilir.

K-Fold Cross Validation'ın avantajları şunlardır:

- Tüm veri seti hem eğitim hem de test için kullanılır, bu da modelin genelleme performansının daha doğru bir tahminini sağlar.
- Modelin performansının varyansını azaltır, çünkü modelin performansı "K" farklı alt küme üzerinde ölçülür.

Ancak, K-Fold Cross Validation'ın bazı dezavantajları da vardır:

- Büyük veri setleri için zaman alıcı olabilir, çünkü model "K" kez eğitilir ve test edilir.
- Veri setinin rastgele bölünmesi, eğitim ve test setlerinin dağılımlarının farklı olmasına neden olabilir. Bu durumda, stratified K-Fold Cross Validation kullanılabilir.

Python'da, `sklearn.model_selection` modülündeki `cross_val_score` fonksiyonu ile K-Fold Cross Validation uygulanabilir.

```python
from sklearn.ensemble import GradientBoostingClassifier
from sklearn.model_selection import cross_val_score
from sklearn.datasets import load_iris

# Iris veri setini yükle
data = load_iris()
X = data.data
y = data.target

# Modeli oluştur
model = GradientBoostingClassifier(n_estimators=100, learning_rate=1.0, max_depth=1, random_state=42)

# K-Fold Cross Validation uygula
scores = cross_val_score(model, X, y, cv=5)

print('Cross-validation scores:', scores)
print('Average cross-validation score:', scores.mean())
```

Bu kod, Iris veri setini yükler, bir Gradient Boosting Classifier modeli oluşturur ve modelin performansını 5-Fold Cross Validation kullanarak değerlendirir.

K-Fold Cross Validation'ın kullanılabileceği bazı örnek senaryolar şunlardır:

1. **Model Seçimi:** Birden çok modelin performansını karşılaştırmak ve en iyi modeli seçmek için K-Fold Cross Validation kullanılabilir.
2. **Hiperparametre Ayarı:** Modelin hiperparametrelerini ayarlamak için K-Fold Cross Validation kullanılabilir. Bu genellikle bir grid search veya random search ile birlikte kullanılır.
3. **Feature Seçimi:** Hangi özelliklerin modelin performansını en çok etkilediğini belirlemek için K-Fold Cross Validation kullanılabilir.

Bu senaryoların her birinde, K-Fold Cross Validation, modelin genelleme performansının daha doğru bir tahminini sağlar ve modelin performansının varyansını azaltır.
