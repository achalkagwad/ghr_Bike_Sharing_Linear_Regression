# Bike_Sharing_Linear_Regression
This assignment is a programming assignment wherein you have to build a multiple linear regression model for the prediction of demand for shared bikes. 

## Table of Contents
  * [What: Project Overview](#what-project-overview)
  * [Why: Motivation](#why-motivation)
  * [How: Process Involved](#how-process-involved)
  * [Project Problem Statement Description](#project-problem-statement)
  * [Directory Tree](#directory-tree)
  

## WHAT: Project Overview 
This assignment is a programming assignment wherein you have to build a multiple linear regression model for the prediction of demand for shared bikes.We will be using Python.

## WHY: Motivation
This project was part of Upgrads PGDDS(Post Graduate Program in Data Science) with IIITB University Bangalore

## HOW: Process Involved
- This section mentions EDA Process, ML algorithms, Libraries used if any etc
- I used simple Python programming knowledge with numpy, pandas and lambda functions.
- I used data visualization libraries: `seaborn` and `matpotlib` for this project.
- After performing EDA I have got a hang of which features are important and go into the model to explain it better w.r.t to **target variable `cnt`(Count).**
- The `cnt` variable indicates the total number of bike rentals, including both casual and registered. 
- I have first built a model using RFECV and RFE- the automated way to see what RFECV recommends us, later built manual model and finally used model selection and model evaluation techniques.
- The manual Linear Regression Model is built using manual iterations of addition and deletion of features based on p_values and VIF(Variance Inflation Factors) of features to get the optimum R2 score at the same time least number of features which explains the model to business well. (Bias vs Variance Tradeoff)

## Project Problem Statement

### Problem Statement
A bike-sharing system is a service in which bikes are made available for shared use to individuals on a short term basis for a price or free. Many bike share systems allow people to borrow a bike from a "dock" which is usually computer-controlled wherein the user enters the payment information, and the system unlocks it. This bike can then be returned to another dock belonging to the same system.

A US bike-sharing provider BoomBikes has recently suffered considerable dips in their revenues due to the ongoing Corona pandemic. The company is finding it very difficult to sustain in the current market scenario. So, it has decided to come up with a mindful business plan to be able to accelerate its revenue as soon as the ongoing lockdown comes to an end, and the economy restores to a healthy state. 

In such an attempt, BoomBikes aspires to understand the demand for shared bikes among the people after this ongoing quarantine situation ends across the nation due to Covid-19. They have planned this to prepare themselves to cater to the people's needs once the situation gets better all around and stand out from other service providers and make huge profits.

They have contracted a consulting company to understand the factors on which the demand for these shared bikes depends. Specifically, they want to understand the factors affecting the demand for these shared bikes in the American market. The company wants to know:

Which variables are significant in predicting the demand for shared bikes.
How well those variables describe the bike demands
Based on various meteorological surveys and people's styles, the service provider firm has gathered a large dataset on daily bike demands across the American market based on some factors. 

### Business Goal:
You are required to model the demand for shared bikes with the available independent variables. It will be used by the management to understand how exactly the demands vary with different features. They can accordingly manipulate the business strategy to meet the demand levels and meet the customer's expectations. Further, the model will be a good way for management to understand the demand dynamics of a new market. 

### Data Preparation:

- You can observe in the dataset that some of the variables like 'weathersit' and 'season' have values as 1, 2, 3, 4 which have specific labels associated with them (as can be seen in the data dictionary). These numeric values associated with the labels may indicate that there is some order to them - which is actually not the case (Check the data dictionary and think why). So, it is advisable to convert such feature values into categorical string values before proceeding with model building. Please refer the data dictionary to get a better understanding of all the independent variables.
 
- You might notice the column 'yr' with two values 0 and 1 indicating the years 2018 and 2019 respectively. At the first instinct, you might think it is a good idea to drop this column as it only has two values so it might not be a value-add to the model. But in reality, since these bike-sharing systems are slowly gaining popularity, the demand for these bikes is increasing every year proving that the column 'yr' might be a good variable for prediction. So think twice before dropping it. 

### Model Building

In the dataset provided, you will notice that there are three columns named 'casual', 'registered', and 'cnt'. The variable 'casual' indicates the number casual users who have made a rental. The variable 'registered' on the other hand shows the total number of registered users who have made a booking on a given day. Finally, the 'cnt' variable indicates the total number of bike rentals, including both casual and registered. **The model should be built taking this 'cnt' as the target variable.**

### Model Evaluation:
When you're done with model building and residual analysis and have made predictions on the test set, just make sure you use the following two lines of code to calculate the R-squared score on the test set.

```
from sklearn.metrics import r2_score
r2_score(y_test, y_pred)
``` 

where y_test is the test data set for the target variable, and y_pred is the variable containing the predicted values of the target variable on the test set.
Please don't forget to perform this step as the R-squared score on the test set holds some marks. The variable names inside the 'r2_score' function can be different based on the variable names you have chosen.



<!--## Directory Tree 
```
├── app 
│   ├── __init__.py
│   ├── main.py
│   ├── model
│   ├── static
│   └── templates
├── config
│   ├── __init__.py
├── processing
│   ├── __init__.py
├── requirements.txt
├── runtime.txt
├── LICENSE
├── Procfile
├── README.md
└── wsgi.py
```
-->

## Directory Tree
```
|--   app
|     |-- Readme.md 
|     |-- notebooks -- main.py <-This is the main python jupyter notebook where execution of project starts
|     |-- data <-- If this folder is absent, data is larger than 100MB, have to use GIT LFS
|          |-- raw -- day.csv <- This has input data for the project
|     |-- references <- This has Data dictionaries, manuals, and all other explanatory materials.
|     |-- reports <- Generated analysis as HTML, PDF, LaTeX, etc.
|           |-- figures <- Generated graphics and figures to be used in reporting
|     |-- presentations <-Manually created presentations for business users,stake holders in pptx,pdf etc
|           |-- images <- Manual images obtained from various sources for presentation & other checkpoints
```
