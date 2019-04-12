---
layout: post
title: How many visitors do the National Parks get?
date: 12-04-2019
---

How many people visit the National Parks every year? This question can't be exactly answered using the data available, but the NPS does provide an estimated number of visits for each park for each year. Number of visits of course does not equal number of visitors, as an example, we often visit the same National Park for a few days in a row. We are just 5 visitors, but may count as 25 visits.

The map below marks each park site with a circle corresponding to the number of visits that it gets each year. Like the previous map, this map is created using [Folium](https://python-visualization.github.io/folium/){:target="_blank"}, using circle markers. Those Alaska parks that had the large cirlces in the area map of the previous post now show up with small circle markers. They don't get anywhere near the number of visits some of the parks in the lower 48 get each year. Hover over a circle to display the park name and the number of visits in 2018.

* The National Park that receives the most visits per year by far is Great Smoky Mountains National Park in Tennessee with over 11 million visits in 2018. This is almost twice as many visits as second place, Grand Canyon National Park.
* The park that received the fewest vists in 2018 is Gates of the Arctic National Park with only 9500 visits. This park has no roads or trails and you can only get there by plane or by hiking in from the nearest highway!

### Interactive Map
[Click here for interactive map.](https://goodmorningdata.github.io/assets/nps_parks_map_visits.html){:target="_blank"}

### Static Map
![Clickable map image]({{ site.baseurl }}/assets/20190412_nps_map_visits.png){:target="_blank"}

### Data Sources
* The master list of the National Parks is from the [NPS Data API](https://www.nps.gov/subjects/digital/nps-data-api.htm){:target="_blank"} (see the [first post](https://goodmorningdata.github.io/NPS-Clickable-Map-Parks/) for more information).

* Park visit data is available by downloading the [Annual Visitation by Park (1979 - Last Calendar Year)](https://irma.nps.gov/Stats/SSRSReports/National%20Reports/Annual%20Visitation%20By%20Park%20%281979%20-%20Last%20Calendar%20Year%29) report from the NPS Stats website. 20 years maximum are available at a time, and the data is available back to 1979.

### Notes
* The visitation reports, like the acreage report, identify each park by name only, there is no 4-character park code included. The same method as described in the last post was used to strip the park names for matching.

### Data Cleanup
* Data cleanup tasks described in the [first post](https://goodmorningdata.github.io/NPS-Clickable-Map-Parks/) in addition to the ones below.
* Like the acreage report, the park visitation reports include some park sites that are not on the master list form the API just as the park acreage reports do. These were removed. Parks missing from the API list include: 'Ross Lake NRA', 'Fort Caroline NMEM', 'Lake Chelan NRA', 'John D. Rockefeller, Jr. MEM PKWY'. Again, this deserves more research.
* Some park names from the visitation reports needed replacement in order for their park code to be found by the lookup function. These include: 'National Capital Parks Central' replaced with 'National Mall and Memorial Parks', 'Longfellow NHS' replaced with "Longfellow House Washington's Headquarters", and 'White House' replaced with "President's Park (White House)".
* Like the acreage report, some parks were broken out into two lines in the visitation reports. The visits for these were summed into one line in the master dataframe. Example: The visits for 'Glacier Bay National Park', and 'Glacier Bay National Preserve' were summed into 'Glacier Bay National Park and Preserve'.

### Creating the Map
The park visit comparison map was created using Folium.

```python
center_lower_48 = [39.833333, -98.583333]
map = folium.Map(location = center_lower_48,
                 zoom_start = 3,
                 control_scale = True,
                 tiles = 'Stamen Terrain')
```

Circle markers with size corresponding to the number of visits in 2018 relative to other parks were added to the map with a hoverable tooltip giving the name of the park and the number of visitors in 2018. A tooltip was used instead of a popup because the mouse action for the popup was less sensitive for the circle markers than for the location markers, making it difficult to get the information without frustration.

```python
for _, row in df[~df.lat.isnull()].iterrows():
    tooltip = (row.park_name.replace("'", r"\'")
               + ', {:,.0f}'.format(row['2018'])
               + ' visits in 2018')
    folium.Circle(
        radius=row['2018']/100,
        location=[row.lat, row.long],
        tooltip=tooltip,
        color='blue',
        fill=True,
        fill_color='blue'
    ).add_to(map)
```

### Using the Scripts
Instructions to run the scripts are found in the readme in the GitHub repository found [here](https://github.com/goodmorningdata/nps){:target="_blank"}.

### Raw Data
{% include 20190412_nps_parks_sorted_by_visits.html %}
