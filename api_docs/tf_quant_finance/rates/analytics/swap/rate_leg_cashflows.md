<!--
This file is generated by a tool. Do not edit directly.
For open-source contributions the docs will be updated automatically.
-->

*Last updated: 2021-03-03.*

<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf_quant_finance.rates.analytics.swap.rate_leg_cashflows" />
<meta itemprop="path" content="Stable" />
</div>

# tf_quant_finance.rates.analytics.swap.rate_leg_cashflows

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api" align="left">
</table>

<a target="_blank" href="https://github.com/google/tf-quant-finance/blob/master/tf_quant_finance/rates/analytics/swap.py">View source</a>



Computes cashflows for a batch or interest rate legs.

```python
tf_quant_finance.rates.analytics.swap.rate_leg_cashflows(
    coupon_rates, notional, daycount_fractions, dtype=None, name=None
)
```



<!-- Placeholder for "Used in" -->

#### Example
```python
coupon_rates = [[0.1, 0.1, 0.1], [0.02, 0.12, 0.14]]
notional = 1000
daycount_fractions = [[1, 1, 1], [1, 2, 1]]
rate_leg_cashflows(
    coupon_rates, notional, daycount_fractions, dtype=tf.float64)
# Expected:
#  [[100.0, 100.0, 100.0],
#   [ 20.0, 240.0, 140.0]]
```

#### Args:


* <b>`coupon_rates`</b>: A real `Tensor` of shape `batch_shape + [num_cashflows]`,
  where `num_cashflows` is the number of cashflows for each batch element.
  Coupon rates for each cashflow of the leg. Can be a scalar for a fixed
  leg or represent forward rates for a floating leg.
* <b>`notional`</b>: A `Tensor` of the same `dtype` as `coupon_rates` and of
  compatible shape. Notional amount for each cashflow.
* <b>`daycount_fractions`</b>: A `Tensor` of the same `dtype` as `coupon_rates` and of
  compatible shape. Year fractions for the coupon accrual.
* <b>`dtype`</b>: `tf.Dtype`. If supplied the dtype for the input and ouput `Tensor`s.
  Default value: None which maps to the default dtype inferred from
  `coupon_rates`.
* <b>`name`</b>: Python str. The name to give to the ops created by this function.
  Default value: None which maps to 'rate_leg_cashflows'.


#### Returns:

A `Tensor` of the same `dtype` as `coupon_rates` and of shape
`batch_shape + [num_cashflows]`.