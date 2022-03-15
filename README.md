# San Francisco Real Estate Dashboard

![San Francisco Park Reading](Images/san-francisco-park-reading.jpg)

*[San Francisco Park Reading by Juan Salamanca](https://www.pexels.com/photo/park-san-francisco-reading-61109/) | [Free License](https://www.pexels.com/photo-license/)*

## Goal

The goal of this dashboard is to provide charts, maps, and interactive visualizations that help customers explore the data and determine if they want to invest in rental properties in San Francisco.

Accomplish the following tasks:

1. [Complete a notebook of rental analysis](#Rental-Analysis)

2. [Create a dashboard of interactive visualizations to explore the market data](#Dashboard)

---

## Files

* [sfo_neighborhoods_census_data.csv](Starter_Code/Data/sfo_neighborhoods_census_data.csv)
* [neighborhoods_coordinates.csv](Starter_Code/Data/neighborhoods_coordinates.csv)
* [Rental Analysis Starter Jupyter Notebook](Starter_Code/rental_analysis.ipynb)
* [Dashboard Starter Jupyter Notebook](Starter_Code/dashboard.ipynb)


### Rental Analysis

The first step to building the dashboard is to work out all of the calculations and visualizations in an analysis notebook. Once the code is worked out here, it can be copied over to a dashboard code and used with Panel to create the final layout. See `rental_analysis.ipynb`.

#### Housing Units Per Year

Calculated the number of housing units per year and visualized the results as a bar chart using the Pandas plot function.

Note: By default, the limits auto-scale to the data. However, it is hard to see the difference between the yearly data. Used the min, max, and standard deviation of the data to manually scale the y-limits of the plot.

Default Bar Chart

  ![unscaled-bar.png](Images/unscaled-bar.png)

Bar Chart with y-axis limits adjusted

  ![scaled-bar.png](Images/scaled-bar.png)


#### Average Gross Rent in San Francisco Per Year

Visualized the average gross rent per year to better understand the trends for rental income over time. Visualized the average (mean) gross rent per year and visualized it as a line chart.

1. Calculated the mean `gross` for each year.
2. Visualized the mean `gross` rent per year as a line chart.

  ![gross-rent.png](Images/gross-rent.png)

#### Average Sales Price Per Year

Determined the average sales price per year to better understand the sales price of the rental property over time. For example, a customer will want to know if they should expect an increase or decrease in the property value over time so they can determine how long to hold the rental property. Visualized the average (mean) `sales_price_sqr_foot` and visualized it as a bar chart.

1. Calculated the mean `gross` for each year.
2. Visualized the mean `gross` rent per year as a line chart.

  ![average-sales.png](Images/average-sales.png)

#### Average Prices By Neighborhood

Compared the average prices by neighborhood.

1. Grouped the data by year and by neighborhood and calculated the average (mean) `sales_price_sqr_foot`.
2. Visualized the mean `sales_price_sqr_foot` per year with the neighborhood as a dropdown selector. Used hvplot to obtain the interactive dropdown selector for the neighborhood.

  ![avg-price-neighborhood.png](Images/avg-price-neighborhood.png)

#### Top 10 Most Expensive Neighborhoods

Determined the most expensive neighborhoods. Calculated the mean sale price for each neighborhood and then sorted the values to obtain the Top 10 Most Expensive Neighborhoods on average. Plotted the results as a bar chart.

  ![top-10-expensive-neighborhoods.png](Images/top-10-expensive-neighborhoods.png)

#### Parallel Coordinates and Parallel Categories Analysis

Used plotly express to create parallel coordinates and parallel category visualizations so that investors can interactively filter and explore various factors related to the sales price of the neighborhoods.

Used the DataFrame of Average Values Per Neighborhood (calculated above):

1. Created a Parallel Coordinates Plot

  ![parallel-coordinates.png](Images/parallel-coordinates.png)

2. Created a Parallel Categories Plot

  ![parallel-categories.png](Images/parallel-categories.png)

#### Neighborhood Map

Read-in neighborhood location data and built an interactive map with the average prices per neighborhood. Used a scatter mapbox object from plotly express to create the visualization. Needed a mapbox API key for this.

Create maps visualizations using Plotly Express, create an account at [mapbox](https://www.mapbox.com/) and [create an access token](https://docs.mapbox.com/help/how-mapbox-works/access-tokens/#creating-and-managing-access-tokens).

  ![neighborhood-map.png](Images/neighborhood-map.png)

### Dashboard

Usec the Panel library to build an interactive dashboard for all of the visualizations. 

Created a new `dashboard.ipynb` for the dashboard code. Copied over the code for each visualization and placed into separate functions (1 function per visualization). Made it easier to build and modify the layouts later. Each function returned the plot figure in a format that Panel could use to plot the visualization.

Dashboard:

  ![dashboard-demo.gif](Images/dashboard-demo.gif)
