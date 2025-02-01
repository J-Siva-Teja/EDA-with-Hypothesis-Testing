**1. Problem Statement:**

Electrice Bike Rental company has recently suffered considerable dips in its revenues and they want to understand the factors affecting the demand for these shared electric cycles in the Indian market.

**Approach :** Now we are going to identify the dependent variable and will explore the relation or dependencies of dependent variable with independent  variables.


**2. Insights about Dataset:**

a) Total no of records in dataset are 10886.

b) There are 12 columns in Dataset of which 11 are numerical variables and 1 variable is categorical.

c) “datetime” is of object type hence it has to be converted to datetime format.

d) There are no null values hence there is no need for imputation.

e) There are no duplicate records in dataset all the records are unique.

f) Dependent variable in the given dataset is “count” and it is dependent on “working day”, ”weather”, “season”, “temperature” and “humidity” which are independent variables. 

g) In the given dataset the unique values of nominal variables are : 

season : [1,2,3,4], weather = [1,2,3,4], working day = [0,1], holiday = [0,1] and all the other variables are continuous variables.


**3. Identification of Outliers and Transformation of data:**

As our dependent variable is “count” and our analysis is based on effect of other variables on this variable lets proceed with identification and removal of outliers.

As per the boxplot and histogram of the variable it is evident that data is positively skewed and not normally distributed hence let’s proceed with IQR method. The details are as under:

Lower Bound : -321.0

Upper Bound : 647.0

No of Outliers : 300

Share of outliers : 2.76%

Skewness of count variable before Outlier treatment is : 1.2420662117180776 (Positive Skewness)

Kurtosis  of count variable before Outlier treatment is : 1.3000929518398334 (Platykurtic)

Skewness of count variable after Outlier treatment is : 0.9155844120178854

Kurtosis  of count variable after Outlier treatment is : 0.05712315829641046

Even after treating outliers “count” variable is still positively skewed which will give us deviated results in our analysis hence “count” variable has been transformed and standardized using boxcox transformation.

![image](https://github.com/user-attachments/assets/91075ce0-76d7-44d8-892c-b53167367a75) ![image](https://github.com/user-attachments/assets/c6d3de39-6248-45a0-9681-ea3eebfd5f0b)

           

**4. Visual Analysis:**
**Univariate Analysis:**

a)	Univariate Analysis of continuous variables have been analysed using boxplot and histogram plots. As we are concerned of dependent variable discussion has been limited to “count” variable only.

As per histogram it is evident that data is positively skewed and wider width of histogram indicates higher variability.
As per boxplot we can see that median of data is around 150 and with more no of outliers above the upper whisker, median is closer to lower quartile indicating positive skewness.

![image](https://github.com/user-attachments/assets/57d52d38-f95f-4f44-b565-a02db6936d0a)

  
b)	Distribution of Rental Bike usage was analysed w.r.t “Year” and “Month” and from the plot we can infer that average usage of bikes has been increased in 2012 as compared to 2011. Average usage of bikes improved from the month of May onwards.

![image](https://github.com/user-attachments/assets/0f3aab21-7026-4169-bf60-73b69ff2839e)

 
**Bivariate Analysis:**

In order to analyse the relation between dependent and independent variables bivariate analysis has been carried out and observations are as under:

**a)	Rental Bike “Count” Vs Season:**

 ![image](https://github.com/user-attachments/assets/22f49c22-ea13-4e9b-bc00-6fd781fe816d)

From above bar plot we can infer that Rental Bike usage is more in Fall (30%) followed by Summer (28%). The usage of rental bike is minimum during Spring season (16%).

**b)	Rental Bike “Count” Vs Working Day:**

 ![image](https://github.com/user-attachments/assets/4c27dbb9-fc72-4b1d-88f4-f0fe4d6d8979)


From above pie plot we can infer that Rental Bike usage is more on Working Day as compared to Non-working Day. Usage on working day comprises of 66.60% and is 33.40% on non-working day.

**c)	Rental Bike “Count” Vs Weather:**

![image](https://github.com/user-attachments/assets/b155e305-f67f-4eeb-9356-b35f7865b551)

 
From above barplot it is evident that rental bikes are most used when weather is clear i.e., 70 % of total rental bike usage and is almost NIL when weather is Heavy Rain.

**d) Trend of Rental Bike Usage w.r.t temperature :**

  ![image](https://github.com/user-attachments/assets/60ba0de3-cd89-43c8-80dd-72a1154e2ca6)

From above lineplot we can infer that usage of rental bike increases with increase in temperature. Usage of rental bike peaked when temperature is in the range of 30-40

**e) Correlation between variables :**

 ![image](https://github.com/user-attachments/assets/3fd27f49-5cda-414b-a2f1-fdfe02423344)

As per above heatmap we can infer that variables temp, season, windspeed, casual and registered are positively correlated to “count” variable.


**5. Hypothesis Testing:**

Hypothesis Testing has been carried out to conclude our inferences derived out of visual analysis.

**Note :** 

1. As dependent variable “count” is positively skewed for analysis purpose we are using boxcox transformed data for Hypothesis testing purpose.
2.  Significance Level used for all tests is 5 % .
   
**a) Test to check if rental bike usage is dependent on season:**

As we are comparing one numerical variable i.e., “count” against more than two categories of categorical variable “season” let’s proceed with ANOVA Test after checking our assumptions.

Even though “count” data is in Gaussian distribution there is no equality in variances among the groups hence proceeded with Kruskal Wallis Test. Test results are as under: 

![image](https://github.com/user-attachments/assets/337abb16-931d-4ae5-b0e7-9ef04394863c)

 
**Conclusion: Rental Bike Usage varied based on season.**

**b) Weather Vs Rental Bike Usage:**

As we are comparing one numerical variable i.e., “count” against more than two categories of categorical variable “weather” let’s proceed with ANOVA Test after checking our assumptions.
Even though “count” data is in Gaussian distribution there is no equality in variances among the groups hence proceeded with Kruskal Wallis Test. Test results are as under:

![image](https://github.com/user-attachments/assets/532a0ec5-5441-4fa4-89e5-67bffd822cfe)

**Conclusion : Rental Bike Usage is dependent on weather.**

**c) Working Day Vs Rental Bike Usage:**

As we are comparing one numerical variable i.e., “count” against a categorical variable with two categories lets proceed with Two Sample Independent T-Test.
As we already know that transformed “count” is in Gaussian distribution we need to conduct the Levene Test to check the equal variances between working and non-working day groups. Test results are as under:

![image](https://github.com/user-attachments/assets/a3635795-4d9f-416e-a824-2af56e0c31eb)
 
**Conclusion: Rental Bike Usage is more on working day as compared to non working day.**

**d) Season vs Weather dependency Test :**

As season and weather variables are categorical in order to check dependency between these variables Chisquared Test was conducted and the results of the test are as under:

![image](https://github.com/user-attachments/assets/e372caa1-c2e3-4f49-be76-c7e1ebd8c985)
 
**Conclusion : Season and weather are dependent on each other.**

**e) Rental Bike count Vs Temperature :**

In order to check the dependency of temperature on rental bike usage, continuous variable “Temp” was converted to categorical with the help of binning and Kruskal Wallis Test has been carried out. Test results are as under :

![image](https://github.com/user-attachments/assets/1190490e-89f3-41df-b600-484bad3d4798)
 
**Conclusion: Rental Bike Usage varies based on Temperature.**

**f) Rental Bike count Vs Humidity :**

In order to check the dependency of temperature on rental bike usage, continuous variable “humidity” was converted to categorical with the help of binning and Kruskal Wallis Test has been carried out. Test results are as under :

![image](https://github.com/user-attachments/assets/627ac9e3-2766-42dc-b8fd-c8a4dbb0e76b)
 
**Conclusion: Rental Bike Usage varies based on Humidity.**


**6. Recommendations:**

From the Visual analysis and Hypothesis Testing we can conclude that :

a) Rental Bike Usage is dependent on season and weather. Usage of the electric bikes is more in Fall and Summer seasons as weather during these seasons is Clear. Hence company should focus on maintaining more no of bikes in these seasons and weather conditions.

b) Promotional activities like giving offers, discounts or conducting special campaigns during above mentioned seasons will help to boost the revenue of company.

c) As per analysis Casual users contribute to 20 % of total usage as compared to 80 % for registered users. Company can implement one time registration offers to increase the registration count of the users. 

d) As per pie plot and Two Sample Independent T Test its evident that usage of rental bikes on working day is more than non working day. In order to improve the usage of bikes on non working day we can make discount offers to those who used bikes throughout the week.

**Dataset Used**:

The datasets used include:

bike_sharing.csv

**Tools and Technologies used :**

The tools used in this project include:

Python - This was needed to conduct Data Quality Assessment and also for Data Cleaning processes. With Python libraries pandas, matplotlib, seaborn exploratory data analysis of the datasets and to gain useful insights from the data was possible.

**Built With:**

Python 3.10.12

**Authors**

J Siva Teja
