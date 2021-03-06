page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>

<!-- DO NOT EDIT! Automatically generated file. -->

# tf.math.squared_difference

### Aliases:

* `tf.math.squared_difference`
* `tf.squared_difference`

``` python
tf.math.squared_difference(
    x,
    y,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_math_ops.py`.

Returns (x - y)(x - y) element-wise.

*NOTE*: `math.squared_difference` supports broadcasting. More about broadcasting
[here](http://docs.scipy.org/doc/numpy/user/basics.broadcasting.html)

#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `int32`, `int64`, `complex64`, `complex128`.
* <b>`y`</b>: A `Tensor`. Must have the same type as `x`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `x`.