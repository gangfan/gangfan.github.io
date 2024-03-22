---
layout: default
title: Data
permalink: /data/
---




## Correction 
We made a mistake when calculating the time-distribution for the 1st and 2nd stage. 
 
```wrap
! We have constructed a graphic data structure (a symbolic Control/data
dependence graph (G)) for both the points-to analysis and the 
path-condition collection. 

However, we included the time cost of the G construction in the 2nd phase,
which is incorrect since we should not count the time cost on "solving".  

This mistake results in an abnormal data of analyzing **Caffe**: even though it 
has no memory leak candidate, the analysis still spent 29s on the "2nd Phase". 

Here is the new table after we correcting this error. We will use this 
table in the revised version.  We also include the time cost of G construction
 for your reference. 
```
![Two Stage Data2](/assets/images/twostage_new_data.png)


The original table is:

![Two Stage Data](/assets/images/twostage_data.png)



*********************************************
## Artifact Evaluation

The package for artifact evaluation will be available after the review process. 
[Package Link](/install)


## Report Details

Thanks to [Github Educate program](https://www.awseducate.com/), we have set up an online report system to host the leak reports together with our manual classification. 

Thanks to [Sourcebrella Inc](https://www.sourcebrella.com/), we borrowed their bug report system to help us speed up the whole process. 
We use their free version for academic use [LINK](https://www.sourcebrella.com/online-showcase) 

The method is to convert all bug reports (SMOKE, Saber, CSA, INFER) to Pinpoint's JSON format and upload them to the server. 

The address is [SMOKE/Saber/CSA/Pinpoint/Infer Reports](http://ec2-54-185-211-230.us-west-2.compute.amazonaws.com:40080/online_report)

Username/pass :  testtest/testtest 

```
Confirmed = True Positive
False Positive = False Positive.

SSU =  SMOKE  
PSA =  PINPOINT  (Pinpoint Static Analyzer) 
CSA =  CSA       (Clang Static Analyzer)
Saber = Saber
Infer = Infer 

```

Note: When collecting the statistics information, we use the default "Cluster" feature provided by Pinpoint. 

Reports are merged if they share the same start points. 

