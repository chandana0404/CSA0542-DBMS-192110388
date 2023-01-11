mysql> use sse;
Database changed

mysql> create table movies(Sno int(3),Moviename varchar(30),Type varchar(15));
Query OK, 0 rows affected, 1 warning (0.04 sec)

mysql> insert into movies values(1,"Ponniyin selvan","History");
Query OK, 1 row affected (0.02 sec)

mysql> insert into movies values(2,"Naane varuven","Crime thriller");
Query OK, 1 row affected (0.01 sec)

mysql> insert into movies values(3,"Cobra","Crime thriller");
Query OK, 1 row affected (0.02 sec)

mysql> insert into movies values(4,"LKG","Comedy");
Query OK, 1 row affected (0.00 sec)
mysql> select*from movies;
+------+-----------------+----------------+
| Sno  | Moviename       | Type           |
+------+-----------------+----------------+
|    1 | Ponniyin selvan | History        |
|    2 | Naane varuven   | Crime thriller |
|    3 | Cobra           | Crime thriller |
|    4 | LKG             | Comedy         |
+------+-----------------+----------------+
4 rows in set (0.00 sec)

mysql> start transaction;
Query OK, 0 rows affected (0.00 sec)

mysql> savepoint ini;
Query OK, 0 rows affected (0.00 sec)

mysql> insert into movies values(5,"DON","Commercial");
Query OK, 1 row affected (0.01 sec)

mysql> select*from movies;
+------+-----------------+----------------+
| Sno  | Moviename       | Type           |
+------+-----------------+----------------+
|    1 | Ponniyin selvan | History        |
|    2 | Naane varuven   | Crime thriller |
|    3 | Cobra           | Crime thriller |
|    4 | LKG             | Comedy         |
|    5 | DON             | Commercial     |
+------+-----------------+----------------+
5 rows in set (0.00 sec)

mysql> savepoint ins;
Query OK, 0 rows affected (0.00 sec)

mysql> update movies set Moviename="Mr.Local" where Sno=5;
Query OK, 1 row affected (0.01 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> select*from movies;
+------+-----------------+----------------+
| Sno  | Moviename       | Type           |
+------+-----------------+----------------+
|    1 | Ponniyin selvan | History        |
|    2 | Naane varuven   | Crime thriller |
|    3 | Cobra           | Crime thriller |
|    4 | LKG             | Comedy         |
|    5 | Mr.Local        | Commercial     |
+------+-----------------+----------------+
5 rows in set (0.00 sec)

mysql> savepoint upd;
Query OK, 0 rows affected (0.00 sec)

mysql> delete from movies where Sno=5;
Query OK, 1 row affected (0.00 sec)

mysql> select*from movies;
+------+-----------------+----------------+
| Sno  | Moviename       | Type           |
+------+-----------------+----------------+
|    1 | Ponniyin selvan | History        |
|    2 | Naane varuven   | Crime thriller |
|    3 | Cobra           | Crime thriller |
|    4 | LKG             | Comedy         |
+------+-----------------+----------------+
4 rows in set (0.00 sec)

mysql> savepoint del;
Query OK, 0 rows affected (0.00 sec)

mysql> rollback to upd;
Query OK, 0 rows affected (0.00 sec)

mysql> select*from movies;
+------+-----------------+----------------+
| Sno  | Moviename       | Type           |
+------+-----------------+----------------+
|    1 | Ponniyin selvan | History        |
|    2 | Naane varuven   | Crime thriller |
|    3 | Cobra           | Crime thriller |
|    4 | LKG             | Comedy         |
|    5 | Mr.Local        | Commercial     |
+------+-----------------+----------------+
5 rows in set (0.00 sec)
mysql> rollback to ini;
Query OK, 0 rows affected (0.00 sec)
mysql> select *from movies;
+------+-----------------+----------------+
| Sno  | Moviename       | Type           |
+------+-----------------+----------------+
|    1 | Ponniyin selvan | History        |
|    2 | Naane varuven   | Crime thriller |
|    3 | Cobra           | Crime thriller |
|    4 | LKG             | Comedy         |
+------+-----------------+----------------+
4 rows in set (0.01 sec)
