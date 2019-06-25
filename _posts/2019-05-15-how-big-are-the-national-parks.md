---
layout: post
title: How big are the national parks?
date: 15-05-2019
tags: national-park-service
---

For the next few posts I will just concentrate on the 61 national parks. How big are they? Are they all close to the same size or are there some outliers?

The map below shows the size of all the national parks with a circle relative to their area (not the actual park boundary). The map was created using park location data from the NPS API and park size data from [NPS Stats](https://irma.nps.gov/Stats/reports/national). It was created using the Python library, [Folium](https://python-visualization.github.io/folium/){:target="_blank"}.

An interactive version of the map that will tell you the park name and size in square miles when you hover over the circles is found [here]({{ site.baseurl }}/assets/20190515_size_map_national_parks.html){:target="_blank"}.

![Map image]({{ site.baseurl }}/assets/20190515_size_map_national_parks.png){:target="_blank"}

### National Parks in Order of Size
{% include 20190515_size_parks_sorted_by_size_national_parks.html %}

### Using the Scripts
Instructions to run the scripts are found in the readme in the GitHub repository found [here](https://github.com/goodmorningdata/nps){:target="_blank"}.

---
