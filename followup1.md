### Visualization 2
**Aim (aim):** From this visualization the aim is to find out how precise the location was mapped in accordance with its geocontext location variables such as latitude and longitude with minimum and maximum date of objects to compare the location precisions with age. From this visualization we can see most of the minimum date is zero. The comparison of latitude and longitude with maximum date shows that precise locations are scattered more than rough and related locations. 

**Visual Design Type (vistype):** Scatter Matrix

**Image:** 
- - -
![Visualization 1](scatter_plot_viz2_plot.png)

Source Code
```python
# importing the necessary libraries altair and pandas for data visualization and manipulation
import altair as alt
import pandas as pd
from vega_datasets import data
alt.data_transformers.disable_max_rows()

# data = pd.read_csv('cw/csvdata/pleiades-places-latest.csv')
places_data_url = 'https://raw.githubusercontent.com/SwanseaU-TTW/csc337_coursework1/master/pleiades-places-latest.csv'
places_data = pd.read_csv(places_data_url)

tp_arr = places_data['timePeriods'].unique()

alt.Chart(places_data).mark_circle().encode(
    alt.X(alt.repeat("column"), type='quantitative'),
    alt.Y(alt.repeat("row"), type='quantitative'),
    color='locationPrecision'
).properties(
    width=150,
    height=150
).repeat(
    row=['reprLat','reprLong'],
    column=['minDate','maxDate']
).interactive()
```

**Visual Mappings (vismapping):** The idea is to create a plot to compare multiple data fields to evaluate the location precision with minimum and maximum date. Thought process infered to make a scatter matrix to display various relationhip such as minimum date vs latitude, minimum date vs longitude, maximum date vs latitude and maximum date vs longitude. Along with this comparison, the location precision field is represented by color. This helps users to identify the location is whether precised or rough or related. The user can zoom in or zoom out each plot in the matrix. This is achieved by incorporating interactive method to chart. Altair's mark_circle method is used for creating the scatter plots and repeat method is used for creating matrix with tow and column.

**Data Preparation (dataprep):** For this visualization, the data preparation is pretty straight forward. We could get geocontext data from fields reprLat and reprLong. Other fields used are minDate, maxDate and locationPrecision. The data is taken from pleiades-places-latest.csv.

**Improvements (improvements):** Couple of improvements could be done is to make the plot more interactive by giving tooltips to each point or showing details of a particular data by clicking on itself showing different chart side by side. Including couple of data fields to row or column would make more comparisons.

