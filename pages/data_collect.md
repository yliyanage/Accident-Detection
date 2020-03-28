---
layout: default
title: Real-Time Data Collection
---
We have collected real-data provided by the California Department of Transportation, and  the California Highway Patrol, during the month of January 2020 in North direction of the I-405 freeway in the Los Angeles County. 

<p align="center">
  <img src="../images/g_map.png" height="400" width="400">
 </p>
    

1. Speed Dataset:  We have created a big-dataset comprising of 1,446,196 speed readings collected from all 162 sensors.
  - Sampling time = 5 minutes
  - No. of missing samples = 140

2. Event Dataset:  We have created a dataset comprising details from all 1163 accidents happened. Details include:
  - Reported time of the accident
  - Duration of the accident
  - Accident location
  
  To handle missing data, we have used a liner-interpolation filter. 

# Data Processing and Visualizing

The below figure shows speed data from an accident reported on absolute postmile (Abs PM) 13.6 at 2:44pm on January 1st, 2020. 

![Sample Acc](../images/sample_acc.png)

In this figure, solid lines represent speed readings from upstream sensors, while dashed lines represents speed readings from downstream sensors.  

![Down Up](../images/down_up.png)

[Back](../)
