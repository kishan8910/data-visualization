### Visualization 1
**Aim (aim):** This visualization aims to find the object's geographical position by mapping its latitude and longitude along with the version. From that particular location of the object, infer what kind of feature type is existing. For eg: temple, settlement etc

**Visual Design Type (vistype):** Scatter Plot

**Image:** 
* * *
![Source Code](scatter_plot_viz1_code.png)
![Source Code](scatter_plot_viz1_plot.png)

**Visual Mappings (vismapping):** The unique concept that generated from an intricate amount of data is to visualize the objects for their different versions along with geographical locations with the help of latitude and longitude. Hence the visualization is done by plotting the latitude on X axis and longitude on Y axis. That would give us the position and scatter plot is used for this concept to make a visualization. The next objective was to plot versions of each entry and we are able to make the color factor to define the versions. More instensity relates to latest version. Less intensity refers to older version. An interactive element is made by giving a tooltip for every points to display the details including feature types and timeperiod.

**Data Preparation (dataprep):** Data is taken from pleiades-places-latest.csv. This file has fields for latitude(reprLat) and longitude(reprLong) to plot the location and a field for storing version(currentVersion). For identifying feature type of that location, data was taken from featureTypes field and timePeriods field is used for plotting time period into the tooltip.

**Improvements (improvements):** Improvements could be done by plotting the geo cordinates to actual world maps and even the time periods and feature types could be specifically given. For the feature types it would be great to give a unique small icon for every points. For eg: if the feature type is a temple then a small icon of temple could be shown in the plot.

