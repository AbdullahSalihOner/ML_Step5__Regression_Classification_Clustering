<h1>MachineLearning_Step5_Regression_Classification_Clustering</h1>

### 9.Gradient Boosting Classifier

Gradient Boosting Classifier, bir dizi zayıf öğrenici (genellikle karar ağaçları) kullanarak bir topluluk modeli oluşturan bir makine öğrenmesi algoritmasıdır. Her bir zayıf öğrenici, önceki öğrenicinin hatalarını düzeltmeye çalışır. Bu, hataların bir gradyan iniş algoritması kullanılarak azaltılmasıyla elde edilir, bu da algoritmanın adını verir.



### 10.K-Fold Cross Validation

K-Fold Cross Validation, bir makine öğrenmesi modelinin performansını değerlendirmek için kullanılan bir tekniktir. Bu teknik, veri setini "K" sayıda eşit büyüklükteki alt küme (veya "fold") olarak bölme ve modeli bu "K" alt küme üzerinde "K" kez test etme ve eğitme prensibine dayanır.



### 11.Grid Search Cross Validation

Grid Search Cross Validation, bir makine öğrenmesi modelinin hiperparametrelerini ayarlamak için kullanılan bir tekniktir. Bu teknik, belirtilen bir hiperparametreler kümesi üzerinde bir grid (ızgara) oluşturur ve her bir hiperparametre kombinasyonu için modelin performansını değerlendirir. Modelin performansı genellikle K-Fold Cross Validation kullanılarak ölçülür.



### 12.Randomsized Search Cross Validation

Randomized Search Cross Validation, bir makine öğrenmesi modelinin hiperparametrelerini ayarlamak için kullanılan bir tekniktir. Bu teknik, belirtilen bir hiperparametre dağılımı üzerinde rastgele örnekler alır ve her bir hiperparametre kombinasyonu için modelin performansını değerlendirir. Modelin performansı genellikle K-Fold Cross Validation kullanılarak ölçülür.



### 13.K-Means Clusturing

K-Means Clustering, bir unsupervised (denetimsiz) öğrenme algoritmasıdır ve veri noktalarını benzerliklerine göre gruplara (veya "kümelere") ayırmak için kullanılır. Algoritma, her bir kümenin merkezini (veya "merkezini") hesaplar ve her veri noktasını en yakın merkeze göre atar.



### 14.Hieararchic Clusturing

Hierarchical Clustering (Hiyerarşik Kümeleme), bir unsupervised (denetimsiz) öğrenme algoritmasıdır ve veri noktalarını benzerliklerine göre gruplara (veya "kümeler") ayırmak için kullanılır. Bu algoritma, bir hiyerarşi veya ağaç yapısı oluşturarak kümeleri oluşturur.

Hiyerarşik Kümeleme'nin iki ana türü vardır: Agglomerative (Birleştirici) ve Divisive (Bölücü). Birleştirici hiyerarşik kümeleme, her veri noktasını ayrı bir küme olarak başlatır ve benzer kümeleri birleştirir. Bölücü hiyerarşik kümeleme, tüm veri noktalarını içeren tek bir küme ile başlar ve kümeyi alt kümelerine böler.

## 


### 9. Gradient Boosting Classifier
The Gradient Boosting Classifier is a machine learning algorithm that builds an ensemble model using a series of weak learners, typically decision trees. Each weak learner attempts to correct the errors of the previous learner. This is achieved by reducing errors using a gradient descent algorithm, hence the name of the algorithm.

### 10. K-Fold Cross Validation
K-Fold Cross Validation is a technique used to evaluate the performance of a machine learning model. This technique involves dividing the dataset into "K" equally sized subsets (or "folds") and testing and training the model "K" times on different subsets, providing a robust performance estimate.

### 11. Grid Search Cross Validation
Grid Search Cross Validation is a technique used to tune the hyperparameters of a machine learning model. This technique creates a grid of specified hyperparameters and evaluates the model's performance for each combination. Model performance is typically measured using K-Fold Cross Validation.

### 12. Randomized Search Cross Validation
Randomized Search Cross Validation is a technique used to tune the hyperparameters of a machine learning model. This technique samples randomly from a specified hyperparameter distribution and evaluates the model's performance for each combination. Model performance is typically measured using K-Fold Cross Validation.

### 13. K-Means Clustering
K-Means Clustering is an unsupervised learning algorithm used to group data points based on their similarities. The algorithm calculates the center (or "centroid") of each cluster and assigns each data point to the nearest centroid.

### 14. Hierarchical Clustering
Hierarchical Clustering is an unsupervised learning algorithm used to group data points based on their similarities, creating a hierarchical or tree structure of clusters. There are two main types of Hierarchical Clustering: Agglomerative (bottom-up) and Divisive (top-down). Agglomerative starts with individual data points as separate clusters and merges similar clusters, while Divisive starts with a single cluster containing all data points and divides it into subclusters.
