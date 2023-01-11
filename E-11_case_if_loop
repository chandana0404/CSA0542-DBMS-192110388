mysql> use sse;
Database changed
mysql> show tables;
+---------------+
| Tables_in_sse |
+---------------+
| bin           |
| empdepartment |
| empdept       |
| employee      |
| marks_view    |
| mdept         |
| mentees       |
| mentees1      |
| student       |
| studepartment |
| t             |
+---------------+
11 rows in set (0.00 sec)mysql> select*from mentees;
+-----------+---------+------+---------+------------+-------+---------+
| Regno     | Name    | Dept | Address | Fathername | Marks | subject |
+-----------+---------+------+---------+------------+-------+---------+
| 192011090 | Gowtham | CSE  | Chennai | moorthi    |    99 | DBMS    |
| 192011079 | arun    | BME  | nellore | muthu      |    91 | BIOEVS  |
| 192011095 | Harish  | ECE  | Madurai | Kannan     |    95 | PDSD    |
| 192211080 | Dhivya  | ECE  | Tirupur | Ramesh     |    91 | PDSD    |
+-----------+---------+------+---------+------------+-------+---------+
4 rows in set (0.01 sec)mysql> SELECT Name, Marks,CASE WHEN Marks > 95 THEN 'Excellent' WHEN Marks >90 THEN 'Good' ELSE 'average' END AS performance FROM mentees;
+---------+-------+-------------+
| Name    | Marks | performance |
+---------+-------+-------------+
| Gowtham |    99 | Excellent   |
| arun    |    91 | Good        |
| Harish  |    95 | Good        |
| Dhivya  |    91 | Good        |
+---------+-------+-------------+
4 rows in set (0.00 sec)
mysql> select Name,Marks,if(Marks>=95,"Excellent marks","Good marks") from mentees;
+---------+-------+----------------------------------------------+
| Name    | Marks | if(Marks>=95,"Excellent marks","Good marks") |
+---------+-------+----------------------------------------------+
| Gowtham |    99 | Excellent marks                              |
| arun    |    91 | Good marks                                   |
| Harish  |    95 | Excellent marks                              |
| Dhivya  |    91 | Good marks                                   |
+---------+-------+----------------------------------------------+
4 rows in set (0.00 sec)
mysql> DELIMITER $$
mysql> CREATE FUNCTION REPEAT_DEMO(INC INT)
    -> RETURNS CHAR(40)
    -> DETERMINISTIC
    -> BEGIN
    -> DECLARE INCOME INT;
    -> SET INCOME=0;
    -> REPEAT
    -> SET INCOME=INCOME+INC;
    -> UNTIL INCOME>4000
    -> END REPEAT;
    -> RETURN "INCOME>4000 DETECTED";
    -> END;
    -> $$
Query OK, 0 rows affected (0.01 sec)

mysql> SELECT REPEAT_DEMO(3000);$$
+----------------------+
| REPEAT_DEMO(3000)    |
+----------------------+
| INCOME>4000 DETECTED |
+----------------------+
1 row in set (0.00 sec)

mysql> SELECT REPEAT_DEMO(4000);$$
+----------------------+
| REPEAT_DEMO(4000)    |
+----------------------+
| INCOME>4000 DETECTED |
+----------------------+
1 row in set (0.00 sec)
mysql> DELIMITER $$
mysql> CREATE FUNCTION WHILE_DEMO(VALUE CHAR(1))
    -> RETURNS CHAR(20)
    -> DETERMINISTIC
    -> BEGIN
    -> DECLARE STR CHAR(100);
    -> DECLARE I INT;
    -> SET STR='';
    -> SET I=1;
    -> LABEL:
    -> WHILE I<=5 DO
    -> SET STR =CONCAT(STR,VALUE);
    -> SET I=I+1;
    -> END WHILE LABEL;
    -> RETURN STR;
    -> END;
    -> $$
Query OK, 0 rows affected (0.02 sec)

mysql> SELECT WHILE_DEMO('A');$$
+-----------------+
| WHILE_DEMO('A') |
+-----------------+
| AAAAA           |
+-----------------+
1 row in set (0.01 sec)
