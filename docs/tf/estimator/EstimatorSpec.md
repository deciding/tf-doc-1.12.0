page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>

<!-- DO NOT EDIT! Automatically generated file. -->
page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>

<!-- DO NOT EDIT! Automatically generated file. -->

# tf.estimator.EstimatorSpec

## Class `EstimatorSpec`



See the guide: [Regression Examples > custom_regression.py](../../../../api_guides/python/regression_examples#custom_regression_py)

Ops and objects returned from a `model_fn` and passed to an `Estimator`.

`EstimatorSpec` fully defines the model to be run by an `Estimator`.

<h2 id="__new__"><code>__new__</code></h2>

``` python
@staticmethod
__new__(
    cls,
    mode,
    predictions=None,
    loss=None,
    train_op=None,
    eval_metric_ops=None,
    export_outputs=None,
    training_chief_hooks=None,
    training_hooks=None,
    scaffold=None,
    evaluation_hooks=None,
    prediction_hooks=None
)
```

Creates a validated `EstimatorSpec` instance.

Depending on the value of `mode`, different arguments are required. Namely

* For `mode == ModeKeys.TRAIN`: required fields are `loss` and `train_op`.
* For `mode == ModeKeys.EVAL`: required field is `loss`.
* For `mode == ModeKeys.PREDICT`: required fields are `predictions`.

model_fn can populate all arguments independent of mode. In this case, some
arguments will be ignored by an `Estimator`. E.g. `train_op` will be
ignored in eval and infer modes. Example:

```python
def my_model_fn(features, labels, mode):
  predictions = ...
  loss = ...
  train_op = ...
  return tf.estimator.EstimatorSpec(
      mode=mode,
      predictions=predictions,
      loss=loss,
      train_op=train_op)
```

Alternatively, model_fn can just populate the arguments appropriate to the
given mode. Example:

```python
def my_model_fn(features, labels, mode):
  if (mode == tf.estimator.ModeKeys.TRAIN or
      mode == tf.estimator.ModeKeys.EVAL):
    loss = ...
  else:
    loss = None
  if mode == tf.estimator.ModeKeys.TRAIN:
    train_op = ...
  else:
    train_op = None
  if mode == tf.estimator.ModeKeys.PREDICT:
    predictions = ...
  else:
    predictions = None

  return tf.estimator.EstimatorSpec(
      mode=mode,
      predictions=predictions,
      loss=loss,
      train_op=train_op)
```

#### Args:

* <b>`mode`</b>: A `ModeKeys`. Specifies if this is training, evaluation or
    prediction.
* <b>`predictions`</b>: Predictions `Tensor` or dict of `Tensor`.
* <b>`loss`</b>: Training loss `Tensor`. Must be either scalar, or with shape `[1]`.
* <b>`train_op`</b>: Op to run one training step.
* <b>`eval_metric_ops`</b>: Dict of metric results keyed by name. The values of the
    dict are the results of calling a metric function, namely a
    `(metric_tensor, update_op)` tuple. `metric_tensor` should be evaluated
    without any impact on state (typically is a pure computation results
    based on variables.). For example, it should not trigger the `update_op`
    or requires any input fetching.
* <b>`export_outputs`</b>: Describes the output signatures to be exported to
    `SavedModel` and used during serving.
    A dict `{name: output}` where:
    * name: An arbitrary name for this output.
    * output: an `ExportOutput` object such as `ClassificationOutput`,
        `RegressionOutput`, or `PredictOutput`.
    Single-headed models only need to specify one entry in this dictionary.
    Multi-headed models should specify one entry for each head, one of
    which must be named using
    signature_constants.DEFAULT_SERVING_SIGNATURE_DEF_KEY.
    If no entry is provided, a default `PredictOutput` mapping to
    `predictions` will be created.
* <b>`training_chief_hooks`</b>: Iterable of <a href="../../tf/train/SessionRunHook"><code>tf.train.SessionRunHook</code></a> objects to
    run on the chief worker during training.
* <b>`training_hooks`</b>: Iterable of <a href="../../tf/train/SessionRunHook"><code>tf.train.SessionRunHook</code></a> objects to run
    on all workers during training.
* <b>`scaffold`</b>: A <a href="../../tf/train/Scaffold"><code>tf.train.Scaffold</code></a> object that can be used to set
    initialization, saver, and more to be used in training.
* <b>`evaluation_hooks`</b>: Iterable of <a href="../../tf/train/SessionRunHook"><code>tf.train.SessionRunHook</code></a> objects to
    run during evaluation.
* <b>`prediction_hooks`</b>: Iterable of <a href="../../tf/train/SessionRunHook"><code>tf.train.SessionRunHook</code></a> objects to
    run during predictions.


#### Returns:

A validated `EstimatorSpec` object.


#### Raises:

* <b>`ValueError`</b>: If validation fails.
* <b>`TypeError`</b>: If any of the arguments is not the expected type.



## Properties

<h3 id="mode"><code>mode</code></h3>



<h3 id="predictions"><code>predictions</code></h3>



<h3 id="loss"><code>loss</code></h3>



<h3 id="train_op"><code>train_op</code></h3>



<h3 id="eval_metric_ops"><code>eval_metric_ops</code></h3>



<h3 id="export_outputs"><code>export_outputs</code></h3>



<h3 id="training_chief_hooks"><code>training_chief_hooks</code></h3>



<h3 id="training_hooks"><code>training_hooks</code></h3>



<h3 id="scaffold"><code>scaffold</code></h3>



<h3 id="evaluation_hooks"><code>evaluation_hooks</code></h3>



<h3 id="prediction_hooks"><code>prediction_hooks</code></h3>





