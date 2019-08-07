---
layout: post
title: Which parks are the most popular?
date: 10-7-2019
tags: national-park-service
---
Which parks are the most popular? The post, [How many people visit the national parks?](https://goodmorningdata.github.io/how-many-visitors-to-the-national-parks/){:target="_blank"} lists the national parks in order of number of visits in 2018, but let's also take a look at this data per capita and over time. Are certain parks getting more popular and others declining? After visiting 30 national parks over this past year, anecdotally I could name the most popular based on the crowds that we experienced, but better to let the numbers do the talking.

Visits to the top 10 most visited parks, from 1904 to 2018, are shown in the plot below. They all show the same general upward trend that the national parks do as a whole, with Great Smoky Mountains NP way in the lead. An exception to the trend is Acadia NP, which shows a spike in visits prior to 1990 that is the result of a change in counting methodology that provides more accurate estimates from 1990 forward ([source](https://bangordailynews.com/2016/02/02/news/hancock/acadia-national-park-visitor-level-hit-20-year-high-in-2015/){:target="_blank"}). Grand Teton NP shows a pronounced dip in the 1980s, which I have not yet been able to find a reason for.

![Line plot image]({{ site.baseurl }}/assets/06_visit_park_visits_vs_year_highest_10_national_parks.png)

The plot below is a park popularity quadrant. It plots mean park visits per capita since 1967<sup>*</sup> vs. change rate of visits per capita over that time. The horizontal red line divides parks with positive change rates (number of visits per capita is going up) and negative change rates. The vertical red line splits the parks in half by mean visits per capita. Parks to the left are in the bottom half of visits and parks to the right are in the top half.

>It is important to note that a park may have a negative change rate in visits per capita even if their total park visits is still increasing.

<sup>*</sup><span style="font-size:10pt;">1967 is the first year in which total national park visits per capita declined since the end of WWII. I am using 1967 as the starting year of stablized park visitation numbers.</span>

![Quadrant image]({{ site.baseurl }}/assets/06_census_park_popularity_quadrant_national_parks.png)
<span style="font-size:10pt;">Because there are 61 parks on the plot, and many are clustered together, it is difficult to read the park codes. Quadrant contents are listed at the bottom of this post.</span>

* It is no surprise that of the 8 parks in Quadrant I, 5 are in the list of top 10 most visited. But where are the remaining 5 top tenners? They can all be found in Quadrant IV, still very popular, but their visits per capita rate is actually declining.
* The additional 3 parks in Quadrant I, popular and getting more popular, are Indiana Dunes NP, Cuyahoga Valley NP, and Joshua Tree NP. These parks are all near major urban areas, which may contribute to their increasing popularity - this is worth looking into more in a future blog post.
* Quadrant II contains the "up and comers." These parks are less popular and presumably less crowded, but their popularity is on the increase.
* Quadrant IV contains the less popular parks whose popularity is on the decline. These are the ones to visit to avoid the crowds.
* Interestingly, all 8 of the national parks in Alaska are in Quadrant II. They don't get a lot of visitors, but their popularity is on the rise.

Over the next blog posts, I will look at a few of these parks in more detail.

### Parks by quadrant
#### Quadrant I
Cuyahoga Valley National Park, Glacier National Park, Grand Canyon National Park, Indiana Dunes National Park, Joshua Tree National Park, Yellowstone National Park, Yosemite National Park, Zion National Park.

#### Quadrant II
Arches National Park, Big Bend National Park, Biscayne National Park, Bryce Canyon National Park, Canyonlands National Park, Capitol Reef National Park, Channel Islands National Park, Congaree National Park, Death Valley National Park, Denali National Park, Dry Tortugas National Park, Gates of the Arctic National Park, Glacier Bay National Park, Great Basin National Park, Great Sand Dunes National Park, Guadalupe Mountains National Park, Haleakalā National Park, Katmai National Park, Kenai Fjords National Park, Kobuk Valley National Park, Lake Clark National Park, National Park of American Samoa, Redwood National Park, Saguaro National Park, Virgin Islands National Park, Voyageurs National Park, Wrangell-St. Elias National Park.

#### Quadrant III
Black Canyon of the Gunnison National Park, Carlsbad Caverns National Park, Crater Lake National Park, Everglades National Park, Isle Royale National Park, Kings Canyon National Park, Lassen Volcanic National Park, Mesa Verde National Park, North Cascades National Park, Petrified Forest National Park, Pinnacles National Park, Sequoia National Park, Theodore Roosevelt National Park, Wind Cave National Park.

#### Quadrant IV
Acadia National Park, Badlands National Park, Gateway Arch National Park, Grand Teton National Park, Great Smoky Mountains National Park, Hawai'i Volcanoes National Park, Hot Springs National Park, Mammoth Cave National Park, Mount Rainier National Park, Olympic National Park, Rocky Mountain National Park, Shenandoah National Park.

### Data Sources
The list of 419 official park units (as of 5/1/2019) broken out by designation comes from the [National Park System](https://www.nps.gov/aboutus/national-park-system.htm){:target="_blank"} page at nps.gov. Park visit data from the report, "Annual Summary Report (1904 - Last Calendar Year)" found on the [NPS Stats](https://irma.nps.gov/Stats/reports/national){:target="_blank"} website. 2010-2018 U.S. population data from the [U.S. Census Bureau American Fact Finder](https://factfinder.census.gov/faces/nav/jsf/pages/searchresults.xhtml?refresh=t){:target="_blank"}. 1900-2009 U.S. population data from State Intercensal Tables found on [www.census.gov](www.census.gov){:target="_blank"}.

### Using the Scripts
Instructions to run the scripts are found in the readme in the GitHub repository found [here](https://github.com/goodmorningdata/nps){:target="_blank"}.

---
