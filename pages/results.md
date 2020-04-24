---
layout: default
title: Experiments and Results
---

## Experimental Setup

We evaluate our proposed three–stage approach on a real–world dataset. (See [here](./data_collect.html) for details on real-time data collecting process). Specifically, we consider a set of 80 accident events from the event dataset and train our model on random selected 60 events and test on the rest 20 events.

During model training, we basically learn conditional probability distributions for all selected features under the assumption that:

$$F_i|\mathcal{A}=j \sim \mathcal{N} (\mu_{ij},\sigma^2_{ij})$$ 

During testing, at each time step, we:
1. extract the set $F$ of selected features
2. compute the sufficient statistic $\pi$
3. predict the optimum decision $D_{F}^\text{optimum}$

The above three steps are repeated until an accident is detected (i.e., $D_{F}^\text{optimum}$ = 1), at which point an alert is raised, and $D_{F}^\text{optimum}$ is reset to $0$, and the process of extracting features resumes. Note that in step 2, $\pi$ can be computed using conditional probability distributions as follows:

$$
\begin{align}
\pi &= P(\mathcal{A} = 0 | F) \\
    &= \frac{P(F|\mathcal{A} = 0 )P(\mathcal{A} = 0 )}{P(F)}\\
    &= \frac{ \prod_{i} P(F_i|\mathcal{A} = 0 )P(\mathcal{A} = 0 )}{\sum_j \prod_{i} P(F_i|\mathcal{A} =j}  
\end{align}
$$

## Results and Discussion



[Go Back](../)

