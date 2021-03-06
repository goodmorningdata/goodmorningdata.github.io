---
layout: post
title: A closer look at popularity
date: 24-7-2019
tags: national-park-service
---
In the last post, [Which parks are the most popular?](http://goodmorningdata.com/which-parks-are-most-popular/), we took a look at park popularity using a plot of mean visits per capita vs. visits per capita change rate divided into quadrants. In this post, let's take a look at four parks in each of the quadrants.
![Quadrant image]({{ site.baseurl }}/assets/06_census_park_popularity_quadrant_national_parks.png)

### Quadrant I - Highest visits and increasing
The parks in Quadrant I have the highest mean visits per capita since 1967<sup>*</sup> and an increasing visit change rate since that year. The plot below shows the data for four of these parks.
<br/><sup>*</sup><span style="font-size:10pt;">1967 is the first year in which total national park visits per capita declined since the end of WWII. I am using 1967 as the starting year of stablized park visitation numbers.</span>

![Plot image]({{ site.baseurl }}/assets/07_census_park_visits_per_capita_vs_year_4_parks_q1.png)

Glacier and Yellowstone show visits per capita bouncing around a per capita rate of .006 and .011 respectively with a steady increase over time. Zion shows a real change - a very steady increase up to Yellowstone levels, and still climbing. Zion actually is the park with the maximum per capita visit change rate of all the national parks. Having been there, I can attest to its massive popularity. It is amazingly beautiful and crowded - a challenge for the NPS. One of these things is not like the others, and this is Cuyahoga Valley National Park. Its popularity is not increasing, in fact, visits per capita have been going down for some time. CVNP experienced a huge surge in visits in 2000 when it was redesignated from a national recreation area to a national park. Since then, per capita visists have been declining, but that initial surge is still driving the regression line upward. It looks like a change to my methodology of determining popularity is in order. Instead of calculating the regression line beginning in 1967 when visits per capita started to stablize, I may want to use a later date to give greater weight to recent visit numbers.

### Quadrant II - Lowest visits and increasing
The parks in Quadrant II have mean per capita visits in the bottom half, but an increasing visit change rate indicating that their popularity is on the rise. The plot below shows the data for four of these parks.

![Plot image]({{ site.baseurl }}/assets/07_census_park_visits_per_capita_vs_year_4_parks_q2.png)

We see two of the Utah parks in the top row. Arches and Capitol Reef National Parks have a visits per capita rate firmly on the rise. Joshua Tree, in California and close to Los Angeles, is even more drastically on the rise and the jump over the past few years is pretty incredible, this is one to keep an eye on. At first glance, Virgin Islands National Park doesn't seem to belong in this group. Visits bounced around a stable level from about 1980 on until 2017 when the island was devastated by two hurricanes and visits went way down. The high numbers prior to 2017 keep the per capita visit rate on the upswing and I would expect this park to recover to prior year levels.

### Quadrant III - Lowest visits and declining
The parks in Quadrant III have mean per capita visits in the bottom half and their visit change rate is declining. The plot below shows the data for four of these parks. Some of the parks in this quadrant, like Isle Royale, an island in the middle of Lake Superior, are not a surprise - they are difficult to get to!

![Plot image]({{ site.baseurl }}/assets/07_census_park_visits_per_capita_vs_year_4_parks_q3.png)

Pinnacles and Redwood actually seem to be holding fairly steady. Their per capita change rate looks like it could go either way over the next years. I am surprised that more people don't actually visit Redwood National Park. It is so famous, but it is far away from any major urban areas which keeps the numbers down. Carlsbad Caverns and Everglades have a definite downturn in per capita visits. This would take more research to determine the reason. Perhaps caves aren't very interesting right now because it is difficult to take Instagram photos while in them? Maybe too many mousquitoes in Florida?

### Quadrant IV - Highest visits and declining
The parks in Quadrant IV have mean per capita vistis in the top half with a declining visit change rate. The plot below shows the data for four of these parks.

![Plot image]({{ site.baseurl }}/assets/07_census_park_visits_per_capita_vs_year_4_parks_q4.png)

Acadia National Park discovered an error in their visitor counting procedures leading to the sharp decline around 1990. Otherwise, it seems to be holding fairly steady, a better look at this park could be had with a change in my methodology, and perhaps only look at visit change rate since 1990 instead of 1967 - a topic for a future blog post. Grand Teton had a big dip in the 1980s but seems to have recovered. Both Mammoth Cave and Shenandoah are definitely on the downswing. Perhaps Mammoth Cave is suffering from the same cave effect as Carlsbad Caverns? This is something worth looking into. Shenandoah's numbers are a mystery to me. It has the most negative per capita visit change rate of any of the national parks. It is close to major urban areas and is a beautiful, accessible park, so why would the visits per capita rate be going down?

### Data Sources
The list of 419 official park units (as of 5/1/2019) broken out by designation comes from the [National Park System](https://www.nps.gov/aboutus/national-park-system.htm){:target="_blank"} page at nps.gov. Park visit data from the report, "Annual Summary Report (1904 - Last Calendar Year)" found on the [NPS Stats](https://irma.nps.gov/Stats/reports/national){:target="_blank"} website. 2010-2018 U.S. population data from the [U.S. Census Bureau American Fact Finder](https://factfinder.census.gov/faces/nav/jsf/pages/searchresults.xhtml?refresh=t){:target="_blank"}. 1900-2009 U.S. population data from State Intercensal Tables found on [www.census.gov](www.census.gov){:target="_blank"}.

### Using the Scripts
Instructions to run the scripts are found in the readme in the GitHub repository found [here](https://github.com/goodmorningdata/nps){:target="_blank"}.

---
