# SQL-Practice-Data Analytics-

 - Postgre SQL

Data Query Language (DQL)


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



*********************************************************************************************************************************************

String Function

    CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    Email VARCHAR(100)
    );

.

    INSERT INTO Employees (EmployeeID, FirstName, LastName, Email) VALUES
    (1, ' John ', 'Doe ', ' john.doe@example.com '),
    (2, 'Jane', 'Smith', 'jane.smith@example.com'),
    (3, ' Alice', 'Johnson ', ' alice.j@example.com');

.

    SELECT * FROM public.employees
    ORDER BY employeeid ASC 

1. CONCAT: Combine first name and last name into a full name.
	
       Select employeeid,
	   concat(trim(firstname), ' ', trim(lastname)) as FullName
	   from employees

Ans - 1	"John Doe"
      2	"Jane Smith"
      3	"Alice Johnson"


2. SUBSTRING: Extract the first three characters of the email.

       Select employeeid,
	   substring(trim(email),1,3) as emailprefix
	   from employees

Ans -  1	"joh"
       2	"jan"
       3	"ali"

3. LENGTH: Find the length of each employee's first name.

       Select employeeid,
       length(trim(firstname)) as firstnamelength
       from employees

Ans - 1	4
      2	4
      3	5

4. UPPER: Convert last names to uppercase.

       SELECT EmployeeID, 
       UPPER(TRIM(LastName)) AS LastNameUpper
       FROM Employees;

Ans-  1	"DOE"
      2	"SMITH"
      3	"JOHNSON"

5. LOWER: Convert emails to lowercase.
	
	   SELECT EmployeeID, 
       LOWER(TRIM(Email)) AS EmailLower
       FROM Employees;

Ans - 1	"john.doe@example.com"
      2	"jane.smith@example.com"
      3	"alice.j@example.com"

6. TRIM: Remove spaces from first names.
	
	   SELECT EmployeeID, 
       TRIM(FirstName) AS TrimmedFirstName
       FROM Employees;

Ans - 1	"John"
      2	"Jane"
      3	"Alice"
