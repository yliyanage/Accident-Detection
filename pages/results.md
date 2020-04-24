---
layout: default
title: Experiments and Results
---

We evaluate our proposed three–stage approach on a real–world dataset. (See [here](./data_collect.html) for details on real-time data collecting process). Specifically, we consider a set of 80 accident events from our event dataset and train our model on random selected 60 events and test on the rest 20 events. 

During model training, we basically learn conditional probability distributions, i.e., $P(F_i|\mathcal{A})$ for all selected features under the assumption that $F_i|\mathcal{A}=j \sim \mathcal{N} (\mu_{ij},\sigma^2_{i,j})$. 


[Go Back](../)

