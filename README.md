# Zillow_clustering_Project: Understanding and improving the Zestimate 

By: Glady Barrios 

- Kalpana Cohort

---------------------------

## Project Description 

The goal of this project is to find the driving errors in the Zestimate and find ways to better improve Zillows current models. Improving our models will help zillow customers get more accurate home prices. We want our customers to have the most accurate information 



## Project planning:

### Goals

- Use clustering to algorythims to determine driving errors in the current Zestimate.
- Trying to find and use the differnt drivers of logerror to improve the Zestimate Model.
- Mostly we want to improve the Zestimate model using our diffrent modeling methods.


## Data Dictionary
Target   | Datatype       |Defenition
---------|----------------|------------
logerror |   float64      |  Log error



Feature        | Datatype   | Defenition
---------------|------------|------------
bathroomcnt    |float64     | Number of bathrooms
bedroomcnt     |float64     | Number of Bedrooms
fips           |float64     | Area Codes
latitude       |float64     | Latitude
longitude      |float64     | Longitude
lotsizesquarefeet |float64  |The squarefeet of the property 
yearbuilt         |float64  | Year the home was built 
taxvaluedollarcnt |float64  | The total tax value 
age               |float64  |years since the home was built 
LA                |int64    |Los Angeles Family 
Orange            |int64    |Orange County
Ventura           |int64    |Ventura County


## Data Aquisition and Prepreation

### Aquire

- Aquirred the data from the SQL Database with the MYSQL codeup database 

### Prepare

-  DATA_PREP function was To prepare the data, I decided that much of the data was was missing and filled with "NONE" or "null" I decided for each collumn to keep any collumn with 60% of the data and for the rows i decided that 75% of the infrmation of the row.

- I decided for important collums like lotsizesquarefeet, taxvaluedollarcnt and yearbuilt




### Exploration 

### Modeling

### Conclusion 


