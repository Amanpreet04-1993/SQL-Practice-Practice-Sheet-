# SQL-Practice-Practice-Sheet-

Data Analytics - Postgre SQL

    CREATE TABLE Sales (
    SaleID INT PRIMARY KEY,
    Product VARCHAR(50),
    Quantity INT,
    Price DECIMAL(10, 2),
    SaleDate DATE
    );

    INSERT INTO Sales (SaleID, Product, Quantity, Price, SaleDate) VALUES
    (1, 'Widget A', 3, 10.00, '2024-01-01'),
    (2, 'Widget B', 5, 15.00, '2024-01-02'),
    (3, 'Widget A', 2, 10.00, '2024-01-03'),
    (4, 'Widget C', 1, 20.00, '2024-01-04'),
    (5, 'Widget B', 4, 15.00, '2024-01-05');


    SELECT * FROM public.sales
    ORDER BY saleid ASC 

Aggregate Functions - 

     #Sum
    Select sum(quantity * price) as Totalsales 
    from sales;

Ans - 205.00

    #Avg
    select avg(price) as avgprice
    from sales;
Ans - 14.0000

    #Count 
    select count (saleid) as count
    from sales;
    
Ans - 5

    #Max 	
    select max(quantity) as Highest
    from sales;

Ans - 5

    #Min 	
    select min(quantity) as Lowest
    from sales;

Ans - 1
