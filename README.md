# Personal-Bank-Loan-Modelling
This project deals comprehensive analysis of personal bank loan modeling, employing various machine learning algorithms. The project delves into data analysis and employs logistic regression, decision trees, random forest, and AdaBoost techniques.Through rigorous examination, it provides insights into credit risk assessment and lending strategies.
## Dataset and Description
The dataset is taken from the kaggle. we will solve a problem for classifying personal loans on the **Thera-Bank dataset**. The majority of Thera-Bank's customers are depositors. The number of customers who are also borrowers (asset customers) is quite small, and the bank is interested in quickly expanding this base to do more loan business while earning more through loan interest. In particular, management wants to look for ways to convert its liability customers into retail loan customers while keeping them as depositors. A campaign the bank ran last year for deposit customers showed a conversion rate of over 9.6% success. This has prompted the retail marketing department to develop campaigns with better target marketing to increase the success rate with a minimal budget. The department would like to develop a classifier that will help them identify the potential customers who are more likely to purchase the loan. This will increase the success rate while reducing the cost of the campaign.

## General Details
The dataset has data on 5000 customers.
We have 14 variables including 13 independent variables and 1 dependent variable which is Personal Loan.
- **ID**: ID of the customer
- **Age:** Age of the customer in completed years
- **Experience:** Amount of work experience in years
- **Income:** Amount of annual income (in thousands)
- **Zipcode:** Postal code in which the client lives
- **Family:** Number of family members
- **CCAvg:** Average monthly spending with the credit card (in thousands)
- **Education:** Education level (1: bachelor's degree, 2: master's degree, 3: advanced/professional degree)
- **Mortgage:** Value of home mortgage, if any (in thousands)
- **Securities Account:** Does the customer have a securities account with the bank?
- **CD Account:** Does the customer have a certificate of deposit account (CD) with the bank?
- **Online:** Does the customer use the internet banking facilities?
- **CreditCard:** Does the customer use a credit card issued by the bank?
- **Personal Loan:** Did this customer accept the personal loan offered in the last campaign? **(Target Variable)**

## Data Analysis Report
- This dataset has 14 variable, 13 are independent and 1 is dependent which is personal loan.
- Dataset has 6 numeric variables namely ID , age, experience, salary ,ccavg and mortgage.
- Dataset has 5 boolean variables namely CreditCard,personal loan,online,CD account & securities account
- Dataset has 3 categorical features namely Family,education,Zip code
- Also, Based on the **Profile_report.html** we can perform univariate as well as bivariate anlysis i.e missing value, correlation, skewness and kurtosis.
- Based on this, we find that there is neither missing nor duplicate value in the data
- The dataset is imbalanced.
  
### Feature Analysis Report
- Family: Around 29% customer family size is 1, 26% is 2, 20% is 3 and 24% is 4
- Education: Around 42% Customer are undergrad ,28% graduate and 30% are having advanced or professional degree.
- ID: This column is uniformly distributed and lacks the necessary information for model building.
- AGE: The mean is around 45 and std is 11.45
- CCAVG: The mean is 1.93 with std is 1.74 and the curve is fairly right skewed.
- Income: The mean is 73.44 with std 46.33 and curve is moderately positive skewed.
- Mortgage: The mean is 56.49 with std 101.71 and curve is highly postive skewed and there are a **lot of outliers.**
- ZIP Code : The column contain noise.
  
### Correlation Analysis
- **Spearman correlation** is used.
- Income is directly correlated with Personal loan
- experience is highly correlated with age
- CCavg is highly correlated with income

### Noise and outlier treatment
- ZIP code contain noise.
- Z score method is used and outliers are trimmed.

### Bivariate Analysis
- The Customer who has certificate of deposit (CD) with the bank appears to take personal loan.
- The Customer having high level of education are more likely to take personal loan.
- No of family member has no significant effect on the Personal loan modelling.
- The customer have or not have a securities account does not have any significant effect on personal loan modelling
- The customer who use or donot use online services does not have any significant effect on personal loan modelling.

## MOdel Building
- CLassifiers used Logistic regression, decision tree, random forest, Adaboost
- Metrics used for evaluation F!_score, Accuracy, Precision, Recall, AUC
- For Feature importance, drop column method is used
- Train test split with stratifiedkfold

### Logistic Regression
- step 1 : standard scaling of training and test data
- step 2 : Hyperparameter tuning
- step 3 : Removing the features with negative importance
- step 4 : tuning the hyperparameters again
- step 5 : Model evaluation
- **Result Achieved** 
  Accuracy :94.28% ;
  Precision	:72.46% ;
  Recall	:57.47% ;
  F1-score	:64.1% ;
  AUC	:95.74%


