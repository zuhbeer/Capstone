## Tropical Cyclone data around Texas

 Why did I choose this capstone? The graph below contains data that I manually entered from an NOAA pdf 

![Screenshot](https://github.com/zuhbeer/Capstone/blob/caps/deaths.png | width=100)

This made me curious, are storms getting worse in Texas?

## Null Hypothesis- Storms are NOT increasing around Texas

## Alternative Hypothesis- Storms are increasing around texas




I pulled a large csv file from the NOAA - https://www.ncdc.noaa.gov/ibtracs/index.php?name=wmo-data -
that included details of every recorded storm on Earth from 1851. This file contained roughly 50,000 data points, with a varying amount of data points for each storm system. 

## Visualizing the data, enter Pandas, NumPy, & MatPlotLib
The head of the dataframe is shown below; I was only interested in the Serial_Num (Storm I.D), Season(Year), Longitude & Latitude, and wind speed. Pandas easily refined this data. 

![Screenshot](https://github.com/zuhbeer/Capstone/blob/caps/Storm%20Header.png)

Before I constrained my dataset to Texas & and the Gulf, I was curious to see what the data world wide looked like.

![Screenshot](https://github.com/zuhbeer/Capstone/blob/caps/1900%20frequency.png | width=100)
![Screenshot](https://github.com/zuhbeer/Capstone/blob/caps/1900%20intensity.png | width=100)

These graphs triggered my spidey senses, I could not in good conscience run statistical tests on these datasets as there is an obvious change in the methodology of recording storm data around the 1960s. I decided to set the bar for my analyses at 1969, when stable weather satellites began recording data for NASA and the NOAA.

One other parameter I used to refine my data was a wind speed of 34+ knots (40 mph). This is the 1-minute sustained wind speed measurement that classifies a tropical cyclone, with category 1 hurricanes starting at 64 knots (74 mph).

## Storm frequecy & intensity for the World, N. Atlantic, and Texas/Gulf area

Below is the same worldwide tropical cyclone data, but refined for years 1969-2017 , and 34+ knots wind speed

![Screenshot](https://github.com/zuhbeer/Capstone/blob/caps/1969%20frequency.png)
![Screenshot](https://github.com/zuhbeer/Capstone/blob/caps/1969%20intensity.png)

N. Atlantic data

![Screenshot](https://github.com/zuhbeer/Capstone/blob/caps/N.Atl%20freq.png)
![Screenshot](https://github.com/zuhbeer/Capstone/blob/caps/N.Atl%20int.png)

The map below shows the boundaries I used to analyze storms around Texas

![Screenshot](https://github.com/zuhbeer/Capstone/blob/caps/Screen%20Shot%20Gulf.png)


![Screenshot](https://github.com/zuhbeer/Capstone/blob/caps/Gulf%20freq.png)
![Screenshot](https://github.com/zuhbeer/Capstone/blob/caps/Gulf%20int.png)


