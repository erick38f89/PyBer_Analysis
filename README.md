# PyBer_Analysis

#Written report
  
##Overview of the analysis: 
    This is an analysis of the cuantitative distribution of the ridesharing service PyBer. We are looking at the ride id segmented by date, city, type if city, driver and fare. This is with the purpose of strenghtening the areas that need attention adn focusing the investments in the appropriate type of ciry in order to drive the highest posible benefits.

##Results
  We analyzed two dataframes ride_data_df and city_data_df and merging them into one data frame called pyber_data_df with the Pandas merge function as the following code shows:

pyber_data_df = pd.merge(ride_data_df, city_data_df, how="left", on=["city", "city"])

  With this data frame we were able to observe the total rides, total drivers, as well as the sum of fares and average of fares per rides and driver by using the following Panda functions:

rides_by_city = pyber_data_df.groupby('type').count().ride_id
drivers_by_city_type = city_data_df.groupby('type').sum().driver_count
fares_by_city_type = pyber_data_df.groupby('type').sum().fare
avg_fare_by_city_type = pyber_data_df.groupby('type').mean().fare
avg_driver_fare_by_city_type = pyber_data_df.groupby('type').sum().fare / drivers_by_city_type

  The results indicate from the dataframe indicate that the vast majority of the rides happen in urban cities. However, the higher average fare amount comes from the rural types; this could be due to the longer distance usually involving rural rides. To increase the potential revenue, marketing efforts may focus rural users to increase the frequency of rides.

##Summary: 

  To increase the potential revenue, marketing efforts may focus rural users to increase the frequency of rides.
  Consider potential pricing adjustment for the fare based on the urban type.
  Issue bonus for drivers to take rides in rural areas.
