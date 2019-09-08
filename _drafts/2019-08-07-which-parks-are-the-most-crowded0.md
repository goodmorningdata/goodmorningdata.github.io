---
layout: post
title: Revisiting park size
date: 21-8-2019
tags: national-park-service
---
In the post, [How big are the national parks?](http://goodmorningdata.com/how-big-are-the-national-parks/), we took an initial look at park size. Let's now revisit that topic and get an idea of how park area is distributed among the states.

There are national parks in 

I took an initial look at park size in this post.
Which national parks are the most crowded? Some parks certainly seem more crowded than others, especially at the beginning of August. For example Zion National Park feels much more crowded than Grand Teton National Park although both are in the top 10 of number of visits per year. Is there a way to quantify this anecdotal feeling?

Using the data that we have available at this point, the best measure of "crowdedness" is number of visits per acre. This ratio gives us an idea of the density of humans in the park. See below for a table of all 61 national parks and the number of visits per acre for each. Gateway Arch National Park is by far the most crowded - this makes perfect sense as it is essentially a museum that occupies the smallest area of any of the national parks. Zion is also in the top 10 as expected, but parks like Yellowstone and Glacier are not, although they both have overflowing parking lots and people everywhere.

Although a good start, visits per acre is ultimately not a good measure of crowdedness. Other factors need to be taken into account. Some parks are very large (giving a low visits per acre), but much of the park is not accessible, and perhaps even designated wilderness, which crowds visitors into a much smaller space than indicated by their total size. Crowdedness should also take into account the number of miles of road available for visitors to drive, miles of trail to hike, and number of parking spots available. Larger numbers for all of these factors will spread out the visitors and make the park feel less crowded. Now, if I could just get my hands on that data short of adding up the miles manually from individual park maps. I haven't found any of this data readily available, but will keep searching.

The histogram below shows that over 50 of the national parks have less than 25 visits per acre. Gateway Arch is not included in the plot because it is an extreme outlier with over 10,000 visits per acre.

![Histogram image]({{ site.baseurl }}/assets/08_visits_per_acre_histogram_national_parks.png)

### National Parks in Order of Number of Vists per Acre
{% include 08_visit_park_visits_per_acre_national_parks.html %}

### Data Sources
The list of 419 official park units (as of 5/1/2019) broken out by designation comes from the [National Park System](https://www.nps.gov/aboutus/national-park-system.htm){:target="_blank"} page at nps.gov. Park visit data from the report, "Annual Summary Report (1904 - Last Calendar Year)" found on the [NPS Stats](https://irma.nps.gov/Stats/reports/national){:target="_blank"} website. 2010-2018 U.S. population data from the [U.S. Census Bureau American Fact Finder](https://factfinder.census.gov/faces/nav/jsf/pages/searchresults.xhtml?refresh=t){:target="_blank"}. 1900-2009 U.S. population data from State Intercensal Tables found on [www.census.gov](www.census.gov){:target="_blank"}.

### Using the Scripts
Instructions to run the scripts are found in the readme in the GitHub repository found [here](https://github.com/goodmorningdata/nps){:target="_blank"}.

---
