Maggiore Project

GOAL:

Create a map for trail running with two paths and two elevation graph turning on / off

Step:

X Create map

X Load Mapbox Tiles

X Load track from external GeoJson (stresa.geojson)
  [trouble using QGIS export, I finally did it using ogr2ogr from command line]

X Load start/finish from external GeoJson (pti.geojson)

X Create Elevation profile using Leaflet.Elevation

X Add scale bar

X Add title

X Style track and start/finish
  Define a style and then add it before onEachFeature..
    var mystyle = {...};
      var percorso;
        $.getJSON("data/stresa.geojson", function(json) {
          percorso = L.geoJson(json,
          {
              style: mystyle, onEachFeature: el.addData.bind(el) //working on a better solution
          }
            ).addTo(map);
          });


X Create groups polylines and markers

X Added control layer group

- Groups elevation graph to turn on and off with the tracks and markers

- Transform control layers into toggling mapbox style
