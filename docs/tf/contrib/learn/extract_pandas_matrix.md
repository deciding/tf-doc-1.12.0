page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>

<!-- DO NOT EDIT! Automatically generated file. -->

# tf.contrib.learn.extract_pandas_matrix

``` python
tf.contrib.learn.extract_pandas_matrix(data)
```



Defined in [`tensorflow/contrib/learn/python/learn/learn_io/pandas_io.py`](https://github.com/tensorflow/tensorflow/blob/r1.12/tensorflow/contrib/learn/python/learn/learn_io/pandas_io.py).

Extracts numpy matrix from pandas DataFrame. (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Please access pandas data directly.

#### Args:

* <b>`data`</b>: `pandas.DataFrame` containing the data to be extracted.


#### Returns:

A numpy `ndarray` of the DataFrame's values.