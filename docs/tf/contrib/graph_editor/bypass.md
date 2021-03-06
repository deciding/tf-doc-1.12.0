page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>

<!-- DO NOT EDIT! Automatically generated file. -->

# tf.contrib.graph_editor.bypass

``` python
tf.contrib.graph_editor.bypass(sgv)
```



Defined in [`tensorflow/contrib/graph_editor/edit.py`](https://github.com/tensorflow/tensorflow/blob/r1.12/tensorflow/contrib/graph_editor/edit.py).

See the guide: [Graph Editor (contrib) > Module: edit](../../../../../api_guides/python/contrib.graph_editor#Module_edit)

Bypass the given subgraph by connecting its inputs to its outputs.

#### Args:

* <b>`sgv`</b>: the subgraph view to be bypassed. This argument is converted to a
    subgraph using the same rules than the function subgraph.make_view.
    Note that sgv is modified in place.

#### Returns:

A tuple `(sgv, detached_inputs)` where:
  `sgv` is a new subgraph view of the bypassed subgraph;
  `detached_inputs` is a list of the created input placeholders.

#### Raises:

* <b>`StandardError`</b>: if sgv cannot be converted to a SubGraphView using
    the same rules than the function subgraph.make_view.