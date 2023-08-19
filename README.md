# DataScience_Portfolio


# Data Science Salary Estimator: Project Overview 
* Created a tool that estimates data science salaries (MAE ~ $ 12K) to help data scientists negotiate their income when they get a job.
* Downloaded already scraped data of over 1000 job descriptions from glassdoor for my analysis
* Performed exploratory data analysis to establish relevant relationships between variables. 
* Built appropriate machine learning models (linear multiple regression, lasso regression, random forest regressor) and optimized using the GridsearchCV to reach the best model 


## Code and Resources Used 
**Python Version:** 3.7  
**Packages:** pandas, numpy, sklearn, matplotlib, seaborn.  
**Softwares:**  Spyder, Jupyter Notebook


## Dataset Variables
*	Job title
*	Salary Estimate
*	Job Description
*	Rating
*	Company 
*	Location
*	Company Headquarters 
*	Company Size
*	Company Founded Date
*	Type of Ownership 
*	Industry
*	Sector
*	Revenue
*	Competitors 


## Data Cleaning
After importing the data, I needed to clean it up so that it was usable for our model. I made the following changes and created the following variables:

*	Parsed numeric data out of salary 
*	Made columns for employer provided salary and hourly wages 
*	Removed rows without salary 
*	Parsed rating out of company text 
*	Made a new column for company state 
*	Added a column for if the job was at the company’s headquarters 
*	Transformed founded date into age of company 
*	Made columns for if different skills were listed in the job description:
    * Python  
    * R  
    * Excel  
    * AWS  
    * Spark 
*	Column for simplified job title and Seniority 
*	Column for description length 


## Exploratory Data Analysis
I looked at the distributions of the data and the value counts for the various categorical variables. Below are a few highlights from the pivot tables. 


## Model Building 
First, I transformed the categorical variables into dummy variables. I also split the data into train and tests sets with a test size of 20%.   

I tried three different models, performed cross-validation and evaluated them using Mean Absolute Error. 
I chose MAE because it is relatively easy to interpret and outliers aren’t really bad.

I tried three different models:
*	**Multiple Linear Regression** – Baseline for the model
*	**Lasso Regression** – Because of the sparse data from the many categorical variables, I thought a normalized regression like lasso would be effective.
*	**Random Forest** – Again, with the sparsity associated with the data, I thought that this would be a good fit. 


## Model performance
The Random Forest model far outperformed the other approaches on the test and validation sets. 
*	**Random Forest** : MAE = 12.46
*	**Linear Regression**: MAE = 18.82
*	**Lasso Regression**: MAE = 19.67

