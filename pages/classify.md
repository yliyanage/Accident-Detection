---
layout: default
title: Classification
---

This is the final stage of our project. Here our goal is to predict the accident variable using the 7 selected features. (see [here](./feat_select.html) for details.) For ease of reference, we name these 7 features as follows:

1. $F_1$ : Mean Absolute Deviation                                                    
2. $F_2$ : Standard deviation               
3. $F_3$ : DFT Coefficient 1                 
4. $F_4$ : DFT Coefficient 2
5. $F_5$ : KLE Coefficient 1
6. $F_6$ : Inter Quartile Range
7. $F_7$ : KLE Coefficient 3

and, we denote accident variable by $\mathcal{A}\in \{0,1\}$.

## Optimum Classification

To optimally predict the accident variable, we define misclassification cost $Q_{ij}$, representing the cost of selecting $\mathcal{A} =j$ when $\mathcal{A}=i$, where $i,j \in \{0,1\}$.



[Go Back](../)
