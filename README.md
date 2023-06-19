# Project1

## Where to open a brewery?
- Using U.S. Census Data and Open Brewery DB, identify the demographics of the area with the most breweries and see what might be ideal conditions for where to open a brewery.

## Part 1: Creating the Brewery Dataframe

### Connect to OpenBrewery API
- Used the OpenBreweryAPI. The API is free, however it limits the number of queries to 200 rows and restricts sourcing of data to 2 pages at a time. To load all necessary data, it was necessary to create a loop to move through all 156 pages of the API and collect 100 cases per page or 200 every two pages for the United States locations. 

### Find missing data
- In the Brewery API ~2.3k breweries were missing the latitude and longtitude data. 
  
### Populate missing data
- Seperate the breweries that are missing latitude and longtitude into it's own dataframe
  
- Used Geopify to pull latitude and longtitude for the missing zip codes. Since Geopify did not recognize the postal code +4 format; opted to use the uszipcode package to extract the first 5 digits.

- Merged the dataframes back together to get the complete brewery dataframe

### Create csv file
 - Created csv file with the completed breweries dataset. File name is breweries_complete. 

## Part 2: Creating the Census Dataframe

### Select Census API
 - Used the API from the American Community Survey (ACS). This was chosen because it contained both data relating to demographics and location. Parametrs used were intended to later uncover dependencies between the density of brewery locations and increased size population of the groups known to carry the charasteristics of the craft beer's primary consumer group. The dataset also included necessary geographic locations [City, State] to allow merging with the brewery_complete dataset [later reffered to as brewery_last dataframe]

- The ACS covers a broad range of topics about social, economic, demographic, and housing characteristics of the U.S. population

-  Dataset consists of high-level detailed tables tabulated on the 1-year microdata for geographies with populations of 20,000 or more

### Identify Parameters 

- Selected population, income, employment, and occupancy parameters

### Create csv file

- Created csv file with the completed census dataset. File name is census_names. 

## Part 3: Merge the Brewery and Census Dataframes

### Update data to maximize number of successful rows merged
- Created a new key and renamed city and state columns
- Removed additional signs and spaces in the city and state columns to ensure proper merge
- Edit city names from each dataset so they match up correctly in merge
- Merge two dataframes by City and State column 

### Create csv file
- Created csv file with the completed census dataset. File name is merged_df_cleaned

## Part 4: Create Visualizations
- Generate a bar plot showing total number of breweries by state 
- Identify number of closed breweries in comparison to other types 
- count brewery type per state 
- Display bar plot of brewery type per state 
- Diplay bar plot of total number of Micro and Brewpubs Per State
- Map the micro and brewpubs by latitude and longitude 
- Generate a bar plot showing total number of closed breweries by state
- Generate a bar plot showing total number of closed breweries by state 
- Top 5 states for micro/brewpub concentration
- Display bar plot of states with most Micro and Brewpubs
- Bottem 5 states for micro/brewpub concentration
- Display bar plot of states with least Micro and Brewpubs
- Find top 3 cities from top state for micro/brewpub concentration
- Display bar plot of cities in CA with Most Micro and Brewpubs


