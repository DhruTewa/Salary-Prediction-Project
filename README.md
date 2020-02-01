# Salary-Prediction-Project

## Problem Defination
This project is to examine a set of job postings with salaries and then predict salaries for a new set of job postings. Our job is as a data scientist is to create a model which predict the salaries for the job posting.

## Discover the Data

The dataset given hasthree CSV data files:
+ **train_features.csv**
+ **train_salaries.csv**
+ **test_features.csv**

The features in the train_features and test_features are:

+ **jobId**: unique id for each job
+ **companyId**: unique id for each company
+ **degree**: The level of education each observation in the dataset has
+ **major**: the area of study in which the degree is obtained
+ **industry**: the type of industry for each observation
+ **yearsExperience**:Total number of years of experience
+ **milesFromMetropolis**: Distance between the work location and the metropolis city

The features in train_salaries are :
+ **jobId**: unique id for each job
+ **Salaray**: This is the target varialbe

The datasets have total of **two** *numerical variables* and **six** *categorical variables*

## EDA

### Basic observations

+ There are total 8 features in the dataset out of which two features are numerical and six are categorical
+ Total number of observation in the dataset is 100k
+ Salary is our target variable
+ There are no duplicates in the data and there are no values missing in the dataset

### Target variable analysis

+ The target variable is somewhat normally distributed and has some outliers.
+ The **lower** and **upper** limit of the salary feautre is **8.5** and **220.5** respectively.
+ While exploring it was found there were *5 observation* with **0** salary and hence it was showing below lower limit of 8.5, those observation are removed as a part of data cleaning process.
+ Values which are aboe the upper limit are because the jobType of those are higher managment profiles or with higher degree, so we can keep them in our data.

![Salary Distribution](./images/SalaryDistribution.png)



### Training variable analysis

+ The boxplot for jobtype is showing data as normal, the higher the designation then higher the salary
+ There is significant difference in salaries between the high school degree and masters or doctorate degree observation
+ It is obvious, higher is the experience, higher is the salary
+ The more far is the work location from the mertropolitan, the less is the salary

### Features correlation

+ There is a **positive correlation** between:
    + salary Vs jobtype with *.6* value
    + salary Vs degree with *.4* value
    + salary Vs major with *.38* value
    + salary Vs industry with *.3* value
    + salary Vs yearofexperience with *.38* value
+ There is a **negative correaltion** bewteen salary vs milesfrommertropolis with *-.3* value
