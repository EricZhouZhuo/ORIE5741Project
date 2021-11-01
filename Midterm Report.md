# Statistical Analysis on factors influencing Life Expectancy
## Dataset Description
## Data Pre-processing and Analysis
  Firstly, we used describe() method to generate the basic statistics about the features in dataset, such as mean, median, maximum, and minimum. We concluded the following findings that could be the possible steps for our data pre-processing. 
  1. The minimum value of "Adult Mortality" is 1, which might not be correct since motality rate of 1 out of 1000 people is unrealistic. 
  2. The minimum value of  "Infant deaths" is 0. This might be an outlier. Also, the maximum value of "Infant deaths" is 1800 which is much higher than the 75%          percentile value(22).
  3. "BMI" also has some possible outliers: as lower as 1 and as high as 87
  4. Minimum GDP is about 1.68, which might be an outlier.
  5. Minimum of population is 34. This might be unrealistic for a country.

  Then, we made several bocplot to check for the obvious outliers. Concluding from the boxplots, we decided to replace the data with following conditions with NULLs.
  1. "Infant deaths" equals to 0.
  2. "Adult Mortality" equals to 1.
  3. "BMI" less than or equal to 5 and greater than or equal to 60.

  After removing the outliers, we first check for the missing value statistics, as shown in figure 1. 
<p align = "center">
  <img src = "/Images/Missing Value Statistics">
</p>
## Methodology and Preliminary Analysis
## Next Step

