---
title: "Evaluation of E-scooter Usage in South-West Munich"
date: 2022-03-09
draft: false
---

This was an independent research project in the first semester of my Master's program. It was also my first time doing a GIS analysis!

---

E-scooter Sharing Services (ESS) began operating in Munich in 2019. In theory, the flexibility of ESS makes it well suited to address transit's first- and last-mile problem. In this project, I analyzed ESS utilization in Southwest Munich.

![map of the study area](../resources/e-scooter-study-area.png)
{{<caption>}}study area{{</caption>}}

The big technical limitation of the analysis was that trip data is not publicly available. This is also what made the project interesting as I needed to come up with a workaround. [TIER](https://www.tier.app/en/)'s public API allowed for the position of all *rentable* scooters to be queried. I set up an AWS server which ran a script to collect data each minute over the course of 11 weeks. I then reconstructed trips on the basis of temporal gaps in availability and changes in vehicle position. 

![methodology overview](../resources/e-scooter-method.png)
{{<caption>}}overview of methodology{{</caption>}}

The "feeder trip" classification was assigned if a trip end was within 50 meters of a rail stop entrance. The analysis identified that 25% of trips served a feeder purpose. When analyzing the data, I thought that determining "catchment-extending" feeder trips would also be interesting. I defined this as trips which began/ended (depending on access or egress) beyond a 10-minute walking isochrone of the rail stops[^1]. This is where I realized my data collection area should have been larger than my study area (oops!) as I could only perform this analysis for the trips which started and ended within the study area. Of all trips, 8% could be confirmed as "catchment-extending" (i.e. having a meaningful influence on providing first- and last-mile service). 

![map of access trip origins and egress trip destinations](../resources/e-scooter-access-egress-map.png)
{{<caption>}}hex bin map of access trip origins and egress trip destinations{{</caption>}}

While there is a longer, more nuanced conclusion that can be drawn from this, overall ESS had a marginal role in facilitating trips by public transport despite the study area being conducive to these types of trips (lower urban and transit system densities relative to the city center).

[^1]: In Munich, ten minutes represents the upper limit of users’ acceptance of walking access time to rail stations 