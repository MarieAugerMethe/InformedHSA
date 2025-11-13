# InformedHSA

This repository contains the code and data associated with the article: 

Auger-Méthé, M, F Dupont, A Eby, KH Elliott, N Hussey, DA Lyons, M Marcoux, A Patterson,
S Shadloo, and CR Shuert (2025) Including fitness and health proxies can alter our
understanding of habitat selection. Preprint available on bioRxiv.

# Data

All the data is available in the folder `Data`

## Literature review

The literature review information is available in the file `Literature_review.xlsx` 
found in the subfolder `0_Review`. 

The excel file has 3 tabs:

1. Documents: contains the information extracted from the articles. 
Specifically it contains the columns:
    - Authors: full author list
    - Article Title: title
    - Abstract: arcticle abstract
    - TitleExclude: whether or not the article was excluded while reviewing the titles
    - AbstractExlude: whether or not the article was excluded while reviewing the abstracts
    - FullTextExclude: whether or not the article was excluded while reviewing the articles
    - AccountForIndividuals: whether or not the habitat selection analysis account for individual (e.g., via random effect or separate analyses)
    - IncludeCharacteristicsOfFitnessHealth: whether or not  the habitat selection analysis include characteristics of an individual fitness or health
    - FitnessHealthCharacteristic: the fitness or health characteristics included in the habitat selection analysis
    - IncludeCharacteristicsOfFitnessHealthSpecific: More specific info on whether or not the habitat selection analysis included characteristics of an individual fitness or health
    - IncludeOtherCharacteristic: whether or not the habitat analysis include other characteristics of the individuals
    - OtherCharacteristic: the other individual characteristics was included in the habitat selection analysis
    - MethodCharacteristic: information on the method used to include individual characteristics (see keywords)
    - CommentMethodCharacteristic: additional comment on method to include individual characteristics
    - PrimaryFocus: What is the primary focus of the paper? Is it a review, methodological, theory, or empirical  paper?
    - ManagementConservationInference: whether or not conservation or management inference was made based on the results
    - Additional info on inference made: additional information on the statements
    - Species common: common species name
    - Species scientific: Latin species name
    
2. Full questions: contains the relationship between the column short form name and the full question associated with that column.

3. Keywords to use: contains a list of keywords to use from some of the columns (to help consistency).

## Simulations

The simulations do not require data. 
However, as some code sections take hours to run, 
we have saved the results in .csv files. The files are:
 - `sim.rsf.sc1_20251112.csv`
 - `sim.rsf.sc2_20251112.csv`
 - `sim.rsf.sc3_20251112.csv`
 - `sim.ssf.sc1_20251112.csv`
 - `sim.ssf.sc2_20251112.csv`

These files are not stand alone files. 
They are meant to be loaded in the simulation code and all of the columns are detailed in the code itself.

## Case study 1: murres

The data files associated with the first case study are found in the subfolder `1_Murres`. 

1. `murres_rsf_clean_maxdist.csv`: file that contains the movement data for thick-billed murres. Found in the subfolder `Movement`. 
Specifically, this file contains the farthest location from the colony 54 murres did during a foraging bout (~ 1 day; deployment < 26 hours).
The columns are:
    - dep_id: the identifier for the deployment
    - metal_band: the individual number, specifically their Canadian Wildlife Service metal band number
    - dep_id_short: short version of dep_id
    - lon: longitude of the "foraging" location (in decimal degrees)
    - lat: latitude of the "foraging" location (in decimal degrees)
    - datetime_UTC: date time of the "foraging" location (in UTC)
    - datetime_release_UTC: date time when the individual was released (in UTC)
    - deployment_dur_min: duration of deployment (in minutes)
    - mass_gain: massed gained during the deployment (in grams)
    - rate_mass: rate of mass gained during the deployment (in grams/minutes)
    - dep_lon: longitude of the deployment location (in decimal degrees)
    - dep_lat: latitude of the deployment location (in decimal degrees)
    - distNest: distance to nest, sometimes referred to distance to colony (in kilometers)
    - X_UTM: Easting value of the "foraging" location (in meters; EPSG:32617 (WGS 84 / UTM zone 17N) coordinate system)
    - Y_UTM: Northing value of the "foraging" location (in meters; EPSG:32617 (WGS 84 / UTM zone 17N) coordinate system)

2. `Nest_UTM`: folder that contains the files needed for the `nest_UTM.shp` shapefile. 
It is simply the colony location in a spatial object. 
The Easting and Northing values in meters and the coordinate system is EPSG:32617 (WGS 84 / UTM zone 17N).

3. `Bylot_UTM`: folder that contains the files needed for the `Bylot_UTM.shp` shapefile. 
This shapefile contains the land layer around Bylot Island, Nunavut, Canada. 
The original data was downloaded from NOAA: https://www.ngdc.noaa.gov/mgg/shorelines/. 
We use here the full (f) resolution. 
We have simply clipped the original file to be focussed on the area around the study site 
and have transform the coordinate system to be EPSG:32617 (WGS 84 / UTM zone 17N).

## Case study 2: gull

The data files associated with the second case study are found in the subfolder `2_Gulls`. 

1. `gulls_day_notoncol.csv`: file that contains the movement data for glaucous-winged gulls. Found in the subfolder `Movement`. 
Specifically, this file contains the daytime location outside a 200 meter buffer from their colony for 12 glaucous-winged gulls.
The columns are:
    - device_id: individual identification number, specifically the tagging device number
    - UTC_datetime: date time of the location (in UTC)
    - satcount: the number of satellites used for the location
    - hdop: horizontal dilution of precision (no units)
    - Latitude: latitude of the location
    - Longitude: longitude of the location
    - final_chick: number of chicks
    - tagging_date_local: date of tagging in local time (Pacific time zone)
    - release_time_local: time of release in local time (Pacific time zone)
    - DatetimeLocal: date time in local time (Pacific time zone)
    - X_UTM: Easting value of the location (in meters; EPSG: 26910 (WGS 84 / UTM zone 10N) coordinate system)
    - Y_UTM: Northing value of the location (in meters; EPSG: 26910 (WGS 84 / UTM zone 10N) coordinate system)

2. `BC_UTM`: folder that contains the files needed for the `bc_UTM.shp` shapefile. 
This shapefile contains the land layer around the study area in British Columbia, Canada (and northern Washington, USA). 
The original data was downloaded from NOAA: https://www.ngdc.noaa.gov/mgg/shorelines/. 
We use here the full (f) resolution. 
We have simply clipped the original file to be focused on the area around the study site 
and have transform the coordinate system to be EPSG:26910 (WGS 84 / UTM zone 10N).

3. `XOXDEL_UTM`: folder that contains the files needed for `xoxdel_UTM.shp` shapefile. 
The file represent the buffer around the island where the gulls have their colony, named XOXDEL (Mandarte Island). 
First, a polygon was created by hand using Google Earth satellite images.  
The polygon represents the line above the intertidal zone. 
Then, the projection was changed to EPSG:26910 (WGS 84 / UTM zone 10N).
Finally, a 200 meters buffer around the polygon was added.
Only the 200 meters buffer is kept in the final shapefile.

4. `CumHumanImpact.tiff`: contains the cumulative human impact raster. 
The file is found in the `Covariates/HumanImpact` subfolder. 
The original data from Mu et al. (2021, 2022) is found on Figshare: https://figshare.com/articles/figure/An_annual_global_terrestrial_Human_Footprint_dataset_from_2000_to_2018/16571064
We clipped it to be the area around the study area and changed the projection to EPSG:26910 (WGS 84 / UTM zone 10N).
We rescaled the values to that they ranged from 0 to 1.
Using the R package `terra` we filled missing values on the coast using:

```
# Original humanImpact is the clipped and transformed version of
# the layer available via the link above.
humanImpact <- focal(humanImpact, w = 9, fun = mean, na.policy = "only")
humanImpact <- mask(humanImpact, land)
# land is the layer found in the `bc_UTM.shp` shapefile
```

Mu H., Li X., Wen Y., Huang J., Du P., Su W., Miao S., & Geng M. (2021). An annual global terrestrial Human Footprint dataset from 2000 to 2018. figshare. Figure. https://doi.org/10.6084/m9.figshare.16571064.v7

Mu H., Li X., Wen Y., Huang J., Du P., Su W., Miao S., & Geng, M. (2022). A global record of annual terrestrial human footprint dataset from 2000 to 2018. Scientific Data, 9, 176.


## Case study 3: narwhal

The data files associated with the third case study are found in the subfolder `3_Narwhals`. 

1. `narwhals_clean.csv`: file that contains the movement data for narwhals. Found in the subfolder `Movement`. 
Specifically, this file contains the narwhal movement data used in the step selection analysis.
The columns are:
    - 

2. `NorthernBaffin_UTM`: folder that contains the files needed for the `NorthernBaffin_UTM.shp` shapefile. 
This shapefile contains the land layer around the study area in Nunavut, Canada. 
The original data was downloaded from NOAA: https://www.ngdc.noaa.gov/mgg/shorelines/. 
We use here the full (f) resolution. 
We have simply clipped the original file to be focused on the area around the study site 
and have transform the coordinate system to be EPSG:32617 (WGS 84 / UTM zone 17N).

# Code

## Literature review

The code to reproduce the figures of the literature review is available in `0_review.Rmd`. 
A compiled version is also available in `0_review.html`.

## Simulations

The code to reproduce simulations and the associated figures is available in two sets of files. 

- The first set of files are for the resource selection function (RSF) simulations, 
with `1_rsf_simulations.Rmd` containing the code and `1_rsf_simulations.html` being a compiled version of the code.

- The second set of files are for the step selection function (SSF) simulations, 
with `2_ssf_simulations.Rmd` containing the code and `2_ssf_simulations.html` being a compiled version of the code.

## Case study 1: murres

The code to reproduce the analyses, tables, and figures associated with case study 1, 
which is focused on thick-billed murres, is available in `3_rsf_murre.Rmd`. 
A compiled version is also available in `3_rsf_murre.html`.

## Case study 2: gull

The code to reproduce the analyses, tables, and figures associated with case study 2, 
which is focused on glaucous-winged gulls, is available in `4_ssf_gull.Rmd`. 
A compiled version is also available in `4_ssf_gull.html`.
