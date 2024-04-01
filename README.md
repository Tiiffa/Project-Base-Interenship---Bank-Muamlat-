Project Base Internship Bank Muamalat - Create tabel master 

CREATE TABLE Bank_Muamalat.table_master AS
  SELECT
  o.Date as order_date, 
  pc.CategoryName as category_name, 
  p.ProdName as product_name,
  p.Price as product_price, 
  o.Quantity as order_qty,
  (o.Quantity*p.Price) as total_sales,
  c.CustomerEmail as cust_email,
  c.CustomerCity as cust_city,
  FROM Bank_Muamalat.Customers as c
  INNER JOIN Bank_Muamalat.Orders as o
  on c.CustomerID = o.CustomerID
  INNER JOIN  Bank_Muamalat.Products as p 
  on o.ProdNumber = p.ProdNumber
  INNER JOIN Bank_Muamalat.ProductCategory as pc 
  on p.Category = pc.CategoryID
  ORDER BY Date ASC;
