# Statistical Analysis on factors influencing Life Expectancy
## Dataset Description
   The dataset we use concentrated on immunization factors, mortality factors, economic facors, social factors and other health related factors. The dataset related to life expectancy, health factors for 193 countries has been collected from the same WHO data repository website and its corresponding economic data was collected from United Nation website. Among all categories of health-related factors only those critical factors were chosen which are more representative. In this project, we have considered data from year 2000-2015 for 193 countries for further analysis. The final dataset consists of 22 Columns and 2938 rows which meant 20 predicting variables. All predicting variables was then divided into several broad categories:Immunization related factors, Mortality factors, Economical factors and Social factors.
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
  <img src = "/Images/Missing Value Statistics" width = "400" height = "200">
</p>
## Methodology and Preliminary Analysis
## Next Step

