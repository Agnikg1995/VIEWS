1. Create a view named customer_info for the Customer table that displays Customer’s Full name and email address. Then perform the SELECT operation for the customer_info view.
-- Create the customer_info view
CREATE VIEW customer_info AS
SELECT CONCAT(First_name, ' ', Last_name) AS Full_Name, Email
FROM Customer;
-- Perform SELECT operation on customer_info view
SELECT * FROM customer_info;
2. Create a view named US_Customers that displays customers located in the US.
-- Create the US_Customers view
CREATE VIEW US_Customers AS
SELECT *
FROM Customer
WHERE Country = 'USA';
3. Create another view named Customer_details with columns full name (Combine first_name and last_name), email, phone_no, and state.
-- Create the Customer_details view
CREATE VIEW Customer_details AS
SELECT CONCAT(First_name, ' ', Last_name) AS Full_Name, Email, Phone_no, State
FROM Customer;
4. Update phone numbers of customers who live in California for Customer_details view.
-- Update phone numbers of customers in California in the Customer table
UPDATE Customer
SET Phone_no = 'Updated Phone Number'
WHERE State = 'California';
5. Count the number of customers in each state and show only states with more than 5 customers.
-- Count customers in each state and filter states with more than 5 customers
SELECT State, COUNT(*) AS Customer_Count
FROM Customer
GROUP BY State
HAVING Customer_Count > 5;
6. Write a query that will return the number of customers in each state, based on the "state" column in the "customer_details" view.
-- Query to count customers in each state based on customer_details view
SELECT State, COUNT(*) AS Customer_Count
FROM Customer_details
GROUP BY State;
7. Write a query that returns all the columns from the "customer_details" view, sorted by the "state" column in ascending order.
-- Query to fetch all columns from customer_details view sorted by state
SELECT *
FROM Customer_details
ORDER BY State ASC;
