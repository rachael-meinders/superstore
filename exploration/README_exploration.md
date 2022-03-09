# README

## Data Exploration
Superstore sales data exploration lead to both key insights and  
areas of concern that needed to be addressed before proceeding.  
Some of the info collected is shown below. We will then investigate  
the potentially problematic areas.

## Initial Observations While Filtering by...
Country
  - Sales leaders were US, Australia, France, China, Germany
  - A Majority of countries with lowest sales were in Africa
  - Top 5 countries for gross $ in returns  were identical to  
    the top 5 in Sales  
Order Priority
  - As Order priority became higher, shipping cost inccreased with
    the exception of going from low to medium priority
  - 88% of items fell in to either Medium or High categories
  - Items in the Critical Priority had a 22% higher profit margin
    than the other 3 classes, on average  
Category & Subcategory
  - Wide variation in shipping cost by Subcategory $3.39 for Labels  
    and $92.76 for Tables
  - Paper and Labels were the most profitable, with margins of 
    19.4% and 11.9% respectively
  - Tables were ~20% less profitable than any other Subcategory  

## Concerns
Becoming more familiar with the data revealed two obstacles that
need to be addressed before moving forward with our analysis:

***1. Low-Volume countries will skew the data and lessen our ability  
     to forecast sales***  
     
      To address the first issue we will be creating a dataset including  
      only countries with 500 orders or more, the hypothesis being this  
      will lead to more accurate sales forecasts.  
      
***2. The Subcategory of Tables has an unusually negative profit  
     margin of -24.2%, which is 27.7% lower than the average of 3.5%***  

     The only other Subcategory below -1% is Machines at -4.35%. To address  
     the subcategory of Tables, we seek to answer the following:  

  Is this negative profit margin due to bad data?  
   
    - The data seems to be accurate. No extreme outliers are pulling the average  
    down and Tables tend to cost more to ship- the average cost to ship is $92.76,  
    which is over 3 times higher than the average for other categories, $29.27  
    - Info is not included on if the shipping cost is instead incurred by  
    the customer. However, even if 100% of the avg shipping cost ($92.76)  
    was added the the avg Table sale of $879.26 that would only lead to a margin   
    improvement from -24.2% to -13.65% for Tables. It would still be the least  
    profitable by over 9%.  

  If the data is accurate, why is such an unprofitable Subcategory allowed to continue to operate?  
  
    Tables may be a "Loss Leader", meaning they bring customer traffic to other  
    (potentially more profitable) products. For example, it might seem intuitive  
    that customers that purchase tables also buy Chairs. There is substantial  
    evidence of this:
  
  There were 861 orders in which Tables were sold, and 3434 in which chairs were sold.  
  
  ![image](https://user-images.githubusercontent.com/91306342/157396117-50a3badd-9580-462d-9630-cc01ca85d5bc.png)  
  
  There were 25728 unique orders.  
  
  ![image](https://user-images.githubusercontent.com/91306342/157396664-9dc8fb68-a151-4925-a816-3ba3f78ba18e.png)  

  While only looking at orders including tables or chairs  
  
  ![image](https://user-images.githubusercontent.com/91306342/157399114-2fbf0392-0410-449d-a736-d980541d5520.png)  
  
  We created a dataframe grouped by Order ID and looked only at orders in which both  
  subcategories were sold.  
  
  ![image](https://user-images.githubusercontent.com/91306342/157397361-0b864fd4-2dcf-4710-a8f4-efecaa130fbc.png)  

Of the 25728 TOTAL Order in our dataframe, 3434 contained chairs (13%)  
Of the 861 orders containing Tables, 322 of them contained chairs (37%)  
***People who bought tables were almost 3 times more likely to buy chairs***  
  
  
## Moving Forward
Given the above, we will move in to hypothesis testing with an original cleaned  
dataframe and another only containing countries with 500 or more orders. The Sub-  
category Tables will remain in our analysis despite its extremely low profit margin  
because bad data was not the cause of this outlier and there is evidence Tables  
could be a [Loss Leader](https://en.wikipedia.org/wiki/Loss_leader).  
