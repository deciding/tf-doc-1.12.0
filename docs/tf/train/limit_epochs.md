page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>

<!-- DO NOT EDIT! Automatically generated file. -->

# tf.train.limit_epochs

``` python
tf.train.limit_epochs(
    tensor,
    num_epochs=None,
    name=None
)
```



Defined in [`tensorflow/python/training/input.py`](https://github.com/tensorflow/tensorflow/blob/r1.12/tensorflow/python/training/input.py).

See the guide: [Inputs and Readers > Input pipeline](../../../../api_guides/python/io_ops#Input_pipeline)

Returns tensor `num_epochs` times and then raises an `OutOfRange` error. (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Queue-based input pipelines have been replaced by <a href="../../tf/data"><code>tf.data</code></a>. Use `tf.data.Dataset.from_tensors(tensor).repeat(num_epochs)`.

Note: creates local counter `epochs`. Use `local_variables_initializer()` to
initialize local variables.

#### Args:

* <b>`tensor`</b>: Any `Tensor`.
* <b>`num_epochs`</b>: A positive integer (optional).  If specified, limits the number
    of steps the output tensor may be evaluated.
* <b>`name`</b>: A name for the operations (optional).


#### Returns:

tensor or `OutOfRange`.


#### Raises:

* <b>`ValueError`</b>: if `num_epochs` is invalid.