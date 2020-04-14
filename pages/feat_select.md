---
layout: default
title: Feature Selection
---

In feature selection, our goal is to select the most informative features (out of all extracted time domain and frequency domain features [here.](./feat_extract.html)) for accident detection. 

## Information Theoretic Feature Selection

### Mutual Information

$$ I(X;Y) = \sum_{y \in Y} \sum_{x \in X}  { P(x,y) \log{ \left(\frac{P(x,y)}{P(x)P(y)} \right) }} $$

Mutual information is a measure of the mutual dependence between the two variables. Specifically, it quantifies the amount of information obtained about one random variable through observing the other random variable. 

In our accident detetecion problem, in order to compute the amount of information that each feature has to discriminate between a normal traffic condition vs a accident condition, we labeled each time samples as 1 or 0, where 1 repesents a accident, while a 0 represents a normal traffic condition. 


[Go Back](../)
