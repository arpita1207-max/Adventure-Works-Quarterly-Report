```

# Adventure-Works-Quarterly-Report
```

```
Problem Statement
Adventure Works requires an analysis of quarterly sales, profit margins, and year-on-year revenue. The report highlights top-selling products and top performing Salesperson, detailed Sales of each Category by Country.
```

```
#Data Model
```
![Date Model](https://github.com/user-attachments/assets/66ded848-650a-4896-a314-bc61d64e909c)



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


```
# Insights
1. Total Sales 3.51 M
2. Quantity Sold 6560
3. Profit Margin 1.31%
4. Profit 45.81k
5. Profit Margin decreases year on year.Least Profit Margin -0.60%
6. Top 3 Performing Salesperson Tsvi Reiter,Micheal Blythe,Jillian Carson
7. Top 3 Selling Products Mountain-200 Black,38,Mountain-100 Black,42,Mountain -100 Black,44
8. Top Region by Sales is USA and Cananda
9. 45.40% Revenue comes from Accessories,20.35% comes from Clothing and 19.62% comes from Components
10. 83.28% Profit Margin  comes from Components followed by 12.10% Profit Margin from Clothing
11. Profit Margin comes most from these SubCategory Mountain Frames Road Frames and Wheels for Component Category
12. Profit Margin comes most from these SubCategory Shorts,Tight and Gloves for Clothing Category   
```
