### 12.Randomsized Search Cross Validation

Randomized Search Cross Validation, bir makine öğrenmesi modelinin hiperparametrelerini ayarlamak için kullanılan bir tekniktir. Bu teknik, belirtilen bir hiperparametre dağılımı üzerinde rastgele örnekler alır ve her bir hiperparametre kombinasyonu için modelin performansını değerlendirir. Modelin performansı genellikle K-Fold Cross Validation kullanılarak ölçülür.

Randomized Search Cross Validation'ın avantajları şunlardır:

- Büyük hiperparametre uzayları için daha verimlidir, çünkü tüm hiperparametre kombinasyonlarını değerlendirmek yerine belirli bir sayıda rastgele kombinasyonu değerlendirir.
- Hem ayrık hem de sürekli hiperparametre dağılımları ile kullanılabilir.
- Modelin genelleme performansının daha doğru bir tahminini sağlar, çünkü modelin performansı K-Fold Cross Validation kullanılarak ölçülür.

Ancak, Randomized Search Cross Validation'ın bazı dezavantajları da vardır:

- En iyi hiperparametrelerin bulunması garantili değildir, çünkü hiperparametre uzayının sadece bir alt kümesi araştırılır.
- Hiperparametre dağılımlarının uygun bir şekilde belirlenmesi gereklidir.

Python'da, `sklearn.model_selection` modülündeki `RandomizedSearchCV` sınıfı ile Randomized Search Cross Validation uygulanabilir. 

```python
from sklearn.ensemble import GradientBoostingClassifier
from sklearn.model_selection import RandomizedSearchCV
from sklearn.datasets import load_iris
from scipy.stats import uniform, randint

# Iris veri setini yükle
data = load_iris()
X = data.data
y = data.target

# Modeli oluştur
model = GradientBoostingClassifier(random_state=42)

# Hiperparametre dağılımını tanımla
param_dist = {
    'n_estimators': randint(50, 200),
    'learning_rate': uniform(0.01, 1.0),
    'max_depth': randint(1, 3)
}

# Randomized Search Cross Validation uygula
random_search = RandomizedSearchCV(model, param_dist, n_iter=100, cv=5, random_state=42)
random_search.fit(X, y)

print('Best parameters:', random_search.best_params_)
print('Best score:', random_search.best_score_)
```

Bu kod, Iris veri setini yükler, bir Gradient Boosting Classifier modeli oluşturur ve modelin hiperparametrelerini Randomized Search Cross Validation kullanarak ayarlar.

Randomized Search Cross Validation'ın kullanılabileceği bazı örnek senaryolar şunlardır:

1. **Model Seçimi:** Birden çok modelin performansını karşılaştırmak ve en iyi modeli seçmek için Randomized Search Cross Validation kullanılabilir.
2. **Hiperparametre Ayarı:** Modelin hiperparametrelerini ayarlamak için Randomized Search Cross Validation kullanılabilir.
3. **Feature Seçimi:** Hangi özelliklerin modelin performansını en çok etkilediğini belirlemek için Randomized Search Cross Validation kullanılabilir.

Bu senaryoların her birinde, Randomized Search Cross Validation, modelin genelleme performansının daha doğru bir tahminini sağlar ve en iyi hiperparametreleri bulmak için kullanılır.
