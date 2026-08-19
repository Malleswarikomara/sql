**assignment:**

&#x20;create database student;

use student;

create table student(sid int, sname varchar(20), age int, city varchar(20));

desc student;

create table employee(eid int primary key,

&#x20;   ->                        ename varchar(20) not null,

&#x20;   ->                        salary int, email varchar(20) unique);

desc employee;

create table department(did int primary key, dname varchar(20) unique, location varchar(20));

desc department;



create table product(pid int primary key,

&#x20;   ->                        pname varchar(20) not null,

&#x20;   ->                        price int check (price>0),

&#x20;   ->                        quantity int check (quantity>=0));

create table customer( customer\_id int primary key);



**Alter assignment:**

alter table student add column email varchar(20);

Query OK, 0 rows affected (0.04 sec)

Records: 0  Duplicates: 0  Warnings: 0



mysql> alter table employee add column phone int(10) unique;

Query OK, 0 rows affected, 1 warning (0.10 sec)

Records: 0  Duplicates: 0  Warnings: 1



mysql> alter table product modify pname varchar(50);

Query OK, 0 rows affected (0.08 sec)

Records: 0  Duplicates: 0  Warnings: 0



mysql> rename table student to student\_name;

Query OK, 0 rows affected (0.08 sec)



mysql> alter table employee drop column address;

ERROR 1091 (42000): Can't DROP 'address'; check that column/key exists

mysql> show tables





































12-08-2026



mysql> use da22

Database changed

mysql> show databases

&#x20;   -> ;

+--------------------+

| Database           |

+--------------------+

| da                 |

| da22               |

| information\_schema |

| mysql              |

| performance\_schema |

| student            |

| sys                |

+--------------------+

7 rows in set (0.07 sec)



mysql> drop table student;

ERROR 1051 (42S02): Unknown table 'da22.student'

mysql> show tables;

+----------------+

| Tables\_in\_da22 |

+----------------+

| dep            |

| dept           |

| emp            |

| employee       |

| employees      |

+----------------+

5 rows in set (0.06 sec)



mysql> create table employees(emp\_id

&#x20;   -> INT AUTO\_INCREMENT

&#x20;   -> emp\_name

&#x20;   -> VARCHAR(50)

&#x20;   -> department

&#x20;   -> VARCHAR(50)

&#x20;   -> salary

&#x20;   -> DECIMAL(10,2)

&#x20;   -> experience

&#x20;   -> INT

&#x20;   -> status

&#x20;   -> INT

&#x20;   ->

&#x20;   ->

&#x20;   ->

&#x20;   -> );

ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'emp\_name

VARCHAR(50)

department

VARCHAR(50)

salary

DECIMAL(10,2)

experience

INT

' at line 3

mysql> create table employees(emp\_id int auto\_increment, emp\_name varchar(50), department varchar(50), salary decimal(10,2), experience int, status int);

ERROR 1050 (42S01): Table 'employees' already exists

mysql> create table employees1(emp\_id int auto\_increment, emp\_name varchar(50), department varchar(50), salary decimal(10,2), experience int, status int);

ERROR 1075 (42000): Incorrect table definition; there can be only one auto column and it must be defined as a key

mysql> create table employees1(emp\_id int primary key auto\_increment, emp\_name varchar(50), department varchar(50), salary decimal(10,2), experience int, status int);

Query OK, 0 rows affected (0.09 sec)



mysql> INSERT INTO employees

&#x20;   -> (emp\_name, department, salary, experience, status)

&#x20;   -> VALUES

&#x20;   -> ('Ravi',   'IT',        60000, 4, 1),

&#x20;   -> ('Anil',   'HR',        45000, 3, 2),

&#x20;   -> ('Priya',  'Finance',   70000, 6, 4),

&#x20;   -> ('Sneha',  'IT',        85000, 7, 3),

&#x20;   -> ('Kiran',  'Sales',     35000, 2, 1),

&#x20;   -> ('Arjun',  'IT',        55000, 5, 5),

&#x20;   -> ('Divya',  'HR',        40000, 4, 2),

&#x20;   -> ('Rahul',  'Finance',   65000, 8, 6),

&#x20;   -> ('Meena',  'Sales',     30000, 1, 1),

&#x20;   -> ('Suresh', 'IT',        95000, 10, 7),

&#x20;   -> ('Pooja',  'Marketing', 50000, 3, 2),

&#x20;   -> ('Vijay',  'Finance',   48000, 4, 4),

&#x20;   -> ('Neha',   'IT',        72000, 6, 3),

&#x20;   -> ('Amit',   'Sales',     42000, 5, 1),

&#x20;   -> ('Swathi', 'Marketing', 58000, 7, 5);

ERROR 1054 (42S22): Unknown column 'emp\_name' in 'field list'

mysql> INSERT INTO employees1

&#x20;   -> (emp\_name, department, salary, experience, status)

&#x20;   -> VALUES

&#x20;   -> ('Ravi',   'IT',        60000, 4, 1),

&#x20;   -> ('Anil',   'HR',        45000, 3, 2),

&#x20;   -> ('Priya',  'Finance',   70000, 6, 4),

&#x20;   -> ('Sneha',  'IT',        85000, 7, 3),

&#x20;   -> ('Kiran',  'Sales',     35000, 2, 1),

&#x20;   -> ('Arjun',  'IT',        55000, 5, 5),

&#x20;   -> ('Divya',  'HR',        40000, 4, 2),

&#x20;   -> ('Rahul',  'Finance',   65000, 8, 6),

&#x20;   -> ('Meena',  'Sales',     30000, 1, 1),

&#x20;   -> ('Suresh', 'IT',        95000, 10, 7),

&#x20;   -> ('Pooja',  'Marketing', 50000, 3, 2),

&#x20;   -> ('Vijay',  'Finance',   48000, 4, 4),

&#x20;   -> ('Neha',   'IT',        72000, 6, 3),

&#x20;   -> ('Amit',   'Sales',     42000, 5, 1),

&#x20;   -> ('Swathi', 'Marketing', 58000, 7, 5);

Query OK, 15 rows affected (0.05 sec)

Records: 15  Duplicates: 0  Warnings: 0



mysql> create table products(product\_id int primary key auto\_increment, product\_name varchar(50), price decimal(10,2), quantity int);

Query OK, 0 rows affected (0.07 sec)



mysql> INSERT INTO products

&#x20;   -> (product\_name, price, quantity)

&#x20;   -> VALUES

&#x20;   -> ('Laptop',       55000, 10),

&#x20;   -> ('Mouse',         800, 25),

&#x20;   -> ('Keyboard',     1500, 15),

&#x20;   -> ('Monitor',     12000, 8),

&#x20;   -> ('Headphones',   2500, 20),

&#x20;   -> ('Webcam',        3500, 12),

&#x20;   -> ('Printer',      15000, 5),

&#x20;   -> ('SSD',           6000, 18),

&#x20;   -> ('RAM',           4000, 30),

&#x20;   -> ('USB Cable',      500, 40),

&#x20;   -> ('Router',        3000, 10),

&#x20;   -> ('Speaker',       4500, 7);

Query OK, 12 rows affected (0.01 sec)

Records: 12  Duplicates: 0  Warnings: 0



mysql>

mysql> select emp\_name, salary, salary + 5000 from employees1;

+----------+----------+---------------+

| emp\_name | salary   | salary + 5000 |

+----------+----------+---------------+

| Ravi     | 60000.00 |      65000.00 |

| Anil     | 45000.00 |      50000.00 |

| Priya    | 70000.00 |      75000.00 |

| Sneha    | 85000.00 |      90000.00 |

| Kiran    | 35000.00 |      40000.00 |

| Arjun    | 55000.00 |      60000.00 |

| Divya    | 40000.00 |      45000.00 |

| Rahul    | 65000.00 |      70000.00 |

| Meena    | 30000.00 |      35000.00 |

| Suresh   | 95000.00 |     100000.00 |

| Pooja    | 50000.00 |      55000.00 |

| Vijay    | 48000.00 |      53000.00 |

| Neha     | 72000.00 |      77000.00 |

| Amit     | 42000.00 |      47000.00 |

| Swathi   | 58000.00 |      63000.00 |

+----------+----------+---------------+

15 rows in set (0.05 sec)



mysql> select emp\_name, salary,salary+10/100 as 10% increment from employees1;

ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '10% increment from employees1' at line 1

mysql> select emp\_name, salary,salary+10/100 as 10 increment from employees1;

ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '10 increment from employees1' at line 1

mysql> select emp\_name, salary,salary+10/100 as increment from employees1;

+----------+----------+------------+

| emp\_name | salary   | increment  |

+----------+----------+------------+

| Ravi     | 60000.00 | 60000.1000 |

| Anil     | 45000.00 | 45000.1000 |

| Priya    | 70000.00 | 70000.1000 |

| Sneha    | 85000.00 | 85000.1000 |

| Kiran    | 35000.00 | 35000.1000 |

| Arjun    | 55000.00 | 55000.1000 |

| Divya    | 40000.00 | 40000.1000 |

| Rahul    | 65000.00 | 65000.1000 |

| Meena    | 30000.00 | 30000.1000 |

| Suresh   | 95000.00 | 95000.1000 |

| Pooja    | 50000.00 | 50000.1000 |

| Vijay    | 48000.00 | 48000.1000 |

| Neha     | 72000.00 | 72000.1000 |

| Amit     | 42000.00 | 42000.1000 |

| Swathi   | 58000.00 | 58000.1000 |

+----------+----------+------------+

15 rows in set (0.04 sec)



mysql> select \* from employess1 where salary>50000;

ERROR 1146 (42S02): Table 'da22.employess1' doesn't exist

mysql> select \* from employees1 where salary>50000;

+--------+----------+------------+----------+------------+--------+

| emp\_id | emp\_name | department | salary   | experience | status |

+--------+----------+------------+----------+------------+--------+

|      1 | Ravi     | IT         | 60000.00 |          4 |      1 |

|      3 | Priya    | Finance    | 70000.00 |          6 |      4 |

|      4 | Sneha    | IT         | 85000.00 |          7 |      3 |

|      6 | Arjun    | IT         | 55000.00 |          5 |      5 |

|      8 | Rahul    | Finance    | 65000.00 |          8 |      6 |

|     10 | Suresh   | IT         | 95000.00 |         10 |      7 |

|     13 | Neha     | IT         | 72000.00 |          6 |      3 |

|     15 | Swathi   | Marketing  | 58000.00 |          7 |      5 |

+--------+----------+------------+----------+------------+--------+

8 rows in set (0.04 sec)



mysql> select name, salary from employees1 where salary>=30000 and salary<=60000;

ERROR 1054 (42S22): Unknown column 'name' in 'field list'

mysql> select emp\_name, salary from employees1 where salary>=30000 and salary<=60000;

+----------+----------+

| emp\_name | salary   |

+----------+----------+

| Ravi     | 60000.00 |

| Anil     | 45000.00 |

| Kiran    | 35000.00 |

| Arjun    | 55000.00 |

| Divya    | 40000.00 |

| Meena    | 30000.00 |

| Pooja    | 50000.00 |

| Vijay    | 48000.00 |

| Amit     | 42000.00 |

| Swathi   | 58000.00 |

+----------+----------+

10 rows in set (0.04 sec)



mysql> select emp\_name, salary from employees1 where salary>30000 and salary<60000;

+----------+----------+

| emp\_name | salary   |

+----------+----------+

| Anil     | 45000.00 |

| Kiran    | 35000.00 |

| Arjun    | 55000.00 |

| Divya    | 40000.00 |

| Pooja    | 50000.00 |

| Vijay    | 48000.00 |

| Amit     | 42000.00 |

| Swathi   | 58000.00 |

+----------+----------+

8 rows in set (0.00 sec)



mysql> select \* from employees1 where department = 'IT' and salary > 50000;

+--------+----------+------------+----------+------------+--------+

| emp\_id | emp\_name | department | salary   | experience | status |

+--------+----------+------------+----------+------------+--------+

|      1 | Ravi     | IT         | 60000.00 |          4 |      1 |

|      4 | Sneha    | IT         | 85000.00 |          7 |      3 |

|      6 | Arjun    | IT         | 55000.00 |          5 |      5 |

|     10 | Suresh   | IT         | 95000.00 |         10 |      7 |

|     13 | Neha     | IT         | 72000.00 |          6 |      3 |

+--------+----------+------------+----------+------------+--------+

5 rows in set (0.00 sec)



mysql> select \* from employees1 where department = 'IT' and 'HR';

Empty set, 1 warning (0.04 sec)



mysql> select \* from employees1 where department = 'IT' and department = 'HR';

Empty set (0.00 sec)



mysql> select \* from employees1 where department = 'IT' or department = 'HR';

+--------+----------+------------+----------+------------+--------+

| emp\_id | emp\_name | department | salary   | experience | status |

+--------+----------+------------+----------+------------+--------+

|      1 | Ravi     | IT         | 60000.00 |          4 |      1 |

|      2 | Anil     | HR         | 45000.00 |          3 |      2 |

|      4 | Sneha    | IT         | 85000.00 |          7 |      3 |

|      6 | Arjun    | IT         | 55000.00 |          5 |      5 |

|      7 | Divya    | HR         | 40000.00 |          4 |      2 |

|     10 | Suresh   | IT         | 95000.00 |         10 |      7 |

|     13 | Neha     | IT         | 72000.00 |          6 |      3 |

+--------+----------+------------+----------+------------+--------+

7 rows in set (0.00 sec)



mysql> select \* from employees1 where department != 'Finance' and experience> 3;

+--------+----------+------------+----------+------------+--------+

| emp\_id | emp\_name | department | salary   | experience | status |

+--------+----------+------------+----------+------------+--------+

|      1 | Ravi     | IT         | 60000.00 |          4 |      1 |

|      4 | Sneha    | IT         | 85000.00 |          7 |      3 |

|      6 | Arjun    | IT         | 55000.00 |          5 |      5 |

|      7 | Divya    | HR         | 40000.00 |          4 |      2 |

|     10 | Suresh   | IT         | 95000.00 |         10 |      7 |

|     13 | Neha     | IT         | 72000.00 |          6 |      3 |

|     14 | Amit     | Sales      | 42000.00 |          5 |      1 |

|     15 | Swathi   | Marketing  | 58000.00 |          7 |      5 |

+--------+----------+------------+----------+------------+--------+

8 rows in set (0.00 sec)



mysql> select \* from employees1 where salary > 40000 and experience >5;

+--------+----------+------------+----------+------------+--------+

| emp\_id | emp\_name | department | salary   | experience | status |

+--------+----------+------------+----------+------------+--------+

|      3 | Priya    | Finance    | 70000.00 |          6 |      4 |

|      4 | Sneha    | IT         | 85000.00 |          7 |      3 |

|      8 | Rahul    | Finance    | 65000.00 |          8 |      6 |

|     10 | Suresh   | IT         | 95000.00 |         10 |      7 |

|     13 | Neha     | IT         | 72000.00 |          6 |      3 |

|     15 | Swathi   | Marketing  | 58000.00 |          7 |      5 |

+--------+----------+------------+----------+------------+--------+

6 rows in set (0.00 sec)



mysql> select \* from employees1 where salary/1000;

+--------+----------+------------+----------+------------+--------+

| emp\_id | emp\_name | department | salary   | experience | status |

+--------+----------+------------+----------+------------+--------+

|      1 | Ravi     | IT         | 60000.00 |          4 |      1 |

|      2 | Anil     | HR         | 45000.00 |          3 |      2 |

|      3 | Priya    | Finance    | 70000.00 |          6 |      4 |

|      4 | Sneha    | IT         | 85000.00 |          7 |      3 |

|      5 | Kiran    | Sales      | 35000.00 |          2 |      1 |

|      6 | Arjun    | IT         | 55000.00 |          5 |      5 |

|      7 | Divya    | HR         | 40000.00 |          4 |      2 |

|      8 | Rahul    | Finance    | 65000.00 |          8 |      6 |

|      9 | Meena    | Sales      | 30000.00 |          1 |      1 |

|     10 | Suresh   | IT         | 95000.00 |         10 |      7 |

|     11 | Pooja    | Marketing  | 50000.00 |          3 |      2 |

|     12 | Vijay    | Finance    | 48000.00 |          4 |      4 |

|     13 | Neha     | IT         | 72000.00 |          6 |      3 |

|     14 | Amit     | Sales      | 42000.00 |          5 |      1 |

|     15 | Swathi   | Marketing  | 58000.00 |          7 |      5 |

+--------+----------+------------+----------+------------+--------+

15 rows in set (0.04 sec)



mysql> select emp\_name, salary/1000 from employees1;

+----------+-------------+

| emp\_name | salary/1000 |

+----------+-------------+

| Ravi     |   60.000000 |

| Anil     |   45.000000 |

| Priya    |   70.000000 |

| Sneha    |   85.000000 |

| Kiran    |   35.000000 |

| Arjun    |   55.000000 |

| Divya    |   40.000000 |

| Rahul    |   65.000000 |

| Meena    |   30.000000 |

| Suresh   |   95.000000 |

| Pooja    |   50.000000 |

| Vijay    |   48.000000 |

| Neha     |   72.000000 |

| Amit     |   42.000000 |

| Swathi   |   58.000000 |

+----------+-------------+

15 rows in set (0.00 sec)



mysql> select \* from products where price \* quantity as total\_amount;

ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'as total\_amount' at line 1

mysql> select price \* quantity as total\_amount from products;

+--------------+

| total\_amount |

+--------------+

|    550000.00 |

|     20000.00 |

|     22500.00 |

|     96000.00 |

|     50000.00 |

|     42000.00 |

|     75000.00 |

|    108000.00 |

|    120000.00 |

|     20000.00 |

|     30000.00 |

|     31500.00 |

+--------------+

12 rows in set (0.00 sec)



mysql> select product\_name price \* quantity as total\_amount from products;

ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '\* quantity as total\_amount from products' at line 1

mysql> select product\_name, price \* quantity as total\_amount from products;

+--------------+--------------+

| product\_name | total\_amount |

+--------------+--------------+

| Laptop       |    550000.00 |

| Mouse        |     20000.00 |

| Keyboard     |     22500.00 |

| Monitor      |     96000.00 |

| Headphones   |     50000.00 |

| Webcam       |     42000.00 |

| Printer      |     75000.00 |

| SSD          |    108000.00 |

| RAM          |    120000.00 |

| USB Cable    |     20000.00 |

| Router       |     30000.00 |

| Speaker      |     31500.00 |

+--------------+--------------+

12 rows in set (0.04 sec)



mysql> select \* from employees1 where salary+15/100 and department ='IT';

+--------+----------+------------+----------+------------+--------+

| emp\_id | emp\_name | department | salary   | experience | status |

+--------+----------+------------+----------+------------+--------+

|      1 | Ravi     | IT         | 60000.00 |          4 |      1 |

|      4 | Sneha    | IT         | 85000.00 |          7 |      3 |

|      6 | Arjun    | IT         | 55000.00 |          5 |      5 |

|     10 | Suresh   | IT         | 95000.00 |         10 |      7 |

|     13 | Neha     | IT         | 72000.00 |          6 |      3 |

+--------+----------+------------+----------+------------+--------+

5 rows in set (0.00 sec)



mysql> select \* from employees1 where salary = salary+15/100 and department ='IT';

Empty set (0.00 sec)



mysql> select salary ,salary\*0.15 where department='IT';

ERROR 1054 (42S22): Unknown column 'salary' in 'field list'

mysql> select salary ,salary\*0.15 from employees1 where department='IT';

+----------+-------------+

| salary   | salary\*0.15 |

+----------+-------------+

| 60000.00 |   9000.0000 |

| 85000.00 |  12750.0000 |

| 55000.00 |   8250.0000 |

| 95000.00 |  14250.0000 |

| 72000.00 |  10800.0000 |

+----------+-------------+

5 rows in set (0.00 sec)



mysql> select \* from employees1 where salary\*15/100 and department ='IT';

+--------+----------+------------+----------+------------+--------+

| emp\_id | emp\_name | department | salary   | experience | status |

+--------+----------+------------+----------+------------+--------+

|      1 | Ravi     | IT         | 60000.00 |          4 |      1 |

|      4 | Sneha    | IT         | 85000.00 |          7 |      3 |

|      6 | Arjun    | IT         | 55000.00 |          5 |      5 |

|     10 | Suresh   | IT         | 95000.00 |         10 |      7 |

|     13 | Neha     | IT         | 72000.00 |          6 |      3 |

+--------+----------+------------+----------+------------+--------+

5 rows in set (0.00 sec)



mysql> select \* from employees1 where  salary= salary\*15/100 and department ='IT';

Empty set (0.00 sec)



mysql> select salary ,salary\*0.15 from employees1 where department='IT';

+----------+-------------+

| salary   | salary\*0.15 |

+----------+-------------+

| 60000.00 |   9000.0000 |

| 85000.00 |  12750.0000 |

| 55000.00 |   8250.0000 |

| 95000.00 |  14250.0000 |

| 72000.00 |  10800.0000 |

+----------+-------------+

5 rows in set (0.00 sec)



mysql> select \* from employees1;

+--------+----------+------------+----------+------------+--------+

| emp\_id | emp\_name | department | salary   | experience | status |

+--------+----------+------------+----------+------------+--------+

|      1 | Ravi     | IT         | 60000.00 |          4 |      1 |

|      2 | Anil     | HR         | 45000.00 |          3 |      2 |

|      3 | Priya    | Finance    | 70000.00 |          6 |      4 |

|      4 | Sneha    | IT         | 85000.00 |          7 |      3 |

|      5 | Kiran    | Sales      | 35000.00 |          2 |      1 |

|      6 | Arjun    | IT         | 55000.00 |          5 |      5 |

|      7 | Divya    | HR         | 40000.00 |          4 |      2 |

|      8 | Rahul    | Finance    | 65000.00 |          8 |      6 |

|      9 | Meena    | Sales      | 30000.00 |          1 |      1 |

|     10 | Suresh   | IT         | 95000.00 |         10 |      7 |

|     11 | Pooja    | Marketing  | 50000.00 |          3 |      2 |

|     12 | Vijay    | Finance    | 48000.00 |          4 |      4 |

|     13 | Neha     | IT         | 72000.00 |          6 |      3 |

|     14 | Amit     | Sales      | 42000.00 |          5 |      1 |

|     15 | Swathi   | Marketing  | 58000.00 |          7 |      5 |

+--------+----------+------------+----------+------------+--------+

15 rows in set (0.00 sec)



mysql> insert into employees1 values(16,'jay','IT', 50000,2,3);

Query OK, 1 row affected (0.01 sec)



mysql> select \* from employees1;

+--------+----------+------------+----------+------------+--------+

| emp\_id | emp\_name | department | salary   | experience | status |

+--------+----------+------------+----------+------------+--------+

|      1 | Ravi     | IT         | 60000.00 |          4 |      1 |

|      2 | Anil     | HR         | 45000.00 |          3 |      2 |

|      3 | Priya    | Finance    | 70000.00 |          6 |      4 |

|      4 | Sneha    | IT         | 85000.00 |          7 |      3 |

|      5 | Kiran    | Sales      | 35000.00 |          2 |      1 |

|      6 | Arjun    | IT         | 55000.00 |          5 |      5 |

|      7 | Divya    | HR         | 40000.00 |          4 |      2 |

|      8 | Rahul    | Finance    | 65000.00 |          8 |      6 |

|      9 | Meena    | Sales      | 30000.00 |          1 |      1 |

|     10 | Suresh   | IT         | 95000.00 |         10 |      7 |

|     11 | Pooja    | Marketing  | 50000.00 |          3 |      2 |

|     12 | Vijay    | Finance    | 48000.00 |          4 |      4 |

|     13 | Neha     | IT         | 72000.00 |          6 |      3 |

|     14 | Amit     | Sales      | 42000.00 |          5 |      1 |

|     15 | Swathi   | Marketing  | 58000.00 |          7 |      5 |

|     16 | jay      | IT         | 50000.00 |          2 |      3 |

+--------+----------+------------+----------+------------+--------+

16 rows in set (0.00 sec)































**17-08-26**



mysql> CREATE DATABASE CompanyDB;

Query OK, 1 row affected (0.14 sec)



mysql> USE CompanyDB;

Database changed

mysql> CREATE TABLE Employee

&#x20;   -> (

&#x20;   ->     empid INT PRIMARY KEY,

&#x20;   ->     ename VARCHAR(30),

&#x20;   ->     gender VARCHAR(10),

&#x20;   ->     dept VARCHAR(20),

&#x20;   ->     job VARCHAR(20),

&#x20;   ->     sal DECIMAL(10,2),

&#x20;   ->     city VARCHAR(20),

&#x20;   ->     age INT

&#x20;   -> );

Query OK, 0 rows affected (0.16 sec)



mysql> INSERT INTO Employee VALUES

&#x20;   -> (101,'Ravi','Male','IT','Developer',55000,'Hyderabad',25),

&#x20;   -> (102,'Sita','Female','HR','HR Executive',40000,'Chennai',28),

&#x20;   -> (103,'Arjun','Male','IT','Tester',45000,'Bangalore',26),

&#x20;   -> (104,'Priya','Female','Finance','Accountant',60000,'Hyderabad',30),

&#x20;   -> (105,'Kiran','Male','Sales','Sales Executive',35000,'Mumbai',24),

&#x20;   -> (106,'Anjali','Female','IT','Developer',70000,'Hyderabad',29),

&#x20;   -> (107,'Rahul','Male','HR','Manager',65000,'Delhi',35),

&#x20;   -> (108,'Sneha','Female','Sales','Sales Executive',38000,'Mumbai',27),

&#x20;   -> (109,'Vijay','Male','Finance','Manager',80000,'Chennai',40),

&#x20;   -> (110,'Divya','Female','IT','Developer',75000,'Bangalore',31),

&#x20;   -> (111,'Ajay','Male','IT','Developer',52000,'Hyderabad',27),

&#x20;   -> (112,'Pooja','Female','HR','HR Executive',42000,'Delhi',26),

&#x20;   -> (113,'Manoj','Male','Sales','Manager',68000,'Mumbai',36),

&#x20;   -> (114,'Neha','Female','Finance','Accountant',58000,'Hyderabad',29),

&#x20;   -> (115,'Karthik','Male','IT','Tester',48000,'Bangalore',25),

&#x20;   -> (116,'Meena','Female','Sales','Sales Executive',39000,'Chennai',28),

&#x20;   -> (117,'Surya','Male','Finance','Accountant',61000,'Hyderabad',33),

&#x20;   -> (118,'Lavanya','Female','IT','Developer',72000,'Hyderabad',30),

&#x20;   -> (119,'Ramesh','Male','HR','Manager',67000,'Delhi',38),

&#x20;   -> (120,'Keerthi','Female','Sales','Manager',69000,'Mumbai',34);

Query OK, 20 rows affected (0.07 sec)

Records: 20  Duplicates: 0  Warnings: 0



mysql> select sum(sal) as total salary from Employee

&#x20;   -> group by department;

ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'salary from Employee

group by department' at line 1

mysql> select sum(sal) as total\_salary from Employee

&#x20;   -> group by department;

ERROR 1054 (42S22): Unknown column 'department' in 'group statement'

mysql> select sum(sal) as total salary from Employee

&#x20;   -> group by dept;

ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'salary from Employee

group by dept' at line 1

mysql> select sum(sal) as total\_salary from Employee

&#x20;   -> group by dept;

+--------------+

| total\_salary |

+--------------+

|    417000.00 |

|    214000.00 |

|    259000.00 |

|    249000.00 |

+--------------+

4 rows in set (0.07 sec)



mysql> select dept,sum(sal) as total salary from Employee

&#x20;   -> group by dept;

ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'salary from Employee

group by dept' at line 1

mysql> select dept,sum(sal) as total\_salary from Employee

&#x20;   -> group by dept;

+---------+--------------+

| dept    | total\_salary |

+---------+--------------+

| IT      |    417000.00 |

| HR      |    214000.00 |

| Finance |    259000.00 |

| Sales   |    249000.00 |

+---------+--------------+

4 rows in set (0.00 sec)



mysql> select count(\*) from Employee

&#x20;   -> group by dept;

+----------+

| count(\*) |

+----------+

|        7 |

|        4 |

|        4 |

|        5 |

+----------+

4 rows in set (0.07 sec)



mysql> select name,count(\*) from Employee

&#x20;   -> group by dept;

ERROR 1054 (42S22): Unknown column 'name' in 'field list'

mysql> select ename,count(\*) from Employee

&#x20;   -> group by dept;

ERROR 1055 (42000): Expression #1 of SELECT list is not in GROUP BY clause and contains nonaggregated column 'companydb.Employee.ename' which is not functionally dependent on columns in GROUP BY clause; this is incompatible with sql\_mode=only\_full\_group\_by

mysql> select name,count(\*) from Employee;

ERROR 1054 (42S22): Unknown column 'name' in 'field list'

mysql> select ename,count(\*) from Employee

&#x20;   -> ;

ERROR 1140 (42000): In aggregated query without GROUP BY, expression #1 of SELECT list contains nonaggregated column 'companydb.Employee.ename'; this is incompatible with sql\_mode=only\_full\_group\_by

mysql> select ename, count

&#x20;   -> (\*) from Employee;

ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '\*) from Employee' at line 2

mysql> select ename, count(\*) from Employee;

ERROR 1140 (42000): In aggregated query without GROUP BY, expression #1 of SELECT list contains nonaggregated column 'companydb.Employee.ename'; this is incompatible with sql\_mode=only\_full\_group\_by

mysql> select count(\*) from Employee

&#x20;   -> group by dept;

+----------+

| count(\*) |

+----------+

|        7 |

|        4 |

|        4 |

|        5 |

+----------+

4 rows in set (0.00 sec)



mysql> select ename, count(\*) from Employee

&#x20;   -> group by dept;

ERROR 1055 (42000): Expression #1 of SELECT list is not in GROUP BY clause and contains nonaggregated column 'companydb.Employee.ename' which is not functionally dependent on columns in GROUP BY clause; this is incompatible with sql\_mode=only\_full\_group\_by

mysql> select dept, count(\*) from Employee

&#x20;   -> group by dept;

+---------+----------+

| dept    | count(\*) |

+---------+----------+

| IT      |        7 |

| HR      |        4 |

| Finance |        4 |

| Sales   |        5 |

+---------+----------+

4 rows in set (0.00 sec)



mysql> select avg(sal) as avg\_salary from Employee

&#x20;   -> group by dept;

+--------------+

| avg\_salary   |

+--------------+

| 59571.428571 |

| 53500.000000 |

| 64750.000000 |

| 49800.000000 |

+--------------+

4 rows in set (0.05 sec)



mysql> select dept,avg(sal) as avg\_salary from Employee

&#x20;   -> group by dept;

+---------+--------------+

| dept    | avg\_salary   |

+---------+--------------+

| IT      | 59571.428571 |

| HR      | 53500.000000 |

| Finance | 64750.000000 |

| Sales   | 49800.000000 |

+---------+--------------+

4 rows in set (0.00 sec)



mysql> select dept,max(sal) as avg\_salary from Employee

&#x20;   -> group by dept;

+---------+------------+

| dept    | avg\_salary |

+---------+------------+

| IT      |   75000.00 |

| HR      |   67000.00 |

| Finance |   80000.00 |

| Sales   |   69000.00 |

+---------+------------+

4 rows in set (0.01 sec)



mysql> select dept,min(sal) as avg\_salary from Employee

&#x20;   -> group by dept;

+---------+------------+

| dept    | avg\_salary |

+---------+------------+

| IT      |   45000.00 |

| HR      |   40000.00 |

| Finance |   58000.00 |

| Sales   |   35000.00 |

+---------+------------+

4 rows in set (0.00 sec)



mysql> select  count(\*) from Employee

&#x20;   -> group by gender;

+----------+

| count(\*) |

+----------+

|       10 |

|       10 |

+----------+

2 rows in set (0.00 sec)



mysql> select  gender, count(\*) from Employee

&#x20;   -> group by gender;

+--------+----------+

| gender | count(\*) |

+--------+----------+

| Male   |       10 |

| Female |       10 |

+--------+----------+

2 rows in set (0.00 sec)



mysql> select gender,avg(sal) as avg\_salary from Employee

&#x20;   -> group by gender;

+--------+--------------+

| gender | avg\_salary   |

+--------+--------------+

| Male   | 57600.000000 |

| Female | 56300.000000 |

+--------+--------------+

2 rows in set (0.00 sec)



mysql> select  job, count(\*) from Employee

&#x20;   -> group by job;

+-----------------+----------+

| job             | count(\*) |

+-----------------+----------+

| Developer       |        5 |

| HR Executive    |        2 |

| Tester          |        2 |

| Accountant      |        3 |

| Sales Executive |        3 |

| Manager         |        5 |

+-----------------+----------+

6 rows in set (0.00 sec)

mysql> select  dept, job, sum(sal) from Employee group by dept,job;

+---------+-----------------+-----------+

| dept    | job             | sum(sal)  |

+---------+-----------------+-----------+

| IT      | Developer       | 324000.00 |

| HR      | HR Executive    |  82000.00 |

| IT      | Tester          |  93000.00 |

| Finance | Accountant      | 179000.00 |

| Sales   | Sales Executive | 112000.00 |

| HR      | Manager         | 132000.00 |

| Finance | Manager         |  80000.00 |

| Sales   | Manager         | 137000.00 |

+---------+-----------------+-----------+

8 rows in set (0.01 sec)



mysql> select count(\*) from Employee

&#x20;   -> group by city;

+----------+

| count(\*) |

+----------+

|        7 |

|        3 |

|        3 |

|        4 |

|        3 |

+----------+

5 rows in set (0.00 sec)



mysql> select city,count(\*) from Employee

&#x20;   -> group by city;

+-----------+----------+

| city      | count(\*) |

+-----------+----------+

| Hyderabad |        7 |

| Chennai   |        3 |

| Bangalore |        3 |

| Mumbai    |        4 |

| Delhi     |        3 |

+-----------+----------+

5 rows in set (0.00 sec)



mysql>











18-08-26



mysql> use da22

Database changed

mysql> show tables

&#x20;   -> ;

+----------------+

| Tables\_in\_da22 |

+----------------+

| dep            |

| dept           |

| emp            |

| employee       |

| employees      |

| employees1     |

| employeess     |

| products       |

+----------------+

8 rows in set (0.01 sec)



mysql> use companyDB

Database changed

mysql> show tables;

+---------------------+

| Tables\_in\_companydb |

+---------------------+

| employee            |

+---------------------+

1 row in set (0.01 sec)



mysql> select \* from employee;

+-------+---------+--------+---------+-----------------+----------+-----------+------+

| empid | ename   | gender | dept    | job             | sal      | city      | age  |

+-------+---------+--------+---------+-----------------+----------+-----------+------+

|   101 | Ravi    | Male   | IT      | Developer       | 55000.00 | Hyderabad |   25 |

|   102 | Sita    | Female | HR      | HR Executive    | 40000.00 | Chennai   |   28 |

|   103 | Arjun   | Male   | IT      | Tester          | 45000.00 | Bangalore |   26 |

|   104 | Priya   | Female | Finance | Accountant      | 60000.00 | Hyderabad |   30 |

|   105 | Kiran   | Male   | Sales   | Sales Executive | 35000.00 | Mumbai    |   24 |

|   106 | Anjali  | Female | IT      | Developer       | 70000.00 | Hyderabad |   29 |

|   107 | Rahul   | Male   | HR      | Manager         | 65000.00 | Delhi     |   35 |

|   108 | Sneha   | Female | Sales   | Sales Executive | 38000.00 | Mumbai    |   27 |

|   109 | Vijay   | Male   | Finance | Manager         | 80000.00 | Chennai   |   40 |

|   110 | Divya   | Female | IT      | Developer       | 75000.00 | Bangalore |   31 |

|   111 | Ajay    | Male   | IT      | Developer       | 52000.00 | Hyderabad |   27 |

|   112 | Pooja   | Female | HR      | HR Executive    | 42000.00 | Delhi     |   26 |

|   113 | Manoj   | Male   | Sales   | Manager         | 68000.00 | Mumbai    |   36 |

|   114 | Neha    | Female | Finance | Accountant      | 58000.00 | Hyderabad |   29 |

|   115 | Karthik | Male   | IT      | Tester          | 48000.00 | Bangalore |   25 |

|   116 | Meena   | Female | Sales   | Sales Executive | 39000.00 | Chennai   |   28 |

|   117 | Surya   | Male   | Finance | Accountant      | 61000.00 | Hyderabad |   33 |

|   118 | Lavanya | Female | IT      | Developer       | 72000.00 | Hyderabad |   30 |

|   119 | Ramesh  | Male   | HR      | Manager         | 67000.00 | Delhi     |   38 |

|   120 | Keerthi | Female | Sales   | Manager         | 69000.00 | Mumbai    |   34 |

+-------+---------+--------+---------+-----------------+----------+-----------+------+

20 rows in set (0.05 sec)



mysql> select dept from employee having dept>5;

Empty set, 9 warnings (0.01 sec)



mysql> select dept, count(\*) from employee group by dept having dept>5;

Empty set, 2 warnings (0.03 sec)



mysql> select dept, count(\*) from employee group by dept;

+---------+----------+

| dept    | count(\*) |

+---------+----------+

| IT      |        7 |

| HR      |        4 |

| Finance |        4 |

| Sales   |        5 |

+---------+----------+

4 rows in set (0.04 sec)



mysql> select dept, count(\*) from employee group by dept having count(\*)>5;

+------+----------+

| dept | count(\*) |

+------+----------+

| IT   |        7 |

+------+----------+

1 row in set (0.00 sec)



mysql> select dept, avg(sal) from employee group by dept having avg(sal)>50000;

+---------+--------------+

| dept    | avg(sal)     |

+---------+--------------+

| IT      | 59571.428571 |

| HR      | 53500.000000 |

| Finance | 64750.000000 |

+---------+--------------+

3 rows in set (0.01 sec)



mysql> select job,max(sal) from employee group by job having max(sal)>80000;

Empty set (0.01 sec)



mysql> select job,max(sal) from employee group by job having max(sal)=80000;

+---------+----------+

| job     | max(sal) |

+---------+----------+

| Manager | 80000.00 |

+---------+----------+

1 row in set (0.00 sec)



mysql> select job,max(sal) from employee group by job having max(sal)=>80000;

ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '=>80000' at line 1

mysql> select job,max(sal) from employee group by job having max(sal)=80000;

+---------+----------+

| job     | max(sal) |

+---------+----------+

| Manager | 80000.00 |

+---------+----------+

1 row in set (0.00 sec)



mysql> select city, count(\*) from employee group by city having count(\*)>3;

+-----------+----------+

| city      | count(\*) |

+-----------+----------+

| Hyderabad |        7 |

| Mumbai    |        4 |

+-----------+----------+

2 rows in set (0.00 sec)



mysql> select gender, sum(sal) from employee group by sal having sum(sal)>3;

ERROR 1055 (42000): Expression #1 of SELECT list is not in GROUP BY clause and contains nonaggregated column 'companydb.employee.gender' which is not functionally dependent on columns in GROUP BY clause; this is incompatible with sql\_mode=only\_full\_group\_by

mysql> select gender, sum(sal) from employee group by gender having sum(sal)>3;

+--------+-----------+

| gender | sum(sal)  |

+--------+-----------+

| Male   | 576000.00 |

| Female | 563000.00 |

+--------+-----------+

2 rows in set (0.04 sec)



mysql> select gender, sum(sal) from employee group by gender having sum(sal)>20000;

+--------+-----------+

| gender | sum(sal)  |

+--------+-----------+

| Male   | 576000.00 |

| Female | 563000.00 |

+--------+-----------+

2 rows in set (0.00 sec)



mysql> select dept, min(sal) from employee group by sal having min(sum)>30000;

ERROR 1054 (42S22): Unknown column 'sum' in 'having clause'

mysql> select dept, min(sal) from employee group by sal having min(sal)>30000;

ERROR 1055 (42000): Expression #1 of SELECT list is not in GROUP BY clause and contains nonaggregated column 'companydb.employee.dept' which is not functionally dependent on columns in GROUP BY clause; this is incompatible with sql\_mode=only\_full\_group\_by

mysql> select dept, min(sal) from employee group by dept having min(sal)>30000;

+---------+----------+

| dept    | min(sal) |

+---------+----------+

| IT      | 45000.00 |

| HR      | 40000.00 |

| Finance | 58000.00 |

| Sales   | 35000.00 |

+---------+----------+

4 rows in set (0.04 sec)



mysql> select job, count(\*) from employee group by job having count(\*)>3;

+-----------+----------+

| job       | count(\*) |

+-----------+----------+

| Developer |        5 |

| Manager   |        5 |

+-----------+----------+

2 rows in set (0.00 sec)



mysql> select job, count(\*) from employee group by job having count(\*)>2;

+-----------------+----------+

| job             | count(\*) |

+-----------------+----------+

| Developer       |        5 |

| Accountant      |        3 |

| Sales Executive |        3 |

| Manager         |        5 |

+-----------------+----------+

4 rows in set (0.00 sec)



mysql> select dept, total(sal) from product group by dept having total(sal)<30000;

ERROR 1146 (42S02): Table 'companydb.product' doesn't exist

mysql> select dept, total(sal) from employee group by dept having total(sal)<30000;

ERROR 1305 (42000): FUNCTION companydb.total does not exist

mysql> select dept, sum(sal) from employee group by dept having sum(sal)<30000;

Empty set (0.04 sec)



mysql> select dept, sum(sal) from employee group by dept having sum(sal)<300000;

+---------+-----------+

| dept    | sum(sal)  |

+---------+-----------+

| HR      | 214000.00 |

| Finance | 259000.00 |

| Sales   | 249000.00 |

+---------+-----------+

3 rows in set (0.00 sec)



mysql> select city, avg(age) from employee group by city having avg(age)>30;

+---------+----------+

| city    | avg(age) |

+---------+----------+

| Chennai |  32.0000 |

| Mumbai  |  30.2500 |

| Delhi   |  33.0000 |

+---------+----------+

3 rows in set (0.00 sec)



mysql> select dept, max(sal) from employee group by dept having max(sal)<70000;

+-------+----------+

| dept  | max(sal) |

+-------+----------+

| HR    | 67000.00 |

| Sales | 69000.00 |

+-------+----------+

2 rows in set (0.00 sec)



mysql> select \* from employee having salary asc;

ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'asc' at line 1

mysql> select \* from employee order by price;

ERROR 1054 (42S22): Unknown column 'price' in 'order clause'

mysql> select \* from employee order by sal;

+-------+---------+--------+---------+-----------------+----------+-----------+------+

| empid | ename   | gender | dept    | job             | sal      | city      | age  |

+-------+---------+--------+---------+-----------------+----------+-----------+------+

|   105 | Kiran   | Male   | Sales   | Sales Executive | 35000.00 | Mumbai    |   24 |

|   108 | Sneha   | Female | Sales   | Sales Executive | 38000.00 | Mumbai    |   27 |

|   116 | Meena   | Female | Sales   | Sales Executive | 39000.00 | Chennai   |   28 |

|   102 | Sita    | Female | HR      | HR Executive    | 40000.00 | Chennai   |   28 |

|   112 | Pooja   | Female | HR      | HR Executive    | 42000.00 | Delhi     |   26 |

|   103 | Arjun   | Male   | IT      | Tester          | 45000.00 | Bangalore |   26 |

|   115 | Karthik | Male   | IT      | Tester          | 48000.00 | Bangalore |   25 |

|   111 | Ajay    | Male   | IT      | Developer       | 52000.00 | Hyderabad |   27 |

|   101 | Ravi    | Male   | IT      | Developer       | 55000.00 | Hyderabad |   25 |

|   114 | Neha    | Female | Finance | Accountant      | 58000.00 | Hyderabad |   29 |

|   104 | Priya   | Female | Finance | Accountant      | 60000.00 | Hyderabad |   30 |

|   117 | Surya   | Male   | Finance | Accountant      | 61000.00 | Hyderabad |   33 |

|   107 | Rahul   | Male   | HR      | Manager         | 65000.00 | Delhi     |   35 |

|   119 | Ramesh  | Male   | HR      | Manager         | 67000.00 | Delhi     |   38 |

|   113 | Manoj   | Male   | Sales   | Manager         | 68000.00 | Mumbai    |   36 |

|   120 | Keerthi | Female | Sales   | Manager         | 69000.00 | Mumbai    |   34 |

|   106 | Anjali  | Female | IT      | Developer       | 70000.00 | Hyderabad |   29 |

|   118 | Lavanya | Female | IT      | Developer       | 72000.00 | Hyderabad |   30 |

|   110 | Divya   | Female | IT      | Developer       | 75000.00 | Bangalore |   31 |

|   109 | Vijay   | Male   | Finance | Manager         | 80000.00 | Chennai   |   40 |

+-------+---------+--------+---------+-----------------+----------+-----------+------+

20 rows in set (0.06 sec)



mysql> select \* from employee order by sal desc;

+-------+---------+--------+---------+-----------------+----------+-----------+------+

| empid | ename   | gender | dept    | job             | sal      | city      | age  |

+-------+---------+--------+---------+-----------------+----------+-----------+------+

|   109 | Vijay   | Male   | Finance | Manager         | 80000.00 | Chennai   |   40 |

|   110 | Divya   | Female | IT      | Developer       | 75000.00 | Bangalore |   31 |

|   118 | Lavanya | Female | IT      | Developer       | 72000.00 | Hyderabad |   30 |

|   106 | Anjali  | Female | IT      | Developer       | 70000.00 | Hyderabad |   29 |

|   120 | Keerthi | Female | Sales   | Manager         | 69000.00 | Mumbai    |   34 |

|   113 | Manoj   | Male   | Sales   | Manager         | 68000.00 | Mumbai    |   36 |

|   119 | Ramesh  | Male   | HR      | Manager         | 67000.00 | Delhi     |   38 |

|   107 | Rahul   | Male   | HR      | Manager         | 65000.00 | Delhi     |   35 |

|   117 | Surya   | Male   | Finance | Accountant      | 61000.00 | Hyderabad |   33 |

|   104 | Priya   | Female | Finance | Accountant      | 60000.00 | Hyderabad |   30 |

|   114 | Neha    | Female | Finance | Accountant      | 58000.00 | Hyderabad |   29 |

|   101 | Ravi    | Male   | IT      | Developer       | 55000.00 | Hyderabad |   25 |

|   111 | Ajay    | Male   | IT      | Developer       | 52000.00 | Hyderabad |   27 |

|   115 | Karthik | Male   | IT      | Tester          | 48000.00 | Bangalore |   25 |

|   103 | Arjun   | Male   | IT      | Tester          | 45000.00 | Bangalore |   26 |

|   112 | Pooja   | Female | HR      | HR Executive    | 42000.00 | Delhi     |   26 |

|   102 | Sita    | Female | HR      | HR Executive    | 40000.00 | Chennai   |   28 |

|   116 | Meena   | Female | Sales   | Sales Executive | 39000.00 | Chennai   |   28 |

|   108 | Sneha   | Female | Sales   | Sales Executive | 38000.00 | Mumbai    |   27 |

|   105 | Kiran   | Male   | Sales   | Sales Executive | 35000.00 | Mumbai    |   24 |

+-------+---------+--------+---------+-----------------+----------+-----------+------+

20 rows in set (0.00 sec)



mysql> select \* from employee order by dept;

+-------+---------+--------+---------+-----------------+----------+-----------+------+

| empid | ename   | gender | dept    | job             | sal      | city      | age  |

+-------+---------+--------+---------+-----------------+----------+-----------+------+

|   104 | Priya   | Female | Finance | Accountant      | 60000.00 | Hyderabad |   30 |

|   109 | Vijay   | Male   | Finance | Manager         | 80000.00 | Chennai   |   40 |

|   114 | Neha    | Female | Finance | Accountant      | 58000.00 | Hyderabad |   29 |

|   117 | Surya   | Male   | Finance | Accountant      | 61000.00 | Hyderabad |   33 |

|   102 | Sita    | Female | HR      | HR Executive    | 40000.00 | Chennai   |   28 |

|   107 | Rahul   | Male   | HR      | Manager         | 65000.00 | Delhi     |   35 |

|   112 | Pooja   | Female | HR      | HR Executive    | 42000.00 | Delhi     |   26 |

|   119 | Ramesh  | Male   | HR      | Manager         | 67000.00 | Delhi     |   38 |

|   101 | Ravi    | Male   | IT      | Developer       | 55000.00 | Hyderabad |   25 |

|   103 | Arjun   | Male   | IT      | Tester          | 45000.00 | Bangalore |   26 |

|   106 | Anjali  | Female | IT      | Developer       | 70000.00 | Hyderabad |   29 |

|   110 | Divya   | Female | IT      | Developer       | 75000.00 | Bangalore |   31 |

|   111 | Ajay    | Male   | IT      | Developer       | 52000.00 | Hyderabad |   27 |

|   115 | Karthik | Male   | IT      | Tester          | 48000.00 | Bangalore |   25 |

|   118 | Lavanya | Female | IT      | Developer       | 72000.00 | Hyderabad |   30 |

|   105 | Kiran   | Male   | Sales   | Sales Executive | 35000.00 | Mumbai    |   24 |

|   108 | Sneha   | Female | Sales   | Sales Executive | 38000.00 | Mumbai    |   27 |

|   113 | Manoj   | Male   | Sales   | Manager         | 68000.00 | Mumbai    |   36 |

|   116 | Meena   | Female | Sales   | Sales Executive | 39000.00 | Chennai   |   28 |

|   120 | Keerthi | Female | Sales   | Manager         | 69000.00 | Mumbai    |   34 |

+-------+---------+--------+---------+-----------------+----------+-----------+------+

20 rows in set (0.05 sec)



mysql> select \* from employee order by dept, order by sal desc;

ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'order by sal desc' at line 1

mysql> select \* from employee order by dept,sal desc;

+-------+---------+--------+---------+-----------------+----------+-----------+------+

| empid | ename   | gender | dept    | job             | sal      | city      | age  |

+-------+---------+--------+---------+-----------------+----------+-----------+------+

|   109 | Vijay   | Male   | Finance | Manager         | 80000.00 | Chennai   |   40 |

|   117 | Surya   | Male   | Finance | Accountant      | 61000.00 | Hyderabad |   33 |

|   104 | Priya   | Female | Finance | Accountant      | 60000.00 | Hyderabad |   30 |

|   114 | Neha    | Female | Finance | Accountant      | 58000.00 | Hyderabad |   29 |

|   119 | Ramesh  | Male   | HR      | Manager         | 67000.00 | Delhi     |   38 |

|   107 | Rahul   | Male   | HR      | Manager         | 65000.00 | Delhi     |   35 |

|   112 | Pooja   | Female | HR      | HR Executive    | 42000.00 | Delhi     |   26 |

|   102 | Sita    | Female | HR      | HR Executive    | 40000.00 | Chennai   |   28 |

|   110 | Divya   | Female | IT      | Developer       | 75000.00 | Bangalore |   31 |

|   118 | Lavanya | Female | IT      | Developer       | 72000.00 | Hyderabad |   30 |

|   106 | Anjali  | Female | IT      | Developer       | 70000.00 | Hyderabad |   29 |

|   101 | Ravi    | Male   | IT      | Developer       | 55000.00 | Hyderabad |   25 |

|   111 | Ajay    | Male   | IT      | Developer       | 52000.00 | Hyderabad |   27 |

|   115 | Karthik | Male   | IT      | Tester          | 48000.00 | Bangalore |   25 |

|   103 | Arjun   | Male   | IT      | Tester          | 45000.00 | Bangalore |   26 |

|   120 | Keerthi | Female | Sales   | Manager         | 69000.00 | Mumbai    |   34 |

|   113 | Manoj   | Male   | Sales   | Manager         | 68000.00 | Mumbai    |   36 |

|   116 | Meena   | Female | Sales   | Sales Executive | 39000.00 | Chennai   |   28 |

|   108 | Sneha   | Female | Sales   | Sales Executive | 38000.00 | Mumbai    |   27 |

|   105 | Kiran   | Male   | Sales   | Sales Executive | 35000.00 | Mumbai    |   24 |

+-------+---------+--------+---------+-----------------+----------+-----------+------+

20 rows in set (0.00 sec)



mysql> select \* from employee order by city, ename;

+-------+---------+--------+---------+-----------------+----------+-----------+------+

| empid | ename   | gender | dept    | job             | sal      | city      | age  |

+-------+---------+--------+---------+-----------------+----------+-----------+------+

|   103 | Arjun   | Male   | IT      | Tester          | 45000.00 | Bangalore |   26 |

|   110 | Divya   | Female | IT      | Developer       | 75000.00 | Bangalore |   31 |

|   115 | Karthik | Male   | IT      | Tester          | 48000.00 | Bangalore |   25 |

|   116 | Meena   | Female | Sales   | Sales Executive | 39000.00 | Chennai   |   28 |

|   102 | Sita    | Female | HR      | HR Executive    | 40000.00 | Chennai   |   28 |

|   109 | Vijay   | Male   | Finance | Manager         | 80000.00 | Chennai   |   40 |

|   112 | Pooja   | Female | HR      | HR Executive    | 42000.00 | Delhi     |   26 |

|   107 | Rahul   | Male   | HR      | Manager         | 65000.00 | Delhi     |   35 |

|   119 | Ramesh  | Male   | HR      | Manager         | 67000.00 | Delhi     |   38 |

|   111 | Ajay    | Male   | IT      | Developer       | 52000.00 | Hyderabad |   27 |

|   106 | Anjali  | Female | IT      | Developer       | 70000.00 | Hyderabad |   29 |

|   118 | Lavanya | Female | IT      | Developer       | 72000.00 | Hyderabad |   30 |

|   114 | Neha    | Female | Finance | Accountant      | 58000.00 | Hyderabad |   29 |

|   104 | Priya   | Female | Finance | Accountant      | 60000.00 | Hyderabad |   30 |

|   101 | Ravi    | Male   | IT      | Developer       | 55000.00 | Hyderabad |   25 |

|   117 | Surya   | Male   | Finance | Accountant      | 61000.00 | Hyderabad |   33 |

|   120 | Keerthi | Female | Sales   | Manager         | 69000.00 | Mumbai    |   34 |

|   105 | Kiran   | Male   | Sales   | Sales Executive | 35000.00 | Mumbai    |   24 |

|   113 | Manoj   | Male   | Sales   | Manager         | 68000.00 | Mumbai    |   36 |

|   108 | Sneha   | Female | Sales   | Sales Executive | 38000.00 | Mumbai    |   27 |

+-------+---------+--------+---------+-----------------+----------+-----------+------+

20 rows in set (0.00 sec)



mysql> select \* from employee order by age asc;

+-------+---------+--------+---------+-----------------+----------+-----------+------+

| empid | ename   | gender | dept    | job             | sal      | city      | age  |

+-------+---------+--------+---------+-----------------+----------+-----------+------+

|   105 | Kiran   | Male   | Sales   | Sales Executive | 35000.00 | Mumbai    |   24 |

|   101 | Ravi    | Male   | IT      | Developer       | 55000.00 | Hyderabad |   25 |

|   115 | Karthik | Male   | IT      | Tester          | 48000.00 | Bangalore |   25 |

|   103 | Arjun   | Male   | IT      | Tester          | 45000.00 | Bangalore |   26 |

|   112 | Pooja   | Female | HR      | HR Executive    | 42000.00 | Delhi     |   26 |

|   108 | Sneha   | Female | Sales   | Sales Executive | 38000.00 | Mumbai    |   27 |

|   111 | Ajay    | Male   | IT      | Developer       | 52000.00 | Hyderabad |   27 |

|   102 | Sita    | Female | HR      | HR Executive    | 40000.00 | Chennai   |   28 |

|   116 | Meena   | Female | Sales   | Sales Executive | 39000.00 | Chennai   |   28 |

|   106 | Anjali  | Female | IT      | Developer       | 70000.00 | Hyderabad |   29 |

|   114 | Neha    | Female | Finance | Accountant      | 58000.00 | Hyderabad |   29 |

|   104 | Priya   | Female | Finance | Accountant      | 60000.00 | Hyderabad |   30 |

|   118 | Lavanya | Female | IT      | Developer       | 72000.00 | Hyderabad |   30 |

|   110 | Divya   | Female | IT      | Developer       | 75000.00 | Bangalore |   31 |

|   117 | Surya   | Male   | Finance | Accountant      | 61000.00 | Hyderabad |   33 |

|   120 | Keerthi | Female | Sales   | Manager         | 69000.00 | Mumbai    |   34 |

|   107 | Rahul   | Male   | HR      | Manager         | 65000.00 | Delhi     |   35 |

|   113 | Manoj   | Male   | Sales   | Manager         | 68000.00 | Mumbai    |   36 |

|   119 | Ramesh  | Male   | HR      | Manager         | 67000.00 | Delhi     |   38 |

|   109 | Vijay   | Male   | Finance | Manager         | 80000.00 | Chennai   |   40 |

+-------+---------+--------+---------+-----------------+----------+-----------+------+

20 rows in set (0.04 sec)



mysql> select \* from employee order by age desc;

+-------+---------+--------+---------+-----------------+----------+-----------+------+

| empid | ename   | gender | dept    | job             | sal      | city      | age  |

+-------+---------+--------+---------+-----------------+----------+-----------+------+

|   109 | Vijay   | Male   | Finance | Manager         | 80000.00 | Chennai   |   40 |

|   119 | Ramesh  | Male   | HR      | Manager         | 67000.00 | Delhi     |   38 |

|   113 | Manoj   | Male   | Sales   | Manager         | 68000.00 | Mumbai    |   36 |

|   107 | Rahul   | Male   | HR      | Manager         | 65000.00 | Delhi     |   35 |

|   120 | Keerthi | Female | Sales   | Manager         | 69000.00 | Mumbai    |   34 |

|   117 | Surya   | Male   | Finance | Accountant      | 61000.00 | Hyderabad |   33 |

|   110 | Divya   | Female | IT      | Developer       | 75000.00 | Bangalore |   31 |

|   104 | Priya   | Female | Finance | Accountant      | 60000.00 | Hyderabad |   30 |

|   118 | Lavanya | Female | IT      | Developer       | 72000.00 | Hyderabad |   30 |

|   106 | Anjali  | Female | IT      | Developer       | 70000.00 | Hyderabad |   29 |

|   114 | Neha    | Female | Finance | Accountant      | 58000.00 | Hyderabad |   29 |

|   102 | Sita    | Female | HR      | HR Executive    | 40000.00 | Chennai   |   28 |

|   116 | Meena   | Female | Sales   | Sales Executive | 39000.00 | Chennai   |   28 |

|   108 | Sneha   | Female | Sales   | Sales Executive | 38000.00 | Mumbai    |   27 |

|   111 | Ajay    | Male   | IT      | Developer       | 52000.00 | Hyderabad |   27 |

|   103 | Arjun   | Male   | IT      | Tester          | 45000.00 | Bangalore |   26 |

|   112 | Pooja   | Female | HR      | HR Executive    | 42000.00 | Delhi     |   26 |

|   101 | Ravi    | Male   | IT      | Developer       | 55000.00 | Hyderabad |   25 |

|   115 | Karthik | Male   | IT      | Tester          | 48000.00 | Bangalore |   25 |

|   105 | Kiran   | Male   | Sales   | Sales Executive | 35000.00 | Mumbai    |   24 |

+-------+---------+--------+---------+-----------------+----------+-----------+------+

20 rows in set (0.00 sec)



mysql> select gender from employee order by sal desc;

+--------+

| gender |

+--------+

| Male   |

| Female |

| Female |

| Female |

| Female |

| Male   |

| Male   |

| Male   |

| Male   |

| Female |

| Female |

| Male   |

| Male   |

| Male   |

| Male   |

| Female |

| Female |

| Female |

| Female |

| Male   |

+--------+

20 rows in set (0.00 sec)



mysql> select gender,sal from employee order by sal desc;

+--------+----------+

| gender | sal      |

+--------+----------+

| Male   | 80000.00 |

| Female | 75000.00 |

| Female | 72000.00 |

| Female | 70000.00 |

| Female | 69000.00 |

| Male   | 68000.00 |

| Male   | 67000.00 |

| Male   | 65000.00 |

| Male   | 61000.00 |

| Female | 60000.00 |

| Female | 58000.00 |

| Male   | 55000.00 |

| Male   | 52000.00 |

| Male   | 48000.00 |

| Male   | 45000.00 |

| Female | 42000.00 |

| Female | 40000.00 |

| Female | 39000.00 |

| Female | 38000.00 |

| Male   | 35000.00 |

+--------+----------+

20 rows in set (0.00 sec)



mysql> select \* from employee order by job,dept,sal;

+-------+---------+--------+---------+-----------------+----------+-----------+------+

| empid | ename   | gender | dept    | job             | sal      | city      | age  |

+-------+---------+--------+---------+-----------------+----------+-----------+------+

|   114 | Neha    | Female | Finance | Accountant      | 58000.00 | Hyderabad |   29 |

|   104 | Priya   | Female | Finance | Accountant      | 60000.00 | Hyderabad |   30 |

|   117 | Surya   | Male   | Finance | Accountant      | 61000.00 | Hyderabad |   33 |

|   111 | Ajay    | Male   | IT      | Developer       | 52000.00 | Hyderabad |   27 |

|   101 | Ravi    | Male   | IT      | Developer       | 55000.00 | Hyderabad |   25 |

|   106 | Anjali  | Female | IT      | Developer       | 70000.00 | Hyderabad |   29 |

|   118 | Lavanya | Female | IT      | Developer       | 72000.00 | Hyderabad |   30 |

|   110 | Divya   | Female | IT      | Developer       | 75000.00 | Bangalore |   31 |

|   102 | Sita    | Female | HR      | HR Executive    | 40000.00 | Chennai   |   28 |

|   112 | Pooja   | Female | HR      | HR Executive    | 42000.00 | Delhi     |   26 |

|   109 | Vijay   | Male   | Finance | Manager         | 80000.00 | Chennai   |   40 |

|   107 | Rahul   | Male   | HR      | Manager         | 65000.00 | Delhi     |   35 |

|   119 | Ramesh  | Male   | HR      | Manager         | 67000.00 | Delhi     |   38 |

|   113 | Manoj   | Male   | Sales   | Manager         | 68000.00 | Mumbai    |   36 |

|   120 | Keerthi | Female | Sales   | Manager         | 69000.00 | Mumbai    |   34 |

|   105 | Kiran   | Male   | Sales   | Sales Executive | 35000.00 | Mumbai    |   24 |

|   108 | Sneha   | Female | Sales   | Sales Executive | 38000.00 | Mumbai    |   27 |

|   116 | Meena   | Female | Sales   | Sales Executive | 39000.00 | Chennai   |   28 |

|   103 | Arjun   | Male   | IT      | Tester          | 45000.00 | Bangalore |   26 |

|   115 | Karthik | Male   | IT      | Tester          | 48000.00 | Bangalore |   25 |

+-------+---------+--------+---------+-----------------+----------+-----------+------+

20 rows in set (0.00 sec)



mysql> select \* from employee order by job asc ,dept asc,sal asc;

+-------+---------+--------+---------+-----------------+----------+-----------+------+

| empid | ename   | gender | dept    | job             | sal      | city      | age  |

+-------+---------+--------+---------+-----------------+----------+-----------+------+

|   114 | Neha    | Female | Finance | Accountant      | 58000.00 | Hyderabad |   29 |

|   104 | Priya   | Female | Finance | Accountant      | 60000.00 | Hyderabad |   30 |

|   117 | Surya   | Male   | Finance | Accountant      | 61000.00 | Hyderabad |   33 |

|   111 | Ajay    | Male   | IT      | Developer       | 52000.00 | Hyderabad |   27 |

|   101 | Ravi    | Male   | IT      | Developer       | 55000.00 | Hyderabad |   25 |

|   106 | Anjali  | Female | IT      | Developer       | 70000.00 | Hyderabad |   29 |

|   118 | Lavanya | Female | IT      | Developer       | 72000.00 | Hyderabad |   30 |

|   110 | Divya   | Female | IT      | Developer       | 75000.00 | Bangalore |   31 |

|   102 | Sita    | Female | HR      | HR Executive    | 40000.00 | Chennai   |   28 |

|   112 | Pooja   | Female | HR      | HR Executive    | 42000.00 | Delhi     |   26 |

|   109 | Vijay   | Male   | Finance | Manager         | 80000.00 | Chennai   |   40 |

|   107 | Rahul   | Male   | HR      | Manager         | 65000.00 | Delhi     |   35 |

|   119 | Ramesh  | Male   | HR      | Manager         | 67000.00 | Delhi     |   38 |

|   113 | Manoj   | Male   | Sales   | Manager         | 68000.00 | Mumbai    |   36 |

|   120 | Keerthi | Female | Sales   | Manager         | 69000.00 | Mumbai    |   34 |

|   105 | Kiran   | Male   | Sales   | Sales Executive | 35000.00 | Mumbai    |   24 |

|   108 | Sneha   | Female | Sales   | Sales Executive | 38000.00 | Mumbai    |   27 |

|   116 | Meena   | Female | Sales   | Sales Executive | 39000.00 | Chennai   |   28 |

|   103 | Arjun   | Male   | IT      | Tester          | 45000.00 | Bangalore |   26 |

|   115 | Karthik | Male   | IT      | Tester          | 48000.00 | Bangalore |   25 |

+-------+---------+--------+---------+-----------------+----------+-----------+------+

20 rows in set (0.00 sec)



mysql> select dept, sum(sal) from employee group by dept order by sum(sal) desc;

+---------+-----------+

| dept    | sum(sal)  |

+---------+-----------+

| IT      | 417000.00 |

| Finance | 259000.00 |

| Sales   | 249000.00 |

| HR      | 214000.00 |

+---------+-----------+

4 rows in set (0.00 sec)

