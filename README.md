# nodejs-beginner

The objective of this repo is to learn how to make API calls using `NodeJS`.  
The API is the `Met Office` `data point` API which provides access via an
`Open Government Licence` to approximately 15 meterological and oceanographic
data sets.

## API calls
 * My API key is `2fb4da01-1217-4b07-bcac-b9136697856c`
 * I'll be using the `marine observation data` product which uses the resource category field = `wxmarineobs`
 * full documentation on the API is available [here](http://www.metoffice.gov.uk/datapoint/product/marine-observations/detailed-documentation)
 * a full list of all `locationIDs` is [here](http://www.metoffice.gov.uk/datapoint/support/documentation/marineobs-sites)

#### requesting `timestamp` capabilities:
* syntax
`http://datapoint.metoffice.gov.uk/public/data/val/wxmarineobs/all/json/capabilities?res=hourly&key=<API key>`
* example
http://datapoint.metoffice.gov.uk/public/data/val/wxmarineobs/all/json/capabilities?res=hourly&key=2fb4da01-1217-4b07-bcac-b9136697856c

#### requesting a `single` location
* syntax `http://datapoint.metoffice.gov.uk/public/data/val/wxmarineobs/all/json/{locationID}?res=hourly&key=<API key>`
* example for `locationID=162103`
http://datapoint.metoffice.gov.uk/public/data/val/wxmarineobs/all/json/162103?res=hourly&key=2fb4da01-1217-4b07-bcac-b9136697856c

#### requesting all `ship` locations
* syntax
`http://datapoint.metoffice.gov.uk/public/data/val/wxmarineobs/all/json/all?res=hourly&type=ShipSynops&key=<API key>`
* example
http://datapoint.metoffice.gov.uk/public/data/val/wxmarineobs/all/json/all?res=hourly&type=ShipSynops&key=2fb4da01-1217-4b07-bcac-b9136697856c

#### requesting all `buoy` locations
* syntax
`http://datapoint.metoffice.gov.uk/public/data/val/wxmarineobs/all/json/all?res=hourly&type=BuoyObs&key=<API key>`
* example
http://datapoint.metoffice.gov.uk/public/data/val/wxmarineobs/all/json/all?res=hourly&type=BuoyObs&key=2fb4da01-1217-4b07-bcac-b9136697856c
