# Linear & Logistic Regression

## Pre-processing
After initially cleaning the data, it did still need some pre-processing for regression & machine learning. 

The first thing we addressed was the order date. We started with encoding the order day into day of the week, and reducing it down into order year and order month - all in effort to address the seasonlity exhibited during Prophet analysis. We then dropped the original order date column, and also deleted the ship date as we felt this was made redundant by the order date information combined with the days to ship.
![prophet_profit](https://user-images.githubusercontent.com/90879979/157558073-ea5de008-ef47-4911-85ea-104a22edf04f.png)

The following columns were also dropped.
![image](https://user-images.githubusercontent.com/90879979/157558181-2e2a1059-b664-4efc-8104-af4d93435326.png)

We enoded the following categorical data into binary varibles.
![image](https://user-images.githubusercontent.com/90879979/157558497-8216770e-a90d-452b-9614-df719d46c79b.png)

This preprocessed data was saved to a separate .csv for easy importing.

## Linear Regression
We performed linear regression with sales, profit, and shipping cost. 

### Method
The same process was followed for each target variable.
- Set target & features
- Split into test & train groups
- Fit the model to the train set
- Have the model predict the target
- Examine each variable and its respective coefficient
- Look at the intercept
- Calculate the r² score

### Results
In both cases (examining all orders vs orders from top countries), the regression for sales was the most accurate, with shipping costs closely behind, then profit as last. 
![regression_all_orders](https://user-images.githubusercontent.com/90879979/157560882-da71f0c0-c265-4454-9550-004e5afcf13a.png)

![regression_top_countries](https://user-images.githubusercontent.com/90879979/157560887-aaa2138f-6aec-412f-8b27-da5841780b9e.png)

#### Profit
The lack of success for profit likely is due to the lack of cost information. While shipping costs can play a large part in the total cost, they surely are not the only cost. Not having information relating to the cost of goods and production, cost of storing, and cost of getting new customers and maintaining good business relationships leaves a huge part of the profit picture as a mystery.\
#### Shipping Costs
While order priority, ship mode, and region were somewhat reliable in predicting shipping costs, I think that including encoded countries in future regression would increase the accuracy score. Each country is unique in its customs processes and duty fees that may be incurred. Furthemore, shipping something to Egypt and to South Africa is a difference of over 3,000 miles. Region alone cannot accurately captrue this information for prediction.
#### Sales 
I believe that sales was the most sucessful simply because we have the most data directly surronding that piece of data - item ordered, quantity, discount, order priority.

## Logistic Regression
We performed logistic regression to determine if an order was returned.

### Method
- Set target & features
- Split into test & train groups
- Set target & features
- Split into test & train groups
- Fit the model to the train set
- Have the model predict the target
- Examine each variable and its respective coefficient
- Look at the intercept
- Calculate the r² score

#### Re-sampling
While looking at the test/train split, it became very obvious that our data was unbalanced with only 4.5% of the train data being returned. To address this, we turned to over & undersampling. I tested all five techniques - random over & undersampling, SMOTE, Cluster Centroid, and SMOTEENN - to compare their accuracy scores. For both all orders and top countries, SMOTE was usually the clear winner with SMOTEENN following somewhat closely behind. As a result, these two methods were used for our primary regressions.

## Results
Our un-altered (not resampled) regression was not very successful - it essentially guessed "no" for everything and was always wrong for the "yes"es. This resulted in a normal accuracy score of ~.095, but a balanced accuracy score of ~0.5. Adding in the SMOTE resampling pulls this up to ~0.7 - a significant improvement. SMOTEEN was only a mild iprovement over the un-altered.
