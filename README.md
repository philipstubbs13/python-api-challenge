# Python API Challenge

Data analysis of world weather data to better understand and explain what the weather is like close to the equator. Used Python, Matplotlib, Citipy, the OpenWeatherMapAPI, the Google Places API, and other technologies to help create a representative model of weather across world cities.

* [Background](#background)
* [Observations and Insights](#insights)
* [Jupyter Notebook](#nb)
* [Images](#images)
* [Technologies Used](#technologies)

## <a name="background"></a>Background

For this project, I am trying to answer the following fundamental question: What's the weather like as we approach the equator? We already knows it gets hotter, but the goal is to analyze weather data to explain why it gets hotter.

There are two parts to this project. The different folders inside this repository correspond to the two parts.

### WeatherPy

For the first part of this project (WeatherPy), I created a Python script to visualize the weather of 500+ cities across the world of varying distances from the equator. Using the numpy package, I generated a random set of at least 500 latitude and longitude coordinates and used a package called Citipy to identify the nearest city for each latitude and longitude pair. I then made API calls to the OpenWeatherMap API to get weather data for each of the cities. After the API calls were complete, I saved the retrieved data to a csv file, which can be found [here](./WeatherPy/output_data).

Using the data I received from the OpenWeatherMap API, I built a series of scatter plots to visualize the following relationships:

* Temperature (F) vs. Latitude
* Humidity (%) vs. Latitude
* Cloudiness (%) vs. Latitude
* Wind Speed (mph) vs. Latitude

After each plot, you will find a mini summary about the code and what it is analyzing.

I then conducted a linear regression on each relationship. But, this time, I separated them into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude).

* Northern Hemisphere - Temperature (F) vs. Latitude
* Southern Hemisphere - Temperature (F) vs. Latitude
* Northern Hemisphere - Humidity (%) vs. Latitude
* Southern Hemisphere - Humidity (%) vs. Latitude
* Northern Hemisphere - Cloudiness (%) vs. Latitude
* Southern Hemisphere - Cloudiness (%) vs. Latitude
* Northern Hemisphere - Wind Speed (mph) vs. Latitude
* Southern Hemisphere - Wind Speed (mph) vs. Latitude

After each plot, I included a small explanation of what the linear regression is modeling and of any other interesting relationships I found. Saved PNG images of all the plots I created are available [here](./WeatherPy/Images).

### VacationPy

For the second part of this project (VacationPy), I used the weather data gathered from part one to help plan for future vacations. Specifically, I used jupyter-gmaps and the Google Places API to create a heatmap that displays the humidity for every city from part one. I then narrowed down the list of cities to find the ideal weather conditions, including:

* A max temperature lower than 80 degrees but higher than 70.
* Wind speed less than 10 mph.
* Zero cloudiness.

I ended up dropping any rows that didn't contain all three conditions.

I then used the Google Places API to find the first hotel for each city located within 5000 meters of the coordinates. Finally, I plotted the hotels on top of the humidity heatmap with each pin containing the hotel name, city, and country.

## <a name="insights"></a>Observations and Insights

From part one (WeatherPy), here are some observations and insights that can be made from the data:

* There is a strong, negative correlation between a city's latitude and maximum temperature in the northern hemisphere. That is, as you go farther away from the equator (latitude increases), a city's maximum temperature will generally be lower than cities closer to the equator in the northern hemisphere.
* There is a very weak, positive correlation between cloudiness and a city's latitude for both the northern and southern hemispheres. This is represented in the scatter plots in this notebook for those two factors as the data points being scattered across the graph. As a result, we can conclude that a city's latitude has little to no influence on how cloudy a city is.
* There is a very weak, positive correlation for the northern hemisphere between a city's latitude and wind speed (mph), and there is a very weak, negative correlation for the southern hemisphere for those same two factors. As a result, latitude has a small influence on wind speed but not very much. However, it is important to note that the correlation between these two factors for the southern hemisphere is stronger than the correlation between these two factors for the northern hemisphere.

## <a name="nb"></a>Jupyter Notebook

For this project, I used jupyter notebook to render and display the results of this analysis. There are two notebook files. One for part 1 (WeatherPy) and another for part 2 (VacationPy) of this project.

* [WeatherPy](./WeatherPy/WeatherPy.ipynb)
* [VacationPy](./VacationPy/VacationPy.ipynb)

## <a name="nb"></a>Images

* Static images of the different visualizations I created can be found [here](./WeatherPy/Images).

## <a name="technologies"></a>Technologies Used

* Python
* Pandas library
* Jupyter Notebook
* Matplotlib library
* Citipy
* OpenWeatherMap API
* Google Places API
* jupyter-gmaps
