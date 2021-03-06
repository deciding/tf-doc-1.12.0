page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>

<!-- DO NOT EDIT! Automatically generated file. -->

# tf.io.match_filenames_once

### Aliases:

* `tf.io.match_filenames_once`
* `tf.train.match_filenames_once`

``` python
tf.io.match_filenames_once(
    pattern,
    name=None
)
```



Defined in [`tensorflow/python/training/input.py`](https://github.com/tensorflow/tensorflow/blob/r1.12/tensorflow/python/training/input.py).

See the guides: [Inputs and Readers > Input pipeline](../../../../api_guides/python/io_ops#Input_pipeline), [Reading data > `QueueRunner`](../../../../api_guides/python/reading_data#_QueueRunner_)

Save the list of files matching pattern, so it is only computed once.

NOTE: The order of the files returned can be non-deterministic.

#### Args:

* <b>`pattern`</b>: A file pattern (glob), or 1D tensor of file patterns.
* <b>`name`</b>: A name for the operations (optional).


#### Returns:

A variable that is initialized to the list of files matching the pattern(s).