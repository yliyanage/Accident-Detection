---
layout: default
title: Feature Selection
---

In feature selection, our goal is to select the most informative features (out of all extracted time domain and frequency domain features [here.](./feat_extract.html)) for accident detection. 

## Information Theoretic Feature Selection

### Mutual Information

$$ I(X;Y) = \sum_{y \in Y} \sum_{x \in X}  { P(x,y) \log{ \left(\frac{P(x,y)}{P(x)P(y)} \right) }} $$

Mutual information is a measure of the mutual dependence between the two variables. Specifically, it quantifies the amount of information obtained about one random variable through observing the other random variable. 


[Go Back](../)
