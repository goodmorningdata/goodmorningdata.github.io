---
layout: post
title: What are the national parks?
date: 01-05-2019
---

The very first national park in the United States was Yellowstone National Park, established by an act of Congress on March 1, 1872, in the then territories of Wyoming and Montana. This started a precedent allowing Congress to set aside public lands for the protection of their resources. Resources worthy of protection include a list of natural areas including grasslands, rivers, or a rare species habitat, historical sites of archeologic or geologic interest, and exemplary landforms like caverns, and mountains. There are 419 units managed by the National Park Service today but only 61 of those are given the designation, national park, because they contain a variety of the listed resources and the land and/or water area necessary to protect them. The 61 national parks including places like Grand Canyon, Yosemite, Glacier, Redwoods, and Acadia protect the most beautiful and fantastic parts of our amazing country.

The map below, shows the locations of all 61 national parks. The map was created using data from the NPS using the Python library, [Folium](https://python-visualization.github.io/folium/){:target="_blank"}, which uses the Leaflet.js library for map visualizations. A clickable version of the map that gives you park name and a link to it's website on click is found [here](https://goodmorningdata.github.io/assets/nps_parks_map_location.html){:target="_blank"}.

![Clickable map image]({{ site.baseurl }}/assets/20190320_nps_map_location.png){:target="_blank"}

Not every state 

### Data Sources
* The master list of the National Parks is from the [NPS Data API](https://www.nps.gov/subjects/digital/nps-data-api.htm){:target="_blank"}. To use the API, you need to register and receive an API key. For this map, I used the /parks resource endpoint. There are 61 National Parks, but the park service system includes 419 total sites. This API call actually pulls 496 different sites, as several of these sites are managed by the same entity within the NPS.

* Other data sources, including acreage and visitation, are pulled and used to create the master dataframe, but aren't used for this particular map, so I will address them in a later post.

### Notes
* All NPS sites are assigned a 4 character code which is usually (there are exceptions), the first two characters of the first word and first two characters of the second word for site names with two or more words, or the first four characters of the name for one word site names. For example, the park code for Death Valley National Park is "DEVA" and the park code for Zion National Park is "ZION". This code uniquely identifies the park.

* National Park sites are categorized into larger groups using a "designation". Designations include National Parks, National Monuments, National Historic Sites, etc.

### Data Cleanup
* 33 of the park sites pulled by the API call aren't assigned a designation. Using information found on the [NPS site](https://www.nps.gov/articles/nps-designations.htm){:target="_blank"}, I assigned designations to these parks.

* Latitude and longitude were delivered in the same column by the API call, so these were split out into two columns.

### Creating the Map
The clickable map was created using Folium.

```python
center_lower_48 = [39.833333, -98.583333]
map = folium.Map(location = center_lower_48,
                 zoom_start = 4,
                 control_scale = True,
                 tiles = 'Stamen Terrain')
```

Location markers for each National Park were added to the map with a clickable popup link to the NPS page for the park. Icon types (Font Awsesome), and colors are assigned in the dataframe, icon_df.

```python
for _, row in df[~df.lat.isnull()].iterrows():

    # Create popup with link to park website.
    popup_string = ('<a href="'
                    + 'https://www.nps.gov/' + row.park_code
                    + '" target="_blank">'
                    + row.park_name + '</a>').replace("'", r"\'")
    popup_html = folium.Html(popup_string, script=True)

    # Assign color and graphic to icon.
    icon_df_row = icon_df[icon_df.park_set == row.park_set]
    map_icon = folium.Icon(color=icon_df_row.values[0][1],
                           prefix='fa',
                           icon=icon_df_row.values[0][2])

    marker = folium.Marker(location = [row.lat, row.long],
                           icon = map_icon,
                           popup = folium.Popup(popup_html)
                          ).add_to(map)
```

### Using the Scripts
Instructions to run the scripts are found in the readme in the GitHub repository found [here](https://github.com/goodmorningdata/nps){:target="_blank"}.

---
