page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>

<!-- DO NOT EDIT! Automatically generated file. -->

# tf.contrib.graph_editor.ControlOutputs

## Class `ControlOutputs`





Defined in [`tensorflow/contrib/graph_editor/util.py`](https://github.com/tensorflow/tensorflow/blob/r1.12/tensorflow/contrib/graph_editor/util.py).

See the guide: [Graph Editor (contrib) > Module: util](../../../../../api_guides/python/contrib.graph_editor#Module_util)

The control outputs topology.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(graph)
```

Create a dictionary of control-output dependencies.

#### Args:

* <b>`graph`</b>: a <a href="../../../tf/Graph"><code>tf.Graph</code></a>.

#### Returns:

A dictionary where a key is a <a href="../../../tf/Operation"><code>tf.Operation</code></a> instance and the
   corresponding value is a list of all the ops which have the key
   as one of their control-input dependencies.

#### Raises:

* <b>`TypeError`</b>: graph is not a <a href="../../../tf/Graph"><code>tf.Graph</code></a>.



## Properties

<h3 id="graph"><code>graph</code></h3>





## Methods

<h3 id="get"><code>get</code></h3>

``` python
get(op)
```

return the control outputs of op.

<h3 id="get_all"><code>get_all</code></h3>

``` python
get_all()
```



<h3 id="update"><code>update</code></h3>

``` python
update()
```

Update the control outputs if the graph has changed.



