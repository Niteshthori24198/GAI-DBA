# SQL Practice Problems for Customers Table

This README file provides a set of SQL practice problems focusing on the **`Customers`** table. Each problem is accompanied by the SQL query required to solve it.

## Customers Table Schema

```sql
CREATE TABLE Customers (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100),
    address VARCHAR(255),
    phone_number VARCHAR(50)
);



-- Problem 1: Create Customers table
CREATE TABLE Customers (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100),
    address VARCHAR(255),
    phone_number VARCHAR(50)
);

-- Problem 2: Insert data into Customers table
INSERT INTO Customers (id, name, email, address, phone_number)
VALUES
    (1, 'John Doe', 'john@example.com', '123 Main St', '555-1234'),
    (2, 'Jane Smith', 'jane@example.com', '456 Elm St', '555-5678'),
    (3, 'Alice Johnson', 'alice@example.com', '789 Oak St', '555-9876'),
    (4, 'Bob Williams', 'bob@example.com', '321 Pine St', '555-4321'),
    (5, 'Eva Brown', 'eva@example.com', '654 Birch St', '555-8765');

-- Problem 3: Fetch all data from Customers table
SELECT * FROM Customers;

-- Problem 4: Select name and email fields for all customers
SELECT name, email FROM Customers;

-- Problem 5: Fetch customer by id
SELECT * FROM Customers WHERE id = 3;

-- Problem 6: Fetch customers with names starting with 'A'
SELECT * FROM Customers WHERE name LIKE 'A%';

-- Problem 7: Order customers by name in descending order
SELECT * FROM Customers ORDER BY name DESC;

-- Problem 8: Update address of customer with id 4
UPDATE Customers SET address = '123 New St' WHERE id = 4;

-- Problem 9: Fetch top 3 customers ordered by id ascending
SELECT * FROM Customers ORDER BY id ASC LIMIT 3;

-- Problem 10: Delete customer with id 2
DELETE FROM Customers WHERE id = 2;

-- Problem 11: Count number of customers
SELECT COUNT(*) FROM Customers;

-- Problem 12: Fetch customers skipping the first two, ordered by id ascending
SELECT * FROM Customers ORDER BY id ASC OFFSET 2;

-- Problem 13: Fetch customers with id > 2 and names starting with 'B'
SELECT * FROM Customers WHERE id > 2 AND name LIKE 'B%';

-- Problem 14: Fetch customers with id < 3 or names ending with 's'
SELECT * FROM Customers WHERE id < 3 OR name LIKE '%s';

-- Problem 15: Fetch customers with NULL phone numbers
SELECT * FROM Customers WHERE phone_number IS NULL OR phone_number = '';
