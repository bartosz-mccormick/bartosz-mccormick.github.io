---
title: "Strain Response Shape Classification for Bridge Weigh-in-Motion Applications"
date: 2020-04-30
draft: false
categories:
- research
---

This project was my introduction to academic research. During my junior and senior years of undergrad I had the opportunity to be a part of UConn's [Smart Infrastructure Lab](https://smart.engr.uconn.edu/people/) and work under Dr. Shinae Jang. More important than the outcome of the research was that the project allowed me to go through the entire research process, including literature review, writing a grant proposal, running my own project, and sharing my findings. 

Below you'll find a description of the project. You can also click [here](../resources/bwim-poster.pdf) to view a poster I made.

---

Trucks are really heavy, so much so that they are largely responsible for the structural requirements of transportation infrastructure. Bridge Weigh-in-Motion (BWIM) systems are non-intrusive alternatives to static weigh stations.


![comparison of BWIM to static weigh stations](../resources/bwim-system-comparison.png)

These systems typically utilize strain data collected during the passing of a vehicle over a bridge.The following data sample illustrates the variability of the strain response within the domain.

![sample of strain data](../resources/bwim-data-sample.png)

In this research, I developed a novel classifier for the strain response shape. This was an interesting problem to work on as I leveraged a shape-based clustering algorithm. Typically, clustering is performed on a dataset in which each sample is represented by a point in an N-dimensional space. In this case, however, each sample was represented by a sequence of strain measurements.

![BWIM classifier visualization](../resources/bwim-classifier.png)

The algorithm achieved an 80% classification accuracy, allowing for the differentiation between different types of vehicles and the validation of an in-use BWIM algorithm.







