# Weather API Visualizations
This project takes API calls from OpenWeatherMap.org to plot various weather measurements versus latitude.

## Dataset Generation
* Random Latitudes and Longitude pairs are generated and run through citipy.nearest_city in order to generate a close-to-random list of global cities.
* API calls for those city names are made to OpenWeatherMap.org to retrieve the following for each city:
    * Latitude and Longitude
    * County
    * Max daily temp (converted to Fahrenheit from Kelvin)
    * Humidity
    * Cloud cover
    * Wind Speed
* These calls are made inside a try/except loop to exclude missing/invalid API returns.
* A running printout from these calls is make to show progress through the list of cities and whether the API calls were successful.
* Data are stored in a DataFrame.

## Plotting
* Scatter plots are made for each of max temp, humidity, cloud cover, and wind speed versus latitude for all cities.
* Cities are split into Northern and Southern Hemisphere latitudes and scatter plots for the prior measurements are made, this is done in order to analyze trends by distance from the equator.
* Linear regressions with R2 values are calculated and plotted on each of these scatter plots.

## Output storage
All outputs are stored in a folder "output_data" in the repository
* Full dataset of randomly generated cities with OpenWeatherMap API call data, "cities.csv"
* Each generated scatterplot stored as a .png, with a title including date and time of inital API call.