<!DOCTYPE html>
<html lang="en">
<body>

<h1>SQL – Complete Beginner to Intermediate Guide</h1>

<hr>

<h2>1. What is SQL?</h2>
<p>
SQL stands for <b>Structured Query Language</b>.  
It is a standard language used to <b>store, retrieve, manipulate, and manage data</b> in relational databases.
</p>

<p>
SQL works with data stored in <b>tables</b> (rows and columns).  
Popular databases using SQL:
</p>
<ul>
  <li>MySQL</li>
  <li>SQL Server</li>
  <li>PostgreSQL</li>
  <li>Oracle</li>
</ul>

<p><b>Why SQL?</b></p>
<ul>
  <li>Easy to learn</li>
  <li>Works with large data</li>
  <li>Used in Data Analysis, Backend, AI & ML</li>
</ul>

<hr>

<h2>2. Installing SSMS & Basic Introduction</h2>

<h3>SSMS (SQL Server Management Studio)</h3>
<p>
SSMS is a graphical tool used to <b>connect, write, execute, and manage SQL Server databases</b>.
</p>

<h3>Installation Steps</h3>
<ol>
  <li>Download SSMS from Microsoft official site</li>
  <li>Install SQL Server (Express / Developer edition)</li>
  <li>Install SSMS</li>
  <li>Open SSMS → Connect to Database Engine</li>
</ol>

<h3>SSMS Components</h3>
<ul>
  <li><b>Object Explorer</b> – shows databases, tables, views</li>
  <li><b>Query Editor</b> – write SQL queries</li>
  <li><b>Results Pane</b> – shows query output</li>
</ul>

<hr>

<h2>3. Creating and Activating Database</h2>

<h3>Create Database</h3>
<pre>
CREATE DATABASE CompanyDB;
</pre>

<h3>Activate (Use) Database</h3>
<pre>
USE CompanyDB;
</pre>

<p>
Only one database can be active at a time.
</p>

<hr>

<h2>4. DDL Operations (Data Definition Language)</h2>
<p>
DDL commands define or modify database structure.
</p>

<h3>Common DDL Commands</h3>
<ul>
  <li>CREATE</li>
  <li>ALTER</li>
  <li>DROP</li>
  <li>TRUNCATE</li>
</ul>

<h3>Examples</h3>

<pre>
CREATE TABLE Employees (
  EmpID INT,
  Name VARCHAR(50),
  Salary INT
);
</pre>

<pre>
ALTER TABLE Employees ADD Department VARCHAR(30);
</pre>

<pre>
DROP TABLE Employees;
</pre>

<hr>

<h2>5. Data Types and Memory Allocation</h2>

<table border="1" cellpadding="5">
<tr>
  <th>Data Type</th>
  <th>Description</th>
  <th>Memory</th>
</tr>
<tr>
  <td>INT</td>
  <td>Whole numbers</td>
  <td>4 bytes</td>
</tr>
<tr>
  <td>BIGINT</td>
  <td>Large integers</td>
  <td>8 bytes</td>
</tr>
<tr>
  <td>CHAR(n)</td>
  <td>Fixed length text</td>
  <td>n bytes</td>
</tr>
<tr>
  <td>VARCHAR(n)</td>
  <td>Variable length text</td>
  <td>Actual length</td>
</tr>
<tr>
  <td>FLOAT</td>
  <td>Decimal values</td>
  <td>4–8 bytes</td>
</tr>
<tr>
  <td>DATE</td>
  <td>Date values</td>
  <td>3 bytes</td>
</tr>
</table>

<hr>

<h2>6. DML Operations (Data Manipulation Language)</h2>

<p>
DML commands manage data inside tables.
</p>

<ul>
  <li>INSERT</li>
  <li>UPDATE</li>
  <li>DELETE</li>
</ul>

<h3>Examples</h3>

<pre>
INSERT INTO Employees VALUES (1, 'John', 50000);
</pre>

<pre>
UPDATE Employees SET Salary = 60000 WHERE EmpID = 1;
</pre>

<pre>
DELETE FROM Employees WHERE EmpID = 1;
</pre>

<hr>

<h2>7. Identity (Seed & Increment) Concept</h2>

<p>
Identity column automatically generates numbers.
</p>

<pre>
CREATE TABLE Users (
  UserID INT IDENTITY(1,1),
  Name VARCHAR(50)
);
</pre>

<p>
Here:
</p>
<ul>
  <li><b>Seed</b> = 1 (starting value)</li>
  <li><b>Increment</b> = 1 (increase by 1)</li>
</ul>

<hr>

<h2>8. SQL Set Concepts</h2>

<p>
SQL supports set operations:
</p>

<ul>
  <li>UNION</li>
  <li>UNION ALL</li>
  <li>INTERSECT</li>
  <li>EXCEPT</li>
</ul>

<pre>
SELECT City FROM Table1
UNION
SELECT City FROM Table2;
</pre>

<hr>

<h2>9. DQL Operations (Data Query Language)</h2>

<p>
DQL is used to retrieve data.
</p>

<pre>
SELECT * FROM Employees;
</pre>

<pre>
SELECT Name, Salary FROM Employees WHERE Salary > 40000;
</pre>

<hr>

<h2>10. Primary Key and Foreign Key</h2>

<h3>Primary Key</h3>
<ul>
  <li>Uniquely identifies a row</li>
  <li>No NULL values</li>
</ul>

<pre>
EmpID INT PRIMARY KEY
</pre>

<h3>Foreign Key</h3>
<ul>
  <li>References primary key of another table</li>
</ul>

<pre>
DeptID INT,
FOREIGN KEY (DeptID) REFERENCES Department(DeptID)
</pre>

<hr>

<h2>11. Difference Between CHAR and VARCHAR</h2>

<table border="1" cellpadding="5">
<tr>
  <th>CHAR</th>
  <th>VARCHAR</th>
</tr>
<tr>
  <td>Fixed length</td>
  <td>Variable length</td>
</tr>
<tr>
  <td>Consumes full memory</td>
  <td>Saves memory</td>
</tr>
<tr>
  <td>Faster for equal length data</td>
  <td>Better for variable text</td>
</tr>
</table>

<hr>

<h2>12. TCL Operations (Transaction Control Language)</h2>

<ul>
  <li>COMMIT</li>
  <li>ROLLBACK</li>
  <li>SAVEPOINT</li>
</ul>

<pre>
BEGIN TRANSACTION;
UPDATE Employees SET Salary = 70000;
ROLLBACK;
</pre>

<hr>

<h2>13. Ranking Concepts</h2>

<p>
Ranking functions assign ranks to rows.
</p>

<ul>
  <li>ROW_NUMBER()</li>
  <li>RANK()</li>
  <li>DENSE_RANK()</li>
</ul>

<pre>
SELECT Name, Salary,
RANK() OVER (ORDER BY Salary DESC) AS Rank
FROM Employees;
</pre>

<hr>

<h2>14. Clauses with Aggregations</h2>

<h3>Clauses</h3>
<ul>
  <li>WHERE</li>
  <li>GROUP BY</li>
  <li>HAVING</li>
  <li>ORDER BY</li>
</ul>

<pre>
SELECT Department, COUNT(*) 
FROM Employees
GROUP BY Department
HAVING COUNT(*) > 2;
</pre>

<hr>

<h2>15. Python with MySQL + SQL Connection</h2>

<p>
Python connects to SQL databases using connectors.
</p>

<pre>
import mysql.connector

conn = mysql.connector.connect(
  host="localhost",
  user="root",
  password="password",
  database="CompanyDB"
)

cursor = conn.cursor()
cursor.execute("SELECT * FROM Employees")
</pre>

<hr>

<h2>16. Python with Redis Connection</h2>

<p>
Redis is an in-memory key-value database.
</p>

<pre>
import redis

r = redis.Redis(host='localhost', port=6379)
r.set("name", "Sachin")
print(r.get("name"))
</pre>

<hr>

<h2>Conclusion</h2>
<p>
This guide covers SQL fundamentals, database operations, constraints, transactions, ranking, and Python integrations.
It is ideal for beginners, backend developers, and data analysts.
</p>

</body>
</html>
