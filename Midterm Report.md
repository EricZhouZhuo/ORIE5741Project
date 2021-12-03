# Statistical Analysis on factors influencing Life Expectancy
## Dataset Description
   The dataset we use concentrated on immunization factors, mortality factors, economic facors, social factors and other health related factors. The dataset related to life expectancy, health factors for 193 countries has been collected from the same WHO data repository website and its corresponding economic data was collected from United Nation website. Among all categories of health-related factors only those critical factors were chosen which are more representative. In this project, we have considered data from year 2000-2015 for 193 countries for further analysis. The final dataset consists of 22 Columns and 2938 rows which meant 20 predicting variables. All predicting variables was then divided into several broad categories:Immunization related factors, Mortality factors, Economical factors and Social factors.
## Data Pre-processing
  Firstly, we used describe() method to generate the basic statistics about the features in dataset, such as mean, median, maximum, and minimum. We concluded the following findings that could be the possible steps for our data pre-processing. 
  1. The minimum value of "Adult Mortality" is 1, which might not be correct since motality rate of 1 out of 1000 people is unrealistic. 
  2. The minimum value of  "Infant deaths" is 0. This might be an outlier. Also, the maximum value of "Infant deaths" is 1800 which is much higher than the 75%          percentile value(22).
  3. "BMI" also has some possible outliers: as lower as 1 and as high as 87
  4. Minimum GDP is about 1.68, which might be an outlier.
  5. Minimum of population is 34. This might be unrealistic for a country.
  
  

  Then, we made several boxplot to check for the obvious outliers. Concluding from the boxplots, we decided to replace the data with following conditions with NULLs.
<p align = "center">
  <img src = "/Images/Boxplot" width = "600" height = "250">
</p>  

  1. "Infant deaths" equals to 0.
  2. "Adult Mortality" equals to 1.
  3. "BMI" less than or equal to 5 and greater than or equal to 60.

  After removing the outliers, we first check for the missing value statistics, as shown below. 
<p align = "center">
  <img src = "/Images/Missing Value Statistics" width = "600" height = "300">
</p>

   Clearly, there are significant number of null values and for each feature, the percentage of null values is not too high (less than 30%). We decided to impute the missing values with the mean of all the other values for the features. 
   
## Data Visualization
   We initially generated the below correlation heatmap and tried to identify the potential collinearity among features. We found that "under-five deaths" and "Infant deaths" has strong positive correlation of 0.98. 
<p align = "center">
  <img src = "/Images/Heatmap" width = "800" height = "600">
</p>
   Also, "Percentage Expenditure" and "GDP" has strong positive correlation of 0.89. Moreover, we calculated the relationship for each feature with target variable "Life expectancy" stored coefficients, P-value, level of relationship and significance into the table below. 
<p align = "center">
  <img src = "/Images/Correlation Table" width = "500" height = "400">
</p>
   
   From the table, we can conclude that "Population" is the insignificant feature since its P-value is greater than 0.05. Also, for the two pairs of collinear features, we decided to drop the ones which have weaker correlations with target variable. Therefore, we decided to drop "Population", "Percentage Expenditure", and "Infant deaths" to form a sparse model. 
## Methodology and Preliminary Analysis
   In this part, we tried to fit the linear regression model on our dataset after pre-processing and one-hot encoding on categorical features "Country" and "Status". We split our dataset into training set and testing set with a percentage of 30 on testing set. As a result, the accuracy on training set is 96.3%, which is high enough since we have included many feature. However, the accuracy on testing set is very low. We concluded that the model is overfitting. 
### Avoiding Overfitting
   We applied L1 regularization Lasso onto our model to reduce the overfitting. First, we implemented a grid search to find the best parameter Alpha for Lasso. We found that for Alpha = 0.1, we got the highest score. After we applied this parameter with Lasso on our dataset, we got a relatively lower accuracy on our training set(80.3%), but much more higher accuracy on testing set(79.0%).
   
## Next Step
According to the preliminary analysis above, the model still needs to be refined. As a plan, we will try regularization and PCA to choose a sparse mode. Although regularization may cause bias, we can not ignore the benefit it does on reducing variance and improving interpretability. Besides, the application of PCA will help us with dimensionality reduction. As for the final goal of the project, we are trying to figure out the significance of different features and even broad categories that mentioned above. Some recommendations will be made to government on improving the life expectancy as well. With consideration of the shape of dataset, we will try other evaluation matrics like cross validation rather than fix-percentage dividing on training and testing sets.
   

