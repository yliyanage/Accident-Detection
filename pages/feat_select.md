---
layout: default
title: Feature Selection
---

In feature selection, our goal is to select the most informative features (out of all extracted time domain and frequency domain features [here.](./feat_extract.html)) for accident detection. 

## Information Theoretic Feature Selection

### Mutual Information

$$ I(X;Y) = \sum_{y \in Y} \sum_{x \in X}
    { P(x,y) \log{ \left(\frac{P(x,y)}{P(x),P(y)} \right) }} $$

[Go Back](../)
