# 📂 Database Lab: Performing a Conditional Search
## Overview
The database operations team has created a relational database named world containing three tables: city, country, and countrylanguage. To help the team, i will write a few queries to search for records in the country table by using the SELECT statement and a WHERE clause.

## 🎯Lab overview and objectives
This lab demonstrates how to use the SELECT statement and a WHERE clause to filter records with a conditional search.

## Architecture Diagram

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%201_%20Database/commandHost.png)



![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%201_%20Database/Operations.png)

Task 1: Task 1: Connect to the Command Host
In this task, you connect to an Amazon Elastic Compute Cloud (Amazon EC2) instance containing a database client, which you will use to connect to a database. This instance will be referred to as the Command Host.

In the AWS Management Console, choose the  Services menu. Choose Compute, and then choose EC2.

In the left navigation menu, choose Instances.

Next to the instance labelled Command Host, select the check box  and then choose Connect.

Note: If you do not see the Command Host, the lab is probably still being provisioned, or you might be using another Region.

For Connect to instance, choose the Session Manager tab.

Choose Connect to open a terminal window.

Note: If the Connect button is not available, wait for a few minutes and try again.

To configure the terminal to access all required tools and resources, run the following command:

sudo su
cd /home/ec2-user/
 Tips:

Copy and paste the command into the Session Manager terminal window.
If you are using a Windows system, press Shift+Ctrl+V to paste the command.
To connect to the database server, run the following command. A password was configured when the database was installed.

mysql -u root --password='re:St@rt!9'
 Tip: At any stage of the lab, if the Session Manager window is not responsive or if you need to reconnect to the database instance, then follow these steps:

Close the Session Manager window, and try to reconnect using the previous steps.

Run the following commands in the terminal.

sudo su
cd /home/ec2-user/
mysql -u root --password='re:St@rt!9'


Task 2:Query the world database 
In this task, you will query the world database by using various SELECT statements and database functions.

To show the existing databases, run the following query. 

SHOW DATABASES;
Verify that a database named world is available. If the world database is not available, then contact your instructor.

To review the table schema, data, and number of rows in the country table, run the following query.

SELECT * FROM world.country;
By reducing the number of records, the result set would be smaller and easier to work with. To limit the number of records returned, you can use a WHERE clause to define the conditions that records must match.

Use the AND operator to combine two conditions. Each record is checked against both conditions before it's included in the result set. You can use the > operator and = operator to query values that are greater than or equal to a certain value. Similarly, you can combine the < operator and = operator to query values that are less than or equal to a certain value.

To reduce the number of records in the result set by using a WHERE clause and the AND operator, run the following query.

SELECT Name, Capital, Region, SurfaceArea, Population FROM world.country WHERE Population >= 50000000 AND Population <= 100000000;
When searching for records by using a range condition, you can use the BETWEEN operator instead of the >= operator and <= operator. By using the BETWEEN operator, the query is easier to read. Note that the operator is inclusive, meaning that the beginning and ending values are included.

To return the same records as the previous result set by using the BETWEEN operator, run the following query.

SELECT Name, Capital, Region, SurfaceArea, Population FROM world.country WHERE Population BETWEEN 50000000 AND 100000000;
You can use the LIKE function to search for a string pattern. The following query will return records that include the string Europe in the Region column. The percent symbol (%) is a wildcard character that represents any number of characters before or after the word Europe. The query will aggregate the population of all European countries by using the SUM function.

To return the population of all European countries by using the LIKE function and SUM function, run the following query.

SELECT sum(Population) from world.country WHERE Region LIKE "%Europe%";
In the previous query, the SELECT clause included a SUM function. In the following query, the SUM function is still used to calculate the total population of Europe. The query also includes a column alias, which makes the output easier to read. To define the column alias, the AS command is used in the SELECT statement.

To return the same information as the previous query with the column alias, run the following query.

SELECT sum(population) as "Europe Population Total" from world.country WHERE region LIKE "%Europe%";
Note that SQL is not a case-sensitive language. You can use either SELECT or select when writing a query. However, databases that you query might be configured with a case-sensitive collation. If the database was case sensitive, you would not be able to query a column named Population by using the following: select population from world.country

Even though the database used in this lab is not case sensitive, we recommended making your queries consistent with the naming convention that is used in the database.

The following example demonstrates how to perform a case-sensitive search. Depending on the database configuration, when comparing Central to central, the outcome might be false, because the strings don't use the same case. To solve this problem, you can use the LOWER function in the WHERE clause to compare the strings both as lowercase.

To perform a case-sensitive search by using the LOWER function, run the following query.

SELECT Name, Capital, Region, SurfaceArea, Population from world.country WHERE LOWER(Region) LIKE "%central%";


## Conclusion
In this lab, you successfully connected to the Command Host EC2 instance using AWS Systems Manager Session Manager and prepared the environment to work with the MySQL database client. After establishing the connection, you accessed the world database and practiced using a variety of SQL queries to explore and analyze data.

You worked with core SQL concepts, including filtering results with WHERE, combining conditions with AND, and using range queries with BETWEEN. You also applied pattern matching with LIKE, performed calculations with aggregate functions such as SUM, and improved readability using column aliases. Additionally, you learned how SQL handles case sensitivity and how functions like LOWER can help produce accurate and consistent results.

Overall, you gained practical experience navigating an EC2-based database environment and strengthened your SQL querying skills using real-world datasets.










