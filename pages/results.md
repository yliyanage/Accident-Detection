---
layout: default
title: Experiments and Results
---

## Experimental Setup

We evaluate our proposed three–stage approach on a real–world dataset. (See [here](./data_collect.html) for details on real-time data collecting process). Specifically, we consider a set of 80 accident events from the event dataset and train our model on 60 (randomly selected) events and test on the rest 20 events.

During model training, we basically learn conditional probability distributions for all selected features under the assumption that:

$$F_i|\mathcal{A}=j \sim \mathcal{N} (\mu_{ij},\sigma^2_{ij})$$ 

During testing, at each time step, we:
1. extract the set $F$ of selected features
2. compute the sufficient statistic $\pi$
3. obtain the optimum decision $D_{F}^\text{optimum}$

The above three steps are repeated until an accident is detected (i.e., $D_{F}^\text{optimum}$ = 1), at which point an alert is raised, and the process of extracting features resumes. Note that in step 2, $\pi$ can be computed using conditional probability distributions as follows:

$$
\begin{align}
\pi &= P(\mathcal{A} = 0 | F) \\
    &= \frac{P(F|\mathcal{A} = 0 )P(\mathcal{A} = 0 )}{P(F)}\\
    &= \frac{ \prod_{i} P(F_i|\mathcal{A} = 0 )P(\mathcal{A} = 0 )}{\sum_j \prod_{i} P(F_i|\mathcal{A} =j)},
\end{align}
$$

where the prior probability $P(\mathcal{A} = i), i \in \lbrace 0,1 \rbrace$ is estimated using training data. Finally, we set constant misclassification costs, i.e. $Q_{10} =0.6, Q_{01}=0.4, Q_{00}=0, Q_{11} =0$.

## Results and Discussion

Following figure shows the performance of our approach on an example accident event.

<p align="center">
       <img src="../images/result.png" height="400" width="400">
</p>

We consider probability of false alarm (PFA), probability of miss-detection (PMD) and avarage detection delay (ADD) as performance measures. We report for three different threshold $\alpha$ values on the mutual information. 

    
|            |  $\alpha=0.1$ |  $\alpha=0.12$ |  $\alpha =0.14$     | Cali. Highway Patrol   |
|:---------: | :-------------: | :-------------: | :-------------: | :--------------------: |
|    # selected \ features    |     7     |      6       |      3        |         N.A.            |
|   PFA        |      0.0       |      0.0       |      0.0        |         0.0            |
|   PMD           |      0.0       |      0.0       |      0.05        |         0.0            |
|   ADD (mins)     |      3.75         |      3.75         |      5.0        |         16.45            |



[Go Back](../)

