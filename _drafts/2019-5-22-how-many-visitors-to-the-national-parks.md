---
layout: post
title: How many people visit the national parks?
date: 22-5-2019
tags: national-park-service
---

We can't answer the question of how many unique visitors the national parks get each year, but the NPS does provide reports giving the number of visits each year. The number of visits will be greater than number of visitors because if you visit the same park more than once in a year, even though you are one visitor, each visit will be counted.

The map below marks the location of each national park with a circle with size relative to the number of visits to that park in 2018. The map was created using the Python library, [Folium](https://python-visualization.github.io/folium/){:target="_blank"}, with park location data from the NPS API and park visit data from [NPS Stats](https://irma.nps.gov/Stats/reports/national).

An interactive version of the map that will tell you the park name and number of visits in 2018 when you hover over the circles is found [here]({{ site.baseurl }}/assets/20190522_visit_map_national_parks.html){:target="_blank"}.

![Map image]({{ site.baseurl }}/assets/20190522_visit_map_national_parks.png){:target="_blank"}

The national park with the highest numbers of visits in 2018 is Great

### National Parks in Order of Number of Visits
{% include 20190522_visit_parks_sorted_by_visits_national_parks.html %}

### Using the Scripts
Instructions to run the scripts are found in the readme in the GitHub repository found [here](https://github.com/goodmorningdata/nps){:target="_blank"}.

---
