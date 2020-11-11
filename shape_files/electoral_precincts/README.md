# Georgia Election Shapefile

This shapefile is a combination of the 2018 VTDs published by the GA Reapportionment office and a few county specific corrected maps. These Precincts were adjusted slightly to reflect census blocks if the census block in question had less than 10 voting aged individuals in the 2010 census and no geocoded voters from any other precinct.

## Sources
The 2018 VTD shapefile (along with current district shapefiles) was downloaded on September 27th 2019 from the Georgia General Assembly Reapportionment Office website (http://www.legis.ga.gov/Joint/reapportionment/en-US/default.aspx). Maps of Catham and Fulton Counties were requested from county clerks because of suspected problems.

Election results come from the MIT Election Data Science Lab (https://github.com/MEDSL/2018-elections-official/blob/master/precinct_2018.zip).

## Metadata

* `loc_prec`: Unique precinct identifier, locality and precinct separated by a comma.
* `locality`: County name
* `prec_shp`: Precinct name from shapefile
* `prec_elec`: Precinct name from election results
* `G18DATG`: Total votes democratic Attorney General
* `G18DCmAg`: Total votes democratic Commissioner Of Agriculture
* `G18DCmIns`: Total votes democratic Commissioner Of Insurance
* `G18DCmLab`: Total votes democratic Commissioner Of Labor
* `G18DGOV`: Total votes democratic Governor
* `G18DLTG`: Total votes democratic Lieutenant Governor
* `G18DPbSrv`: Total votes democratic Public Service Commission
* `G18DSOS`: Total votes democratic Secretary Of State
* `G18DSchSpr`: Total votes democratic State School Superintendent
* `G18DStSen`: Total votes democratic State Senate
* `G18LCmIns`: Total votes libertarian Commissioner Of Insurance
* `G18LGOV`: Total votes libertarian Governor
* `G18LPbSrv`: Total votes libertarian Public Service Commission
* `G18LSOS`: Total votes libertarian Secretary Of State
* `G18RATG`: Total votes republican Attorney General
* `G18RCmAg`: Total votes republican Commissioner Of Agriculture
* `G18RCmIns`: Total votes republican Commissioner Of Insurance
* `G18RCmLab`: Total votes republican Commissioner Of Labor'
* `G18RGOV`: Total votes republican Governor
* `G18RLTG`: Total votes republican Lieutenant Governor
* `G18RPbSrv`: Total votes republican Public Service Commission
* `G18RSOS`: Total votes republican Secretary Of State
* `G18RSchSpr`: Total votes republican State School Superintendent
* `G18RStSen`: Total votes republican State Senate
* `tot`: Total population from 2010 Census aggregated from blocks
* `NHwhite`: Total non-hispanic white population
* `NHblack`: Total non-hispanic black population
* `hispanic`: Total hispanic population
* `totVAP`: Total voting-aged population
* `WVAP`: Total white voting-aged population
* `BVAP`: Total black voting-aged population
* `HVAP`: Total hispanic voting-aged population
* `CD`: Congressional district assignment
* `HD`: State House district assignment
* `SD`: State Senate district assignment


## Preprocessing

The MIT dataset is processed to be sorted by precinct and aggregated by party and office per precinct. This precinct level dataset was used to look for counties where total number of precincts or precinct names did not match up. These states were contacted to verify the correct matching and geographies. Some precincts had to be verified as having no voters, as they were just omitted from the election results all together.

PGP has access to Target Smart voter roll through a partner, and geocoded this via the Census Geocoder. Precinct census block assignments from this voter roll were used to determine counties where errors were likely. These counties were contacted, and the precinct boundaries adjusted to reflect any updates that needed to be made.

Population breakdowns were downloaded from the Census API and aggregated into precincts from blocks. District shapefiles were downloaded from the GA website and labels assigned to precincts accordingly. 
