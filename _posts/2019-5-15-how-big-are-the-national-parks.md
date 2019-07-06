---
layout: post
title: How big are the national parks?
date: 15-5-2019
tags: national-park-service
---

For the next few posts I will concentrate on the 61 units with the designation "national park". These are the crown jewels of the system and certainly get the most press - check out Ken Burn's documentary, "The National Parks: America's Best Idea", watched by over 30 million people in it's first run on PBS.

How big are these national parks? Are they millions of acres? Hundreds? Are they all relatively the same size or are there some outliers? How big does a park have to be to keep the park in it's natural state? That last one is a hard question to answer and has caused some headaches for the National Park Service over the years.

The map below shows the size of all the national parks with a circle relative to their area (not the actual park boundary). The map was created using the Python library, [Folium](https://python-visualization.github.io/folium/){:target="_blank"}, with park location data from the [NPS API](https://www.nps.gov/subjects/digital/nps-data-api.htm) and park size data from [NPS Stats](https://irma.nps.gov/Stats/reports/national).

An interactive version of the map that will tell you the park name and size in acres and square miles when you hover over the circles is found [here]({{ site.baseurl }}/assets/20190515_size_map_national_parks.html){:target="_blank"}.

![Map image]({{ site.baseurl }}/assets/20190515_size_map_national_parks.png){:target="_blank"}

The largest national park is Wrangell-St. Elias in Alaska at 8.3 million acreas (13,004 square miles) and the smallest is Gateway Arch in Missouri at 193 acres (.3 square miles).<sup>*</sup> Those Alaska parks are huge! 7 of the top 10 largest parks are in Alaska. The largest park in the lower 48 is Death Valley National Park in California, number 5 overall, at 3.4 million acres (5,270 square miles).

<sup>*</sup>Gateway Arch National Park protects a manmade object built in the 1960s, and while a notable historic object, perhaps does not fulfill the mission of the national park designation to protect areas of natural signifigance. [Not everyone agreed](https://www.nationalparkstraveler.org/2018/03/whats-name-gateway-arch-national-park) with the designation of the arch as a national park in 2018.

The average (mean) national park size is 856,000 acres (1,338 square miles) and the median is 221,000 acres (346 square miles). Because the median is so much smaller than the mean, we can tell that the data is skewed to the right, or exhibits positive skew. Let's take a look at this in a histogram of the data.

![Histogram image]({{ site.baseurl }}/assets/20190515_size_histogram_national_parks.png)

We can see that 49 of the national parks are smaller than one million acres. The top 12 are greater than one million with two real outliers in Alaska over 7.5 million. Those big parks are very big but most of the national parks lie in a more narrow range.

### National Parks in Order of Size
{% include 20190515_size_parks_sorted_by_size_national_parks.html %}

### Using the Scripts
Instructions to run the scripts are found in the readme in the GitHub repository found [here](https://github.com/goodmorningdata/nps){:target="_blank"}.

---
