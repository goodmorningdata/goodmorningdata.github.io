---
layout: post
title: What are the national parks?
date: 01-05-2019
tags: national-park-service
---

The very first national park in the United States was Yellowstone National Park, established by an act of Congress on March 1, 1872, in the then territories of Wyoming and Montana. The establishment of Yellowstone got the ball rolling, and in the ensuing years, Congress set aside additional public lands for the protection of their resources. Resources protected by the National Park Service are extensive and varied and are listed in their official definition...
>Areas added to the National Park System for their natural values are expanses or features of land or water of great scenic and scientific quality and are usually designated as national parks, monuments, preserves, seashores, lakeshores, or riverways. Such areas contain one or more distinctive attributes like forest, grassland, tundra, desert, estuary, or river systems; they may contain windows on the past for a view of geological history; they may contain imposing landforms like mountains, mesas, thermal areas, and caverns; and they may be habitats of abundant or rare wildlife and plantlife.

Tundra! Mesas! All kinds of good stuff. There are a total of 419 units managed by the National Park Service today, but only 61 of those are given the designation, national park, because they contain a variety of the listed resources and the land and/or water area necessary to protect them. The 61 national parks including places like Grand Canyon, Yosemite, Glacier, Redwoods, and Acadia protect the most beautiful and fantastic parts of our amazing country and give us a glimpse of what our country was like before the European settlers arrived. I won't say that the European settlers ruined everything, I am descended from them after all, but they certainly tried to cut down all the trees.

The map below, shows the locations of all 61 national parks. The map was created using park location data pulled from the NPS API and using the Python library, [Folium](https://python-visualization.github.io/folium/){:target="_blank"}, which uses the Leaflet.js library for map visualizations. A clickable version of the map that gives you the park name and a link to its website is found [here](https://goodmorningdata.github.io/assets/20190501_loc_map_national_parks.html){:target="_blank"}.

![Map image]({{ site.baseurl }}/assets/20190501_loc_map_national_parks.png){:target="_blank"}

National parks are found in 27 of the lower 48 states, in Alaska and Hawaii, and in the U.S. territories of American Samoa, and the U.S. Virgin Islands. California is the winner with 9 national parks and Alaska in a close second with 8.

![Bar chart image]({{ site.baseurl }}/assets/20190501_loc_parks_per_state_national_parks.png){:target="_blank"}

Another way to look at national parks per state is a choropleth map. The winners are in blue.

![Choropleth map]({{ site.baseurl }}/assets/20190501_choropleth_map_national_parks.png){:target="_blank"}

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
