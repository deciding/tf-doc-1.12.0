page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>

<!-- DO NOT EDIT! Automatically generated file. -->

# tf.contrib.graph_editor.keep_t_if_possible_handler

``` python
tf.contrib.graph_editor.keep_t_if_possible_handler(
    info,
    t
)
```



Defined in [`tensorflow/contrib/graph_editor/transform.py`](https://github.com/tensorflow/tensorflow/blob/r1.12/tensorflow/contrib/graph_editor/transform.py).

See the guide: [Graph Editor (contrib) > Module: transform](../../../../../api_guides/python/contrib.graph_editor#Module_transform)

Transform a tensor into itself (identity) if possible.

This handler transform a tensor into itself if the source and destination
graph are the same. Otherwise it will create a placeholder.
This handler is typically used to transform a hidden input tensors.

#### Args:

* <b>`info`</b>: Transform._TmpInfo instance.
* <b>`t`</b>: tensor whose input must be transformed into a place holder.

#### Returns:

The tensor generated by the newly created place holder.