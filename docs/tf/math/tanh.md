page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>

<!-- DO NOT EDIT! Automatically generated file. -->

# tf.math.tanh

### Aliases:

* `tf.math.tanh`
* `tf.nn.tanh`
* `tf.tanh`

``` python
tf.math.tanh(
    x,
    name=None
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](https://github.com/tensorflow/tensorflow/blob/r1.12/tensorflow/python/ops/math_ops.py).

See the guide: [Neural Network > Activation Functions](../../../../api_guides/python/nn#Activation_Functions)

Computes hyperbolic tangent of `x` element-wise.

#### Args:

* <b>`x`</b>: A Tensor or SparseTensor with type `float16`, `float32`, `double`,
    `complex64`, or `complex128`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A Tensor or SparseTensor respectively with the same type as `x`.