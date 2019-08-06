---
layout: post
title: How big are the national parks?
date: 29-05-2019
tags: national-park-service
---

For the next few posts I will concentrate on the 61 units with the designation "national park." These are the crown jewels of the system and certainly get the most press — check out Ken Burns' documentary "The National Parks: America's Best Idea," watched by over 30 million people in its first run on PBS in 2009.

How big are these national parks? Are they millions of acres? Hundreds? Are they all relatively the same size or are there some outliers? How big does a park have to be to keep the park in it's natural state? That last one is a hard question to answer and has caused some headaches for the National Park Service over the years.

The map below shows the size of all the national parks with a circle relative to each park's area (not the actual park boundary).

An interactive version of the map that will tell you the park name and size in acres and square miles when you hover over a circle is found [here]({{ site.baseurl }}/assets/03_size_map_national_parks.html){:target="_blank"}.

![Map image]({{ site.baseurl }}/assets/03_size_map_national_parks.png){:target="_blank"}
*<span style="font-size:10pt;">The map was created using the Python library, [Folium](https://python-visualization.github.io/folium/){:target="_blank"}</span>*

The largest national park is Wrangell-St. Elias in Alaska at 8.3 million acres (13,004 square miles), and the smallest is Gateway Arch in Missouri at 193 acres (.3 square miles).<sup>*</sup> Those Alaska parks are huge! Seven of the top 10 largest parks are in Alaska. The largest park in the lower 48 is Death Valley National Park in California, number 5 overall, at 3.4 million acres (5,270 square miles).

<sup>*</sup>Gateway Arch National Park protects a manmade object built in the 1960s, and while a notable historic object, its being designated a national park perhaps does not fulfill the mission of such a designation, which is meant to protect areas of natural signifigance. [Not everyone agreed](https://www.nationalparkstraveler.org/2018/03/whats-name-gateway-arch-national-park){:target="_blank"} with the designation of the arch as a national park in 2018.

The average (mean) national park size is ~856,000 acres (1,338 square miles) and the median is ~221,000 acres (346 square miles). Because the median is so much smaller than the mean, we can tell that the data is skewed to the right, or exhibits positive skew. Let's take a look at this in a histogram of the data.

![Histogram image]({{ site.baseurl }}/assets/03_size_histogram_national_parks.png)

We can see that 49 of the national parks are smaller than one million acres. The top 12 are greater than one million with two real outliers in Alaska over 7.5 million. Those big parks are very big but most of the national parks lie in a more narrow range.

### National Parks in Order of Size
{% include 03_size_parks_sorted_by_size_national_parks.html %}

### Data Sources
The list of 419 official park units (as of 5/1/2019) broken out by designation comes from the [National Park System](https://www.nps.gov/aboutus/national-park-system.htm){:target="_blank"} page at nps.gov. Park location data, including latitude, longitude, and state(s) are from the National Park Service [API](https://www.nps.gov/subjects/digital/nps-data-api.htm){:target="_blank"}. Park size data is from the report, "Park Acreage Reports (1997 – Last Calendar/Fiscal Year)" found on the [NPS Stats](https://irma.nps.gov/Stats/reports/national){:target="_blank"} website.

### Using the Scripts
Instructions to run the scripts are found in the readme in the GitHub repository found [here](https://github.com/goodmorningdata/nps){:target="_blank"}.

---
