
# BookStore MGMT project
# Bookstore management system

## Technologies used:
	- Server: Mysql server 8.0
	- Database: MySQL
	- Backend
		- JDBC
		- Spring MVC
	- Frontend
		- JSP
		- CSS
		- Bootstrap
		- HTML

## Product Perspective:
## Project Perspective:

	- User management(only for Admins and Employees(not for customers)):
		- Register
   -LOGING/LOGOUT
	- Stores purchase history
	- The header navbar only display for Admin


## Tables creation queries:

*Before running this product, first all below tables should created in bookstore database*

*Before running the project, create the tables by running this sql commands*
sql
create table bookstore.user
(
	id int(50) primary key auto_increment, 
@@ -44,15 +44,17 @@ create table bookstore.user
	password varchar(220),
	date_created timestamp default now()
);


sql
create table bookstore.admin
(
	id int(50) primary key auto_increment, 
	user_id int(45),  
	is_admin boolean default(false),
	FOREIGN KEY (user_id) REFERENCES bookstore.user(id)
);


sql
create table bookstore.book
(
	id int(50) primary key auto_increment, 
@@ -64,7 +66,8 @@ create table bookstore.book
	copy int(10), 
	price decimal(2)
);


sql
create table bookstore.employee
(
	id int(50) primary key auto_increment, 
@@ -73,7 +76,8 @@ create table bookstore.employee
	department varchar(120), 
	reg_date timestamp default now()
);


sql
create table bookstore.feedback 
(
	id int(50) primary key auto_increment, 
@@ -83,7 +87,8 @@ create table bookstore.feedback
	feedback text, 
	date_created timestamp default now()
);


```sql
create table bookstore.purchase_detail
(
	id int(50) primary key auto_increment,  
@@ -94,5 +99,6 @@ create table bookstore.purchase_detail
	total_price decimal(50), 
	date_purchased timestamp default now()
);
