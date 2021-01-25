# San Francisco Real Estate Dashboard

![San Francisco Park Reading](Images/san-francisco-park-reading.jpg)

*[San Francisco Park Reading by Juan Salamanca](https://www.pexels.com/photo/park-san-francisco-reading-61109/) | [Free License](https://www.pexels.com/photo-license/)*

## Background

Build a prototype Real Estate Investment dashboard. The real estate team wants to trial this initial offering with investment opportunities for the San Francisco market.

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

The first step to building the dashboard is to work out all of the calculations and visualizations in an analysis notebook. Once the code is worked out here, it can be copied over to a dashboard code and used with Panel to create the final layout. Use the `rental_analysis.ipynb` to complete the following:

#### Housing Units Per Year

In this section, you will calculate the number of housing units per year and visualize the results as a bar chart using the Pandas plot function.

Note: By default, the limits auto-scale to the data. However, it is hard to see the difference between the yearly data. Use the min, max, and standard deviation of the data to manually scale the y-limits of the plot.

Default Bar Chart

  ![unscaled-bar.png](Images/unscaled-bar.png)

Bar Chart with y-axis limits adjusted

  ![scaled-bar.png](Images/scaled-bar.png)


#### Average Gross Rent in San Francisco Per Year

Visualize the average gross rent per year to better understand the trends for rental income over time. Visualize the average (mean) gross rent per year and visualize it as a line chart.

1. Calculate the mean `gross` for each year.
2. Visualize the mean gross rent per year as a line chart.

  ![gross-rent.png](Images/gross-rent.png)

#### Average Sales Price Per Year

Determine the average sales price per year to better understand the sales price of the rental property over time. For example, a customer will want to know if they should expect an increase or decrease in the property value over time so they can determine how long to hold the rental property. You will visualize the average (mean) `sales_price_sqr_foot` and visualize it as a bar chart.

1. Calculate the mean `gross` for each year.
2. Visualize the mean gross rent per year as a line chart.

  ![average-sales.png](Images/average-sales.png)

#### Average Prices By Neighborhood

Compare the average prices by neighborhood.

1. Group the data by year and by neighborhood and calculate the average (mean) `sales_price_sqr_foot`.
2. Visualize the mean `sales_price_sqr_foot` per year with the neighborhood as a dropdown selector. Hint: Use hvplot to obtain the interactive dropdown selector for the neighborhood.

  ![avg-price-neighborhood.png](Images/avg-price-neighborhood.png)

#### Top 10 Most Expensive Neighborhoods

Figure out which neighborhoods are the most expensive. You will need to calculate the mean sale price for each neighborhood and then sort the values to obtain the top 10 most expensive neighborhoods on average. Plot the results as a bar chart.

  ![top-10-expensive-neighborhoods.png](Images/top-10-expensive-neighborhoods.png)

#### Parallel Coordinates and Parallel Categories Analysis

Use plotly express to create parallel coordinates and parallel categories visualizations so that investors can interactively filter and explore various factors related to the sales price of the neighborhoods.

Using the DataFrame of Average values per neighborhood (calculated above), create the following:

1. Create a Parallel Coordinates Plot

  ![parallel-coordinates.png](Images/parallel-coordinates.png)

2. Create a Parallel Categories Plot

  ![parallel-categories.png](Images/parallel-categories.png)

#### Neighborhood Map

Read in neighborhood location data and build an interactive map with the average prices per neighborhood. Use a scatter mapbox object from plotly express to create the visualization. Need a mapbox API key for this.

Remember that in order to create maps visualizations using Plotly Express, you will need to create an account at [mapbox](https://www.mapbox.com/) and [create an access token](https://docs.mapbox.com/help/how-mapbox-works/access-tokens/#creating-and-managing-access-tokens).

  ![neighborhood-map.png](Images/neighborhood-map.png)

### Dashboard

Use the Panel library to build an interactive dashboard for all of the visualizations. 

Create a new `dashboard.ipynb` for your dashboard code. Copy over the code for each visualization and place this into separate functions (1 function per visualization). This will make it easier to build and modify the layout later. Each function should return the plot figure in a format that Panel can use to plot the visualization.

Dashboard:

  ![dashboard-demo.gif](Images/dashboard-demo.gif)
