# City Buildings

### Summary

Inventory of fixed assets owned or leased by the City of Philadelphia including buildings, structures, piers, and properties (not including surplus properties) in shapefile (zipped and unzipped), KMZ, CSV and GeoJSON formats.  Also known as the Master Facilities database.  

Also included facilities and fixed assets that have received Capital Program funding (also known as Capital Facilities) including:  administrative or multi-purpose buildings, athletic fields, airfields and airport buildings, bridges, ball courts, fire stations, health centers, libraries, museums, plazas, parks and park buildings, playground equipment, piers, police stations, pools, recreation centers and buildings, radio towers, water and waste water facilities, etc.  This database is UNDER DEVELOPMENT and attributes and features are subject to change. 
PCPC does not warranty the accuracy of the information.  

Attributes Updated: 4/1/14
Features Updated: 4/1/14  
Metadata Updated: 4/1/14  
Update Frequency: As Needed  

### Abstract

The location of City of Philadelphia owned, leased or managed buildings, structures, properties and other fixed assets.  The database includes point feature/records for properties or buildings for which the City has expended Capital Program funds.  The primary uses for this feature class:  

1) Location of City facilities, operations, and fixed assets by status, city ownership or lease, and occupant.  

2) Identification of sites that may have received Capital Program funding (see Site_Code field).  

### Data Development

The database was compiled from 2011 through 2013 from multiple sources including the Budget Office’s financial management database, departmental inventories or GIS data on facilities locations and from feedback from multiple City departments to the Mayor’s Task Force on City-owned Buildings (Spring 2012). Data collection coordinated and maintained by PCPC.    

Point features were initially geocoded from tabular databases and manually adjusted using 2010-2012 aerial photography and 2011-2012 Pictometry.  Reference layers included PWD parcels, street centerlines, and building footprints.   

Developed in ArcGIS Desktop 10 in Esri geodatabase format.  Select fields utilize geodatabase domains to populate cells with full text descriptions.  Use of the layer outside of the Esri geodatabase will result in the appearance of one to three digit codes instead of full text descriptions in the following fields:  Asset_Group1, Asset_Group2, Asset_Type, Asset_Subtype1, Asset_Subtype2, CityUse_Desc, Serving_Type, and Status.  

Each record is attributed with a sequential, numeric identification number (Asset_ID).    

Every building has only one Asset_ID, except in cases where distinct operations required separate tracking and identification. These instances include Police, Fire, Judiciary/District Attorney, garages and Street’s highway facilities, and Older Adult Centers.  Where facilities share a building, each facility is assigned its own Asset_ID and Asset_Subtype values. The shared building relationship is cross-referenced in the SharedBldg_AssetID and ShareBldg_Note fields.  Due to this condition, a summary of the Asset_Type = “B1” values requires the removal of duplicate records using the SharedBldg_AssetID field.

### Attribute Fields

**Exact attribute names may vary depending on data format**

This layer is currently under development. Verification of some attribute fields is underway. Accuracy of some field values is limited at this time.  A data dictionary (.pdf) is available from PCPC (see contact information below) or from GSG’s internal web blog for City departments.

`STATUS` The status of an assets as:  

* A - Active or currently in use
* I - Inactive or closed or shuttered, but not marketed as surplus
* C – Capital Investment (for PCPC analysis purposes)  
Geodatabase coded domain  

`ASSET_ID` Unique ID assigned to an asset by PCPC  
`ASSET_NAME` Name of building, structure, land/site or equipment  
`ASSET_ADDR` Asset or Site address.  
`SITE_NAME` The Asset_Name unless facility or site comprise more than one building, structure, equipment, etc.  All assets are assigned the facility name (e.g., Police Academy has multiple buildings with individual asset names)  
`SITE_CODE` The Capital Program identification number to track expenditures and programming. Also known as the UserCode or Capital Code.  
`SHAREBLDG_` Tracks AssetIDs where two operations share the same buildings. Mostly limited reserved to cases where individual departmental operations must be accounted as separate facilities regardless duplication in the Asset_Type = “B1” Building counts.  
`SHAREBLDG1` Shared building information.  
`ASSET_GROU` Used for PCPC for tracking asset categorizations in the database.  
`ASSET_TYPE` Basic categorization of asset as building, land, equipment, etc. Geodatabase coded domain.  

#### Attribute Lookup

| CODE | Type  
| :--: | :---:
| B1 | Building
| B2 | Equipment
| B3 | Land
| B4 | Structure
| B5 | Parking Lot
| B6 | Pier
| B8 | Other

`ASSET_SUBT` Specified categorization of an asset or operational use.  Primary way to select and identify an asset, building or facility. (See metadata/asset_subtypes for Attribute Lookups)  

`ASSET_SU_1` and `ASSET_SU_2` Secondary use or qualifying characteristic of `ASSET_SUBT` (See metadata/asset_secondary_subtypes for Attribute Lookups)  
`CITYOWNED` City-owned building Yes or No  
`CITYUSE_DE` Description of city ownership, city use or lease status with private entities or other public agencies.  City owned, but leased for use by other entities identified separately.  
Owned - City Owned  
Lessor - City Owned, Lessor  
Lessee - Other Ownership, City Lessee  
Other - Other Ownership, Capital investment  
UA - Other Ownership, Use  Agreement  

`OCCUPANT` Primary city department occupying the site or building.  
`BLDG_SQFT` Building square footage  
`BLDG_FL` Number of floors  
`BLDG_YR` Year building was constructed  
`SITE_ACRES` Acreage based on PWD-based parcel boundary.  In cases of sites with multiple buildings or assets, acreage is assigned only to one record representing the entire site (e.g. Recreation Centers)  `SERVING_TY` Philadelphia2035 designation as municipal-support (M) or community-serving (C ).  
`PCPC_DIST` City Planning Commission’s  Philadelphia2035 planning district name  
`COUNCIL_DI` Council Districts legislatively in effect in 2016, based on 2010 Census redistricting.  
`BLDG_AGE` Age of building from 2013  
`COUNCIL__1` Council Districts effective as of 2000-2016  
`URL` Web site address to facility, if available.  
`DATE_ISO` Date in ISO format

### Coordinate System and Spatial Reference
WGS84 decimal degrees, [EPSG:4326](http://spatialreference.org/ref/epsg/4326)

### Other Information
1. Sites vs. individual buildings or assets:
    * To account for individual buildings that exist at a particular site or campus (e.g., Police Academy) each individual asset is given its own Asset_ID and Asset_SubType1 values.  All buildings and assets associated with a site are found by sorting on or querying the Site_Name field.    
    * Individual recreation centers can be tracked by querying Asset_SubType1 = “C50” or “Recreation Center.”  All buildings and amenities at a center will be found under individual Asset_SubType1 codes such as “C42” “Playground Equipment”.  This situation applies to all sites with multiple assets.  

2. Counting Assets:
    * The Asset_Type field is a broad categorization of assets: buildings, equipment, structures, piers, etc.  This field may be used to get an approximate count of buildings.  As noted above (#1) the number of records in this feature class does not constitute a total count of buildings. There are cases where distinct operations within a single building are required to have separate Asset_IDs.  Always check the SharedBldg_AssetID to remove duplicates for an accurate count of buildings.  

3. Leases
    * Use City_Buildings_Lease subtable to obtain available data on the nature of sites leased by the City and leased square footage. Join on Asset_ID fields.  

4. Capital Investments
    * Use the City_Buildings_CapitalBudget subtable to obtain available data on six year Capital Program Expenditures. Join on Asset_ID fields.   EXP_:  aggregated expenditures by fiscal year range.  

### Credits 
Mark Wheeler, GISP   
City Planner, Strategic Planning and Policy Division   
Philadelphia City Planning Commission   
One Parkway Building   
1515 Arch Street, 13th Floor   
Philadelphia, PA 19102   
e-mail: mark.wheeler@phila.gov   

### Use Limitations
Database is under development and not all data points have been verified for location and attribute accuracy.  The City of Philadelphia reserves all rights in the GIS database and any data contained therein, and the end user’s use of the data does not constitute a transfer of, nor does the end user receive, any title or interest in the database or any other City data. The City of Philadelphia makes no representation about the accuracy of any specific information in this GIS data and is provided “as is” and without Warranty of any kind.  The user of this data will assume complete responsibility for any and all occurrences resulting from its use or display and will hold the City of Philadelphia harmless from any and all claims, demands, liabilities, obligations, damages, suits, judgments or settlements, including reasonable costs and attorneys' fees, that arise from use of this data.  

Critical infrastructure omitted from public version.








