page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>

<!-- DO NOT EDIT! Automatically generated file. -->

# tf.keras.utils.plot_model

``` python
tf.keras.utils.plot_model(
    model,
    to_file='model.png',
    show_shapes=False,
    show_layer_names=True,
    rankdir='TB'
)
```



Defined in [`tensorflow/python/keras/utils/vis_utils.py`](https://github.com/tensorflow/tensorflow/blob/r1.12/tensorflow/python/keras/utils/vis_utils.py).

Converts a Keras model to dot format and save to a file.

#### Arguments:

* <b>`model`</b>: A Keras model instance
* <b>`to_file`</b>: File name of the plot image.
* <b>`show_shapes`</b>: whether to display shape information.
* <b>`show_layer_names`</b>: whether to display layer names.
* <b>`rankdir`</b>: `rankdir` argument passed to PyDot,
        a string specifying the format of the plot:
        'TB' creates a vertical plot;
        'LR' creates a horizontal plot.