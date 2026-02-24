# 📚 DBMS LAB ASSIGNMENT 02

> **Date:** 08/February/2026  
> **Database:** aanchal_2cse12  

### 1: List All Distinct Jobs in EMPLOYEE
```sql
SELECT DISTINCT JOB
FROM EMPLOYEE;
```

**Output:**
```
+-----------+
| JOB       |
+-----------+
| CLERK     |
| SALESMAN  |
| MANAGER   |
| ANALYST   |
| PRESIDENT |
+-----------+
5 rows in set (0.001 sec)
```

###  2: List All Information About Employees in Department 30
```sql
SELECT *
FROM EMPLOYEE
WHERE DEPTNO = 30;
```

**Output:**
```
+-------+--------+-----------+------+------------+------+------+--------+
| EMPNO | ENAME  | JOB       | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |
+-------+--------+-----------+------+------------+------+------+--------+
|  7499 | ALLEN  | SALESMAN  | 7698 | 1981-02-20 | 1600 |  300 |     30 |
|  7521 | WARD   | SALESMAN  | 7698 | 1981-02-22 | 1250 |  300 |     30 |
|  7654 | MARTIN | SALESMAN  | 7698 | 1981-09-28 | 1250 | 1400 |     30 |
|  7698 | BLAKE  | MANAGER   | 7839 | 1981-05-01 | 2850 | NULL |     30 |
|  7844 | TURNER | SALESMAN  | 7698 | 1981-09-08 | 1500 |    0 |     30 |
|  7900 | JAMES  | CLERK     | 7698 | 1981-12-03 |  950 | NULL |     30 |
+-------+--------+-----------+------+------------+------+------+--------+
6 rows in set (0.001 sec)
```



### 3: Find All Department Numbers with Department Names Greater Than 20

```sql
SELECT DEPTNO, DNAME
FROM DEPARTMENT
WHERE DEPTNO > 20;
```

**Output:**
```
+--------+------------+
| DEPTNO | DNAME      |
+--------+------------+
|     30 | SALES      |
|     40 | OPERATIONS |
+--------+------------+
2 rows in set (0.001 sec)
```

### 4: Find All Information About Managers and Clerks in Department 30
```sql
SELECT *
FROM EMPLOYEE
WHERE DEPTNO = 30
AND JOB IN ('MANAGER', 'CLERK');
```

**Output:**
```
+-------+-------+---------+------+------------+------+------+--------+
| EMPNO | ENAME | JOB     | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |
+-------+-------+---------+------+------------+------+------+--------+
|  7698 | BLAKE | MANAGER | 7839 | 1981-05-01 | 2850 | NULL |     30 |
|  7900 | JAMES | CLERK   | 7698 | 1981-12-03 |  950 | NULL |     30 |
+-------+-------+---------+------+------------+------+------+--------+
2 rows in set (0.001 sec)
```
###  5: List Employee Name, Employee Number, and Department of All Clerks
```sql
SELECT ENAME, EMPNO, DEPTNO
FROM EMPLOYEE
WHERE JOB = 'CLERK';
```

**Output:**
```
+--------+-------+--------+
| ENAME  | EMPNO | DEPTNO |
+--------+-------+--------+
| SMITH  |  7369 |     20 |
| ADAMS  |  7876 |     20 |
| JAMES  |  7900 |     30 |
| MILLER |  7934 |     10 |
+--------+-------+--------+
4 rows in set (0.001 sec)
```
### 6: Find All Managers Not in Department 30
```sql
SELECT *
FROM EMPLOYEE
WHERE JOB = 'MANAGER'
AND DEPTNO <> 30;
```

**Output:**
```
+-------+-------+---------+------+------------+------+------+--------+
| EMPNO | ENAME | JOB     | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |
+-------+-------+---------+------+------------+------+------+--------+
|  7566 | JONES | MANAGER | 7839 | 1981-04-02 | 2975 | NULL |     20 |
|  7782 | CLARK | MANAGER | 7839 | 1981-06-09 | 2450 | NULL |     20 |
+-------+-------+---------+------+------------+------+------+--------+
2 rows in set (0.001 sec)
```

### 7: List Information About Employees in Department 10 Who Are Not Managers or Clerks
```sql
SELECT *
FROM EMPLOYEE
WHERE DEPTNO = 10
AND JOB NOT IN ('MANAGER', 'CLERK');
```

**Output:**
```
Empty set (0.001 sec)
```
### 8: Find Employees and Jobs Earning Between 1200 and 1400
```sql
SELECT ENAME, JOB, SAL
FROM EMPLOYEE
WHERE SAL BETWEEN 1200 AND 1400;
```

**Output:**
```
+--------+----------+------+
| ENAME  | JOB      | SAL  |
+--------+----------+------+
| WARD   | SALESMAN | 1250 |
| MARTIN | SALESMAN | 1250 |
| MILLER | CLERK    | 1300 |
+--------+----------+------+
3 rows in set (0.001 sec)
```
### 9: List Name and Department Number of Clerks, Analysts, or Salesmen

```sql
SELECT ENAME, DEPTNO
FROM EMPLOYEE
WHERE JOB IN ('CLERK', 'ANALYST', 'SALESMAN');
```

**Output:**
```
+--------+--------+
| ENAME  | DEPTNO |
+--------+--------+
| SMITH  |     20 |
| ALLEN  |     30 |
| WARD   |     30 |
| MARTIN |     30 |
| SCOTT  |     40 |
| TURNER |     30 |
| ADAMS  |     20 |
| JAMES  |     30 |
| FORD   |     20 |
| MILLER |     10 |
+--------+--------+
10 rows in set (0.001 sec)
```
### Problem 10: List Name and Department Number of Employees Whose Names Begin with M
```sql
SELECT ENAME, DEPTNO
FROM EMPLOYEE
WHERE ENAME LIKE 'M%';
```

**Output:**
```
+--------+--------+
| ENAME  | DEPTNO |
+--------+--------+
| MARTIN |     30 |
| MILLER |     10 |
+--------+--------+
2 rows in set (0.001 sec)
```


> **Submitted By:** Aanchal gurung  

> **Course:** DBMS Lab
