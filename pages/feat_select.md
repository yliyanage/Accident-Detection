---
layout: default
title: Feature Selection
---

In feature selection, our goal is to select a subset of most informative features (out of all extracted features [here](./feat_extract.html)) for accident detection. 

## Information Theoretic Feature Selection

### Mutual Information

$$ I(X;Y) = \sum_{y \in Y} \sum_{x \in X}  { P(x,y) \log{ \left(\frac{P(x,y)}{P(x)P(y)} \right) }} $$

Mutual information is a measure of the mutual dependence between the two variables. Specifically, it quantifies the amount of information obtained about one random variable through observing the other random variable. 

In our accident detetecion problem, in order to compute the amount of information that each feature contains to discriminate a time sample between normal traffic versus accident condition, we assign a binary label for each time sample. Specifically, we use $1$ to repesent an accident sample, while $0$ represents a normal traffic sample. 

![labels](../images/labels.png)

Hereafter, we call this variable as ''accident variable''.

Then, we compute mutual information between each feature and accident variable. 

### Time Domain Features

![MI_time](../images/mi_time.png)

### Frequency Domain Features

![MI_time](../images/mi_freq.png)

$$ S_0,S_1,S_2,S_3,S_4 = \text{Eigen Transform Cofficients} $$


[Go Back](../)
