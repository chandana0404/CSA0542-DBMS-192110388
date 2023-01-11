mysql> use sse;
Database changed
mysql> DELIMITER //
mysql> CREATE FUNCTION CUSTOMER(CRE_LIM INT)
    -> RETURNS VARCHAR(20)
    -> DETERMINISTIC
    -> BEGIN
    ->   DECLARE CUSTOMER_LEVEL VARCHAR(20);
    ->   SET CUSTOMER_LEVEL='';
    -> IF CRE_LIM >50000 THEN
    ->   SET CUSTOMER_LEVEL='PLATINUM';
    -> ELSEIF CRE_LIM <=50000 AND CRE_LIM>=10000 THEN
    ->   SET CUSTOMER_LEVEL='GOLD';
    -> ELSEIF CRE_LIM < 10000 THEN
    ->   SET CUSTOMER_LEVEL='SILVER';
    -> END IF;
    -> RETURN CUSTOMER_LEVEL;
    -> END //
Query OK, 0 rows affected (0.01 sec)

mysql> SELECT CUSTOMER(40000);
    -> //
+-----------------+
| CUSTOMER(40000) |
+-----------------+
| GOLD            |
+-----------------+
1 row in set (0.00 sec)

mysql> SELECT CUSTOMER(50000);
    -> //
+-----------------+
| CUSTOMER(50000) |
+-----------------+
| GOLD            |
+-----------------+
1 row in set (0.00 sec)

mysql> SELECT CUSTOMER(550000);
    -> //
+------------------+
| CUSTOMER(550000) |
+------------------+
| PLATINUM         |
+------------------+
1 row in set (0.00 sec)

mysql> SELECT CUSTOMER(1000);
    -> //
+----------------+
| CUSTOMER(1000) |
+----------------+
| SILVER         |
+----------------+
1 row in set (0.00 sec)


mysql> DELIMITER $$
mysql> CREATE PROCEDURE find_fact(IN n INT)
    -> BEGIN
    -> SET @@GLOBAL.max_sp_recursion_depth =255;
    -> SET @@session.max_sp_recursion_depth=255;
    -> CALL factorial(n,@fact);
    -> SELECT @fact;
    -> END
    -> $$
Query OK, 0 rows affected (0.02 sec)

mysql> DELIMITER $$
mysql> CREATE PROCEDURE factorial(IN n INT,OUT fact INT)
    -> BEGIN
    -> IF n=1 THEN
    ->   SET fact:=1;
    -> ELSE
    ->   CALL factorial(n-1,fact);
    ->   SET fact:=n* fact;
    -> END IF;
    -> END
    -> $$
Query OK, 0 rows affected (0.02 sec)

mysql> call find_fact(5);
    -> $$
+-------+
| @fact |
+-------+
|   120 |
+-------+
1 row in set (0.01 sec)

mysql> DELIMITER //
mysql> CREATE FUNCTION find_sum1(A INT,B INT)
    -> RETURNS INT
    -> DETERMINISTIC
    -> BEGIN
    -> DECLARE SUM INT;
    -> SET SUM=A+B;
    -> RETURN SUM;
    -> END //
Query OK, 0 rows affected (0.02 sec)
mysql> SELECT find_sum1(4,7);
    -> //
+----------------+
| find_sum1(4,7) |
+----------------+
|             11 |
+----------------+
1 row in set (0.01 sec)

mysql> SELECT find_sum1(-2,-9);
    -> //
+------------------+
| find_sum1(-2,-9) |
+------------------+
|              -11 |
+------------------+
1 row in set (0.01 sec)
