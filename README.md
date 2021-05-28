# GeoParsing *The Deluge* by Henryk Sienkiewicz
***
## Introduction
This assignment was my first introduction to GeoParsing. The tutorial provided all the code necessary to get started and provided a text file of Mark Twain's *The Innocence Abroad*. For this coding challenge, *The Deluge* text file is included in this repo and was download from [Project Gutenberg](https://www.gutenberg.org/). *The Deluge* 
(Potop, 1886) is one of Henryk Sienkiwicz's most famous books. The historical novel chronicals Poland's wars with Sweden and Russia. Published in 1886, the novel is part of what Poles call "The Trilogy", and was preceded by *With Fire and Sword* (Ogniem i mieczem, 1884) and followed by *Fire in the Steppe* (Pan Wołodyjowski, 1888). 

***
## The GeoPasrsing Code
The code for this assignment begins with the importation of a number of libraries that are used to GeoParse the text. An error is generated while tring to import the "urllib", however, this does not effect the final results. Next, the URL of the text file is stored as the variable "URL" and passed into the GeoText function. This is used to create a list of place names stored as the variable "Cities". A new empty list is created and stored as the variable "Lat_lon". A for loop iterates through the "Cities" variable. Using OpenStreetMap's "Nominatim" to identify latitude and longitude of place names, the loop appends the coordinates to the location name in the Lat_lon list. A 2 second timeout was used to idenitfy only locations that can easily be linked to its geolocation. The list of place names and coordinates is converted to a pandas dataframe and collumn names are assigned for "Cities" and "Coordinates". A list of Shapely point objects are created for all the coordinates in the dataframe and stored as the variable "geometry". A new  geopandas dataframe is created that combine the original dataframe with a new column for the "geometry" information. 

## Mapping the results
The next sections of code displays the results of GeoParsing Henryk Sienkiewicz's *The Deluge* as maps and charts. A shapefile downloaded from [ArcGIS Online](https://hub.arcgis.com/datasets/a21fdb46d23e4ef896f31475217cbb08_1) (included in data folder of this repo) is imported into Google Colab and is plotted alongside the point locations in the geodataframe. 
[]()
By applying the transparancy parameters in the plot object, a "color ramp" is esentially being created, with darker colors signifying a higher frequency of overlapping points. To display the frequency of the GeoParsing results more accuately, a frequency plot is created. Finally, the geopandas dataframe is converted to geojson and displayed as a folium map.

