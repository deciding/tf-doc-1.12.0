page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>

<!-- DO NOT EDIT! Automatically generated file. -->

# tf.contrib.seq2seq.AttentionWrapper

## Class `AttentionWrapper`

Inherits From: [`RNNCell`](../../../tf/nn/rnn_cell/RNNCell)



Defined in [`tensorflow/contrib/seq2seq/python/ops/attention_wrapper.py`](https://github.com/tensorflow/tensorflow/blob/r1.12/tensorflow/contrib/seq2seq/python/ops/attention_wrapper.py).

See the guide: [Seq2seq Library (contrib) > Attention](../../../../../api_guides/python/contrib.seq2seq#Attention)

Wraps another `RNNCell` with attention.
  

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    cell,
    attention_mechanism,
    attention_layer_size=None,
    alignment_history=False,
    cell_input_fn=None,
    output_attention=True,
    initial_cell_state=None,
    name=None,
    attention_layer=None
)
```

Construct the `AttentionWrapper`.

**NOTE** If you are using the `BeamSearchDecoder` with a cell wrapped in
`AttentionWrapper`, then you must ensure that:

- The encoder output has been tiled to `beam_width` via
  <a href="../../../tf/contrib/seq2seq/tile_batch"><code>tf.contrib.seq2seq.tile_batch</code></a> (NOT <a href="../../../tf/tile"><code>tf.tile</code></a>).
- The `batch_size` argument passed to the `zero_state` method of this
  wrapper is equal to `true_batch_size * beam_width`.
- The initial state created with `zero_state` above contains a
  `cell_state` value containing properly tiled final state from the
  encoder.

An example:

```
tiled_encoder_outputs = tf.contrib.seq2seq.tile_batch(
    encoder_outputs, multiplier=beam_width)
tiled_encoder_final_state = tf.conrib.seq2seq.tile_batch(
    encoder_final_state, multiplier=beam_width)
tiled_sequence_length = tf.contrib.seq2seq.tile_batch(
    sequence_length, multiplier=beam_width)
attention_mechanism = MyFavoriteAttentionMechanism(
    num_units=attention_depth,
    memory=tiled_inputs,
    memory_sequence_length=tiled_sequence_length)
attention_cell = AttentionWrapper(cell, attention_mechanism, ...)
decoder_initial_state = attention_cell.zero_state(
    dtype, batch_size=true_batch_size * beam_width)
decoder_initial_state = decoder_initial_state.clone(
    cell_state=tiled_encoder_final_state)
```

#### Args:

* <b>`cell`</b>: An instance of `RNNCell`.
* <b>`attention_mechanism`</b>: A list of `AttentionMechanism` instances or a single
    instance.
* <b>`attention_layer_size`</b>: A list of Python integers or a single Python
    integer, the depth of the attention (output) layer(s). If None
    (default), use the context as attention at each time step. Otherwise,
    feed the context and cell output into the attention layer to generate
    attention at each time step. If attention_mechanism is a list,
    attention_layer_size must be a list of the same length. If
    attention_layer is set, this must be None.
* <b>`alignment_history`</b>: Python boolean, whether to store alignment history
    from all time steps in the final output state (currently stored as a
    time major `TensorArray` on which you must call `stack()`).
* <b>`cell_input_fn`</b>: (optional) A `callable`.  The default is:
    `lambda inputs, attention: array_ops.concat([inputs, attention], -1)`.
* <b>`output_attention`</b>: Python bool.  If `True` (default), the output at each
    time step is the attention value.  This is the behavior of Luong-style
    attention mechanisms.  If `False`, the output at each time step is
    the output of `cell`.  This is the behavior of Bhadanau-style
    attention mechanisms.  In both cases, the `attention` tensor is
    propagated to the next time step via the state and is used there.
    This flag only controls whether the attention mechanism is propagated
    up to the next cell in an RNN stack or to the top RNN output.
* <b>`initial_cell_state`</b>: The initial state value to use for the cell when
    the user calls `zero_state()`.  Note that if this value is provided
    now, and the user uses a `batch_size` argument of `zero_state` which
    does not match the batch size of `initial_cell_state`, proper
    behavior is not guaranteed.
* <b>`name`</b>: Name to use when creating ops.
* <b>`attention_layer`</b>: A list of <a href="../../../tf/layers/Layer"><code>tf.layers.Layer</code></a> instances or a
    single <a href="../../../tf/layers/Layer"><code>tf.layers.Layer</code></a> instance taking the context and cell output as
    inputs to generate attention at each time step. If None (default), use
    the context as attention at each time step. If attention_mechanism is a
    list, attention_layer must be a list of the same length. If
    attention_layers_size is set, this must be None.


#### Raises:

* <b>`TypeError`</b>: `attention_layer_size` is not None and (`attention_mechanism`
    is a list but `attention_layer_size` is not; or vice versa).
* <b>`ValueError`</b>: if `attention_layer_size` is not None, `attention_mechanism`
    is a list, and its length does not match that of `attention_layer_size`;
    if `attention_layer_size` and `attention_layer` are set simultaneously.



## Properties

<h3 id="activity_regularizer"><code>activity_regularizer</code></h3>

Optional regularizer function for the output of this layer.

<h3 id="dtype"><code>dtype</code></h3>



<h3 id="graph"><code>graph</code></h3>



<h3 id="input"><code>input</code></h3>

Retrieves the input tensor(s) of a layer.

Only applicable if the layer has exactly one input,
i.e. if it is connected to one incoming layer.

#### Returns:

Input tensor or list of input tensors.


#### Raises:

* <b>`AttributeError`</b>: if the layer is connected to
    more than one incoming layers.


#### Raises:

* <b>`RuntimeError`</b>: If called in Eager mode.
* <b>`AttributeError`</b>: If no inbound nodes are found.

<h3 id="input_mask"><code>input_mask</code></h3>

Retrieves the input mask tensor(s) of a layer.

Only applicable if the layer has exactly one inbound node,
i.e. if it is connected to one incoming layer.

#### Returns:

Input mask tensor (potentially None) or list of input
mask tensors.


#### Raises:

* <b>`AttributeError`</b>: if the layer is connected to
    more than one incoming layers.

<h3 id="input_shape"><code>input_shape</code></h3>

Retrieves the input shape(s) of a layer.

Only applicable if the layer has exactly one input,
i.e. if it is connected to one incoming layer, or if all inputs
have the same shape.

#### Returns:

Input shape, as an integer shape tuple
(or list of shape tuples, one tuple per input tensor).


#### Raises:

* <b>`AttributeError`</b>: if the layer has no defined input_shape.
* <b>`RuntimeError`</b>: if called in Eager mode.

<h3 id="losses"><code>losses</code></h3>

Losses which are associated with this `Layer`.

Variable regularization tensors are created when this property is accessed,
so it is eager safe: accessing `losses` under a <a href="../../../tf/GradientTape"><code>tf.GradientTape</code></a> will
propagate gradients back to the corresponding variables.

#### Returns:

A list of tensors.

<h3 id="name"><code>name</code></h3>



<h3 id="non_trainable_variables"><code>non_trainable_variables</code></h3>



<h3 id="non_trainable_weights"><code>non_trainable_weights</code></h3>



<h3 id="output"><code>output</code></h3>

Retrieves the output tensor(s) of a layer.

Only applicable if the layer has exactly one output,
i.e. if it is connected to one incoming layer.

#### Returns:

Output tensor or list of output tensors.


#### Raises:

* <b>`AttributeError`</b>: if the layer is connected to more than one incoming
    layers.
* <b>`RuntimeError`</b>: if called in Eager mode.

<h3 id="output_mask"><code>output_mask</code></h3>

Retrieves the output mask tensor(s) of a layer.

Only applicable if the layer has exactly one inbound node,
i.e. if it is connected to one incoming layer.

#### Returns:

Output mask tensor (potentially None) or list of output
mask tensors.


#### Raises:

* <b>`AttributeError`</b>: if the layer is connected to
    more than one incoming layers.

<h3 id="output_shape"><code>output_shape</code></h3>

Retrieves the output shape(s) of a layer.

Only applicable if the layer has one output,
or if all outputs have the same shape.

#### Returns:

Output shape, as an integer shape tuple
(or list of shape tuples, one tuple per output tensor).


#### Raises:

* <b>`AttributeError`</b>: if the layer has no defined output shape.
* <b>`RuntimeError`</b>: if called in Eager mode.

<h3 id="output_size"><code>output_size</code></h3>



<h3 id="scope_name"><code>scope_name</code></h3>



<h3 id="state_size"><code>state_size</code></h3>

The `state_size` property of `AttentionWrapper`.

#### Returns:

An `AttentionWrapperState` tuple containing shapes used by this object.

<h3 id="trainable_variables"><code>trainable_variables</code></h3>



<h3 id="trainable_weights"><code>trainable_weights</code></h3>



<h3 id="updates"><code>updates</code></h3>



<h3 id="variables"><code>variables</code></h3>

Returns the list of all layer variables/weights.

#### Returns:

A list of variables.

<h3 id="weights"><code>weights</code></h3>

Returns the list of all layer variables/weights.

#### Returns:

A list of variables.



## Methods

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(
    inputs,
    state,
    scope=None
)
```

Run this RNN cell on inputs, starting from the given state.

#### Args:

* <b>`inputs`</b>: `2-D` tensor with shape `[batch_size, input_size]`.
* <b>`state`</b>: if `self.state_size` is an integer, this should be a `2-D Tensor`
    with shape `[batch_size, self.state_size]`.  Otherwise, if
    `self.state_size` is a tuple of integers, this should be a tuple
    with shapes `[batch_size, s] for s in self.state_size`.
* <b>`scope`</b>: VariableScope for the created subgraph; defaults to class name.


#### Returns:

A pair containing:

- Output: A `2-D` tensor with shape `[batch_size, self.output_size]`.
- New state: Either a single `2-D` tensor, or a tuple of tensors matching
  the arity and shapes of `state`.

<h3 id="__deepcopy__"><code>__deepcopy__</code></h3>

``` python
__deepcopy__(memo)
```



<h3 id="apply"><code>apply</code></h3>

``` python
apply(
    inputs,
    *args,
    **kwargs
)
```

Apply the layer on a input.

This simply wraps `self.__call__`.

#### Arguments:

* <b>`inputs`</b>: Input tensor(s).
* <b>`*args`</b>: additional positional arguments to be passed to `self.call`.
* <b>`**kwargs`</b>: additional keyword arguments to be passed to `self.call`.


#### Returns:

Output tensor(s).

<h3 id="build"><code>build</code></h3>

``` python
build(_)
```



<h3 id="compute_mask"><code>compute_mask</code></h3>

``` python
compute_mask(
    inputs,
    mask=None
)
```

Computes an output mask tensor.

#### Arguments:

* <b>`inputs`</b>: Tensor or list of tensors.
* <b>`mask`</b>: Tensor or list of tensors.


#### Returns:

None or a tensor (or list of tensors,
    one per output tensor of the layer).

<h3 id="compute_output_shape"><code>compute_output_shape</code></h3>

``` python
compute_output_shape(input_shape)
```

Computes the output shape of the layer.

Assumes that the layer will be built
to match that input shape provided.

#### Arguments:

* <b>`input_shape`</b>: Shape tuple (tuple of integers)
        or list of shape tuples (one per output tensor of the layer).
        Shape tuples can include None for free dimensions,
        instead of an integer.


#### Returns:

An input shape tuple.

<h3 id="count_params"><code>count_params</code></h3>

``` python
count_params()
```

Count the total number of scalars composing the weights.

#### Returns:

An integer count.


#### Raises:

* <b>`ValueError`</b>: if the layer isn't yet built
      (in which case its weights aren't yet defined).

<h3 id="from_config"><code>from_config</code></h3>

``` python
from_config(
    cls,
    config
)
```

Creates a layer from its config.

This method is the reverse of `get_config`,
capable of instantiating the same layer from the config
dictionary. It does not handle layer connectivity
(handled by Network), nor weights (handled by `set_weights`).

#### Arguments:

* <b>`config`</b>: A Python dictionary, typically the
        output of get_config.


#### Returns:

A layer instance.

<h3 id="get_config"><code>get_config</code></h3>

``` python
get_config()
```

Returns the config of the layer.

A layer config is a Python dictionary (serializable)
containing the configuration of a layer.
The same layer can be reinstantiated later
(without its trained weights) from this configuration.

The config of a layer does not include connectivity
information, nor the layer class name. These are handled
by `Network` (one layer of abstraction above).

#### Returns:

Python dictionary.

<h3 id="get_initial_state"><code>get_initial_state</code></h3>

``` python
get_initial_state(
    inputs=None,
    batch_size=None,
    dtype=None
)
```



<h3 id="get_input_at"><code>get_input_at</code></h3>

``` python
get_input_at(node_index)
```

Retrieves the input tensor(s) of a layer at a given node.

#### Arguments:

* <b>`node_index`</b>: Integer, index of the node
        from which to retrieve the attribute.
        E.g. `node_index=0` will correspond to the
        first time the layer was called.


#### Returns:

A tensor (or list of tensors if the layer has multiple inputs).


#### Raises:

* <b>`RuntimeError`</b>: If called in Eager mode.

<h3 id="get_input_mask_at"><code>get_input_mask_at</code></h3>

``` python
get_input_mask_at(node_index)
```

Retrieves the input mask tensor(s) of a layer at a given node.

#### Arguments:

* <b>`node_index`</b>: Integer, index of the node
        from which to retrieve the attribute.
        E.g. `node_index=0` will correspond to the
        first time the layer was called.


#### Returns:

A mask tensor
(or list of tensors if the layer has multiple inputs).

<h3 id="get_input_shape_at"><code>get_input_shape_at</code></h3>

``` python
get_input_shape_at(node_index)
```

Retrieves the input shape(s) of a layer at a given node.

#### Arguments:

* <b>`node_index`</b>: Integer, index of the node
        from which to retrieve the attribute.
        E.g. `node_index=0` will correspond to the
        first time the layer was called.


#### Returns:

A shape tuple
(or list of shape tuples if the layer has multiple inputs).


#### Raises:

* <b>`RuntimeError`</b>: If called in Eager mode.

<h3 id="get_losses_for"><code>get_losses_for</code></h3>

``` python
get_losses_for(inputs)
```

Retrieves losses relevant to a specific set of inputs.

#### Arguments:

* <b>`inputs`</b>: Input tensor or list/tuple of input tensors.


#### Returns:

List of loss tensors of the layer that depend on `inputs`.


#### Raises:

* <b>`RuntimeError`</b>: If called in Eager mode.

<h3 id="get_output_at"><code>get_output_at</code></h3>

``` python
get_output_at(node_index)
```

Retrieves the output tensor(s) of a layer at a given node.

#### Arguments:

* <b>`node_index`</b>: Integer, index of the node
        from which to retrieve the attribute.
        E.g. `node_index=0` will correspond to the
        first time the layer was called.


#### Returns:

A tensor (or list of tensors if the layer has multiple outputs).


#### Raises:

* <b>`RuntimeError`</b>: If called in Eager mode.

<h3 id="get_output_mask_at"><code>get_output_mask_at</code></h3>

``` python
get_output_mask_at(node_index)
```

Retrieves the output mask tensor(s) of a layer at a given node.

#### Arguments:

* <b>`node_index`</b>: Integer, index of the node
        from which to retrieve the attribute.
        E.g. `node_index=0` will correspond to the
        first time the layer was called.


#### Returns:

A mask tensor
(or list of tensors if the layer has multiple outputs).

<h3 id="get_output_shape_at"><code>get_output_shape_at</code></h3>

``` python
get_output_shape_at(node_index)
```

Retrieves the output shape(s) of a layer at a given node.

#### Arguments:

* <b>`node_index`</b>: Integer, index of the node
        from which to retrieve the attribute.
        E.g. `node_index=0` will correspond to the
        first time the layer was called.


#### Returns:

A shape tuple
(or list of shape tuples if the layer has multiple outputs).


#### Raises:

* <b>`RuntimeError`</b>: If called in Eager mode.

<h3 id="get_updates_for"><code>get_updates_for</code></h3>

``` python
get_updates_for(inputs)
```

Retrieves updates relevant to a specific set of inputs.

#### Arguments:

* <b>`inputs`</b>: Input tensor or list/tuple of input tensors.


#### Returns:

List of update ops of the layer that depend on `inputs`.


#### Raises:

* <b>`RuntimeError`</b>: If called in Eager mode.

<h3 id="get_weights"><code>get_weights</code></h3>

``` python
get_weights()
```

Returns the current weights of the layer.

#### Returns:

Weights values as a list of numpy arrays.

<h3 id="set_weights"><code>set_weights</code></h3>

``` python
set_weights(weights)
```

Sets the weights of the layer, from Numpy arrays.

#### Arguments:

* <b>`weights`</b>: a list of Numpy arrays. The number
        of arrays and their shape must match
        number of the dimensions of the weights
        of the layer (i.e. it should match the
        output of `get_weights`).


#### Raises:

* <b>`ValueError`</b>: If the provided weights list does not match the
        layer's specifications.

<h3 id="zero_state"><code>zero_state</code></h3>

``` python
zero_state(
    batch_size,
    dtype
)
```

Return an initial (zero) state tuple for this `AttentionWrapper`.

**NOTE** Please see the initializer documentation for details of how
to call `zero_state` if using an `AttentionWrapper` with a
`BeamSearchDecoder`.

#### Args:

* <b>`batch_size`</b>: `0D` integer tensor: the batch size.
* <b>`dtype`</b>: The internal state data type.


#### Returns:

An `AttentionWrapperState` tuple containing zeroed out tensors and,
possibly, empty `TensorArray` objects.


#### Raises:

* <b>`ValueError`</b>: (or, possibly at runtime, InvalidArgument), if
    `batch_size` does not match the output size of the encoder passed
    to the wrapper object at initialization time.



