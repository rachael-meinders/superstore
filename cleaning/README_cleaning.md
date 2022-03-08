# Initial Data Cleaning
Overall, our data was very clean from the start with 24 variables, and 51,290 observations spanning from spring 2012 - end of 2015. The only column that had any null values was Postal Code, which was dropped.

## Altered Columns
- Row ID - dropped due to uselessness
- Order ID - set as index, also moved to orders_dictionary
- Order & Ship Date - converted to datetime
- Customer ID & Name - dropped, moved to orders_dictionary
- Product Name & ID - dropped, moved to orders_dictionary
- Postal Code - dropped, largely null values
- Sales & Profit - cleaned to remove $ and , then converted to float (from string)

All other columns were kept, unaltered at this stage of cleaning.

## Returned Data
Our returned data was cleaned to remove Region (due to redundancy post-merge), and to change "Yes" to 1. This was then merged to our orders dataframe, using Order ID.

## Calculated Columns
We added two calculated columns to our dataframe - Profit Margin Percentage, Returned $ Amount, and Days to Ship.

- Profit Margin Percentage = profit / sales, 0 where profit = 0
- Returned $ Amount = sales amount when returned, otherwise 0
- Days to Ship = ship date - order date

## Top Countries
Our analysis down the line examines if the countries with the least amount of orders skews results. Accordingly, a separate dataframe and .csv was created to hold only orders from countries with >500 total orders (23 countries). Orders from all other countries were dropped.