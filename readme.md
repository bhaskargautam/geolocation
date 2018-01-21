# GEOLOCATION APP
##### Bhaskar Gautam - XXX2324

## Problem Defination
Using geolocalization and gmaps library create a page with HTML, CCS3, Javascript where the user selects on the map two positions and get the route by driving, bicycling and walking (you can use the code example) using different colours (the libraries zepto-min.js, touch.js, gmaps.js must be in the same directory as the geo.html file).

## Base app:
Provided example 4-geo.html is used as base for the project. It implements the drawing driving route between given 2 points.

### Travel mode Color Mapping:

```
//Static mapping of travel mode and representing color.
    var travelModesColorMapping = {
          'driving' : '#FF0000', //RED
          'bicycling': '#00FF00', //Green
          'walking' : '#0000FF' //Blue
          }
```
### Computing Distance and Duration for each mode

```
map.getRoutes({
          origin: [lai, loi],
          destination: [laf, lof],
          travelMode: 'bicycling',
          callback : function(routes) {
              try {
                routes.forEach(function(route){
                    leg = route['legs'][0];
                    key = leg.steps[0].travel_mode.toLowerCase();
                    var distance = leg["distance"]["text"];
                    var duration = leg["duration"]["text"];
                    results[key] = [distance, duration];
                    console.log(key + " Distance " + distance
                      + "Duration " + duration);
```
The results are maintained in a static dictionary. For each callback we update the results dict and re-paint the "Resutls" section.

**The project has been developed as part of assignment for "Distrubuted & Parallel Computing" module for Universitat Autonoma de Barcelona.**
