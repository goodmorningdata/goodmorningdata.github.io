---
layout: post
title: How big are the national parks?
date: 15-05-2019
tags: national-park-service
---

The map below, shows the locations of all 61 national parks. The map was created using park location data pulled from the NPS API and using the Python library, [Folium](https://python-visualization.github.io/folium/){:target="_blank"}, which uses the Leaflet.js library for map visualizations.

A clickable version of the map that gives you the park name and a link to its website is found [here](https://goodmorningdata.github.io/assets/20190501_loc_map_national_parks.html){:target="_blank"}.

![Map image]({{ site.baseurl }}/assets/20190501_loc_map_national_parks.png){:target="_blank"}

National parks are found in 27 of the lower 48 states, in Alaska and Hawaii, and in the U.S. territories of American Samoa, and the U.S. Virgin Islands. California is the winner with 9 national parks and Alaska in a close second with 8.

![Bar chart image]({{ site.baseurl }}/assets/20190501_loc_parks_per_state_national_parks.png)

Another way to look at national parks per state is a [choropleth map](https://en.wikipedia.org/wiki/Choropleth_map){:target="_blank"}. The winners are in blue.

![Choropleth map]({{ site.baseurl }}/assets/20190501_choropleth_map_national_parks.png)

### Data Sources
The list of 419 official park units (as of 5/1/2019) broken out by designation comes from the [National Park System](https://www.nps.gov/aboutus/national-park-system.htm){:target="_blank"} page at nps.gov. Park location data, including latitude, longitude, and state(s) are from the National Park Service [API](https://www.nps.gov/subjects/digital/nps-data-api.htm){:target="_blank"}.

### Creating the Map
The clickable map was created using Folium.

```python
center_lower_48 = [39.833333, -98.583333]
map = folium.Map(location = center_lower_48,
                 zoom_start = 4,
                 control_scale = True,
                 tiles = 'Stamen Terrain')
```

Location markers for each national park were added to the map with a clickable popup link to the NPS page for the park. Icon types (Font Awesome), and colors are assigned in the dataframe, df_icon.

```python
for _, row in (df[~df.lat.isnull()]
    .sort_values(by='designation', ascending=False).iterrows()):

    # Create popup with link to park website.
    if ~(row.park_code[:3] == 'xxx'):
        popup_string = ('<a href="'
                       + 'https://www.nps.gov/' + row.park_code
                       + '" target="_blank">'
                       + row.park_name + '</a>').replace("'", r"\'")
    else:
        popup_string = row.park_name
    popup_html = folium.Html(popup_string, script=True)

    # Assign color and graphic to icon.
    df_icon_row = df_icon[df_icon.designation == row.designation]
    map_icon = folium.Icon(color=df_icon_row.values[0][1],
                           prefix='fa',
                           icon=df_icon_row.values[0][2])

    # Add marker to map.
    marker = folium.Marker(location = [row.lat, row.long],
                           popup = folium.Popup(popup_html),
                           icon = map_icon).add_to(map)
```

### Using the Scripts
Instructions to run the scripts are found in the readme in the GitHub repository found [here](https://github.com/goodmorningdata/nps){:target="_blank"}.

---
