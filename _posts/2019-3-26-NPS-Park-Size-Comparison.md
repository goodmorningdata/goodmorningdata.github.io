---
layout: post
title: National Park Size Comparison
date: 26-03-2019
---

Ever wondered how large the National Parks are or which park is the biggest? The map below marks each park site with a circle corresponding to its size. The circle does not define the exact boundaries of the park, but is of an area equal to the area of the park. Like the previous map, this map is created using [Folium](https://python-visualization.github.io/folium/){:target="_blank"}, but uses circle markers instead of location markers. Zooming in and out of the interactive map is the best way to compare the park areas. Check out the size of those Alaska parks! Hover over a circle to display the park name and size in square miles.

* The largest National Park is Wrangell - St Elias National Park & Preserve in Alaska at ~20,600 square miles.
* The smallest National Park is Gateway Arch National Park in Missouri at just .3 square miles.
* The average size of a National Park is 1,596 square miles.

### Interactive Map
[Click here for interactive map.](https://goodmorningdata.github.io/assets/nps_parks_map_area.html){:target="_blank"}

### Static Map
![Clickable map image]({{ site.baseurl }}/assets/20190326_nps_map_area.png){:target="_blank"}

### Data Sources
* The master list of the National Parks is from the [NPS Data API](https://www.nps.gov/subjects/digital/nps-data-api.htm){:target="_blank"} (see the previous post for more information).

* Park size data is not available via the NPS API and is downloaded as an Excel spreadsheet from the NPS website, [National Park Service Acreage Reports](https://www.nps.gov/subjects/lwcf/acreagereports.htm).

### Notes
* The acreage report identifies each park by name only, there is no 4-character park code included. To match each park from this report to its corrresponding park in the API park list, the park names of each were stripped of all designation identifiers and extraneous characters to reveal the essence of the name and then the best match was found using the python method, SequenceMatcher(). In addition, some cases required more brute force replacement to find the match such as replacing 'T ROOSEVELT' with 'Theodore Roosevelt'.

    Example:  NPS API park name = 'Lincoln Boyhood National Memorial', and Acreage Report park name = 'LINCOLN BOYHOOD NMEM'. Both were converted to lower case and stripped of their designation for matching, so that 'lincoln boyhood' was matched correctly to 'lincoln boyhood'.

### Data Cleanup
* Data cleanup tasks described in the [previous post](https://goodmorningdata.github.io/NPS-Clickable-Map-Parks/) in addition to the ones below.
* The park acreage report includes some park sites that are not on the master list from the API. These were removed but deserve further research as to why they aren't on the master list. Perhaps they are a part of a larger park and should be rolled up into it? Parks missing from the API list include: 'Ross Lake NRA', 'Fort Caroline NMEM', 'Lake Chelan NRA', and 'John D. Rockefeller, Jr. MEM PKWY'.
* Columns for park size in square meters and square miles were added to the master dataframe for reporting.
* Some parks were broken out into two lines in the acreage report. The acreage for these were summed into one line in the master dataframe. Example: The acreage for 'Glacier Bay National Park', and 'Glacier Bay National Preserve' were summed into 'Glacier Bay National Park and Preserve'.

### Creating the Map
The area comparison map was created using Folium.

```python
center_lower_48 = [39.833333, -98.583333]
map = folium.Map(location = center_lower_48,
                 zoom_start = 4,
                 control_scale = True,
                 tiles = 'Stamen Terrain')
```

Circle markers with area corresponding to the area of the National Park that they mark were added to the map with a hoverable tooltip giving the name of the park and the size in square miles. A tooltip was used instead of a popup because the mouse action for the popup was less sensitive for the circle markers than for the location markers of the previous map, making it difficult to get the information without frustration.

```python
for _, row in df[~df.lat.isnull()].iterrows():
    tooltip = (row.park_name.replace("'", r"\'")
               + ', {:,.0f}'.format(row.gross_area_square_miles)
               + ' square miles')
    folium.Circle(
        radius=math.sqrt(row.gross_area_square_meters/math.pi),
        location=[row.lat, row.long],
        tooltip=tooltip,
        color='crimson',
        fill=True,
        fill_color='crimson'
    ).add_to(map)
```

### Using the Scripts
Instructions to run the scripts are found in the readme in the GitHub repository found [here](https://github.com/goodmorningdata/nps){:target="_blank"}.

### Raw Data
{% include 20190326_nps_parks_sorted_by_size.html %}
