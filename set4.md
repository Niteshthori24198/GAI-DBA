# SQL Practice Problems for Rides Table (Continued)

This README file provides a set of SQL practice problems focusing on the **`Rides`** table. Each problem is accompanied by a brief description and the SQL query required to solve it.

## Problems and Queries 

```sql
-- Problem 36: Find ride with highest and lowest fare
SELECT * FROM Rides WHERE fare = (SELECT MAX(fare) FROM Rides)
UNION
SELECT * FROM Rides WHERE fare = (SELECT MIN(fare) FROM Rides);

-- Problem 37: Calculate average fare and distance for each driver_id
SELECT driver_id, AVG(fare) AS avg_fare, AVG(distance) AS avg_distance
FROM Rides GROUP BY driver_id;

-- Problem 38: Find driver_ids with more than 5 rides
SELECT driver_id FROM Rides GROUP BY driver_id HAVING COUNT(*) > 5;

-- Problem 39: Find name of driver with highest fare
SELECT D.name
FROM Rides R
INNER JOIN Drivers D ON R.driver_id = D.driver_id
WHERE R.fare = (SELECT MAX(fare) FROM Rides);

-- Problem 40: Find top 3 drivers with highest earnings
SELECT R.driver_id, SUM(R.fare) AS total_earnings
FROM Rides R
GROUP BY R.driver_id
ORDER BY total_earnings DESC
LIMIT 3;

-- Problem 41: Find rides in the last 7 days
SELECT * FROM Rides
WHERE ride_date >= NOW() - INTERVAL 7 DAY;

-- Problem 42: Find rides with end_location not set
SELECT * FROM Rides WHERE end_location IS NULL;

-- Problem 43: Calculate fare per mile for each ride
SELECT id, fare / distance AS fare_per_mile
FROM Rides
ORDER BY fare_per_mile DESC;

-- Problem 44: Return rides with driver's and passenger's names
SELECT R.id, R.driver_id, D.name AS driver_name, R.passenger_id, P.name AS passenger_name
FROM Rides R
LEFT JOIN Drivers D ON R.driver_id = D.driver_id
LEFT JOIN Passengers P ON R.passenger_id = P.passenger_id;

-- Problem 45: Add 'tip' field to Rides table
ALTER TABLE Rides ADD COLUMN tip DECIMAL(5,2);
