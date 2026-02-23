# Power-BI-Data-Measures
// 1. Total Sales Amount
Total Sales = SUMX(    Sales,  Sales[Quantity] * RELATED(Product[UnitPrice])*(1-Sales[Discount]))
// 2. Total Quantity Sold
Total Quantity = SUM(Sales[Quantity])
// 3. Average Discount
Average Discount = AVERAGE(Sales[Discount])
// 4. Number of Transactions
Transaction Count = COUNTROWS(Sales)
// 5. Average Transaction Value
Avg Transaction Value = DIVIDE([Total Sales], [Transaction Count], 0)
// 6. Unique Products Sold
Unique Products = DISTINCTCOUNT(Sales[ProductID])
// 7. Unique Customers
Unique Customers = DISTINCTCOUNT(Sales[CustID])
// 8. Maximum Sale Amount
Max Sale = MAXX(Sales, Sales[Quantity] * RELATED(Product[UnitPrice])*(1-Sales[Discount]))
// 9. Minimum Sale Amount
Min Sale = MINX(Sales, Sales[Quantity] * RELATED(Product[UnitPrice])*(1-Sales[Discount]))
// 10. Average Sale per Customer
Avg Sale per Customer = DIVIDE([Total Sales], [Unique Customers], 0)
// 11. Revenue per Product
Revenue per Product = DIVIDE([Total Sales], [Unique Products], 0)

