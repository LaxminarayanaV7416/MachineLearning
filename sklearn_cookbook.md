### Lets begin our scikit-learn / sklearn Cookbook

```Python
import sklearn 
```

#### Visit scikit-learn documentation for more information other than examples here

* Now lets try to see loading and making of datasets using sklearn.datasets module
  
```Python
from sklearn import datasets as dt
import pandas as pd
import matplotlib.pyplot as plt

#lets make some data and even try to use the already preprocessed data in this reciepe
feature, target , coeff = dt.make_regression(n_samples=100,
                                             n_features=100,
                                             n_informative=10,
                                             n_targets=1,
                                             coef=True,
                                             noise=0.0,
                                             random_state=1)
# NOTE : n_informative is most useful argument here which determines the number arguments used to generate the target vector in this case its 10 features which are used to generate target vectors.

#lets make some data for classification problem
feature, target = dt.make_classification(n_samples=100,
                                         n_features=3,
                                         n_informative=3,
                                         n_redundant=0,
                                         n_classes=2,
                                         weights =[0.25,0.75],
                                         random_state=42)
# explanation of above arguments used
# weights allows us to generate data with imbalanced classes where in above wwe saw n_classes are 2 so we have 25% to class-1 and 75% to class-2
# n_informative is same as regression
# n_redundant is number of highly correlated features and remaining are self explainable.

#lets make the clustering data 
feature , target = dt.make_blobs(n_samples=100,
                                 n_features=2,
                                 centers=3,
                                 cluster_std=0.5,
                                 shuffle=True,
                                 random_state=35)
# centers number of centers to generate with fixed number of centers
# cluster_std standard deviation of clusters

# lets load the iris and digits dataset
iris = dt.load_iris() #returns a dictionary which contains keys as below
# dict_keys(['data', 'target', 'frame', 'target_names', 'DESCR', 'feature_names', 'filename'])

iris_features = iris['data'] #its a numpy array, we can convert it to pandas dataframe 
iris_df = pd.DataFrame(iris_features, columns = iris['feature_names'])
# as we have converted to  dataframe now we can perform pandas operations on this

digits = dt.load_digits() #its also a dictionary same as above
#lets plot the digit images, for better understanding read the DESCr uisng didgits['DESCR']
plt.imshow(digits['data'][1,:].reshape(8,8), cmap = 'gray')

#try using datasets of sklearn to load and make more datasets!!
```

* Now lets do some preprocessing in sklearn 

```Python
import sklearn.preprocessing as pre


```