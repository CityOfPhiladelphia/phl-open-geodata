# Bicycle Thefts

### Summary

Reported bicycle thefts to the Philadelphia Police Department from the 2010-01-01 to 2013-09-16 in shapefile (zipped and unzipped), KMZ, CSV and GeoJSON formats.

Additional bicycle theft data from 9/15/2014 to 2/8/2015 is available for export at: [http://phl.maps.arcgis.com/home/item.html?id=15feb954cd6f4b59ad5ef086a1d4f38f](http://phl.maps.arcgis.com/home/item.html?id=15feb954cd6f4b59ad5ef086a1d4f38f)

### Data Development
Data comes directly from the Police Departments mainframe INCT system. The INCT system is fed by field incident reports and Computer Aided Dispatch system.

### Attribute Fields

`DC_KEY` The unique identifier of the crime that consists of Year + District + Unique  
`DC_NUM` The unique crime identifier   
`UCR` The Uniform Crime Reports code.

#### Attribute Lookup

| UCR | Explanation
| :-: | :---------:
| 615 | value of $200 or over
| 625 | value of $50-199.99
| 635 | value of under $50

`DC_DIST` A two character field that identifies the district boundary  
`THEFT_DATE` The date of the theft ([ISO 8601 format](http://en.wikipedia.org/wiki/ISO_8601))    
`THEFT_YEAR` The year of the theft  
`THEFT_HOUR` The hour of the theft  
`STOLEN_VAL` The value in dollars of the bicycle stolen  
`LAT` Latitude of crime location  
`LNG` Longitude of crime location  
`LOCATION_B` The location of crime generalized by street block

### Coordinate System and Spatial Reference
WGS84 decimal degrees, [EPSG:4326](http://spatialreference.org/ref/epsg/4326)

### Credits 
Philadelphia Police Department, Mapping & Analysis Unit  
Police Administration Building  
750 Race Street, Room 204  
Philadelphia, PA 19106  
publicsafetygis@phila.gov

### Use Limitations
The City of Philadelphia makes no representation about the accuracy of any specific information, including the standardization, precision, or formalization of crime occurrence locations, in this GIS data and is provided “as is” and without Warranty of any kind.  The user of this data will assume complete responsibility for any and all occurrences resulting from its use or display and will hold the City of Philadelphia harmless from any and all claims, demands, liabilities, obligations, damages, suits, judgments or settlements, including reasonable costs and attorneys' fees that arise from use of this data.  

The City of Philadelphia and the Philadelphia Police Department make no warranty or representation, express or implied, with respect to the quality, content, accuracy, completeness, currency, freedom from computer virus, or non-infringement of proprietary rights, of any of the design, information, text, graphics, images, pages, interfaces, links, software, or other materials and items contained in or displayed on this site. All such items and materials are provided on an "as is" basis and you are fully and solely responsible for your use of them and for any results or consequences of your use. These materials have been compiled from a variety of sources and are subject to change without notice from the City or the Police Department. This map or downloaded data may not reflect official crime index totals as reported to the FBI's Uniform Crime Reporting program. The listed crimes are subject to change for a variety of reasons, including late reporting, reclassification of some offenses, and discovery that some offenses were unfounded. Commercial use is prohibited without the prior written permission of the City.    

In order to protect privacy, no personal or identifying information is included in the map. Addresses are rounded to the hundred block level and should be considered approximate; any attempts to derive a specific address are strictly prohibited. To ensure privacy of the victims involved some sensitive crime offenses will not be mapped or available for download.   

In no event shall the City of Philadelphia or the Philadelphia Police Department, or their agencies, officers, employees, agents, or representatives, be liable for any and all damages, including but not limited to direct, indirect, special, punitive, incidental, exemplary or consequential damages, arising from accessing, downloading data, or using the site, or otherwise arising from the site or from anything contained in or displayed on the site. Nothing contained in or displayed on this site constitutes or is intended to constitute legal advice by the City of Philadelphia or the Philadelphia Police Department or any of their agencies, officers, employees, agents or representatives.





