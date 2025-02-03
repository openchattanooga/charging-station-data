# charging-station-data
> Charging Station Locations in Chattanooga

## download link
https://raw.githubusercontent.com/openchattanooga/charging-station-data/refs/heads/main/files/charging_stations.csv

## overpass query
```
[out:csv(::type,::lat,::lon,access,'addr:housenumber','addr:street',amenity,brand,'brand:wikidata','brand:wikipedia',capacity,'capacity:trailer',fee,name,network,note,'opening_hours',operator,'operator:wikidata','operator:wikipedia','parking:fee',short_name,'socket:chademo','socket:tesla_supercharger','socket:tesla_supercharger:output','socket:type1','socket:type1_cable','socket:type1_cable:current','socket:type1_cable:output','socket:type1_cable:voltage','socket:type1_combo','socket:type1:output',website;true;',')];

// search for the relation named Chattanooga
area
  [place=city]
  ["wikidata"="Q186702"]
  ["name"="Chattanooga"]->.a;


// get all charging stations in the area
(
  nwr["amenity"="charging_station"](area.a);
);

out body center;
```

## note
Data comes from OpenStreetMap and is under the Open Database License (ODbL).
