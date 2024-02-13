### 11.Grid Search Cross Validation

Grid Search Cross Validation, bir makine öğrenmesi modelinin hiperparametrelerini ayarlamak için kullanılan bir tekniktir. Bu teknik, belirtilen bir hiperparametreler kümesi üzerinde bir grid (ızgara) oluşturur ve her bir hiperparametre kombinasyonu için modelin performansını değerlendirir. Modelin performansı genellikle K-Fold Cross Validation kullanılarak ölçülür.

Grid Search Cross Validation'ın avantajları şunlardır:

- Tüm hiperparametre kombinasyonları değerlendirilir, bu da en iyi hiperparametrelerin bulunmasını sağlar.
- Modelin genelleme performansının daha doğru bir tahminini sağlar, çünkü modelin performansı K-Fold Cross Validation kullanılarak ölçülür.

Ancak, Grid Search Cross Validation'ın bazı dezavantajları da vardır:

- Büyük hiperparametre gridleri için zaman alıcı olabilir, çünkü her bir hiperparametre kombinasyonu için model eğitilir ve değerlendirilir.
- Hiperparametrelerin sürekli olduğu durumlarda kullanılamaz. Bu durumda, Random Search gibi diğer teknikler daha uygundur.

Python'da, `sklearn.model_selection` modülündeki `GridSearchCV` sınıfı ile Grid Search Cross Validation uygulanabilir.

```python
from sklearn.ensemble import GradientBoostingClassifier
from sklearn.model_selection import GridSearchCV
from sklearn.datasets import load_iris

# Iris veri setini yükle
data = load_iris()
X = data.data
y = data.target

# Modeli oluştur
model = GradientBoostingClassifier(random_state=42)

# Hiperparametre gridini tanımla
param_grid = {
    'n_estimators': [50, 100, 200],
    'learning_rate': [0.01, 0.1, 1.0],
    'max_depth': [1, 2, 3]
}

# Grid Search Cross Validation uygula
grid_search = GridSearchCV(model, param_grid, cv=5)
grid_search.fit(X, y)

print('Best parameters:', grid_search.best_params_)
print('Best score:', grid_search.best_score_)
```

Bu kod, Iris veri setini yükler, bir Gradient Boosting Classifier modeli oluşturur ve modelin hiperparametrelerini Grid Search Cross Validation kullanarak ayarlar.

Grid Search Cross Validation'ın kullanılabileceği bazı örnek senaryolar şunlardır:

1. **Model Seçimi:** Birden çok modelin performansını karşılaştırmak ve en iyi modeli seçmek için Grid Search Cross Validation kullanılabilir.
2. **Hiperparametre Ayarı:** Modelin hiperparametrelerini ayarlamak için Grid Search Cross Validation kullanılabilir.
3. **Feature Seçimi:** Hangi özelliklerin modelin performansını en çok etkilediğini belirlemek için Grid Search Cross Validation kullanılabilir.

Bu senaryoların her birinde, Grid Search Cross Validation, modelin genelleme performansının daha doğru bir tahminini sağlar ve en iyi hiperparametreleri bulmak için kullanılır.
