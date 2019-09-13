# Tropical Cyclone data around Texas

 Why did I choose this capstone? The graph below contains data that I manually entered from an NOAA pdf 

<img src="https://github.com/zuhbeer/Capstone/blob/caps/deaths.png" width="600">

This made me curious, are storms getting worse in Texas?

## Null Hypothesis- Tropical cyclones are NOT increasing around Texas

## Alternative Hypothesis- Tropical cyclones are increasing around texas

A tropical cyclone is any storm system that gains to a speed of 34 knots, more intense than a tropical 


I pulled a large csv file from the NOAA - https://www.ncdc.noaa.gov/ibtracs/index.php?name=wmo-data -
that included details of every recorded storm on Earth from 1851. This file contained roughly 50,000 data points, with a varying amount of data points for each storm system. 

## Visualizing the data, enter Pandas, NumPy, & MatPlotLib
The head of the dataframe is shown below; I was only interested in the Serial_Num (Storm I.D), Season(Year), Longitude & Latitude, and wind speed. Pandas easily refined this data. 

![Screenshot](https://github.com/zuhbeer/Capstone/blob/caps/Storm%20Header.png)

Before I constrained my dataset to Texas & and the Gulf, I was curious to see what the data world wide looked like.

<img src="https://github.com/zuhbeer/Capstone/blob/caps/1900%20frequency.png" width="700">
<img src="https://github.com/zuhbeer/Capstone/blob/caps/1900%20intensity.png" width="700">

These graphs triggered my spidey senses, I could not in good conscience run statistical tests on these datasets as there is an obvious change in the methodology of recording storm data around the 1960s. I decided to set the bar for my analyses at 1969, when stable weather satellites began recording data for NASA and the NOAA.

One other parameter I used to refine my data was a wind speed of 34+ knots (40 mph). This is the 1-minute sustained wind speed measurement that classifies a tropical cyclone, with category 1 hurricanes starting at 64 knots (74 mph).


## Storm frequecy & intensity for the World, N. Atlantic, and Texas/Gulf area

Below is the same worldwide tropical cyclone data, but refined for years 1969-2017 , and 34+ knots wind speed.

    Sample size is 3,548


<img src="https://github.com/zuhbeer/Capstone/blob/caps/1969%20frequency.png" width="600">
<img src="https://github.com/zuhbeer/Capstone/blob/caps/1969%20intensity.png" width="600">


## N. Atlantic Data

    Sample size is 575

<img src="https://github.com/zuhbeer/Capstone/blob/caps/N.Atl%20freq.png" width="600">
<img src="https://github.com/zuhbeer/Capstone/blob/caps/N.Atl%20int.png" width="600">


## Texas & Gulf Data


The map below shows the boundaries I used to analyze storms around Texas


<img src="https://github.com/zuhbeer/Capstone/blob/caps/Screen%20Shot%20Gulf.png" width="700">

    Sample size is 70

<img src="https://github.com/zuhbeer/Capstone/blob/caps/Gulf%20freq.png" width="600">
<img src="https://github.com/zuhbeer/Capstone/blob/caps/Gulf%20int.png" width="600">

## Running the numbers

To reiterate, my hypotheses were: 

Null Hypothesis- Storms are NOT increasing around Texas

Alternative Hypothesis- Storms are increasing around texas

I chose to run a two sample t-test with an alpha value of .05 since this was a one-tailed test. I seperated the data at the year 1994 to generate the two samples with 25 (years) and 24 observations respectively (The NOAA data stopped at 2017). 



The results for the world, N.Atlantic, and Texas are as follows


## Globaly

<img src="https://github.com/zuhbeer/Capstone/blob/caps/world_ttest.png" width="600">

    Sample size = 3,548

    The means are 66.56 and 78.50 respectively

    P value = 0.03600669266460539

For the world, I can safely reject my null hypothesis as the P value is 3%, under my 5% threshold 


## North Atlantic

<img src="https://github.com/zuhbeer/Capstone/blob/caps/NAtl_ttest.png" width="600">


    Sample size = 575

    The means are 9.76 and 13.79 respectively

    P value = 0.00312978634567752

For the North Atlantic, I can absolutely demolish my null hypothesis as the P value is .3%, way under my 5% threshold 


## The Gulf & Texas

<img src="https://github.com/zuhbeer/Capstone/blob/caps/TX_ttest.png" width="600">

     Sample size = 70

     The means are 1.32 and 1.54 respectively

     P value = 0.54764510528614

For the Gulf and Texas coastline, I fail to reject the null hypothesis as my P value is 54%, greater than the 5% threshhold

## Conclusion

I failed to reject my null hypothesis that tropical cyclones are not increasing around Texas; meaning I cannot confidently claim that storms are increasing around Texas. Alternatively, I cannot say storms aren't increasing. 

On the bright side, I have statistically significant evidence of tropical cyclones increasing around the world and especially in the N. Atlantic, a better understanding of dataframes and statistics, and all the friends I made along the way.

This first capstone has been an excellent learning experience, and for near future work I plan to merge different datasets (insurance data, death toll, temperature, etc.) with my storm data to find any correlations. I also plan on using Flask App to let users play around with the parameters and return graphs and t-tests of storms in varying years, locations, and intensities.

## References

https://www.wpc.ncep.noaa.gov/research/txhur.pdf https://en.wikipedia.org/wiki/List_of_Texas_hurricanes_(1980%E2%80%93present)

https://www.ncdc.noaa.gov/ibtracs/index.php?name=wmo-data
