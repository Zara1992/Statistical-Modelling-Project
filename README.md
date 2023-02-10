# Final-Project-Statistical-Modelling-with-Python

The objective of this project is to use statistical modelling techniques to capture and analyze data regarding Popular POIs around citybike stations. An important element of this project is to capture data from APIs (Citybikes, Yelp and Foursquare) and load them into a dataframe. For my analysis I have selected the city of Slough in GB. The reason for this selection is that the data was comparatively small as compared to more Metropolitan cities such as New York and it would be interesting to explore the realtionship between POIs and bike usage in smaller cities.

## Project/Goals
Objective --> Study the relationship between restaurant rating and free bikes on stations within the area of Slough, GB. H0: There is no relationship between free_bikes and rating H1: There is a relationship between free_bikes and rating


## Process
1. Capture Data 
    i. Connecting to CityBikes API to get city, stations and bike information 
    ii. Connect to Foursquare API - filtered restaurants within 1000 mile radius of each citybike station 
    iii. Connect to Yelp API - filtered restaurants within 1000 mile radius of each citybike station
2. Joined Data Now that we have the data related to restaurants we will merge them into a single dataframe.
3. Cleaning Data create a new dataframe with only unique records from the joined data.
4. Visualized the data to get a better understanding of the data.
5. Created a sqlite db with multiple tables
6. Run a linear regression analysis by declaing dependent and independent varables from the dataframe

## Results
1. Data Caputre
    i. We can see that the results from both API have different results (141 and 188). 
    ii. Even the top 10 restaurants in both data sets yield different restaurants with a 1000 mile radius of the stations.

2. Data Cleaning 
After merging the data from 2 different sources there might be a chance that some of the records are duplicate. So for this reason we need to perform data cleaning to further proceed in our analysis. There are a total of 179 duplicate records so we drop those from our merged dataframe There are now a total of 150 unique records and we created a new dataframe (unique_merge1) to save them for further analysis.

3. Visual Analysis
    i. Foursquare (Histogram and Scatterplot) a. Rating range is between 0 to 7 b. There are higher ratings given to restaurants within the dataset (5,6 & 7) c. There are no restaurants with lower ratings within this dataset

    ii. Yelp (Histogram and Scatterplot) a. Rating range is between 0 to 5 b. Ratings here are more spread out with restaurants having all types of ratings

    iii. Scatterplot from unique data of the merged dataframe a. Visualized the average rating of restaurants present in a 1000 mile radius of each station. b. On average, the station ‘1 Slough Train Station’ has the highest average rating of 3.5, which might suggest that this station has a really good food culture and people are more likely to eat out around this area. c. There are some stations that have on average zero ratings, which suggest that, restaurants near these stations might:
        * Not have enough virtual presence
        * People are not leaving rating/reviews for them Or
        * the rating is actually 0 and suggest bad food

4. Linear Regression Model 
    i. Based on the value of Adjusted R-square, the model is a poor fit as the value is 0.000 
    ii. The value for the constant of the coefficient (y-intercept) shows a value of 1.1608. This means that if there are 0 free bikes on a station the restaurant ratings would be at least 1.1608 
    iii. free_bikes coefficient represents the change in the output Y (rating) due to a change of one unit in the rating (everything else held constant).
    iv. P >|t| is your p-value. A p-value of less than 0.05 is considered to be statistically significant. 
    v. In our model the p-value is 0.304 which is higher than 5%. The model is statistically insignificant 
    vi. Correlation values between free_bikes and rating = 0.30408302591589037033870113191369455307722091674804875000000 
        Hypothesis Test: p-value is > 0.05, Accept H0 and Reject H1. There is no significant correlation between the two variables


## Challenges 
1. Overall the project was extremely difficult. Particularly the part where we had to call the API for foursquare and yelp. Alot of time was spent on understanding the API and capturing it's data. It would have been better if there was a proper guidance on how to do it, so that more time would have been spent on analysis and regression modelling.
2. No idea why we had to create a sqlite database as even after numerous attempts I wasn’t able to use it for model building. Also when I try to move it to the data folder it gives me an error. 
3. I understand that using API’s is a key skill in the real world. LHL’s teaching material should include it in greater detail.
4. The poor results from the model suggest that the data source can be improved. There might be good data sources available with a better reference to understand data structure, APIs etc.
5. The greater part of the effort for this project was spent on data capture rather than modelling and analysis.




## Future Goals
In the future I would like to attempt developing a model with a good data source.

