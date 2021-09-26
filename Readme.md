Using Google Place API with a database and Visualize Data on GOogle Map

In this project, I am going to use Google geocoding API to clean up some user-entered geographic location and place data on Google Map.

Install SQLite Browser to view and modify databases from 
http://sqlitebrowser.org/

first phase take input data in file (where.data) and read it one line at a time, and retrieve the geocoded response and store it in database 
(geodata.sqlite)
Before using geocoding api, check if already have data
can restart any time removing file (geodata.sqlite)

Run (geoload.py)
- this will read input lines in where.data and for each line check if already in database and 
  if not in db, call geocoding API to retieve data and store in db.

With API key, instructions at 
https://developers.google.com/maps/documentation/geocoding/intro
and put key in the code. 

When some data loaded in (geodata.sqlite), can visualize data using (geodump.py).This program read the database and write tile file 
(where.js) with the location, latitude and longitude in the form of executable javascript code.

(where.html) consists of HTML and javascript to visualize a Google Map. 
It reads most recent data in where.js to get data to be visualized. 

Format of where.js file:
myData = [
[42.3396998,-71.08975, 'Northeastern University, 360 Huntington Avenue, Boston, MA 02115, USA'],
[40.6963857,-89.6160811, 'Bradley University, 1501 West Bradley Avenue, Peoria, IL 61625, USA'],
[32.7775,35.0216667, 'Technion, Viazman 87, Kesalsaba, 32000, Israel'],
   ...
];

This is javascript list of lists. 

open where.html in a browser to see locations. Type > open where.html in terminal. 