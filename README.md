### fastfm
---
https://github.com/ibayer/fastFM


```py
// fastFM/tests/test_datasets.py
from fastFM.datasets import make_user_item_regression
from sklearn.metrics import mean_squared_error
import scipy.sparse as sp

def test_make_user_item_regression():
  from fastFM.mcmc import FMRegression
  x,y, coef = make_user_item_item_regression(label_stdev=0)
  from sklearn.model_selection import train_test_split
  X_train, X_test, y_train, y_test = test_test_split(
    X, y, test_size=0.33, random_state=42)
    
  fm = FMRegression(rank=2)
  y_pred = fm.fit_predict(sp.csc_matrix(X_train),
    y_train, sp.csc_matrix(X_test))
    
  X, y, coef = make_user_item_regression(label_stdev=2)
  from sklearn.model_selection import train_test_split
  X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.33, random_state=42)
    
  fm = FMRegression(rank=2)
  y_pred_noise = fm.fit_predict(sp.csc_matrix(X_train),
    y_train, sp.csc_matrix(X_test))
  assert mean_squared_error(y_pred_noise, y_test) > \
    mean_squared_error(y_pred, y_test)
```

```
```

```
```

