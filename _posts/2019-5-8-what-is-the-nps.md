---
layout: post
title: What is the National Park Service?
date: 08-05-2019
tags: national-park-service
---

>"The primary duty of the National Park Service is to protect the national parks and national monuments under its jurisdiction and keep them as nearly in their natural state as this can be done in view of the fact that access to them must be provided in order that they may be used and enjoyed. All other activities of the bureau must be secondary (but not incidental) to this fundamental function relating to care and protection of all areas subject to its control." -- Stephen Mather, 1925

The National Park Service (NPS), a bureau of the Department of the Interior, was created on August 25, 1916, by the [Organic Act](https://en.wikipedia.org/wiki/National_Park_Service_Organic_Act){:target="_blank"}, signed into law by President Woodrow Wilson. The NPS was created to consolidate management of the various federal park lands. At that time, there were 35 national parks and monuments managed by the Department of the Interior. Other parks existed at the time, managed by the War Department (now the Deparment of Defense), the Department of Agriculture, and the Forest Service. The Forest Service and War Department parks were brought under the auspices of the National Park Service by executive order in 1933, signed by President Franklin D. Roosevelt. The first director of the NPS was Stephen Mather, a conservationist and Sierra Club member, who interestingly made his fortune in borax, an ingredient of detergent, which was mined extensively in the Death Valley region.

Since then, the NPS has grown and now manages 419 official units as of May 2019. The units are categorized into different designations depending on their natural and historical resources. Aside from the national parks introduced in the last post, designations include:
>National battlefields and national battlefield parks, national military parks, national historical parks, national historic sites, national lakeshores, national memorials, national monuments, national parks, national parkways, national preserves and reserves, national recration areas, national rivers and national wild and scenic rivers and riverways, national scenic trails, national seashores, and one international historic site.

The map below shows the locations of all 419 National Park Service units.<sup>*</sup> The map is crazy crowded because there are so many sites. For a more readable version, zoom in to the area you are interested in on the clickable version of the map found [here](https://goodmorningdata.github.io/assets/20190508_loc_map_all_parks.html){:target="_blank"}.

<sup>*</sup>The map does not include the following locations because their latitude and longitude was not available via NPS API: Blackstone River Valley National Historical Park, Camp Nelson National Monument, Delaware National Scenic River, John D. Rockefeller National Parkway, Potomac Heritage National Scenic Trail, World War I Memorial.

![Map image]({{ site.baseurl }}/assets/20190508_nps_parks_map_location_all_parks.png){:target="_blank"}
*<span style="font-size:10pt;">The map was created using the Python library, [Folium](https://python-visualization.github.io/folium/){:target="_blank"}</span>*

National Park System parks/units are found in all 50 states, the District of Columbia, and in the U.S. territories of American Samoa, Guam, Puerto Rico, and the U.S. Virgin Islands. Some parks are in more than one state like Yellowstone National Park which is located in Idaho, Montana, and Wyoming. California is the winner again with 28 NPS sites and the District of Columnbia is second with 25.

![Bar chart image]({{ site.baseurl }}/assets/20190508_loc_parks_per_state_all_parks.png){:target="_blank"}

NPS park/unit location can also be understood by looking at a choropleth map of the data. Winners in blue.

![Choropleth map]({{ site.baseurl }}/assets/20190508_choropleth_map_all_parks.png){:target="_blank"}

### Data Sources
The list of 419 official park units (as of 5/1/2019) broken out by designation comes from the [National Park System](https://www.nps.gov/aboutus/national-park-system.htm){:target="_blank"} page at nps.gov. Park location data, including latitude, longitude, and state(s) are from the National Park Service [API](https://www.nps.gov/subjects/digital/nps-data-api.htm){:target="_blank"}.

### Using the Scripts
Instructions to run the scripts are found in the readme in the GitHub repository found [here](https://github.com/goodmorningdata/nps){:target="_blank"}.

---
