# Village Mapping for Maharashtra
#### An exercise to quality check the Maharashtra village shapefiles and produce metadata along with a webapp for visualization

![](images/Maharashtra_villages.png)

# Background
## Datasets we have:
**1. 2011 District Census handbook (DCHB) Maharashtra** [xlsx and csv format]  
The census has published district census handbooks available openly online which contains information on hundreds of variables (demographic, social, economic, access to water, sanitation, health, education, ICT, transport etc) for all of Maharashtra's approximately 44000 villages.  

You can go to this [link](http://www.censusindia.gov.in/2011census/dchb/DCHB.html) and click on Maharashtra, village amenities to get the large excelsheet for all of Maharashtra (72mb) or download a csv for Maharashtra (38mb) or single district wise csv (<3mb) from this google drive [link](https://docs.google.com/a/datameet.org/folderview?id=0B56AIvhxWGQXVFhWal92Y0EySlE&usp=drive_web)

**2. Census Code Lookup Tables** [csv format]  
The Census codes for villages in India have not remained the same in going from census 2001 to 2011. The coding scheme was changed and lookup tables of 2001 codes and their corresponding 2011 codes are accessible on the Govt of India egov platform via this [link](https://egovstandards.gov.in/mapping_land_region_codification). Note that this egov site is often problematic, alternatively you can go to this google drive [link](https://docs.google.com/a/datameet.org/folderview?id=0B56AIvhxWGQXVFhWal92Y0EySlE&usp=drive_web) for the same file

**3. Village Boundaries for Maharashtra** [shapefile format and their attribute tables in csv format]  
We have two versions of this shapefile and two versions of their attribute tables. Both were obtained from Bhuvan Panchayat, by accessing their WFS endpoint via using the gdal library.

* Version 1: 
The first one has approximately 44,000 villages, it has only 2001 codes: district, sub-district, village. It does not have village names, or any 2011 codes. Hence the problem. We cannot easily append 2011 census data to this file to prepare a map.

* Version 2: 
The second file has both 2001 and 2011 codes, district, sub-district and village and also village names. However it shows approximately 48,000 villages, many more than those existing in the 2011 DCHB. 

# Objectives
####Study both the shapefile attribute tables
* Study version 1 and see how closely it compares with the 2011 DCHB, which can be considered the authentic source for number and names of villages
    + Are there missing villages? 
    + Are there extra villages?
    + Any missing/incorrect values for the 2001 codes

* Append 2011 codes from the census code lookup tables to the shapefile attribute table v1 and then observe
    + How well do they match?

* Study version 2 and see how closely it compares with the 2011 DCHB.
    + Answer questions such as are there missing villages? 
    + Are there extra villages?
    + Any missing/incorrect values for the 2001/2011 codes?
    + How is it that we find 48,000 villages instead of 44,000?

####Prepare sample maps 
Append the 2011 DCHB data to create thematic visualizations. These visualizations will show us spatial trends for any of the census variables we want.

#### Prepare a web map
More to be discussed on how this is to be done
