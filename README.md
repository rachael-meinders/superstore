# Global Superstore Analysis

## Overview
Our data [Superstore Data Sets](https://data.world/tableauhelp/superstore-data-sets) was found on data.world. This dataset contained 51,290 line items within 25728 unique orders. There were 22 columns containing Sales data relating to location, revenue, product info and buyer info. The three main categories of product in this dataset are Furniture, Office supplies, and Technology. A supplemental dataset containing a list of the products returned was also included.  

## Initial Findings
- Sales leaders were the United States, Australia, France, China, and Germany
![Total Sales by Country](https://user-images.githubusercontent.com/90434010/157577466-2bcbc3d2-b31d-4284-b762-b191f0e69009.png)

- 88% of items feel into Medium or High Categories
![Order Priority](https://user-images.githubusercontent.com/90434010/157577645-037af8a9-07a6-402e-8e1c-3fce50160eff.PNG)

- Office supplies were the most ordered category of products.
![Total Orders by Category and Subcategory](https://user-images.githubusercontent.com/90434010/157577800-be12f882-4c8c-45b4-8a6d-f45d8e436690.png)

- Copiers and Phones showed the most profit among the sub-categories, with 
![Profit by Subcategory](https://user-images.githubusercontent.com/90434010/157577709-1aa8d741-1aa9-4395-bee1-8818494b684f.png)

Follow this link to learn more about our [Data Exploration](https://github.com/rachael-meinders/superstore/blob/main/exploration/README_exploration.md) process.

## Logistic and Linear Regression
Logistic and Linear regression was performed with sales, profit, and shipping cost. The regression for sales was the most accurate, with shipping costs closely behind, then profit as last. We performed logistic regression to determine if an order was returned. While looking at the test/train split, it became very obvious that our data was unbalanced with only 4.5% of the train data being returned. To address this, we turned to over & undersampling.

Follow this link to learn more about our [Logistic and Linear Regression](https://github.com/rachael-meinders/superstore/blob/main/linear_logistic_regression/README_regression.md)


## Hypothesis
We intend to identify highly profitable products, geographic locations, customers, market segments, and timeframes. We also want to identify the products and customers that result in high return rates in effort to reduce associated expenses.
## Approach
Currently, we plan on heavily using Pandas, as well as MatPlotLib. Down the line, we do plan on using both supervised and unsupervised machine learning. Supervised ML would involve predicting specific items and orders that will be returned, while unsupervised ML would involve clustering the orders by something like profit. We do plan on storing this data in an SQL database.



