# nodejs-beginner

The objective of this `how-to` is to learn how to make `API` calls using `NodeJS`.

An `Application Programmable Interface` or `API` allows a programmer to interact with a `web service`. An example `web-service` could be a public-facing database.  Another example is where software vendors write `APIs` for programmers to interact with desktop applications to automate tasks.

The `API` that I'll be using is the UK `Met Office` `data point` web service which exposes hourly updated meteorological and oceanographic observational data for ~15 locations around on the north west European Atlantic margin.

As an overview, thsi `how-to` will cover:
 * making specific `HTTP requests` that request specific data, in specific formats, which comply with the `API documentation`.
 * In response to the `HTTP resquest`, the API with provide an `HTTP response` in `JSON` format. The `JavaScript Object Notation` or `JSON` data format is widely used on the internet since it is structured and in plain, readable `ASCII` text.
 * I'll automate `API calls` to download the data and `parse` to a data store.
 * Then I'll manipulate/visualise the data, applying filters etc..

#### Resources
* My API key is `2fb4da01-1217-4b07-bcac-b9136697856c`
* I'll be using the `marine observation data` product which uses the resource category field = `wxmarineobs`
* full documentation on the API is available [here](http://www.metoffice.gov.uk/datapoint/product/marine-observations/detailed-documentation)
* a full list of all `locationIDs` is [here](http://www.metoffice.gov.uk/datapoint/support/documentation/marineobs-sites)
* I'll follow [this blog](http://rapiddg.com/blog/calling-rest-api-nodejs-script) on writing `NodeJS` code to make the `HTTP requests` and dealing with the `HTTP responses`

## 1.  HTTP Requests

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

## 2. HTTP Response
