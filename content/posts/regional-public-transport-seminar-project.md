---
title: "Regional Public Transport for Campus Oberpfaffenhofen"
date: 2023-03-08
draft: false
categories:
- coursework
---
Apart from the thesis, the "project seminar" was the biggest part of my master's program. In this seminar we were asked to 
develop solutions to various mobility challenges that [Air Tech Campus Oberpfaffenhofen](https://www.airtechcampus.de/), a major regional employment center, is facing.

My group was tasked with developing a strategic plan for improving access to the campus by public transport at the regional level.
We adopted the following vision for the project: 
>Regional public transport enables a high degree of access to Campus
Oberpfaffenhofen for all users. The service is financially viable and
competitive with the car, promoting a shift to sustainable mobility

which we operationalized with a goal and indicator system. I was responsible for the public transport modeling and the accessibility analyses. In this post I'll share 
some of the highlights of the project!

---
### context & methods

Located in Starnberg County, Air Tech Campus Oberfaffehofen is approximately 20km southwest of Munich's city
center. While access to the campus is convenient by car via the A 96 highway, it is significantly
more difficult by public transport. Despite the seemingly close proximity to the S8 S-Bahn line, the closest stop is a 20-minute walk from the center of campus.
The number of employees at the campus is expected to nearly double to over 20,000 by 2035, however this growth is threatened by the deficient quality of the existing public transport connections.

![study area](../resources/regional-public-transport-study-area.png)
{{<caption>}}study area (S8 line highlighted){{</caption>}}

The basis for the analyses were public transport and car travel time models. The car model was based on average road speeds from [tomtom](https://www.tomtom.com/products/traffic-stats/). 
The public transport model was based on GTFS data and was built using [r5r](https://github.com/ipeaGIT/r5r). 
Due to the large size of the campus, public transport travel time varies significantly depending on which part you need to get to.
In the interest of a holistic analysis, the reported travel time is the average travel time to the various 
employment areas within the campus, weighted by their 2035 employee forecast.

### existing conditions
Presently, approximately 400,000 working age adults have access to the campus within 60 minutes[^1] by public transport.

![baseline travel time to the campus](../resources/regional-public-transport-seminar-baseline-travel-time.png)
{{<caption>}}baseline travel time to the campus{{</caption>}}

This seems pretty good, but of those 400,000, only 10,000 have a travel time which can be considered of moderate (or better) quality.
This is defined[^2] as a public transport travel time up to 1.5 times longer than that by car. This level of quality highlights the deficiency of the 
existing public transport offer. 

![baseline ratio of public transport / car travel time to the campus](../resources/regional-public-transport-seminar-baseline-travel-time-ratio.png)
{{<caption>}}baseline ratio of public transport / car travel time to the campus{{</caption>}}

### measure development and evaluation

Based on the results of our analyses we identified target areas throughout the region for which we developed
measures to reduce travel time. The most prominent measure was the reactivation of the former Weichselbaum rail stop near the campus which would be served
by the S8 S-Bahn line. This measure has recieved very strong interest from local stakeholders. However, despite the stop being closer to the campus, it is still in a peripheral location. 
Only 12% of the employees (2035 forecast) would be able to walk to the stop within 10 minutes, indicating a persisting last-mile problem.

In light of this, we evaluated two alternatives for shuttle buses. One serving the new Weichselbaum stop (Shuttle A) 
and the other an existing stop, Gilching-Argelsried (Shuttle B). The latter option had the added benefit of supporting transfers from express buses which provide tangential connections from 
surrounding municipalities. We also evaluated numerous new bus route alignments aiming to further improve tangential connections, one of which is included in the scenarios below.

![accessibility to the campus under various scenarios](../resources/regional-public-transport-seminar-scenarios.gif)
{{<caption>}}accessibility to the campus under various scenarios{{</caption>}}

### findings

The modeling results confirmed the limited impact of the standalone reactivation of the Weichselbaum stop. When
coupled with a shuttle from Gilching-Argelsried, however, the set of measures would increase the working age population within 60 minutes by public transport by 103,000.
Additionally, it would result in 46,000 more working age adults with a moderate quality travel time, an increase of over four times from the existing conditions. Due to the urgency of the challenges the campus faces, it was recommended that a shuttle from Gilching-Argelsried is implemented in the short term as this would result in
approximately 60% of the full benefit and allow for a rapid improvement of the mobility situation.

![working age population catchment under highlighted scenarios](../resources/regional-public-transport-seminar-scenario-results.png)
{{<caption>}}working age population catchment under highlighted scenarios{{</caption>}}

 As for new regional bus lines, the best performing one was a bus to Landsberg am Lech, a town of approximately 30,000. The bus improved travel times significantly throughout the target area, albeit not within a 60-minute travel time of the campus. The goal and indicator system that we used was calibrated to isolate benefits relevant to the campus, therefore the measure did not perform very well. That being said, such a service could have benefits to the region beyond improving access to the campus especially given that it aligns with the region's goals of improving public transport along tangential axes. 


[^1]: 60 minutes is the 90th percentile commute time in Germany, accordingly it is used in the analysis as an upper limit to travel time acceptance.  
[^2]: Quality standards derived from the Bavarian local public transport planning guidelines.
