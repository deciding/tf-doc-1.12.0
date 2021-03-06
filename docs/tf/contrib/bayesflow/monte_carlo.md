page_type: reference
<style>{% include "site-assets/css/style.css" %}</style>
<script src="/_static/js/managed/mathjax/MathJax.js?config=TeX-AMS-MML_SVG"></script>

<!-- DO NOT EDIT! Automatically generated file. -->

# Module: tf.contrib.bayesflow.monte_carlo



Defined in [`tensorflow/contrib/bayesflow/python/ops/monte_carlo.py`](https://github.com/tensorflow/tensorflow/blob/r1.12/tensorflow/contrib/bayesflow/python/ops/monte_carlo.py).

Monte Carlo integration and helpers.

## Functions

[`expectation(...)`](../../../tf/contrib/bayesflow/monte_carlo/expectation): Computes the Monte-Carlo approximation of \\(E_p[f(X)]\\). (deprecated)

[`expectation_importance_sampler(...)`](../../../tf/contrib/bayesflow/monte_carlo/expectation_importance_sampler): Monte Carlo estimate of \\(E_p[f(Z)] = E_q[f(Z) p(Z) / q(Z)]\\).

[`expectation_importance_sampler_logspace(...)`](../../../tf/contrib/bayesflow/monte_carlo/expectation_importance_sampler_logspace): Importance sampling with a positive function, in log-space.

