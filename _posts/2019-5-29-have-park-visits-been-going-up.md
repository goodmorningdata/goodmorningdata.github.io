---
layout: post
title: Have park visits been going up over time?
date: 29-5-2019
tags: national-park-service
---

In the last post, we looked at the number of visits to the national parks in 2018. Those numbers are interesting, but how do they compare to historical data? Have park visits been going up or down over time? Has the rate of increase or decrease been constant or has it changed?

In the early days of the National Park Service there was a push to get visitors to the often difficult to reach parks. To make them easier to reach, the railroads built lines to the parks and grand lodges for the visitors to stay in. The railroads and the park service jointly advertised producing such campaigns as "See America First", encouraging Americans to visit their national parks instead of other popular destinations of the time such as Switzerland. More recently, the NPS producted an advertising campaign for the 100th anniversary of the parks in 2016. I have been to almost half of the national parks over the past year, and one thing I notice is no advertising needed. There are plenty of visitors, and in some cases, more than the parks can comfortably handle.

The plot below shows total park visits for the national parks since 1904. A few things to point out:
* We see a small increase in visits until the start of WWII and then visits drop dramatically. Some parks, like [Mount Rainier National Park](https://www.nps.gov/articles/mtrainierwwiitraining.htm), were used as military training sites.
* After WWII, the population of the middle-class and car ownership increased, giving people the money and the transportation to get to the national parks. Park visits increased at a fairly steady rate from the end of WWII through ~1995 with a few dips.
* The oil crisises of 1973 and 1979 surely contributed to the decreases in that decade.
* The Great Recession of 2007-9 caused the sustained decrease in visits during the latter half of the 2000s.
* In 2012 the numbe of visits jump back up to higher than the pre-recession level.

![Line plot image]({{ site.baseurl }}/assets/20190527_visit_total_park_visits_vs_year_national_parks.png)

### Data Sources
The list of 419 official park units (as of 5/1/2019) broken out by designation comes from the [National Park System](https://www.nps.gov/aboutus/national-park-system.htm){:target="_blank"} page at nps.gov. Park location data, including latitude, longitude, and state(s) are from the National Park Service [API](https://www.nps.gov/subjects/digital/nps-data-api.htm){:target="_blank"}. Park visit data from the report, "Annual Summary Report (1904 - Last Calendar Year)" found on the [NPS Stats](https://irma.nps.gov/Stats/reports/national){:target="_blank"} website.

### Using the Scripts
Instructions to run the scripts are found in the readme in the GitHub repository found [here](https://github.com/goodmorningdata/nps){:target="_blank"}.

---
