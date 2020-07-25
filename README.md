# NorfolkParksAndRec
Neighborhood Park and Recreation information for Norfolk, Virginia

This map displays the civic leagues (neighborhood names) as well as recreational locations within Norfolk. It is designed to assist Norfolk residents with locating parks and recreation areas within their neighborhoods. 

I started by downloading shapefiles for neighborhood civic leagues to outline specific neighborhoods within Norfolk from Norfolk Open GIS Data Store: https://norfolkgisdata-orf.opendata.arcgis.com/datasets/civic-leagues 

Then, I downloaded parks and recreation shapefiles from City of Norfolk Open GIS Data Site: https://norfolkgisdata-orf.opendata.arcgis.com/datasets/parks-and-recreation

After acquiring the shapefiles, I used ogrinfo -so within MacOS Terminal to query the data in order to determine projection. After querying all data sets and discovering they were all projected in NAD83, I used the command ogr2ogr (output shapefile name) -t_srs "EPSG:4326" (input shapefile name) to convert from NAD83 to WGS84. When all the shapefiles had successfully been converted to WGS84 projection I converted the shapefiles to GeoJSON using the ogr2ogr -f "GeoJSON" (output file name) (input file name) command.

