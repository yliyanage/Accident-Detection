---
layout: default
title: Feature Extraction
---

Various informative (time domain and frequency domain) features can be extracted from the raw speed readings that can facilitate the detection of accidents. 

# Time-Domain Features

We conisder 11 time-domain features:

i) Mean, ii) Median, iii) Standard deviation, iv) Root mean square, v) Energy, vi) Inter Quartile Range, vii) Mean Absolute Deviation, viii) Skewness, ix) Kurtosis, x) Mean of Maxima, and xi) Mean of Minima. 

All features are computed via a rolling window approach. For example, feature mean is computed as follows:

 <p align="center">
  <img src="../images/eq1.png" height="200" width="300">
 </p>

[Back](../)
