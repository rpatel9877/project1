# Project1

## Where to open a brewery?
- Using U.S. Census Data and Open Brewery DB, identify the demographics of the area with the most breweries and see what might be ideal conditions for where to open a brewery.

## Part 1: Creating the Brewery Dataframe

### Connect to OpenBrewery API
- Used the OpenBreweryAPI. This API is free, however it limits the number of queries to 200 rows and restricts sourcing of data to 2 pages at a time. To load all necessary data, it was necessary to create a loop to move through all 156 pages of the API and collect 100 cases per page or 200 every two pages for the United States locations. 

### Find missing data
- In the Brewery API ~2.3k breweries were missing the latitude and longitude data. 
  
### Populate missing data
- Seperate the breweries that are missing latitude and longitude into it's own dataframe
  
- Used Geopify to pull latitude and longitude for the missing zip codes. Since Geopify did not recognize the postal code +4 format; opted to use the uszipcode package to extract the first 5 digits.

- Merged the dataframes back together to get the complete brewery dataframe

### Create csv file
 - Created csv file with the completed breweries dataset. File name is breweries_complete. 

## Part 2: Creating the Census Dataframe

### Select Census API
 - Used the API from the American Community Survey (ACS). This was chosen because it contained both data relating to demographics and location. Parametrs used were intended to uncover dependencies between the density of brewery locations. The dataset also included necessary geographic locations [City, State] to allow merging with the brewery_complete dataset [later reffered to as brewery_last dataframe]

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
- Generated a bar plot showing total number of breweries by state 
- Identified number of closed breweries in comparison to other types 
- Counted brewery type per state 
- Displayed bar plot of brewery type per state 
- Displayed bar plot of total number of Micro and Brewpubs Per State
- Mapped the micro and brewpubs by latitude and longitude 
- Generated a bar plot showing total number of closed breweries by state
- Generated a bar plot showing total number of planned breweries by state 
- Displayed bar plot of states with most Micro and Brewpubs
- Displayed bar plot of states with least Micro and Brewpubs
- Find top 3 cities from top state for Micro and Brewpubs
- Find top 3 cities from bottom state for Micro and Brewpubs
- Display bar plot of cities in CA with Most Micro and Brewpubs
- Created a bar plot for median income (household and nonhousehold) for San Diego, San Francisco, and Los Angeles
- Created a bar plot for median income (household and nonhousehold) for Jackson, Hattiesburg, and Gulfport
- Created a bar plot for total population and gender distribution for top 3 CA cities
- Created a bar plot for total population and gender distribution for top 3 MS cities
- Created a bar plot for median age, female and male for top 3 CA cities
- Created a bar plot for median age, female and male for top 3 MS cities
- Plot breweries (micro) vs population
- Plot breweries (micro) vs income
- Plotted a histogram showing the data comparing the two populations
- Ran an independednt t-test for the median income of zip codes with breweries and zip codes without breweries




