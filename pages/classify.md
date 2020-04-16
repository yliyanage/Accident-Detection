---
layout: default
title: Classification
---

This is the final stage of our project. Here our goal is to predict the accident variable using the 7 selected features. (See [here](./feat_select.html) for details). For ease of reference, we name these 7 features as follows:

1. $F_1$ : Mean Absolute Deviation                                                    
2. $F_2$ : Standard deviation               
3. $F_3$ : DFT Coefficient 1                 
4. $F_4$ : DFT Coefficient 2
5. $F_5$ : KLE Coefficient 1
6. $F_6$ : Inter Quartile Range
7. $F_7$ : KLE Coefficient 3

and, we denote accident variable by $\mathcal{A}\in \{0,1\}$.

## Optimum Classification

In the interest of predicting the accident variable $\mathcal{A}$ optimally, we define the following quantities:

* $D_F$ : Decision variable. For example, the event $\{D_F = 1 \}$, represents deciding the current time sample as an accident after observing the feature set $F = \{F_1,\dots,F_7 \}$. 
* $Q_{ij} \geqslant 0$ : Misclassification cost of deciding $D_F =j$ when $\mathcal{A}=i$, where $i,j \in \{0,1\}$.

Using these quantities, we define cost function $J(D_F)$, which penalizes the expected cost of decision $D_F$ as follows:

$$ J(D_F) = \sum_{i=0}^1 \sum_{j=0}^1 Q_{ij} P( D_F = j, A = i) $$

Thus, our optimization problem is equivalent to finding $D_F$ such that:

$$ \text{minimize}_{D_F}  J(D_F) $$

[Go Back](../)
