Retail Sales Analysis
I built this project in Excel to practise taking a messy dataset from raw CSV to a finished dashboard. The data is 12,575 retail transactions, and I wanted to see what it could tell me about where the money comes from: which categories, which channels, which payment methods, and whether discounts made any difference.
I used Power Query for cleaning, then PivotTables and PivotCharts for the analysis.
Cleaning the data
The raw file had gaps in Item, Price Per Unit, Quantity, Total Spent and Discount Applied, so cleaning was most of the work. I did it all in Power Query so every step is saved and I can rerun it if the data changes.
I started with the basics: fixing data types and checking that every Transaction ID was unique. After that I dealt with the gaps. Missing item names became `Unknown Item`. For prices, quantities and totals, I worked out the missing value whenever the other two were there (price = total / quantity, and so on). If I couldn't calculate a value reliably, I left it blank.
The discount column needed the most care. A blank could mean "no discount" or it could just mean nobody recorded it, and I had no way of knowing which. So I didn't assume. I created a Discount Status field with three values (Discounted, Not Discounted and Unknown) and kept the unknowns separate. I also added Year, Month, Month Name and Year Month columns for the time analysis.
I chose not to fill gaps with estimates. It would have made the dataset look like it had everything but the numbers would have been fake.
The headline numbers
- Total revenue: £1,552,071
- Transactions: 12,575
- Average order value: £129.65
- Units sold: 66,276
What I found
Categories. Butchers and Electric Household Essentials came out on top, but not by much. Revenue was spread fairly evenly, so no single category carries the business.
Over time. Monthly revenue bounced around a bit but stayed steady across the full months, with no clear upward or downward trend.
Online vs in-store. Online brought approximately £791k and in-store brought approximately £761k. Online is still leading but the gap between them is small.
Payment methods. Cash was highest at about £538k. Digital Wallet and Credit Card were nearly identical at about £507k each.
Discounts. Discounted, non-discounted and unknown transactions all brought in similar revenue. Since so many rows had no discount information, I wouldn't read much into this. It doesn't show that discounts don't work, only that this data can't tell us.
Overall, it's a business with steady, well-balanced sales and no obvious weak spot. The most useful thing I could say about discounts is that the business should record that data properly.
What I practised
I practised cleaning and validating data, handling missing values without making anything up, and building a Power Query process I can rerun. I used PivotTables to turn the results into a dashboard. I also wanted to get better at explaining what the numbers actually mean.

