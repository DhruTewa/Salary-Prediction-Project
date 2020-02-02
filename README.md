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

# Exploratory Data Analysis ([code](https://github.com/DhruTewa/Salary-Prediction-Project/blob/master/Salary%20Prediction%20Project_EDA.ipynb))

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

![Salary Distribution](https://github.com/DhruTewa/Salary-Prediction-Project/blob/master/Images/Salary%20Distribution.png)



### Training variable analysis

+ The boxplot for jobtype is showing data as normal, the higher the designation then higher the salary

![jobType vs salary](https://github.com/DhruTewa/Salary-Prediction-Project/blob/master/Images/jobtype%20_vs_salary.png)

+ There is significant difference in salaries between the high school degree and masters or doctorate degree observation

![degree vs salary](https://github.com/DhruTewa/Salary-Prediction-Project/blob/master/Images/degree%20_vs_salary.png)

+ Salary is also varying depending upon the industry

![industry vs salary](https://github.com/DhruTewa/Salary-Prediction-Project/blob/master/Images/industry%20_vs_salary.png)

+ It is obvious, higher is the experience, higher is the salary

![yearofExperience vs salary](https://github.com/DhruTewa/Salary-Prediction-Project/blob/master/Images/yearofexperience_vs_salary.png)

+ The more far is the work location from the mertropolitan, the less is the salary

![jobType vs salary](https://github.com/DhruTewa/Salary-Prediction-Project/blob/master/Images/milesfrommetropolis_vs_salary.png)

### Features correlation

+ There is a **positive correlation** between:
    + salary Vs jobtype with *.6* value
    + salary Vs degree with *.4* value
    + salary Vs major with *.38* value
    + salary Vs industry with *.3* value
    + salary Vs yearofexperience with *.38* value

+ There is a **negative correaltion** bewteen salary vs milesfrommertropolis with *-.3* value

![Features_Correlation](https://github.com/DhruTewa/Salary-Prediction-Project/blob/master/Images/features_correlation.png)

## Model Developement
We will evaluate algorithms using the Mean Squared Error (MSE) metric. MSE will give a gross idea of how wrong all predictions are.We will use 10-fold cross-validation.

For model developement we are selecting three linear models
- Linear Regression(LR)
- Lasso Regression(LASO)
- Elasctic Net(EN)

The algorithms all use default tuning parameters. By comparing the below table MSE for Linear regression is the lowest and hence we will select it as the baseline model.

|Model |MSE Value|
|------|---------|
|LR    |384.44  |
|LASO  |496.58  |
|EN    |824.97  |

![Model Comparision](https://github.com/DhruTewa/Salary-Prediction-Project/blob/master/Images/model_comparision.png)


## Model Tuning

To improve the performance of algorithms, ensemble methods is used. I have used two ensemble machine learning algorithms:

- **Boosting Method** : Gradient Boosting (GBM).
- **Bagging Method**  : Random Forests (RF)

From we have got following results:

|Model|MSE   |
|-----|------|
|LR   |384.44|
|GBM  |357.16|
|RF   |367.77|

## Model Evaluation

Seeing the above results from the training model we have **357.16** as the lowest **MSE** value and hence is the best model to use for predicting the salary.

## Feature Importance:

By looking at the graph below we can say that *yearofexperience* and *milesfrommetropolitan* are two major factors in predicting the salary.

![Feature Importance](https://github.com/DhruTewa/Salary-Prediction-Project/blob/master/Images/feature_importance.png)






















