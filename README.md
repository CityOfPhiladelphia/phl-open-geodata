# PHL Open Geodata

A collection of geospatial data sets from the City of Philadelphia.

## Data Source

Pennsylvania Geospatial Data Clearinghouse - http://www.pasda.psu.edu/.

## How to help out

Convert geospatial data in Shapefiles to alternate formats for easier use and enhanced sharebility.

1. Navigate to [PASDA](http://www.pasda.psu.edu/).
2. Find a data set that gets you excited and download it.
3. Fork this repository.
4. Create a new directory for your data set.
5. Convert the downlaoded Shapefile to GeoJSON, CSV or KML.
6. Submit a pull request.

## Tools

There are lots of tools that can be used to convert Shaepfiles to alternate formats. Check out CartoDB, [ogr2ogr](http://www.gdal.org/ogr2ogr.html), [File Bakery](http://filebakery.com/) or one of the many other tools available that supports file conversion. Pick your favorite.

## Notes

* GeoJSON, JSON and KMZ files are in [WGS84](http://spatialreference.org/ref/epsg/4326/).
* Shapefiles are in [NAD83 Pennsylvania South](http://spatialreference.org/ref/epsg/2272/).
* Farmers' Market point CSV file has both lat/longs and x/y in the above spatial references.
* The JSON file has geometries represented as GeoJSON, as opposed to [WKT](http://en.wikipedia.org/wiki/Well-known_text).