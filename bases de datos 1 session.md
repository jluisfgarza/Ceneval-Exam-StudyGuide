![NorthwindSchema](/img/NorthwindSchema.jpg)

> 1. List product name

> 2. List product name and category Name

```SQL
SELECT productName, categoryName
FROM Products P, Categories C
WHERE P.categoryID = C.categoryID
```

> 3. List ProductID and total quantity of each product sold

> 4. List total sales for each product (Product Name, sales amount (use discount in calculation, for example discount=.20))

```SQL
SELECT P.productName, SUM(quantity * initprice * (1 - discount))
FROM Products P, [Order Details] OD,
WHERE P.ProductID = OD.ProductID
GROUP BY P.productID, ProductName
HAVING SUM(quantity * unitPrice * (1 - discount)) > 10000
ORDER BY
```

> 5. List total sales for each customer (Customer Name (companyName), sales amount ( use discount in calculation, for example discount=.20))

> 6. SQL to insert a record in ORDER DETAILS table

```SQL
INSERT INTO [Order Details]
  VALUES (100,14,_,_,_)
```

> 7. SQL to delete a record from customers (customer does not have orders) you can choose the customerid you will delete

```SQL
DELETE FROM Curstomers
  WHERE customerID NOT IN (SELECT customerID, FROM Orders)
```

> 8. SQL to delete a record from customers (customer DOES have orders) you can choose the customerid you will delete

## BONUS

1. Update product prices +2%

```SQL
  UPDATE Products
    SET unitPrice = unitPrice * 1.2
    WHERE unitPrice > 110 and unitPrice < 150
```
