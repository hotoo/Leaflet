
# Example

----

<link type="text/css" rel="stylesheet" href="../leaflet.css" />

<div id="map-demo" style="height:300px"></div>

````js
seajs.use('leaflet', function(L){
  L.Icon.Default.imagePath = "../images";

  var map = L.map('map-demo').setView([51.505, -0.09], 13);

  L.tileLayer('http://{s}.tile.osm.org/{z}/{x}/{y}.png', {
    attribution: '&copy; <a href="http://osm.org/copyright">OpenStreetMap</a> contributors'
  }).addTo(map);

  var marker = L.marker([51.5, -0.09]).addTo(map);

  var circle = L.circle([51.508, -0.11], 500, {
    color: 'red',
    fillColor: '#f03',
    fillOpacity: 0.5
  }).addTo(map);

  var polygon = L.polygon([
    [51.509, -0.08],
    [51.503, -0.06],
    [51.51, -0.047]
  ]).addTo(map);

  marker.bindPopup("<b>Hello world!</b><br>I am a popup.").openPopup();
  circle.bindPopup("I am a circle.");
  polygon.bindPopup("I am a polygon.");

})
````
