# Lab1 Basic table.
<br>

1. Create a database : 
```SQL
CREATE DATABASE db_name;
```


2. Select the database you want to create the table inside of by typing the following SQL statement: 
```SQL
USE db_name; 
```


3. Identify a suitable name for the table. 
4. Identify the data type for each column within the table for example
A column called “Device ID” which must store whole numbers. In this case you should use INT as the data type.
5. Write a complete SQL statement to create the table inside the database.
```SQL
CREATE TABLE devices(deviceID int, price decimal);
```


6. If you want to check the structure of the table (columns and data types) type the following SQL statement and click enter.
```SQL
Show columns from devices; 
```


7. you should now be able to see the  table created inside the database by typing the following show tables statement:
```SQL
Show tables;
```


8. to empty the table
```SQL
TRUNCATE TABLE devices;
```



<br><br>
# Lab2 strings.
<br>

CHAR data type allows you to have a fixed length of characters SQL syntax: 
```SQL
username CHAR(9) 
```


Full name need to be more flexible in terms of the length. Therefore, you should choose the VARCHAR datatype and define the maximum length expected for each value. You can declare these two columns in SQL as follows:
```SQL
fullname VARCHAR (100)
```
“TEXT” Data type can be used to define columns requiring less than 65535 characters. This data type could be used to store text content like an article. 



<br><br>
# Lab3 Default values.
<br>

Most customers live in the Harrow area, you can define a default value for the town column as “Harrow” This would ease the process for having to enter “Harrow” repeatedly into the town field for each new record
```SQL
CREATE TABLE address(postcode varchar(10), town varchar(30) default "Harrow");
```



<br><br>
# Lab4 Choosing the right type for a column.
<br>

1. Customer name: the string data type is suitable for the customer's name as you expect it to store data with alphabetic characters. In this case you can use VARCHAR as you expect to have customer names with different lengths of characters.

2. Order date: the date data type is suitable for the order date as you expect it to store data with dates.

3. Product quantity: the integer data type is suitable for the order quantity as you expect it to store whole numbers of data.

4. Total price: the decimal data type is suitable for the product price as you expect it to store numeric data with fractions.



<br><br>
# Lab5 create table and insert data.
<br>

* Task 1: Create a table called customers with customer ID, name, and address, each column must be assigned a suitable datatype.
```SQL
CREATE TABLE customers( customerID int, customerName varchar(50), customerAddress varchar(255));
```


* Task 2: Insert a record of data for one customer. 
```SQL
INSERT INTO customers(customerID, customerName, customerAddress) VALUES (1, "Jack", "115 Old street Belfast");
```

or you can insert more than one recorde be adding more values

```SQL
INSERT INTO customers(customerID, customerName, customerAddress) VALUES (1, "Jack", "115 Old street Belfast"),
(2, "James", "116 Old street Belfast"),
(3, "Maria", "117 Old street Belfast");
```


You can type the following select SQL statement to get the content of the customers table after inserting the data. 
```SQL
SELECT * FROM customers; 
```


Task 3: Write an SQL statement to delete Jack’s record from the Customers table. 
```SQL
DELETE FROM customers WHERE customerID = 1;
```



<br><br>
# Lab6 ORDER BY and WHERE.
<br>
learn how to use the SQL ORDER BY and WHERE clauses to sort and filter data. SQL ORDER BY clause is used to sort the result of a query, and to use the SQL WHERE clause to specify a condition for records filtering.

If you have the giving table
```SQL
CREATE TABLE Customer ( CustomerId INT NOT NULL, FirstName VARCHAR(40) NOT NULL, LastName VARCHAR(20) NOT NULL, Company VARCHAR(80), Address VARCHAR(70), City VARCHAR(40), State VARCHAR(40), Country VARCHAR(40), PostalCode VARCHAR(10), Phone VARCHAR(24), Fax VARCHAR(24), Email VARCHAR(60) NOT NULL, SupportRepId INT, CONSTRAINT PK_Customer PRIMARY KEY  (CustomerId) );

INSERT INTO Customer (CustomerId, FirstName, LastName, Company, Address, City, State, Country, PostalCode, Phone, Fax, Email, SupportRepId) VALUES (1, 'Luís', 'Gonçalves', 'Embraer - Empresa Brasileira de Aeronáutica S.A.', 'Av. Brigadeiro Faria Lima, 2170', 'São José dos Campos', 'SP', 'Brazil', '12227-000', '+55 (12) 3923-5555', '+55 (12) 3923-5566', 'luisg@embraer.com.br', 3);
INSERT INTO Customer (CustomerId, FirstName, LastName, Company, Address, City, State, Country, PostalCode, Phone, Fax, Email, SupportRepId) VALUES (2, 'Eduardo', 'Martins', 'Woodstock Discos', 'Rua Dr. Falcão Filho, 155', 'São Paulo', 'SP', 'Brazil', '01007-010', '+55 (11) 3033-5446', '+55 (11) 3033-4564', 'eduardo@woodstock.com.br', 4);

INSERT INTO Customer (CustomerId, FirstName, LastName, Company, Address, City, State, Country, PostalCode, Phone, Fax, Email, SupportRepId) VALUES
(3, 'Alexandre', 'Rocha', 'Banco do Brasil S.A.', 'Av. Paulista, 2022', 'São Paulo', 'SP', 'Brazil', '01310-200', '+55 (11) 3055-3278', '+55 (11) 3055-8131', 'alero@uol.com.br', 5);

INSERT INTO Customer (CustomerId, FirstName, LastName, Company, Address, City, State, Country, PostalCode, Phone, Fax, Email, SupportRepId) VALUES
(4, 'Roberto', 'Almeida', 'Riotur', 'Praça Pio X, 119', 'Rio de Janeiro', 'RJ', 'Brazil', '20040-020', '+55 (21) 2271-7000', '+55 (21) 2271-7070', 'roberto.almeida@riotur.gov.br', 3);

INSERT INTO Customer (CustomerId, FirstName, LastName, Company, Address, City, State, Country, PostalCode, Phone, Fax, Email, SupportRepId) VALUES (5, 'Mark', 'Philips', 'Telus', '8210 111 ST NW', 'Edmonton', 'AB', 'Canada', 'T6G 2C7', '+1 (780) 434-4554', '+1 (780) 434-5565', 'mphilips12@shaw.ca', 5);

INSERT INTO Customer (CustomerId, FirstName, LastName, Company, Address, City, State, Country, PostalCode, Phone, Fax, Email, SupportRepId) VALUES (6, 'Jennifer', 'Peterson', 'Rogers Canada', '700 W Pender Street', 'Vancouver', 'BC', 'Canada', 'V6C 1G8', '+1 (604) 688-2255', '+1 (604) 688-8756', 'jenniferp@rogers.ca', 3);
```



* Task 1: Write a SQL statement to display CustomerID, FirstName, LastName, City, State and Country from customer table. 
```SQL
select CustomerID, FirstName, LastName, City, State, Country from Customer;
```



* Task 2: Write a SQL statement to sort the result set in the ascending order by first name.
```SQL
select CustomerID, FirstName, LastName, City, State, Country from Customer ORDER BY FirstName; 
```



* Task 3: Filter the result set data based on a condition where country = Brazil. all selected data where the country = brazil is displayed now, and orderd by firstname.
```SQL
select CustomerID, FirstName, LastName, City, State, Country from Customer WHERE Country = "Brazil" ORDER BY FirstName;
```



<br><br>
# Final assigsment.
<br>

What does the following SQL statement do? 
```SQL
SELECT * FROM Players ORDER BY Country, PlayerName;
```
Answer : It displays the results ordered by country first, then players name. <br><br><br>




The output result of the following SQL statement returns the records of all customers from India in Alphabetical order from A to Z.
```SQL
SELECT * FROM students WHERE country = "India" ORDER BY FirstName DESC; 
```
Answer : False <br><br>



The output result of the following SQL statement is the data of all customers from Italy. 
```SQL
SELECT * FROM customers WHERE Country = "Italy"; 
```
Answer : True <br><br>



Database constraints are used to limit the type of data value that can be stored in a table. <br>
Answer : True <br><br>



In a football club the skill level of all new players must automatically be set at the default of level 1. Which SQL syntax is used to set this default level using the DEFAULT keyword? 
Answer : 
```SQL
level INT DEFAULT 1;
``` 
<br><br>



A sports club database includes a table called "Members" with two columns:  1.'member number' column that contains the phone number of each member. 2.'full name' column that contains the full name of each member. Choose the right data type for each column.<br>
Answer : 
The Player number column data type is INT.
The Full name column data type is VARCHAR. <br><br>



What is a row of information about one specific staff member in a college database table referred to as?<br>
Answer : A record <br><br>



Write an SQL statement that outputs all names of the players in the following "Players" table who are older than 25 years of age.
Answer :
```SQL
SELECT Name FROM Players WHERE Age > 25;
```
<br><br>


The following table called "Players", contains four records of data. Write a SQL statement that deletes the record of the player with ID = 4.
Answer :
```SQL
DELETE FROM Players WHERE playerID = 4;
```
<br><br>


The following table called "Players", contains four records of data. Write a SQL statement that updates the age of the player with ID = 3. The new age value should be '22'.
Answer :
```SQL
UPDATE Players SET age = 22 WHERE playerID = 3;
```
<br><br>


In the text field below, input the missing keyword (___) from the following SQL statement to insert data into the "Players" table. INSERT INTO Players (playerID, playerName, age) ____ (1, "Jack", 25);
Answer :
```SQL
INSERT INTO Players (playerID, playerName, age) VALUES (1, "Jack", 25);
```