page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>

<!-- DO NOT EDIT! Automatically generated file. -->

# tf.contrib.framework.load_checkpoint

``` python
tf.contrib.framework.load_checkpoint(filepattern)
```



Defined in [`tensorflow/contrib/framework/python/framework/checkpoint_utils.py`](https://github.com/tensorflow/tensorflow/blob/r1.12/tensorflow/contrib/framework/python/framework/checkpoint_utils.py).

Returns CheckpointReader for latest checkpoint.

#### Args:

* <b>`filepattern`</b>: Directory with checkpoints file or path to checkpoint.


#### Returns:

`CheckpointReader` object.


#### Raises:

* <b>`ValueError`</b>: if checkpoint_dir doesn't have 'checkpoint' file or checkpoints.