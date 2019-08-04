---
layout: post
title: How many people visit the national parks?
date: 12-06-2019
tags: national-park-service
---

With the data that the NPS makes available, we can't determine how many unique visitors that the parks get each year, but they do track the number of visits to each park. The number of visits and how that number changes over time can give us an idea of how crowded a park is and the human impact that the park needs to prepare for.

The map below marks the location of each national park with a circle of size relative to the number of visits to that park in 2018.

An interactive version of the map that will tell you the park name and number of visits in 2018 when you hover over the circles is found [here]({{ site.baseurl }}/assets/04_visit_map_national_parks.html){:target="_blank"}.

![Map image]({{ site.baseurl }}/assets/04_visit_map_national_parks.png){:target="_blank"}
*<span style="font-size:10pt;">The map was created using the Python library, [Folium](https://python-visualization.github.io/folium/){:target="_blank"}</span>*

The national park with the highest numbers of visits in 2018 by far is Great Smoky Mountains National Park, eclipsing the second place park, Grand Canyon, with almost twice as many visitors. The national park with the fewest number of visits is Gates of the Arctic in Alaska, with 9,591. This isn't surprising since Gates of the Arctic doesn't have any roads so to visit you have to fly in or hike in from the nearest highway.

The mean number of visits in 2018 ~1.4 million while the median is ~656,000. This shows the data is skewed to the right, just like the park size data. A few of the national parks are receiving massive numbers of visitors, but the majority receive a much smaller amount.

![Histogram image]({{ site.baseurl }}/assets/04_visit_histogram_national_parks.png)

You can see Great Smoky Mountains NP out there on the right of the histogram, and some of the other biggies, but over half of the national parks receive less than one million visits per year.

### National Parks in Order of Number of Visits
{% include 04_visit_parks_sorted_by_visits_national_parks.html %}

### Data Sources
The list of 419 official park units (as of 5/1/2019) broken out by designation comes from the [National Park System](https://www.nps.gov/aboutus/national-park-system.htm){:target="_blank"} page at nps.gov. Park location data, including latitude, longitude, and state(s) are from the National Park Service [API](https://www.nps.gov/subjects/digital/nps-data-api.htm){:target="_blank"}. Park visit data from the report, "Annual Summary Report (1904 - Last Calendar Year)" found on the [NPS Stats](https://irma.nps.gov/Stats/reports/national){:target="_blank"} website.

### Using the Scripts
Instructions to run the scripts are found in the readme in the GitHub repository found [here](https://github.com/goodmorningdata/nps){:target="_blank"}.

---
