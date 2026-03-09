##📐 Key DAX Measures

Below are some of the main DAX measures used to analyze the checkout funnel and estimate business impact.

### 1️ Total units sold
Total Units Sold = 
CALCULATE (
    COUNTROWS ( events1 ),
    events1[type] = "purchase"
)


Cart Abandonment Rate = 
DIVIDE (
    [Sales Transactions],
    [Sessions with Add-to-Cart]
)

Indicates the proportion of users who abandon the purchase after adding products to their cart.
