# Miss_River_Data

This repository contains the data from Professor John Kim's trip down the Mississippi River. 

Data was collected between 2019-08-30 and 2019-11-21 on five distinct sections of the Mississippi. One near Bemidji, one near Rochester, one South of St. Louis, one south of Cape Girardeau, and one near New Orleans.

### Exploratory Visualization

A web map allowing data to be easily explored can be found at https://grahamammal.shinyapps.io/miss_explore/ The time each data point was recorded can be found by clicking on it. 

### Final Datasets

`clean_legs_non_geom.csv` contains cleaned data in a tabular format. 

`clean_legs/clean_legs_geom.shp` is a shapefile containg the same data with each row classed as a point feature. Attribute names are slightly differnt because writing methods allows only 7 character names. 

### Data Cleaning

In order to clean the data, it was transformed in the following ways using R:

- `ysi_ph, ysi_do, ysi_no3, ysi_sal, ysi_tur`, and `flow` were removed because all values were `NA`
- `crew` was removed because it was only collected for the 0th leg
- Data showing `NA` for `date` was removed
- Data recorded while the canoe was out of the river was removed
- Values of 0 for `air_temp, air_gas, air_humid,` and `air_pressure` were replaced with `NA` because measures appeared to be in error
- Data was aggregated by into 15 second time periods. The median value was taken across this time to smooth errors in data collection