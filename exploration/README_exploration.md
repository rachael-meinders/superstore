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

  1. Low-Volume countries will skew the data and damper our ability  
     to see trends due to low order counts / less datapoints
     
  2. The Subcategory of Tables has an unusually negative profit  
     margin of -24.2%, which is 27.7% lower than the average of 3.5%

To address the first issue we will be creating a dataset including only
countries with 500 orders or more, the hypothesis being this will lead
to more accurate sales forecasts.

To address the subcategory of Tables, we seek to answer the following:
  
  Is this negative profit margin due to bad data?
    The data seems to be good- No extreme outliers are pulling the average up 
    and Tables tend tocost more to ship- the average cost to ship is $92.76,  
    which is over 3 times higher than the average of other categories, $29.27
    *info is not included on if the shipping cost is instead incurred by  
    the customer, but even if 100% of the average shipping cost ($92.76)  
    was added the the avg Table sale of $879 that would only lead to a margin  
    improvement from -24.2% to -13.65%

So we are Paying $
  Should this subcategory still be included in our analysis?
  Do Table sales drive the sale of any other products?
