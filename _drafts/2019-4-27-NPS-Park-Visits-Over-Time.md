---
layout: post
title: National Park visits over time
date: 27-04-2019
---

In the last post we looked at the number of visits to the National Parks in 2018. The NPS makes visit data available back to 1904 so it is possible to examine visit trends over time.

![Histogram image]({{ site.baseurl }}/assets/20190412_park_visits_histogram.png){:target="_blank"}



### Data Sources
* The master list of the National Parks is from the [NPS Data API](https://www.nps.gov/subjects/digital/nps-data-api.htm){:target="_blank"} (see the [first post](https://goodmorningdata.github.io/NPS-Clickable-Map-Parks/) for more information).

* Park visit data is available by downloading the [Annual Summary Report (1904 - Last Calendar Year)](https://irma.nps.gov/Stats/SSRSReports/National%20Reports/Annual%20Summary%20Report%20%281904%20-%20Last%20Calendar%20Year%29){:target="_blank"} report from the NPS Stats website.

* U.S. Population data is from various sources at census.gov. Data from 2010 - 2017 is available via the API. Data for years prior to 2010 are available via downloadable reports.

### Notes
* The visitation reports, like the acreage report, identify each park by name only, there is no 4-character park code included. The same method as described in the last post was used to strip the park names for matching.

### Data Cleanup

### Code Examples
The park visit comparison map was created using Folium.

```python

```

### Using the Scripts
Instructions to run the scripts are found in the readme in the GitHub repository found [here](https://github.com/goodmorningdata/nps){:target="_blank"}.

---

### Raw Data
{% include 20190412_nps_parks_sorted_by_visits.html %}

---
