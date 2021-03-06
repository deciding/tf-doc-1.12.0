page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>

<!-- DO NOT EDIT! Automatically generated file. -->

# tf.distributions.ReparameterizationType

## Class `ReparameterizationType`



### Aliases:

* Class `tf.contrib.distributions.ReparameterizationType`
* Class `tf.distributions.ReparameterizationType`



Defined in [`tensorflow/python/ops/distributions/distribution.py`](https://github.com/tensorflow/tensorflow/blob/r1.12/tensorflow/python/ops/distributions/distribution.py).

Instances of this class represent how sampling is reparameterized.

Two static instances exist in the distributions library, signifying
one of two possible properties for samples from a distribution:

`FULLY_REPARAMETERIZED`: Samples from the distribution are fully
  reparameterized, and straight-through gradients are supported.

`NOT_REPARAMETERIZED`: Samples from the distribution are not fully
  reparameterized, and straight-through gradients are either partially
  unsupported or are not supported at all. In this case, for purposes of
  e.g. RL or variational inference, it is generally safest to wrap the
  sample results in a `stop_gradients` call and use policy
  gradients / surrogate loss instead.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(rep_type)
```





## Methods

<h3 id="__eq__"><code>__eq__</code></h3>

``` python
__eq__(other)
```

Determine if this `ReparameterizationType` is equal to another.

Since RepaparameterizationType instances are constant static global
instances, equality checks if two instances' id() values are equal.

#### Args:

* <b>`other`</b>: Object to compare against.


#### Returns:

`self is other`.



