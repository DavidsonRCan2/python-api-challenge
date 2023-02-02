# python-api-challenge

WeatherPy

I started with importing my dependencies.  I retrofitted the datetime dependency to reformat the dates from UNIX and the scipy.stats to perform the linear regressions down the line.

Then I used the citypy library as indicated to create a randomized list of cities within a range of latitudes and longitudes.  My initial list had about 625 cities.  Then I used API documentation to pull weather data for each city from OpenWeatherMap.  It took a few tries to get the parsing correct.  I ran a separate code for my home zip code so I could see the json print out and I used that to guide my parse code.  The loop took a while to run and I probabaly ran it too many times, but eventually ended up with a list of 574 cities, as some cities did not have data in OpenWeatherMap.

I created my dataframe and converted the UNIX time to something readable.  This iteration of weather data was last pulled February 1, 2023.  I exported the dataframe to a csv, and pulled the csv back in to work off of.

I created all the indicated scatter plots and saved the figures.  Plotting graphs is so fun!  I played with the edgecolors and marker sizes.

I then started the linear regression section.  I created two dataframes, one for the Northern Hemisphere and one for the Southern Hemisphere.  I tried defining a function to create the linear regression plots, but it did not work.  I had to manually copy and paste the code for each plot.  Below is a list of the linear regression plots and my thoughts on them:

    Temperature vs. Latitude Linear Regression Plot:  The above two plots showing the relationship between city latitude and maximum temperatures show the same relation:  as the city's latitude gets higher in the positive or negative way, which means away from the equator, the max temperatures are lower.  This makes sense because those regions are technically farther from the sun and generally have lower temperatures and colder climates.

    Humidity vs. Latitude Linear Regression Plot:  The relationship between the latitude and humidity for the Northern and Southern Hemispheres is interesting!  In the Northern Hemisphere, the farther north from the equator, the higher the humidity.  However, in the Southern Hemisphere, the farther south away from the equator, the lower the humidity!  

    Cloudiness vs. Latitude Linear Regression Plot:  The regression lines in the Latitude vs Cloudiness plots above show a very loose relationship.  The data is very scattered, but there is a slight indication to a positive correlation.  Both plots show that the farther north, the cloudier it is!  In the Northern Hemisphere, the farther north away from the equator, the cloudier it is.  And in the Souther Hemisphere, the farther north toward the equator, the cloudier it is.  This could coincide with the information about the humidity!

    Wind Speed vs. Latitude Linear Regression Plot:  In the Northern Hemiphere, the wind seems to be pretty stagnant, showing an almost horizontal line.  In the Southern Hemisphere, the farther south away from the equator, the windier it is.  But the more north toward the equator, the more stagnant the wind is.  This would help explain why it is cloudier and more humid as we move north; the wind is not moving so clouds and precipitation are easier to form and stay.

These findings had me Google why it was more humid in the Northern Hemisphere!  My quick search showed that it is most likely due to ocean currents!  From washington.edu:  "After using other observations to calculate the ocean heat transport, the authors next used computer models to show the key role of the huge conveyor-belt current that sinks near Greenland, travels along the ocean bottom to Antarctica, and then rises and flows north along the surface. The reason is that as the water moves north over many decades it gradually heats up, carrying some 400 trillion (that’s four with 14 zeroes after it) watts of power across the equator." (https://www.washington.edu/news/2013/10/20/global-ocean-currents-explain-why-northern-hemisphere-is-the-soggier-one/)

VacationPy

This was the tough one!  I imported the csv with the city data.  And when I tried to map them out, I realized I had to import many more dependencies.  I had to conda install geoviews. I then reverted to the classwork from week 6 to guide me through creating the first map.  

Then I narrowed the city data based on some personal preferences for vacation spots.  I wanted a place between 75-85 degF (24-29 degC), a windspeed of less than 4.5 m/s, and a cloudiness of less than 25%.  I created my ideal weather dataframe.  Then I created the hotel dataframe by pulling just City, Country, Lat, Lng, and Humidity columns from the ideal weather dataframe, and added a Hotel Name column.

This next part was the toughest for me.  I sought out help from AskBCS.  They helped me realize that I had some parsing code incorrect and helped me fix it.  I had initially tried changing my parameters and even the url several times because the output was saying there were no hotels in any of those cities.  I knew that could not be true.  But once I fixed my params/parsing code, it ran and gave me successful outputs!  I got my hotel dataframe, then cleaned it up to only show me cities with hotels.  Then I mapped the hotels and figured out how to add colums to the hover message!

It looks like I'm due for a trip to Hawaii!

