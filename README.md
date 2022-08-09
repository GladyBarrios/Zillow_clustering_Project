# Zillow_clustering_Project: Understanding and improving the Zestimate 

By: Glady Barrios 

- Kalpana Cohort

---------------------------

## Project Description 

The goal of this project is to find the driving errors in the Zestimate and find ways to better improve Zillows current models. Improving our models will help zillow customers get more accurate home prices. We want our customers to have the most accurate information 



# Project planning:

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

- Kept the collums that have 60% of their data (since there was many nulls)
    - removed columns that have 30% of data missing 
- Kept the rows that have 75% of their data
    - removed rows that have 15% of data missing
- For some collumns I decided to fill some of the nulls with the mean of the column such as `lotsizesquarefeet`, `taxvaluedollarcount`, `yearbuilt` 

Columns I added:

- 'County'- displaying the names of the three difrent counties 
- 'age' calculated by 2017 -the year it was built
- 'acres' was calculated by lotsizesquarefeet divided by 43560 
- Added dummy variables for counties 

Removing outliers:
- More than 7 bathrroms and bedrooms
- Removed 0 bed and bath 
- Any acres greater than 20 

- then split the data to train vlidate and test
- then scaled the data 



### Exploration 

Exploration Questions asked

- Question 1 - Is log error significantly different for properties in the three counties?
- Question 2 - Is log error significantly different for properties that have diffrent bathroom counts?
- Question 3 - Is log error significantly different for properties that have diffrent bedroom counts?
- Question 4 - Is log error significantly different for properties that have diffrent proprty values?### Modeling
### Clustering 

Used K-means Clustering Method
Choose K using the elbow method (using innertia)
To look at the elbow method visualiation please look at my GitHub repo

Clusters
Size_Cluster , contains features: bathroomcnt , bedroomcnt, lotsizesquarefeet

Location_Cluster, contains features: latitude, longitude

Age_size, contains features: age, lotsize


### Modeling 

I decided since my custers was not able to show me a relationship between features and log error I decided to use some Feature Engineering

To determine the features that have a relationship with logerror, 4 of the best features where chosen using Select k best
Models Used

OLS- (Ordiary Least Squares)

LassoLars

GLM- (Generalized Linear Model)

Polyniomial Model- This model had the lowest RMSE


Takeways
- The best model for this Zillow dataset is Ploynomial Model 2nd degree
  - The models are not significantly different from the baseline
  - Some are better than the baseline, but by a very small amount


### Conclusion 

- Conclusion
From the whole report we can see that some features have a relationsip with log error but those relationsips are to weak to create a great reasonable model.


- Recomendations
Trying other key drivers of logerror that I was not able to touch on
Keep improving the baseline model since it is a very good model to work with
There is alot of missing data, if there is a way we could revisit those properties or find more meaninful ways to aquire such data to therefore make better predictions with our models


- Next Steps
Making different clusters with different features
Get different approches from my peers
Trying different models such as classification models


## Steps to reproduce 
You will need an env.py file that contains your own hostname, username and password of the mySQL database that contains the zillow_db Store that env file locally in the repository. clone my repo (including the acquire.py and prepare.py) (confirm .gitignore is hiding your env.py file) libraries used are pandas, matplotlib, seaborn, numpy, sklearn. you should be able to run final repo.
