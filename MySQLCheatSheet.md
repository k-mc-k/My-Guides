A few things to note:
- a semicolon is used at the end of a statment to terminate the command
- comments can be used to provide clarity about the SQL statemnt. singe and double lines are supported single like is -- (two hyphens) and multiline is /* */
- exit mysql by   exit;

How to login into mysql from terminal
mysql -u username -p
replace username with your MySQL username

How to SHOW USERS
SELECT User, Host FROM mysql.user;

How to CREATE USERS
CREATE USER 'someuser'@'localhost' IDENTIFIED BY 'somepassword';

How to GRANT PRIVILEGES, Show granted privileges and remove.
GRANT ALL PRIVILEGES ON * . * TO 'someuser'@'localhost';
FLUSH PRIVILEGES;
SHOW GRANTS FOR 'someuser'@'localhost';
REVOKE ALL PRIVILEGES, GRANT OPTION FROM 'someuser'@'localhost';

How to SHOW, DELETE & CREATE DATABASES & SELECT DATABASES
SHOW databases;
DROP DATABASE acme;
CREATE databasename;
USE databasename;  > You will be prompted that you have switched

How to CREATE a TABLE with Columns and their data types
CREATE TABLE tablename(
    columnone datatype,
    columntwo datatype,
); 

How to SHOW, DELETE & DROP Tables
SHOW TABLES;
DROP TABLE tablename;

How to Insert ROWS & RECORDS (single and multiple)
INSERT INTO users (first_name, last_name, email, password, location, dept, is_admin, register_date) values ('Brad', 'Traversy', 'brad@gmail.com', '123456','Massachusetts', 'development', 1, now());

INSERT INTO users (first_name, last_name, email, password, location, dept,  is_admin, register_date) values ('Fred', 'Smith', 'fred@gmail.com', '123456', 'New York', 'design', 0, now()), ('Sara', 'Watson', 'sara@gmail.com', '123456', 'New York', 'design', 0, now()),('Will', 'Jackson', 'will@yahoo.com', '123456', 'Rhode Island', 'development', 1, now()),('Paula', 'Johnson', 'paula@yahoo.com', '123456', 'Massachusetts', 'sales', 0, now()),('Tom', 'Spears', 'tom@yahoo.com', '123456', 'Massachusetts', 'sales', 0, now());

How to SELECT with the WHERE Clause
SELECT * FROM users WHERE location='Massachusetts';

How to SELECT with the WHERE Clause using a range

How to DELETE an individual ROW
DELETE FROM users WHERE id = 6;

How to UPDATE a ROW
UPDATE users SET email = 'freddy@gmail.com' WHERE id = 2;

How to add a new column and modify it
ALTER TABLE users ADD age VARCHAR(3);
ALTER TABLE users MODIFY COLUMN age INT(3);

How to Order by and use Distinct
SELECT * FROM users ORDER BY last_name ASC;
SELECT * FROM users ORDER BY last_name DESC;
SELECT DISTINCT location FROM users;

How to Concatenate Columns
SELECT CONCAT(first_name, ' ', last_name) AS 'Name', dept FROM users;
Select Distinct Rows

How to Select Distinct Rows
SELECT DISTINCT location FROM users;

How to use LIKE to Search
SELECT * FROM users WHERE dept LIKE 'dev%';
SELECT * FROM users WHERE dept LIKE '%t';

How Select using IN
SELECT * FROM users WHERE dept IN ('design', 'sales');

How to Create & Remove Index
CREATE INDEX LIndex On users(location);
DROP INDEX LIndex ON users;

How to Create a New Table with Foreign Key
CREATE TABLE posts(
id INT AUTO_INCREMENT,
   user_id INT,
   title VARCHAR(100),
   body TEXT,
   publish_date DATETIME DEFAULT CURRENT_TIMESTAMP,
   PRIMARY KEY(id),
   FOREIGN KEY (user_id) REFERENCES users(id)
);

How to use Inner Join
SELECT
  users.first_name,
  users.last_name,
  posts.title,
  posts.publish_date
FROM users
INNER JOIN posts
ON users.id = posts.user_id
ORDER BY posts.title;

How to JOIN Multiple Tables
SELECT
comments.body,
posts.title,
users.first_name,
users.last_name
FROM comments
INNER JOIN posts on posts.id = comments.post_id
INNER JOIN users on users.id = comments.user_id
ORDER BY posts.title;
