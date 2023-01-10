mysql> select*from mentees;
+-----------+---------+------+---------+------------+-------+---------+
| Regno     | Name    | Dept | Address | Fathername | Marks | subject |
+-----------+---------+------+---------+------------+-------+---------+
| 192011090 | Gowtham | CSE  | Chennai | moorthi    |    99 | DBMS    |
| 192011079 | arun    | BME  | nellore | muthu      |    91 | BIOEVS  |
| 192011095 | Harish  | ECE  | Madurai | Kannan     |    95 | PDSD    |
| 192211080 | Dhivya  | ECE  | Tirupur | Ramesh     |    91 | PDSD    |
+-----------+---------+------+---------+------------+-------+---------+
4 rows in set (0.00 sec)
mysql> create table mdept(Deptid int(5),Deptname varchar(20),Rollno int(10));
Query OK, 0 rows affected, 2 warnings (0.04 sec)

mysql> insert into mdept values(1,"CSE",192011090);
Query OK, 1 row affected (0.02 sec)

mysql> insert into mdept values(2,"ECE",192011079);
Query OK, 1 row affected (0.01 sec)

mysql> insert into mdept values(2,"ECE",192011010);
Query OK, 1 row affected (0.01 sec)

mysql> update mdept set Deptid=3 where Rolln0=192011010;
ERROR 1054 (42S22): Unknown column 'Rolln0' in 'where clause'
mysql> update mdept set Deptid=3 where Rollno=192011010;
Query OK, 1 row affected (0.00 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> select*from mdept;
+--------+----------+-----------+
| Deptid | Deptname | Rollno    |
+--------+----------+-----------+
|      1 | CSE      | 192011090 |
|      2 | ECE      | 192011079 |
|      3 | ECE      | 192011010 |
+--------+----------+-----------+
3 rows in set (0.01 sec)

mysql> update mdept set Deptname="BME" where Rollno=192011079;
Query OK, 1 row affected (0.02 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> select*from mdept;
+--------+----------+-----------+
| Deptid | Deptname | Rollno    |
+--------+----------+-----------+
|      1 | CSE      | 192011090 |
|      2 | BME      | 192011079 |
|      3 | ECE      | 192011010 |
+--------+----------+-----------+
3 rows in set (0.01 sec)

mysql> select Deptid,Deptname from mdept,mentees where mentees.Regno=mdept.Rollno;
+--------+----------+
| Deptid | Deptname |
+--------+----------+
|      1 | CSE      |
|      2 | BME      |
+--------+----------+
2 rows in set (0.01 sec)
mysql> select Deptid,Deptname,Rollno from mdept,mentees where mentees.Regno=mdept.Rollno;
+--------+----------+-----------+
| Deptid | Deptname | Rollno    |
+--------+----------+-----------+
|      1 | CSE      | 192011090 |
|      2 | BME      | 192011079 |
+--------+----------+-----------+
2 rows in set (0.00 sec)
mysql> select Name, Deptid,Deptname,Rollno from mdept m,mentees m1 where m1.Regno=m.Rollno;
+---------+--------+----------+-----------+
| Name    | Deptid | Deptname | Rollno    |
+---------+--------+----------+-----------+
| Gowtham |      1 | CSE      | 192011090 |
| arun    |      2 | BME      | 192011079 |
+---------+--------+----------+-----------+
2 rows in set (0.00 sec)
mysql> select Name,Dept, Deptid,Deptname,Rollno from mdept,mentees where mentees.Regno=mdept.Rollno;
+---------+------+--------+----------+-----------+
| Name    | Dept | Deptid | Deptname | Rollno    |
+---------+------+--------+----------+-----------+
| Gowtham | CSE  |      1 | CSE      | 192011090 |
| arun    | BME  |      2 | BME      | 192011079 |
+---------+------+--------+----------+-----------+
2 rows in set (0.00 sec)
mysql> select Rollno,Deptname,Name,Address from mdept left outer join mentees on mdept.Rollno=mentees.Regno;
+-----------+----------+---------+---------+
| Rollno    | Deptname | Name    | Address |
+-----------+----------+---------+---------+
| 192011090 | CSE      | Gowtham | Chennai |
| 192011079 | BME      | arun    | nellore |
| 192011010 | ECE      | NULL    | NULL    |
+-----------+----------+---------+---------+
3 rows in set (0.00 sec)
mysql> select Rollno,Deptname,Name,Address from mdept right outer join mentees on mdept.Rollno=mentees.Regno;
+-----------+----------+---------+---------+
| Rollno    | Deptname | Name    | Address |
+-----------+----------+---------+---------+
| 192011090 | CSE      | Gowtham | Chennai |
| 192011079 | BME      | arun    | nellore |
|      NULL | NULL     | Harish  | Madurai |
|      NULL | NULL     | Dhivya  | Tirupur |
+-----------+----------+---------+---------+
4 rows in set (0.00 sec)
mysql> insert into mdept values(4,"ENE",192011095);
Query OK, 1 row affected (0.01 sec)
mysql> insert into mdept values(5,"COM",192211080);
Query OK, 1 row affected (0.02 sec)

mysql> select Rollno,Deptname,Name,Address from mdept right outer join mentees on mdept.Rollno=mentees.Regno;
+-----------+----------+---------+---------+
| Rollno    | Deptname | Name    | Address |
+-----------+----------+---------+---------+
| 192011090 | CSE      | Gowtham | Chennai |
| 192011079 | BME      | arun    | nellore |
| 192011095 | ENE      | Harish  | Madurai |
| 192211080 | COM      | Dhivya  | Tirupur |
+-----------+----------+---------+---------+
4 rows in set (0.00 sec)
