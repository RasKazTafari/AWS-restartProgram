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

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%201_%20Database/BETWEEN.png)
To return the same records as the previous result set by using the BETWEEN operator.

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%201_%20Database/SELECT.png)
To return the population of all European countries by using the LIKE function and SUM function

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%201_%20Database/WHERE.png)
To return To return the same information as the previous query with the column alias,

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%201_%20Database/ALIAS.png)

To perform a case-sensitive search by using the LOWER function, run the following query.
![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%201_%20Database/LOWER.png)

## Conclusion
In this lab, you successfully connected to the Command Host EC2 instance using AWS Systems Manager Session Manager and prepared the environment to work with the MySQL database client. After establishing the connection, you accessed the world database and practiced using a variety of SQL queries to explore and analyze data.

You worked with core SQL concepts, including filtering results with WHERE, combining conditions with AND, and using range queries with BETWEEN. You also applied pattern matching with LIKE, performed calculations with aggregate functions such as SUM, and improved readability using column aliases. Additionally, you learned how SQL handles case sensitivity and how functions like LOWER can help produce accurate and consistent results.

Overall, you gained practical experience navigating an EC2-based database environment and strengthened your SQL querying skills using real-world datasets.










