page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>

<!-- DO NOT EDIT! Automatically generated file. -->

# tf.contrib.framework.local_variable

``` python
tf.contrib.framework.local_variable(
    initial_value,
    validate_shape=True,
    name=None,
    use_resource=None
)
```



Defined in [`tensorflow/contrib/framework/python/ops/variables.py`](https://github.com/tensorflow/tensorflow/blob/r1.12/tensorflow/contrib/framework/python/ops/variables.py).

Create a variable with a value and add it to `GraphKeys.LOCAL_VARIABLES`.

#### Args:

* <b>`initial_value`</b>: See variables.Variable.__init__.
* <b>`validate_shape`</b>: See variables.Variable.__init__.
* <b>`name`</b>: See variables.Variable.__init__.
* <b>`use_resource`</b>: If `True` use a ResourceVariable instead of a Variable.

#### Returns:

New variable.