---
layout: post
title: How do visit counts to the National Parks change over time?
date: 13-04-2019
---

Description

### Data Sources
* The master list of the National Parks is from the [NPS Data API](https://www.nps.gov/subjects/digital/nps-data-api.htm){:target="_blank"} (see the [first post](https://goodmorningdata.github.io/NPS-Clickable-Map-Parks/) for more information).

* Park visit data is available by downloading the [Annual Visitation by Park (1979 - Last Calendar Year)](https://irma.nps.gov/Stats/SSRSReports/National%20Reports/Annual%20Visitation%20By%20Park%20%281979%20-%20Last%20Calendar%20Year%29){:target="_blank"} report from the NPS Stats website. 20 years maximum are available at a time, and the data is available back to 1979.

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
