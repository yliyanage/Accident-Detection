---
layout: default
title: Feature Extraction
---

Various informative (time domain and frequency domain) features can be extracted from the raw speed readings that can facilitate the detection of accidents. 

# Time-Domain Features

We conisder 11 time-domain features:
<pre>
1. Mean                             7. Mean Absolute Deviation
2. Median                           8. Skewness
3. Standard deviation               9. Kurtosis
4. Root mean square                 10. Mean of Maxima
5. Energy                           11. Mean of Minima
6. Inter Quartile Range
</pre>

All features are computed via a rolling window approach. For example, feature mean is computed as follows:

$$ Z_k = \frac{\sum_{i=0}^{N-1} Y_{k-i}}{N}, $$

where $Z_k$ is the feature at time $k$, $Y_k$ is the speed reading at time $k$, and $N$ is the window length. 
 
The below figure shows the extracted time-domain features for the accident reported on absolute postmile (Abs PM) 13.6 at 2:44pm on January 1st, 2020. See the coressponding raw speed readings [here.](./data_collect.html)
 
 <p align="center">
  <img src="../images/time_feat.png">
 </p>
 
 
 ## Frequency-Domain Features
 
 
 1. Discrete Fourier Transform
 
 We compute the discrete fourier transform by consider a rolling window of size $N$ as follows:
 
 
 Since the speed observations are real values, we get a symmetric spectrum aroung $N/2$. Hence, we consider the d.c. component, i.e., the zero frequency component, the fundermental frequency component and all its harmonics up to $N/2$ as features at time $k$. 
 
Further, to speed-up the process of computing these features, we utilize a fast-fourier transofrm algorithm to compute discrete fourier transform, which results in reducing the number of computations from $\mathcal{O}(S^2)$ to $\mathcal{O}(Slog(S))$. 

 
[Back](../)
