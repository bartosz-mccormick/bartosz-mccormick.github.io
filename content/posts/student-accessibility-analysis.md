---
title: "Comparing Student Accessibility in Bremen and Leipzig"
date: 2022-08-12
draft: false
categories:
- coursework
---
In this project I compared the accessibility of university students in Bremen and Leipzig. It was my first time analyzing public transport as well as my first accessibility analysis!

---

In some ways, Bremen and Leipzig are fairly similar. They both have:
- a population of approximately 600,000
- bus, tram, and S-Bahn service
- an active (Bike + Walk) mode share of 46%

![map of study areas](../resources/student-study-areas.png)
{{<caption>}}rail systems and population of Bremen and Leipzig {{</caption>}}

These high level statistics don't capture the nuances of the cities and are certainly insufficient to answer questions such as: "in which city is it better to live as a student?" In this project I sought to answer this question through the lens of accessibility.

The focus of the analysis was the cities' largest universities, the University of Bremen and Leipzig University, for which I considered access by public transport, cycling and walking. In addition to campus access, access to everyday amenities was considered as well. 

 The analysis consisted of three main components, (a) defining an area of minimal accessibility (AoMA), (b) determining the level of local accessibility within the AoMA, and (c) a stand-alone analysis of the cities' transportation systems.

### a) Defining an Area of Minimal Accessibility (AoMA)

The AoMA was defined as the public transport commuter catchment area. The following constraints were applied:
- 30 min. total trip duration
- 10 min. cycling access
- 10 min. walking egress

 To estimate travel times I used [r5r](https://github.com/ipeaGIT/r5r), an interface to the [R5](https://github.com/conveyal/r5) routing engine. For cycling, the network was defined as edges with a level of traffic stress (LTS)[^1] of two or less. In other words, infrastructure considered comfortable by the mainstream, adult population. On edges with an LTS greater than two, travel speed would be reduced to that of walking.

### b) Determining Local Accessibility Within the AoMA

The degree of accessibility was calculated within the AoMA by taking the weighted sum of amenities within 15 minutes by bike. Eight types of amenities relevant to students were considered with weights derived from the [2017 MiD](https://www.mobilitaet-in-deutschland.de/archive/publikationen2017.html) travel survey.

### c) transportion system analyses

To determine the _reason_ for differences in accessibility, the transportation systems of the cities were analyzed independently of land use. For public transport, I determined service frequencies by analyzing GTFS feeds (timetables). For cycling, I calculated a bikeability index which was formulated as the proportion of urbanized area accessible within a 3 km network distance relative to to the urbanized area within a 3 km Euclidean buffer. As the network distance considers LTS criteria, the measure reflects not only the form of the network but also its suitability for the target users.


### ...so which city is better?

While an accessibility analysis is still not fully sufficient to answer this question, the results indicate that **Leipzig** is superior. 

Students' accessibility was primarily determined by the size of the AoMA. As this is a public transport commuter catchment area, its extent is dependent on the form (and quality) of the public transport system and the spatial integration of the university within the system. Leipzig University is centrally located while the University of has a more peripheral location. Accordingly, in contrast to the University of Bremen, Leipzig University is directly accessible from more, higher frequency tram services as well as rapid transit (S-Bahn). Furthermore, travel in all directions is possible. Combined, this results in a significantly larger AoMA.

While the extent of the accessible area is constrained by the AoMA, the degree of accessibility within is highly dependent on the ease of biking. Both at the city level and within the AoMA, the city of Bremen is more bikeable than Leipzig. Bremen tends to have a higher degree of bikeability and has a more cohesive spatial distribution. 

![map of bikability](../resources/student-bikeability-map.png)
{{<caption>}}bikeability of Bremen and Leipzig {{</caption>}}

The other component of accessibility is the land use (i.e. the distribution of amenities). Once again, the central location of Leipzig University is a large advantage in comparison to the University of Bremen. Despite better bikeability, the limited number of amenties in the immediate vicinity of the University of Bremen results in lower accessibility scores. 

![map of accessibility](../resources/student-accessibility-map.png)
{{<caption>}}accessibility of Bremen and Leipzig {{</caption>}}

For many reasons, the peripheral location of the University of Bremen hinders the accessibility of students in the city. Additionally, it results in an undesirable consequence where students have to decide on a tradeoff between commuting time and local accessibility. In contrast, as one lives closer to Leipzig University, their commuting time decreases while their local accessibility increases.

 [^1]: The level of traffic stress (LTS) is a normative approach to evaluating cycling infrastructure. Rather than operational performance, the measure is based on Dutch design standards and aims to estimate the suitability of cycling infrastructure for various profiles of cyclists. R5 includes a [rough implementation](https://docs.conveyal.com/learn-more/traffic-stress) of this based on OpenStreetMap data. Click [here](../humboldtstrasse-redesign-for-cyclists) for another project I did involving LTS!




