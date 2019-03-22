---
layout: post
title: Clickable map of the National Parks
date: 20-03-2019
draft: false
output:
  html_document:
    css: custom.css
---

I'll start with a simple task, creating a clickable map of the U.S. National Parks, a long-term interest of mine. The map is created using [Folium](https://python-visualization.github.io/folium/){:target="_blank"}, a Python tool that allows you to visualize a map using the Leaflet.js library.

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
>    center_lower_48 = [39.833333, -98.583333]
>    map = folium.Map(location = center_lower_48,
>                     zoom_start = 4,
>                     control_scale = True,
>                     tiles = 'Stamen Terrain')

Location markers for each National Park were added to the map with a clickable popup link to the NPS page for the park. Icon types (Font Awsesome), and colors are assigned in the dataframe, icon_df.

>     for _, row in map_df[~map_df.lat.isnull()].iterrows():
>        icon_df_row = icon_df[icon_df.park_set == row.park_set]
>        popup_string = ('<a href="'
>                        + 'https://www.nps.gov/' + row.park_code
>                        + '" target="_blank">'
>                        + row.park_name + '</a>').replace("'", r"\'")
>        park_map = add_map_location(park_map, row.lat, row.long,
>                                    icon_df_row.values[0][2],
>                                    icon_df_row.values[0][1],
>                                    popup_string)

The previous code snippet calls the add_map_location method below.

>    popup_html = folium.Html(popup, script=True)
>    marker = folium.Marker(location = [lat, long],
>                           icon = folium.Icon(color=color,
>                                              prefix='fa',
>                                              icon=icon),
>                           popup = folium.Popup(popup_html)
>                           ).add_to(map)

### Using the Scripts
Instructions to run the scripts are found in the readme in the GitHub repository found [here](https://github.com/goodmorningdata/nps){:target="_blank"}.

### Static Map
![Clickable map image]({{ site.baseurl }}/assets/20190320_nps_map.png){:target="_blank"}

### Interactive Map
[Click here for interactive map.](https://goodmorningdata.github.io/assets/nps_parks_map.html){:target="_blank"}
