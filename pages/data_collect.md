---
layout: default
title: Real-Time Data Collecting and Processing
---

# Data Collecting

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
  
  
<details><summary markdown="span">Let's see some code!</summary>
```python
print('Hello World!')
```
Of course, it has to be Hello World, right?
</details>
<br/>

<details>
  <summary> Let's see some code! </summary>
  
```python
import pandas as pd
import datetime

######################################  Speed Dataset #########################################
new = pd.DataFrame()
Speed_data = []

#read all 31 files, each file contains speed readings from a single day in Jan 2020
for i in range(1,32): 
    data_xls = pd.read_excel('Speed_data/pems_output-'+str(i)+'.xlsx', index_col=None)
    new = data_xls[['Time','Postmile (Abs)','VDS','AggSpeed', '% Observed']]
    new = new.rename(index=str, columns={"Time":"Time","Postmile (Abs)": "Postmile",
                              "VDS":"Link_ID","AggSpeed": "Speed","% Observed": "Accuracy"})    
    date = datetime.date(2020,1,i)        
    new['Time'] = pd.to_datetime(date.strftime('%Y-%m-%d:') + new['Time'], format='%Y-%m-%d:%H:%M')
    Speed_data.append(new)

#save all speed readings into a single .csv file
Speed_data = pd.concat(Speed_data, axis=0)
Speed_data.to_csv('Speed_2020_Jan.csv', encoding='utf-8',index=False)

######################################  Event Dataset #########################################
new = pd.DataFrame()
Event_data = []

#read all 5 files, each file contains all accident details happended in a week in Jan 2020
for i in range(1,6):
    
    data_xls = pd.read_excel('Accidents/pems_output-'+str(32+i)+'.xlsx', index_col=None)
    new = data_xls[['Incident Id','Start Time','Duration (mins)','Abs PM','DESCRIPTION']]
    new = new.rename(index=str, columns={"Incident Id":"Incident_ID","Start Time": "Start_Time", 
                     "Duration (mins)":"Duration","Abs PM": "Postmile","DESCRIPTION": "DESCRIP"})
   
    new['Start_Time'] = pd.to_datetime(new['Start_Time'], format='%m-%d-%y %H:%M')   
    Event_data.append(new)

#save all event data into a single .csv file
Event_data = pd.concat(Event_data, axis=0)
Event_data.to_csv('Event_2020_Jan.csv', encoding='utf-8',index=False)
```
</details>
  
# Data Processing and Visualizing

During data processing, we utilize a liner interpolation filter to handle missing samples.  The below figure shows speed data from an accident reported on absolute postmile (Abs PM) 13.6 at 2:44pm on January 1st, 2020. 

![Sample Acc](../images/sample_acc.png)

In this figure, solid lines represent speed readings from upstream sensors, while dashed lines represents speed readings from downstream sensors.  

![Down Up](../images/down_up.png)

[Go Back](../)
