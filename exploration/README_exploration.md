# README

## Data Exploration
Superstore sales data exploration lead to several key insights and  
potentially actionable items.

## Initial Observations While Filtering by...
Country
  - Sales leaders were US, Australia, France, China, Germany
  - A Majority of countries with lowest sales were in Africa
  - Top 5 countries for gross $ in returns  were identical to  
    the top 5 in Sales
Shipping Mode
  - 
Order Priority
  - As Order priority became higher, shipping cost inccreased with
    the exception of going from low to medium priority
  - 
Category & Subcategory

## Concerns
Becoming more familiar with the data revealed two obstacles that
need to be addressed before moving forward with our analysis:

***1. Low-Volume countries will skew the data and lessen our ability  
     to forecast sales due to low order counts / less datapoints***  
     
     To address the first issue we will be creating a dataset including  
     only countries with 500 orders or more, the hypothesis being this  
     will lead to more accurate sales forecasts.
     
***2. The Subcategory of Tables has an unusually negative profit  
     margin of -24.2%, which is 27.7% lower than the average of 3.5%**

The onlty other Subcategory below -1% is Machines at -4.35%. To address  
the subcategory of Tables, we seek to answer the following:
  
  Is this negative profit margin due to bad data?
    The data seems to be good. No extreme outliers are pulling the average up 
    and Tables tend to cost more to ship- the average cost to ship is $92.76,  
    which is over 3 times higher than the average for other categories, $29.27
   *info is not included on if the shipping cost is instead incurred by  
    the customer. However, even if 100% of the avg shipping cost ($92.76)  
    was added the the avg Table sale of $879.26 that would only lead to a margin  
    improvement from -24.2% to -13.65% for Tables. It would still be the least  
    profitable by over 9%

  If the data is good, why is such an unprofitable Subcategory allowed to  
  continue to operate?
  One Theory is that Tables are a "Loss Leader", meaning they bring customer  
  traffic, which can drive sales of other more profitable products.
  One more obvious theory is Tables drive the sales of Chairs.
  
  ![image](https://user-images.githubusercontent.com/91306342/157396117-50a3badd-9580-462d-9630-cc01ca85d5bc.png)![image](https://user-images.githubusercontent.com/91306342/157396664-9dc8fb68-a151-4925-a816-3ba3f78ba18e.png)


![image](https://user-images.githubusercontent.com/91306342/157399114-2fbf0392-0410-449d-a736-d980541d5520.png)  
  ![image](https://user-images.githubusercontent.com/91306342/157397361-0b864fd4-2dcf-4710-a8f4-efecaa130fbc.png)



  Of the 
  
  
