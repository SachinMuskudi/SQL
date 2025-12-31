<h1 align="center">🗄️ SQL – Complete Beginner to Intermediate Guide</h1>

<p align="center">
  <i>A structured, beginner-friendly SQL roadmap with definitions, syntax, examples, and Python integration.</i>
</p>

<hr>

<h2>1️⃣ What is SQL?</h2>

<p>
SQL stands for <b>Structured Query Language</b>.  
It is used to <b>store, retrieve, update, delete, and manage data</b> in relational databases.
</p>

<p>
SQL works with <b>tables</b> made of rows (records) and columns (fields).
</p>

<h3>Popular SQL Databases</h3>
<ul>
  <li>MySQL</li>
  <li>SQL Server</li>
  <li>PostgreSQL</li>
  <li>Oracle</li>
</ul>

<h3>Why SQL?</h3>
<ul>
  <li>Easy to learn and read</li>
  <li>Handles large data efficiently</li>
  <li>Used in Backend, Data Science, AI & Analytics</li>
</ul>

<hr>

<h2>2️⃣ Installing SSMS & Introduction</h2>

<p>
<b>SQL Server Management Studio (SSMS)</b> is a GUI tool used to write and execute SQL queries.
</p>

<h3>Installation Steps</h3>
<ol>
  <li>Install SQL Server (Express / Developer)</li>
  <li>Download SSMS from Microsoft website</li>
  <li>Install SSMS</li>
  <li>Open SSMS → Connect to Database Engine</li>
</ol>

<h3>SSMS Components</h3>
<ul>
  <li><b>Object Explorer</b> – databases & tables</li>
  <li><b>Query Editor</b> – write SQL</li>
  <li><b>Results Pane</b> – query output</li>
</ul>

<hr>

<h2>3️⃣ Creating and Using Database</h2>

<h4>Create Database</h4>
<pre><code>CREATE DATABASE CompanyDB;
</code></pre>

<h4>Use Database</h4>
<pre><code>USE CompanyDB;
</code></pre>

<p>Only one database can be active at a time.</p>

<hr>

<h2>4️⃣ DDL Operations (Data Definition Language)</h2>

<p>DDL commands define or modify database structure.</p>

<ul>
  <li>CREATE</li>
  <li>ALTER</li>
  <li>DROP</li>
  <li>TRUNCATE</li>
</ul>

<h4>Create Table</h4>
<pre><code>CREATE TABLE Employees (
  EmpID INT PRIMARY KEY,
  Name VARCHAR(50),
  Salary INT
);
</code></pre>

<h4>Alter Table</h4>
<pre><code>ALTER TABLE Employees ADD Department VARCHAR(30);
</code></pre>

<h4>Drop Table</h4>
<pre><code>DROP TABLE Employees;
</code></pre>

<hr>

<h2>5️⃣ Data Types & Memory Allocation</h2>

<table>
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
  <td>Fixed-length text</td>
  <td>n bytes</td>
</tr>
<tr>
  <td>VARCHAR(n)</td>
  <td>Variable-length text</td>
  <td>Actual length</td>
</tr>
<tr>
  <td>FLOAT</td>
  <td>Decimal values</td>
  <td>4–8 bytes</td>
</tr>
<tr>
  <td>DATE</td>
  <td>Date</td>
  <td>3 bytes</td>
</tr>
</table>

<hr>

<h2>6️⃣ DML Operations (Data Manipulation Language)</h2>

<ul>
  <li>INSERT</li>
  <li>UPDATE</li>
  <li>DELETE</li>
</ul>

<pre><code>INSERT INTO Employees VALUES (1, 'John', 50000);
</code></pre>

<pre><code>UPDATE Employees SET Salary = 60000 WHERE EmpID = 1;
</code></pre>

<pre><code>DELETE FROM Employees WHERE EmpID = 1;
</code></pre>

<hr>

<h2>7️⃣ Identity (Seed & Increment)</h2>

<pre><code>CREATE TABLE Users (
  UserID INT IDENTITY(1,1),
  Name VARCHAR(50)
);
</code></pre>

<ul>
  <li>Seed → Starting value</li>
  <li>Increment → Step value</li>
</ul>

<hr>

<h2>8️⃣ SQL Set Operators</h2>

<ul>
  <li>UNION</li>
  <li>UNION ALL</li>
  <li>INTERSECT</li>
  <li>EXCEPT</li>
</ul>

<pre><code>SELECT City FROM Table1
UNION
SELECT City FROM Table2;
</code></pre>

<hr>

<h2>9️⃣ DQL (SELECT)</h2>

<pre><code>SELECT * FROM Employees;
</code></pre>

<pre><code>SELECT Name, Salary FROM Employees WHERE Salary > 40000;
</code></pre>

<hr>

<h2>🔟 Primary Key & Foreign Key</h2>

<h4>Primary Key</h4>
<ul>
  <li>Unique</li>
  <li>Not NULL</li>
</ul>

<h4>Foreign Key</h4>
<pre><code>FOREIGN KEY (DeptID) REFERENCES Department(DeptID);
</code></pre>

<hr>

<h2>1️⃣1️⃣ CHAR vs VARCHAR</h2>

<table>
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
</table>

<hr>

<h2>1️⃣2️⃣ TCL (Transactions)</h2>

<ul>
  <li>COMMIT</li>
  <li>ROLLBACK</li>
  <li>SAVEPOINT</li>
</ul>

<pre><code>BEGIN TRANSACTION;
UPDATE Employees SET Salary = 70000;
ROLLBACK;
</code></pre>

<hr>

<h2>1️⃣3️⃣ Ranking Functions</h2>

<pre><code>SELECT Name, Salary,
RANK() OVER (ORDER BY Salary DESC) AS Rank
FROM Employees;
</code></pre>

<hr>

<h2>1️⃣4️⃣ Clauses with Aggregations</h2>

<pre><code>SELECT Department, COUNT(*)
FROM Employees
GROUP BY Department
HAVING COUNT(*) > 2;
</code></pre>

<hr>

<h2>1️⃣5️⃣ Python + MySQL</h2>

<pre><code>import mysql.connector

conn = mysql.connector.connect(
  host="localhost",
  user="root",
  password="password",
  database="CompanyDB"
)

cursor = conn.cursor()
cursor.execute("SELECT * FROM Employees")
</code></pre>

<hr>

<h2>1️⃣6️⃣ Python + Redis</h2>

<pre><code>import redis

r = redis.Redis(host='localhost', port=6379)
r.set("name", "Sachin")
print(r.get("name"))
</code></pre>

<hr>

<h2>✅ Conclusion</h2>

<p>
This README covers SQL fundamentals, database design, transactions, ranking,
and Python integration. Perfect for <b>students, freshers, and developers</b>.
</p>

<p align="center"><b>Happy Learning 🚀</b></p>
