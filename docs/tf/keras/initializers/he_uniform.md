page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>

<!-- DO NOT EDIT! Automatically generated file. -->

# tf.keras.initializers.he_uniform

### Aliases:

* `tf.initializers.he_uniform`
* `tf.keras.initializers.he_uniform`

``` python
tf.keras.initializers.he_uniform(seed=None)
```



Defined in [`tensorflow/python/ops/init_ops.py`](https://github.com/tensorflow/tensorflow/blob/r1.12/tensorflow/python/ops/init_ops.py).

He uniform variance scaling initializer.

It draws samples from a uniform distribution within [-limit, limit]
where `limit` is `sqrt(6 / fan_in)`
where `fan_in` is the number of input units in the weight tensor.

#### Arguments:

* <b>`seed`</b>: A Python integer. Used to seed the random generator.


#### Returns:

    An initializer.

References:
    He et al., http://arxiv.org/abs/1502.01852