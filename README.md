### Alcohol availability in Fayette county’s neighborhoods
This was an exploration aimed at using data from KY's Department of Alcoholic Beverage Control (ABC) to calculate the availability of alcohol in Fayette county’s neighborhoods

I aimed to calculate the rate of liquor licenses per capita (the number of licenses divided by the neighborhood’s population). I showed the top 20 neighborhoods with the highest rate of alcohol availability, as well as the top 20 neighborhoods with the highest number of licenses. Neighborhoods were defined as US Census Bureau tracts

I utilized two files, downloaded from KY's ABC portal. (https://abc.ky.gov/) One contained all licenses, while the other contained a non-quota subset of licenses

Population data was taken from the US Cencus Bureau with the hierarchy being country (largest) -> state -> county -> tract -> blockgroup -> block (smallest). I chose to calculate the rate at the cencus tract level from the 2020 American Communities Survey using the US CEnsus Bureau's API (https://api.census.gov/data/2020/acs/acs5/profile?get=NAME,DP05_0001E&for=tract:*&in=state:21&in=county:067)

Because the license counts were much smaller than the population counts, I adjusted the rate by multiplying by per 100 or 1000 people (so the rate is X licenses per 1000 people instead).

Each license was associated with a street address, so I utilized geocoding to associate particular addresses with a cencus tract. An API call was made keeping in mind the rate limits.

Parts 9 - 13 contain results

### Part 1: Test API call for census and geocoding data
### Part 2: Census API response & Data Cleaning
### Part 3: Import CSVs & Data Cleaning 
### Part 4: Check for missing SiteIDs
### Part 5: Save addresses in batch compatible format
### Part 6: Submit API request
### Part 7: Add headers to the geocodes
### Part 8: Merge Datasets
### Part 9: Calculate the rate of liquor licenses per capita 
### Part 10: Show the top 20 neighborhoods with the highest number of licenses.
### Part 11: Show the top 20 neighborhoods with the highest rate of alcohol availability.
### Part 13: Results/Discussion


### My Goals
- For each neighborhood, calculate the rate of liquor licenses per capita (the number of licenses divided by the neighborhood’s population).
- Show the top 20 neighborhoods with the highest rate of alcohol availability.
- Show the top 20 neighborhoods with the highest number of licenses.
- Calculate the rate at the census tract level; tracts typically average 4,000 people by design (with a range of 1,200 and 8,000 people)
- Determine whether or not these two top-20 lists differ and how.

