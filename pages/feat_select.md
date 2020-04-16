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

Hereafter, we call this variable as the ''accident variable''.

Then, we compute mutual information between each feature and the accident variable. 

### Time Domain Features

![MI_time](../images/mi_time.png)

### Frequency Domain Features


 <p align="center">
       <img src="../images/mi_freq.png" height="400" width="700">
   </p>


$$ \text{KLE}_0, \text{KLE}_1, \text{KLE}_2, \text{KLE}_3, \text{KLE}_4 : \text{Eigenvector Transform Coefficients} $$

$$ \text{DFT}_0, \text{DFT}_1, \text{DFT}_2 : \text{Discrete Fourier Transform Coefficients} $$


We select a subset of most informative features (in both time domain and frequency domain) for accident detection based on a threshold on the mutual information between each feature and the accident variable.

Here are the 7 selected features by setting the threshold at 0.1.

<pre>
1. Mean Absolute Deviation                                                    
2. Standard deviation               
3. DFT Coefficient 1                 
4. DFT Coefficient 2
5. KLE Coefficient 1
6. Inter Quartile Range
7. KLE Coefficient 3
</pre>

[Go Back](../)
