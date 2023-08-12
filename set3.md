# SQL Practice Problems for Rides Table

This README file provides a set of SQL practice problems focusing on the **`Rides`** table. Each problem is accompanied by a brief description and the SQL query required to solve it.

## Rides Table Schema

```sql
CREATE TABLE Rides (
    id INT PRIMARY KEY,
    driver_id INT,
    passenger_id INT,
    start_location VARCHAR(255),
    end_location VARCHAR(255),
    distance DECIMAL(5,2),
    ride_time DECIMAL(5,2),
    fare DECIMAL(6,2)
);


-- Problem 26: Create Rides table
CREATE TABLE Rides (
    id INT PRIMARY KEY,
    driver_id INT,
    passenger_id INT,
    start_location VARCHAR(255),
    end_location VARCHAR(255),
    distance DECIMAL(5,2),
    ride_time DECIMAL(5,2),
    fare DECIMAL(6,2)
);

-- Problem 27: Insert data into Rides table
INSERT INTO Rides (id, driver_id, passenger_id, start_location, end_location, distance, ride_time, fare)
VALUES
    (1, 101, 201, 'City Center', 'Suburbia', 12.5, 25.0, 20.75),
    (2, 102, 202, 'Downtown', 'Airport', 28.0, 40.5, 35.25),
    (3, 103, 203, 'Suburbia', 'City Center', 15.7, 30.0, 25.50),
    (4, 104, 204, 'Office Park', 'Downtown', 9.2, 18.5, 15.75),
    (5, 105, 205, 'Downtown', 'Shopping Mall', 5.3, 10.5, 9.25);

-- Problem 28: Fetch all rides ordered by fare in descending order
SELECT * FROM Rides ORDER BY fare DESC;

-- Problem 29: Calculate total distance and total fare for all rides
SELECT SUM(distance) AS total_distance, SUM(fare) AS total_fare FROM Rides;

-- Problem 30: Calculate average ride_time of all rides
SELECT AVG(ride_time) FROM Rides;

-- Problem 31: Fetch rides with start_location or end_location containing 'Downtown'
SELECT * FROM Rides WHERE start_location LIKE '%Downtown%' OR end_location LIKE '%Downtown%';

-- Problem 32: Count rides for a given driver_id
SELECT COUNT(*) FROM Rides WHERE driver_id = 103;

-- Problem 33: Update fare of the ride with id 4
UPDATE Rides SET fare = 18.0 WHERE id = 4;

-- Problem 34: Calculate total fare for each driver_id
SELECT driver_id, SUM(fare) AS total_fare FROM Rides GROUP BY driver_id;

-- Problem 35: Delete ride with id 2
DELETE FROM Rides WHERE id = 2;
