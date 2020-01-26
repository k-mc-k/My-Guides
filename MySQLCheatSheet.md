## MySQL Cheat Sheet


**A few things to note:** 
- a semicolon is used at the end of every statment to terminate the command ( ; )
- the asterisk symbol ( * ) is used to select all columns in a table
- single line (--) and double line (/* */) comments can be used to describe or provide clarity about the SQL statement
- exit mysql in your terminal by typing ***exit;***

### Login into MySQL
Replace *user* with your MySQL username. You will be prompted for your password. 
```
mysql -u user -p
```

### Show Users
```
SELECT user FROM mysql.user;
```

### Create User
```
CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';
```

### Grant Privileges
In order to save and implement changes made, execute **FLUSH PRIVILEGES;** at the end
```
GRANT ALL PRIVILEGES ON * . * TO 'someuser'@'localhost';
```

### Show Granted Privileges
```
SHOW GRANTS FOR 'someuser'@'localhost';
```

### Remove Privileges
```
REVOKE ALL PRIVILEGES, GRANT OPTION FROM 'someuser'@'localhost';
```

### Show Database
```
SHOW databases;
```

### Delete Database
```
DROP DATABASE databasename;
```

### Create new Database
```
CREATE newdatabasename;
```

### Select and Use Database
```
USE databasename; 
```

### Create a Table 
Visit [this link](https://www.w3resource.com/mysql/mysql-data-types.php) for a full list of different datatypes
```
CREATE TABLE newtable (
    columnone datatype,
    columntwo datatype,
    columnthree datatype
); 
```

### Show Tables
```
SHOW TABLES;
```

### Delete or Drop Tables
```
DROP TABLE tablename;
```

### Insert single row & record
```
INSERT INTO tablename (first_name, last_name, email, phone_number, age) 
VALUES ('Kelly', 'McLaren', 'kellytest@test.com', '123-456-7890',27);
```

### Insert multiple rows & records
```
INSERT INTO tablename (first_name, last_name, email, phone_number, age) 
VALUES ('Kelly', 'McLaren', 'kellytest@test.com', '123-456-7890',27), 
('Johnny', 'Appleseed', 'appleseed@test.com', '987-654-3210',36), 
('Billy', 'Bob', 'bob@test.com', '999-999-9999',64);
```

### Select using WHERE
```
SELECT * FROM tablename WHERE gender='female';
```

### Select using WHERE (using a range)
```
SELECT name FROM city WHERE population BETWEEN 670000 AND 700000;
```

### Delete a Row
```
DELETE FROM users WHERE id = 10;
```

### Update a row
```
UPDATE users SET phonenumber = '123-456-7890' WHERE id = 10;
```

### Create new column
```
ALTER TABLE tablename ADD newcolumn VARCHAR(20) NOT NULL;
```

### Modify a column
```
ALTER TABLE tablename MODIFY COLUMN columnname VARCHAR(100);
```

### Order by Ascending or Descending
```
SELECT * FROM users ORDER BY age ASC;
SELECT * FROM users ORDER BY age DESC;
```

### Select Distinct Rows
The SELECT DISTINCT statement is used to return only distinct (different) values from a table where you have duplicated values in the same column.
```
SELECT DISTINCT provinces FROM users;
```

### Concatenate Column
```
SELECT CONCAT(fname, ' ', lname) AS Name FROM users;
```

### Using LIKE to Search
```
SELECT * FROM users WHERE name LIKE 'K%';
SELECT * FROM users WHERE name LIKE 'Jo_';
```

### Select using IN
```
SELECT * FROM employees WHERE title IN ('manager', 'human resources');
```

### Create Index
```
CREATE INDEX indexname ON tablename(column1);
```

### Remove Index
```
DROP INDEX indexname ON tablename;
```

### Create a New Table with Foreign Key
```
CREATE TABLE users (
   user_id INT AUTO_INCREMENT PRIMARY KEY,
   first_name VARCHAR(50) NOT NULL,
   last_name VARCHAR(50) NOT NULL,
   email_address VARCHAR(100),
   phone_number INT,
   signup_date DATE NOT NULL,
   employee_id INT,
   FOREIGN KEY (employee_id) REFERENCES workers(employee_id)
);
```

### Use INNER JOIN
The INNER JOIN keyword selects all rows from both tables provided there is a match between the columns
```
SELECT column_name(s)
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name;
```

### How to JOIN Multiple Tables
```
SELECT
table1.column1,
table2.column2,
table3.column3,
FROM ((table1
INNER JOIN table2 on table1.column1 = table2.column3)
INNER JOIN table3 on table2.column1 = table3.column3);
```
