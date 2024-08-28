# Database Clients
Explore how to write database driven applications in Python by creating various types of clients that connect to MySQL databases using Python code and Python-related MySQL features and tools. 


## Purpose of the Project
The main goal of this project is to demonstrate my understanding and knowledge of the key learning objectives from the course I’ve just completed.

## Implement and query stored procedures
In this exercise I created a pool of connections and got a connection from the pool to implement the stored procedures to complete the following tasks:

Establish a connection by importing MySQLConnectionPool and creating a pool with two connections.

Create and call a stored procedure named PeakHours that identifies the peak, or busiest hour, for the restaurant based on the number of bookings.

Create and call a stored procedure named GuestStatus that outputs status of each guest’s order based on which employee is assigned to the order.

Stored procedures are created to carry out routine operations on MySQL databases. They are consistent and make sure that the written SQL queries in the procedures are executed in the same way every time you call the stored procedure.

A stored procedure is created only once, and you store it in the MySQL database. You can call the stored procedures as many times as you need in your Python-based application.

### Task 1: Establish a connection 
Step one: Import MySQLConnectionPool

Step two: Import Error

Step three: Create a pool named pool_a with two connections. Use a try-except block to handle any possible errors. 

### Task 2: Implement a stored procedure called PeakHours
Step one: Write a SQL CREATE PROCEDURE query for PeakHours

Use HOUR to extract the hour part from the BookingSlot.

Use COUNT on hour to count the number of bookings.

Use GROUP BY on booking hour.

Use ORDER BY on the number of bookings in descending order.

Step two: Run the stored procedure query by invoking execute module on the cursor.

Step three: Invoke callproc to call the stored procedure.

Step four: Fetch the results in a variable called dataset.

Step five: Extract the names of the columns.

Step six: Print the names of the columns.

Step seven: Print the sorted data using for loop.

### Task 3: Implement a stored procedure GuestStatus
Step one: Write a SQL CREATE PROCEDURE query for GuestStatus.

Step two: Combine the guest’s first and last name from the booking column using CONCAT. 

Step three: Use CASE to implement the following statuses for each guest’s order:

If the Role in the Employee table is Manager or Assistant Manager then the guest’s order status is Ready to pay

If the Role in the Employee table is Head Chef then the status is Ready to serve

If the Role in the Employee table is Assistant Chef then the status is Preparing Order

If the Role in the Employee table is Head Waiter then the status is Order served

Step four: LEFT JOIN Bookings table with Employees ON EmployeeID

Step five: Run the stored procedure query by invoking execute module on the cursor.

Step six: Invoke callproc to call the stored procedure.

Step seven: Fetch the results in a variable called dataset.

Step eight: Extract the names of the columns.

Step nine: Print the names of the columns.

Step ten: Print the sorted data using for loop.

Step eleven: Close the connection to return it back to the pool.


## Little Lemon analysis and sales report

### Task 1:
Complete the following steps to establish a connection pool:

To create a connection pool, import MySQLConnectionPool class from MySQL Connector/Python.

To find the information on the error, import the Error class from MySQL Connector/Python.

Define your database configurations as a Python dictionary object called dbconfig.

Establish a connection pool [pool_name = pool_b] with two connections. 

Implement error handling using a try-except block in case the connection fails. 

### Task 2:
Three guests are trying to book dinner slots simultaneously. Get the connections from pool_b and insert the following data in the Bookings table:


TIP: You need to add a connection to connect the third guest.


Guest 1:

Table Number: 8

First Name: Anees

Last Name: Java

Booking Time: 18:00

EmployeeID: 6


Guest 2:

Table Number: 5

First Name: Bald

Last Name: Vin

Booking Time: 19:00

EmployeeID: 6


Guest 3:

Table Number: 12

First Name: Jay

Last Name: Kon

Booking Time: 19:30 

EmployeeID: 6


Return all the connections back to the pool. 

### Task 3:
Create a report containing the following information:

The name and EmployeeID of the Little Lemon manager.

The name and role of the employee who receives the highest salary.

The number of guests booked between 18:00 and 20:00.

The full name and BookingID of all guests waiting to be seated with the receptionist in sorted order with respect to their BookingSlot.

### Task 4:
Create a stored procedure named BasicSalesReport that returns the following statistics: 

Total sales

Average sale

Minimum bill paid

Maximum bill paid

### Task 5:
Little Lemon needs to display the next three upcoming bookings from the Bookings table on the kitchen screen to notify their chefs which orders are due next. To complete this task, carry out the following steps:

Get a connection from the pool.

Create a buffered cursor.

Combine the data from the Bookings and the Employee tables. Sort the retrieved records in ascending order. Then display the information of the first three guests. 

Returned the connection back to the pool.
