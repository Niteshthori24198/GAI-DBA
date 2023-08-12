# SQL Practice Problems for Restaurants Table

This README file provides a set of SQL practice problems focusing on the **`Restaurants`** table. Each problem is accompanied by a brief description and the SQL query required to solve it.

## Restaurants Table Schema

```sql
CREATE TABLE Restaurants (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    cuisine_type VARCHAR(100),
    location VARCHAR(255),
    average_rating DECIMAL(3,2),
    delivery_available BOOLEAN
);



-- Problem 16: Create Restaurants table
CREATE TABLE Restaurants (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    cuisine_type VARCHAR(100),
    location VARCHAR(255),
    average_rating DECIMAL(3,2),
    delivery_available BOOLEAN
);

-- Problem 17: Insert data into Restaurants table
INSERT INTO Restaurants (id, name, cuisine_type, location, average_rating, delivery_available)
VALUES
    (1, 'Italiano Delights', 'Italian', 'New York', 4.5, TRUE),
    (2, 'Sushi Haven', 'Japanese', 'Los Angeles', 4.8, TRUE),
    (3, 'Spice Bazaar', 'Indian', 'London', 4.2, FALSE),
    (4, 'Burger Joint', 'American', 'Chicago', 4.0, TRUE),
    (5, 'Cafe Paris', 'French', 'Paris', 4.7, TRUE);

-- Problem 18: Fetch all restaurants ordered by average_rating in descending order
SELECT * FROM Restaurants ORDER BY average_rating DESC;

-- Problem 19: Fetch restaurants with delivery_available and average_rating > 4
SELECT * FROM Restaurants WHERE delivery_available = TRUE AND average_rating > 4;

-- Problem 20: Fetch restaurants with NULL cuisine_type
SELECT * FROM Restaurants WHERE cuisine_type IS NULL;

-- Problem 21: Count restaurants with delivery_available
SELECT COUNT(*) FROM Restaurants WHERE delivery_available = TRUE;

-- Problem 22: Fetch restaurants with location containing 'New York'
SELECT * FROM Restaurants WHERE location LIKE '%New York%';

-- Problem 23: Calculate average average_rating of all restaurants
SELECT AVG(average_rating) FROM Restaurants;

-- Problem 24: Fetch top 5 restaurants by average_rating in descending order
SELECT * FROM Restaurants ORDER BY average_rating DESC LIMIT 5;

-- Problem 25: Delete restaurant with id 3
DELETE FROM Restaurants WHERE id = 3;
