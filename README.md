```

# Adventure-Works-Quarterly-Report
```

```
Problem Statement
Adventure Works requires an analysis of quarterly sales, profit margins, and year-on-year revenue. The report highlights top-selling products and top performing Salesperson, detailed Sales of each Category by Country.
```

```
# DAX Query
Total Sales = SUM(Sales[Total Sales])
Quantity Sold = SUM(Sales[Quantity])
Profit = [Total Sales]-[total cost]
total cost = SUM(Sales[Cost])
Profit Margin = [Profit]/[Total Sales]

Revenue YoY % = 
VAR RevenuePreviousYear = CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Date'[Date]))
RETURN
DIVIDE(
    [Total Sales] - RevenuePreviousYear, RevenuePreviousYear,0)

Top 3 Salespersons = 
VAR 
RankigContext = VALUES(Salesperson[Salesperson])
RETURN 
CALCULATE([Total Sales], TOPN(3,
ALL(Salesperson[Salesperson]), [Total Sales]),
RankigContext)

Best Product = 
VAR 
RankigContext = VALUES(Products[Product])
RETURN 
CALCULATE([Total Sales], TOPN(3,
ALL(Products[Product]), [Total Sales]),
RankigContext)
```

```
Executive Summary
```

![Exec Summary](https://github.com/user-attachments/assets/f5324a70-b1fb-4618-877d-f06273a81aa0)

```
Sales Detailed
```
![Sales Detailed](https://github.com/user-attachments/assets/54914822-6d60-4fea-a9ae-3dcffb4a94fb)

```
Category Detailed
```
![category detailed](https://github.com/user-attachments/assets/8210738c-0738-472a-823f-18ba79ce138b)


