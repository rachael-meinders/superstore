# Global Superstore Analysis

## Overview
Our data [Superstore Data Sets](https://data.world/tableauhelp/superstore-data-sets) was found on data.world. This dataset contained 51,290 line items within 25728 unique orders. There were 22 columns containing Sales data relating to location, revenue, product info and buyer info. The three main categories of product in this dataset are Furniture, Office supplies, and Technology. A supplemental dataset containing a list of the returned orders was also included.  

Unforunately, essentially no context was provided for this dataset. An original data source was not provided, nor was the "superstore" name, background, or history. Because of this, we are taking this data with a grain of salt.

## Analysis Methodology
OUr analysis for the data was performed with the following steps:
1. [Initial Tableau exploration](https://github.com/rachael-meinders/superstore/tree/main/tableau_exploration)
2. [Cleaning](https://github.com/rachael-meinders/superstore/tree/main/cleaning)
3. [Python exploration](https://github.com/rachael-meinders/superstore/tree/main/exploration)
4. [Linear & logistic regresion](https://github.com/rachael-meinders/superstore/tree/main/linear_logistic_regression)
5. [Forecasting](https://github.com/rachael-meinders/superstore/tree/main/prophet_analysis)

For more details about the decisions and specific processes used, please click the above links to be taken to that specific section of the repo.

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

## Hypotheses
1. Using only orders from countries with >500 cumulative orders would provide a more accuracy prediction that using orders from all countries. We believed that our smaller countries were skewing results from our more common order countries.
2. Although tables were the sub-category with the lowest profit margin by far, they act as loss leader. That is, they draw in business and encourage order additional, more profitable sub-categories, such as chairs.
3. Given our large amount of transactional, time-series data, our future sales and profit can be accurately predicted.

## Results
#### All Orders vs Top Countries
Based on our linear regression, we are unable to suppor the hypothesis that using ounly the top countries was a more accurate predictor for sales, profit, & shipping costs. The r² scores for each of these were slightly worse (0.01) for our top countries than for all orders. The logistic regression accuracy scores were essentially the same for both sets of orders, so we cannot confidently conclude that one is better than the other for predicting order returns.

All orders
![regression_all_orders](https://user-images.githubusercontent.com/90879979/157745253-1be3b075-9d22-4f24-a67a-39b7f7babe54.png)

Orders from top countries
![regression_top_countries](https://user-images.githubusercontent.com/90879979/157745263-779ea85e-1682-476c-b721-2615df00ecc6.png)

#### Tables - loss leader
Our analysis was able to identify that, of our total unique orders, 13% contained chairs. However, of the orders that included tables, 37% contained chairs. This does indicate order tables does make our customers considerably more likely to order chairs, which have an average profit margin of 2.47%. At this time, further exploration is needed to make the same conclusion for other sub-categories.
![tables_total_orders](https://user-images.githubusercontent.com/90879979/157745283-27805c58-126c-49b0-bac1-93cd7b8e8489.png)

![tables_conclusion](https://user-images.githubusercontent.com/90879979/157745302-6fc9542b-494a-48af-a4a4-0639f093a6b2.png)

#### Forecasting
Based on our Prophet analysis, our data is not strong enough to provide accurate, long-term predictions. We believe this is due to our somewhat short length of timeseries data - only 4 years. If we had any way to find more data across more time, our forecasting and prediction would likely be far stronger and our confidence interval can be tightened.
![prophet_profit](https://user-images.githubusercontent.com/90879979/157745318-b6bdb8ff-5c7b-45a9-b5c3-90c6da5bbf29.png)

## Recommendations for Further Analysis
Ultimately, we believe that our analysis could be far stronger with more data across a long period of time. Additional data regarding costs (such as cost of goods, labor, marketing & advertising, customs duties, cost of storing, etc.) would surely creater a larger, clearer picture of our superstore's profitbality.
- With more time, our analysis could be expanded to delve into machine learning. 
- With such strong seasonlaity for sales on Mondays, our marketing & advertising departments should perform a cost-benefit analysis of running more ads to encourage more orders on Monday.
