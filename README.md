# Visualizing Bike Sharing Ridership in Washington DC and New York City

## Introduction
The repo contains script that analyzes data from Capital Bikeshare (DC) in 2011 and Citi Bike (NYC) in 2014 to perform goals as below:<br>
1. Extracting top 10 stations with the most destinations and departures in DC and NYC<br>
2. Visualizing the top stations into hierarchical bars using matplotlib (pylab) package<br>
3. Extracting the most frequent trips in NYC<br>
4. Plotting the top stations in NYC and DC using D3.js

Note: For Citi Bike (NYC), since the data is very huge (more than 1.5 GB if unzipped, it exceeds Github size limitation), you need to download by yourself.
Refer to Readme under the `data` folder for the download links directly from Citi Bike website.

The script is written in iPython Notebook, view here (http://nbviewer.ipython.org/github/girikuncoro/bikeshare/blob/master/script/Preliminary%20Analysis.ipynb) if you don't have it installed in your computer.

## Requirement
0. iPython Notebook (http://ipython.org/notebook.html)<br>
1. numpy<br>
2. matplotlib<br>
3. csv<br>
4. collections<br>

## Example code 
Import our script as library to be able to use our functions that will extract top stations and most frequent trips in NYC and DC. The default parameter is 10 if you don't specify the argument, but you can specify to see the number of stations you like to return.<br>
For example, this function will return top 10 of stations with most destinations and departures in DC:
```
get_top_stations_dc()
```
But this function will return 20:
```
get_top_stations_dc(20)
```
The `get_top_stations_dc()` will not return the station's name, combine it with `get_station_info_dc()` to get the name.<br>
For example:
```
get_station_info_dc('31200')
```
will return the station's name and location:
```
{'lat': '38.9101',
 'long': '-77.0444',
 'name': 'Massachusetts Ave & Dupont Circle NW'}
 ```
Finally, use our `plot_bike()` function to plot horizontal bars based on matplotlib with format `plot_bike(stations, year, title_name)`. The default is also 10 bars, put number for custom number of bars.
```
plot_bike(stations_nyc, '2014', 'Top 10 bike stations with most destinations in NYC')
 ```
or
```
plot_bike(stations_nyc, '2014', 'Top 20 bike stations with most destinations in NYC', 20)
 ```
Below is the list of functions you can use:
```
get_top_stations_dc()
get_top_stations_nyc()
get_top_trips_dc()
get_top_trips_nyc()
get_station_info_dc(station_id)
plot_bike(stations, year, title_name)
```
Author: Giri Kuncoro (gk256@cornell.edu) and Sam Tung (sat83@cornell.edu)
