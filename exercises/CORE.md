# Core Warm Up Exercises

Uses sample Tables for query practice.

Setup Tables
```sql
-- Create the Employees Table
CREATE TABLE Employees (
    employee_id INT PRIMARY KEY,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE,
    department VARCHAR(50),
    hire_date DATE
);

-- Create the Products Table
CREATE TABLE Products (
    product_id INT PRIMARY KEY,
    product_name VARCHAR(100) NOT NULL,
    category VARCHAR(50),
    price DECIMAL(10, 2) NOT NULL,
    stock_quantity INT NOT NULL
);

-- Create the Orders Table
CREATE TABLE Orders (
    order_id INT PRIMARY KEY,
    employee_id INT,
    product_id INT,
    quantity INT NOT NULL,
    order_date DATE NOT NULL,
    -- Set up Foreign Keys to link back to the other tables
    FOREIGN KEY (employee_id) REFERENCES Employees(employee_id),
    FOREIGN KEY (product_id) REFERENCES Products(product_id)
);
```

Seed Tables
```sql
-- Insert Sample Employees
INSERT INTO Employees (employee_id, first_name, last_name, email, department, hire_date)
VALUES 
    (1, 'Jane', 'Doe', 'jane.doe@company.com', 'Sales', '2021-03-15'),
    (2, 'John', 'Smith', 'john.smith@company.com', 'Sales', '2022-08-01'),
    (3, 'Alice', 'Johnson', 'alice.j@company.com', 'Support', '2023-01-10');

-- Insert Sample Products
INSERT INTO Products (product_id, product_name, category, price, stock_quantity)
VALUES 
    (101, 'Wireless Mouse', 'Electronics', 25.99, 150),
    (102, 'Mechanical Keyboard', 'Electronics', 89.50, 75),
    (103, 'Ergonomic Desk Chair', 'Furniture', 199.99, 20),
    (104, 'Coffee Mug', 'Accessories', 12.00, 200);

-- Insert Sample Orders
-- (e.g., Employee 1 sold 2 Wireless Mice on 2023-10-01)
INSERT INTO Orders (order_id, employee_id, product_id, quantity, order_date)
VALUES 
    (1001, 1, 101, 2, '2023-10-01'),
    (1002, 1, 103, 1, '2023-10-02'),
    (1003, 2, 102, 1, '2023-10-03'),
    (1004, 2, 104, 5, '2023-10-05'),
    (1005, 1, 101, 1, '2023-10-07');
```

## Basic SELECT Drills

* Select specific columns
* Filter with WHERE
* Sort with ORDER BY
* Use LIMIT
* Use DISTINCT

## Using JOIN

* Find all order by employee
* Find employees with no order
* Count order per employee
* Find products never purchased

