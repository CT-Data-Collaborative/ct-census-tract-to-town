# Connecticut 2010 and 2020 Census Tract to Town Crosswalk

This repository contains crosswalks between CT census tracts and towns in Connecticut for 2010 and 2020 Census. **Note that some tracts cross town boundaries, therefore this crosswalk is approximate**. This is usually the case for very small towns.

* The 2010 crosswalk (`2010/tract2town-2010.csv` and `2010/tract2town-2010.xlsx`) contains 833 tracts.
* The 2020 crosswalk (`2020/tract2town-2020.csv` and `2020/tract2town-2020.xlsx`) contains 883 tracts matched to 169 towns; 5 of those census tracts (all coastal) are matched to *County subdivisions not defined*.

> You can learn about the differences between 2010 and 2020 census tract boundaries for Connecticut [in this blog post](https://www.ctdata.org/blog/2020-census-geography-connecticut) using an interactive map and a summary table.

|tract_fips|tract_name|town|county|town_fips
|--|--|--|--|--|
|09003405700|4057|Bristol|Hartford|0900308490
|09003510200|5102|East Hartford|Hartford|0900322630
|09003510400|5104|East Hartford|Hartford|0900322630
|09015901100|9011|Woodstock|Windham|0901588190
|09003510300|5103|East Hartford|Hartford|0900322630


To prevent Excel from transforming FIPS codes to numbers automatically
(which leads to missing leading 0s), do the following:

1. Open Excel, New workbook
1. Go to File > Import > CSV file
1. Choose file, and select "text" as type of tract_fips and town_fips columns


### How it was generated
In QGIS, open census tract boundaries, generate one random point inside each polygon (using `Point on surface` command, not a centroid to account for concave shapes), and perform nearest neighbor spatial join (NNJoin plugin) to assign the "nearest" town.

### Source datasets
* 2020 TIGER/Line Shapefiles: https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.2020.html

### License
Released under MIT license. Feel free to use for any project. We will appreciate if you credited CTData Collaborative, although this is not required.
