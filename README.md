# Different-continent-sales-data-a-local-currency-conversion-to-Danish-kroner.
I N T R O D U C T I O N
You are a data engineer / data scientist for one of Denmark's leading agencies within digital 
marketing and data-driven strategy. You must therefore help Danish e-commerce businesses to 
measure the effectiveness of their digital campaigns.
As a rule, these companies use the reporting interface in Google Analytics (GA) to see the number 
of transactions and revenue broken down by individual campaigns. But for some companies, this is 
not enough. The website may be tracked in such a way that data is not displayed optimally, or the 
company may have a desire to integrate data from GA with other sources, e.g., a CRM or ERP 
system. To help them, you therefore need to extract data via GA’s API and transform them in 
different ways. For this you use R (or Python).
In the present case, a relatively simple data transformation is needed. The customer has tracked 
online purchases in local currency, but now wants to convert these to Danish kroner (DKK). 
Subsequently, the customer wants to see the result in a Power BI dashboard.

T A S K S

1. E X T R A C T H I S T O R I C A L E X C H A N G E R A T E S
Historical daily exchange rates can be downloaded for free from quantmod.com via an API that can 
be accessed via R or Python. R offers a library, quantmod, that makes it easy to use the API. Use 
this library (or an equivalent in Python) to download daily rates that convert the currencies to DKK 
from 1/9 2021 to 30/9 2021. These rates should be used in the next assignment.

2. C O N V E R T U S D T O D K K
GA offers an API that requires authentication. To avoid authentication, you will in this case use a 
(very small) dummy dataset in csv format that could have been extracted from the GA API. The 
dataset shows the number of orders and revenue for each campaign during September 2021.
The attached dataset consists of the following columns: date, source_medium, campaign, currency,
transactions,and transaction_revenue. The latter two show the number of orders and revenue in
local currencies. The columns source_medium and campaign in combination make up unique 
campaigns, while currency is the local currency code needed for matching with the relevant 
exchange rates.
Your task is now to load the csv file into R (or Python), add a column with the exchange rate per 
day, which you extracted in task 1. Then, in another new column, you convert the revenue in local 
currency to DKK.
The resulting table is used in the next task.

3. C A T E G O R I Z A T I O N O F C A M P A I G N S
The customer wants to see the number of orders and revenue for certain types of campaigns. You
are therefore told to group campaigns based on their campaign name (the campaign column).
In the table from task 2, you add a column that divides campaigns into two groups: those starting 
with "00: brand" and all others. The first group gets the value "Brand" and the second "Others".
Finally, the table is saved in a csv file, which will be used in the next and last task.

4 . S I M P L E D A T A V I S U A L I Z A T I O N I N P O W E R B I
The last step is to load the csv file from task 3 into Power BI Desktop. The task is to construct a 
single tab with a single table and a date filter. The table should show "Brand" and "Others" as rows
and two metrics as columns: Number of orders and revenue in DKK. These two metrics should be
defined using DAX. It must be possible to select a period via the date colum
