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

The largest national park is Wrangell-St. Elias in Alaska at 13,000 square miles and the smallest is Gateway Arch in Missouri at .3 square miles. Those Alaska parks are huge! 7 of the top 10 largest parks are in Alaska. The largest park in the lower 48 is Death Valley National Park in California (number 5 overall) at 5,270 square miles.

The average (mean) national park size is 1,338 square miles and the median 346 square miles. Because the median is so much smaller than the mean, we can tell that the data is skewed to the right, or exhibits positive skew. Let's take a look at this in a histogram of the data.

![Histogram image]({{ site.baseurl }}/assets/20190515_size_histogram_national_parks.png)

We can see that well over half of the national parks are smaller than 1,000 square miles and 51 of the parks are smaller than 2,000. The top 10 are the real outliers and range from 2,357 suare miles up to 13,004 square miles. Those big parks are very big but most of the national parks are a much more manageable size.

### National Parks in Order of Size
{% include 20190515_size_parks_sorted_by_size_national_parks.html %}

### Using the Scripts
Instructions to run the scripts are found in the readme in the GitHub repository found [here](https://github.com/goodmorningdata/nps){:target="_blank"}.

---
