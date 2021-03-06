---
layout: post
title: Have park visits been going up over time?
date: 26-06-2019
tags: national-park-service
---

In the last post, we looked at the number of visits to the national parks in 2018. Those numbers are interesting, but how do they compare to historical data? Have park visits been going up or down over time?

In the early days of the National Park Service, there was a push to get visitors to the more difficult-to-reach parks. To make them easier to reach, the railroads built raillines to the parks and [grand lodges](https://en.wikipedia.org/wiki/Glacier_Park_Lodge){:target="_blank"} for visitors to stay in. The railroads and the park service worked together to produce such advertising campaigns as "See America First," encouraging Americans to visit their national parks instead of visiting other popular tourist destinations of the time, such as Switzerland. In 2016, the NPS produced a special advertising campaign for the 100th anniversary of the parks. Some of the parks get so many visits per year that they probably don't need any additional advertising, but letting people know about those lesser-visited national park sites is certainly important.

The plot below shows total park visits for the national parks since 1904. A few things to point out:
* We see a small increase in visits until the start of WWII and then visits drop dramatically. Some parks, like [Mount Rainier National Park](https://www.nps.gov/articles/mtrainierwwiitraining.htm){:target="_blank"}, were used as military training sites during the war.
* After WWII, the population of the middle-class and car ownership increased, giving people the money and the transportation necessary to get to the national parks. Park visits increased at a fairly steady rate from the end of WWII through ~1995 with a few dips.
* The oil crises of 1973 and 1979 surely contributed to the decreases in that decade.
* The Great Recession of 2007-2009 likely caused the sustained decrease in visits during the latter half of the 2000s.
* In 2012, the number of visits jumped back up to higher than the pre-recession level.

![Line plot image]({{ site.baseurl }}/assets/05_visit_total_park_visits_vs_year_national_parks.png)

The next two plots compare the total national park visits per year to the U.S. population.
In the first plot, the data are separated, and we can see the steady increase in the U.S. population up to the current level of ~327 million people (2018) and the less steady, but still increasing, total number of national park visits up to the 2018 level of ~86 million.
The second plot displays the per capita national park visits per year. Per capita means "for each head" in Latin, and park visits per capita are calculated as number of park visits per year divided by U.S. population for that year. This gives us an idea of the growing or decreasing popularity of the national parks. Interestingly, visits per capita increased rapidly between 1904 and 1967 (except for during WWII), when there is a decrease. It then bounces between .21 and .27 from 1970 to 2018 with a mean value of .25. A regression line fit to the data since 1967 shows a slight downtrend in visits per capita for the national parks (the number of visits continues to increase, but per capita figures are different). Perhaps this means that we have reached peak visits per capita and park visits will hover around 25% of the U.S. population with annual variability owing to economic conditions. If true, this would certainly help the NPS plan for visit numbers each year.

![Line plot image]({{ site.baseurl }}/assets/05_census_park_visits_vs_us_pop_national_parks.png)

![Line plot image]({{ site.baseurl }}/assets/05_census_park_visits_per_capita_vs_year_national_parks.png)

### Data Sources
The list of 419 official park units (as of 5/1/2019) broken out by designation comes from the [National Park System](https://www.nps.gov/aboutus/national-park-system.htm){:target="_blank"} page at nps.gov. Park visit data from the report, "Annual Summary Report (1904 - Last Calendar Year)" found on the [NPS Stats](https://irma.nps.gov/Stats/reports/national){:target="_blank"} website. 2010-2018 U.S. population data from the [U.S. Census Bureau American Fact Finder](https://factfinder.census.gov/faces/nav/jsf/pages/searchresults.xhtml?refresh=t){:target="_blank"}. 1900-2009 U.S. population data from State Intercensal Tables found on [www.census.gov](www.census.gov){:target="_blank"}.

### Using the Scripts
Instructions to run the scripts are found in the readme in the GitHub repository found [here](https://github.com/goodmorningdata/nps){:target="_blank"}.

---
