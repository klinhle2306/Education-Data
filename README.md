# Education Inequality

1. Description: This project utilizes two data sets. The primary data set is the EdGap data set from [EdGap.org](https://www.edgap.org/#5/37.875/-96.987). This data set from 2016 includes the average ACT or SAT scores and the socioeconomic characteristics of the school district. The secondary data set consists of the basic information about each school from the [National Center for Education Statistics](https://nces.ed.gov/ccd/pubschuniv.asp).

2. Data: 

  a. EdGap: data: All socioeconomic data (household income, unemployment, adult educational attainment, and family structure) are from the Census Bureau's American Community Survey. [EdGap.org](https://www.edgap.org/#5/37.875/-96.987) reports that ACT and SAT score data is from each state's department of education or some other public data release.

  b. School Information Data: The school data is from the [National Center for Education Statistics](https://nces.ed.gov/ccd/pubschuniv.asp). This data set consists of basic identifying information about schools and can be assumed to be of reasonably high quality. This data set can be accessed [here](https://www.dropbox.com/s/lkl5nvcdmwyoban/ccd_sch_029_1617_w_1a_11212017.csv?dl=0).

 3. Data Preparation: This identifies missing values and imputes data, thus creating a clean dataset version. The first step of this process is to convert some data types into types that are easy to work with and/or to match the data type of two datasets. Since this project aims to answer the question of whether socioeconomic factors affect academic performance, the dataset is made to focus on the prediction 'verage_act'; thus, this process performs the imputation of data on other attributes in the dataset. Using the Multivariate Imputation By Chained Equations algorithm, a method by which we fill in the missing values in a dataset by using information from other columns and making the best guess possible for each one, fills in the NaN in the other attributes in the dataset. This process also splits the dataset into a testing and a training set to prepare for analysis. It exports two cleaned datasets, a training set and a testing set.
 
 4. Analysis: This is the process of answering the subproblem to conclude the main problem. I first want to examine the relationships among all variables. To do this, I plotted a correlation to determine which variable has the most significant relationship with 'average_act.' As a result, 'percent_lunch' is the most deterministic variable for predicting the average ACT score. However, the best subset is tested and selected through a 'best subset selection' algorithm to make this decision more robust. This process loops through all variables and creates a combination of them. Then, each subset is fit and tested to return the r-squared, AIC, and BIC values. With these values, I could determine that the subgroup of percent_college, percent_lunch, percent_married, and rate_unemployment is the most significant at predicting the ACT score.
 
    To enhance the prediction of ACT scores, I introduced a new variable to the dataset. I added region based on the location of the school to answer the question, "Does the region of the school affect the outcome of the ACT score?" After I examine the R squared value between the model with 'region' and the model without 'region', I came to a conclusion that 'region' does not have a strong aspesct on determining the ACT scores. 

 5. Conclusion: 
- Percent Lunch and other variables predict the average ACT score more significantly.
- The added attribute 'region' is not a decisive factor in determining ACT scores.
- This result is not optimal because a few missing factors hinder the performance of the models. The dataset is missing a few important predictors. For example, there is limited data from some states and missing information that some states might or might not require SAT/ACT scores.
