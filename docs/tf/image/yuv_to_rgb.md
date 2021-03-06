page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>

<!-- DO NOT EDIT! Automatically generated file. -->

# tf.image.yuv_to_rgb

``` python
tf.image.yuv_to_rgb(images)
```



Defined in [`tensorflow/python/ops/image_ops_impl.py`](https://github.com/tensorflow/tensorflow/blob/r1.12/tensorflow/python/ops/image_ops_impl.py).

Converts one or more images from YUV to RGB.

Outputs a tensor of the same shape as the `images` tensor, containing the RGB
value of the pixels.
The output is only well defined if the Y value in images are in [0,1],
U and V value are in [-0.5,0.5].

#### Args:

* <b>`images`</b>: 2-D or higher rank. Image data to convert. Last dimension must be
  size 3.


#### Returns:

* <b>`images`</b>: tensor with the same shape as `images`.