---
layout: default
title: Optimum Classification
---

This is the final stage of our project. Here our goal is to predict the accident variable using the 7 selected features. (See [here](./feat_select.html) for details). For ease of reference, we name these 7 features as follows:

1. $F_1$ : Mean Absolute Deviation                                                    
2. $F_2$ : Standard deviation               
3. $F_3$ : DFT Coefficient 1                 
4. $F_4$ : DFT Coefficient 2
5. $F_5$ : KLE Coefficient 1
6. $F_6$ : Inter Quartile Range
7. $F_7$ : KLE Coefficient 3

and, we denote accident variable by $\mathcal{A}\in \lbrace 0,1\rbrace$.

## Optimum Classification

In the interest of predicting the accident variable $\mathcal{A}$ optimally, we define the following quantities:

* $D_F$ : Decision variable which depends on the feature set $F = \lbrace F_1,\dots,F_7 \rbrace$. For example, the event $\lbrace D_F = 1 \rbrace$, represents assigning the current time sample as an accident after observing the feature set $F = \lbrace F_1,\dots,F_7 \rbrace$. 
* $Q_{ij} \geqslant 0$ : Misclassification cost of assigning $D_F =j$ when $\mathcal{A}=i$, where $i,j \in \lbrace 0,1 \rbrace$.

On a more practical note, $0 < Q_{01} < Q{10} $, because miss-detecting an accident is more critical than a false alarm. Next, using the aforementioned quantities we define the cost function $J(D_F)$, which penalizes the expected cost of decision $D_F$ as follows:

$$ J(D_F) = \sum_{i=0}^1 \sum_{j=0}^1 Q_{ij} P( D_F = j, A = i) $$

Thus, our optimization problem is equivalent to finding $D_F$ such that:

$$ \text{minimize}_{D_F}  \ J(D_F) $$

In order to solve this optimzation, we define a sufficient statistic, which is the *a posteriori probability* $\pi$ as follows:

$$ \pi = P (\mathcal{A}=0 | F)$$

Using $\pi$, we rewrite the cost function $J(D_F)$ as follows:

$$ J(D_F) = \sum_{j=0}^1  \big( Q_{0j} \pi + Q_{1j} (1-\pi) \big) \mathbb{1}_{ \lbrace D_F=j \rbrace },$$

where $\mathbb{1}_{ \lbrace . \rbrace }$ is the indicator function. Note that $J(D_F)$ has the following lower bound:

$$  J(D_F) \geqslant \min_{j \in \lbrace 0,1 \rbrace} \big( Q_{0j} \pi + Q_{1j} (1-\pi) \big)$$

Thus, the optimum decision $D_F^{\text{optimum}}$ is given by:

$$ D_F^{\text{optimum}}  = \text{argmin}_{j \in \lbrace 0,1 \rbrace}  \big( Q_{0j} \pi + Q_{1j} (1-\pi) \big)$$

[Go Back](../)
