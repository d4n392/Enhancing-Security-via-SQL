# Enhancing-Security-via-SQL

In this lab I ensured the organization’s system was more secure. By investigating all potential security issues, and updating employee computers as needed. The following steps provide examples of how I used SQL commands and filters to achieve this goal.

### Skills Learned



### Tools Used



## Steps

### Retrieve after hours failed login attempts
A potential security incident occurred after business hours. My team investigated all unsuccessful attempts after 18:00. The following code demonstrates how I created a SQL query to filter through the log_in_attempts table for failed login attempts that occurred after business hours:

![image](https://github.com/user-attachments/assets/84170574-94d5-4c0a-b87c-16059e87de86)

The first three lines of the screenshot is my query, and the rest is the output. This query filters for failed login attempts that occurred after 18:00. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with an AND operator to filter my results to output only login attempts that occurred after 18:00 and were unsuccessful. The first condition is login_time > '18:00', which filters for the login attempts that occurred after 18:00. The second condition is success = 0(FALSE), which filters for the failed login attempts. There were a total of 19 failed login attempts after 18:00.

### Retrieve login attempts on specific dates
A suspicious event occurred on 2022-05-09. Any login activity that happened on 2022-05-09 or on the day before needs to be investigated.
The following code demonstrates how I created a SQL query to filter through the log_in_attempts table for login attempts that occurred on those specific dates:

![image](https://github.com/user-attachments/assets/cc55cce7-6de2-414f-b0f4-53c5bf8ad8ea)

The first two lines of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred between 2022-05-08 and 2022-05-09. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with the BETWEEN as well as the AND operator to filter my results to output only login attempts that occurred between 2022-05-08 and 2022-05-09. 

_Below I used the alternative operator OR to return data for each login date:_

![image](https://github.com/user-attachments/assets/febb2cb3-deab-48e0-bae6-0c4de2e540fc)

The first three lines of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred on 2022-05-08 or 2022-05-09. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with an OR operator to filter my results to output only login attempts that occurred on either 2022-05-08 or 2022-05-09. The first condition is login_date = '2022-05-08', which filters for logins on 2022-05-08. The second condition is login_date = '2022-05-09', which filters for logins on 2022-05-09.

### Retrieve login attempts outside of Mexico

After investigating the organization’s data on login attempts, I believe there is an issue with the login attempts that occurred outside of Mexico. These login attempts should be investigated. The following code demonstrates how I created a SQL query to filter for login attempts that occurred outside of Mexico:

![image](https://github.com/user-attachments/assets/40b53603-151b-417b-9189-2f45add3e49f)

The first part of the screenshot is my query, and the second part is a portion of the output.
This query returns all login attempts that occurred in countries other than Mexico. First, I started by selecting all data from the log_in_attempts table by using SELECT with the asterisk(*). Then, I used a WHERE clause with NOT to filter for countries other than Mexico. I used LIKE with ‘MEX%’ as the pattern to match because the dataset represents Mexico as MEX and MEXICO. The percentage sign(%) represents any number of unspecified characters when used with LIKE.

### Retrieve employees in Marketing

My team needs to update the computers from the Marketing department in the East offices. To do this, I have to sort which employee machines to update. The following code demonstrates how I created a SQL query to filter through the employees table for employee machines from employees in the Marketing department in the East building:

![image](https://github.com/user-attachments/assets/74ccd13f-b357-4fef-a6c7-67ec0777ad7e)

The first three lines of the screenshot is my query, and the rest is the output. This query returns all employees in the Marketing department in the East building. First, I started by selecting all data from the employees table. Then, I used a WHERE clause with the AND operator to filter for employees who work in the Marketing department and in the East building. I used LIKE in conjunction with East% as the pattern to match because the data in the office column represents the East building with different specific office numbers. The first condition is the department = 'Marketing' portion, which filters for employees in the Marketing department. The second condition is the office LIKE 'East%' portion, which filters for employees in the East building. The results returned 7 employee workstations in need of updates.

### Retrieve employees in Finance or Sales

The machines for employees in the Finance and Sales departments also need to be updated. Since a different security update is needed, I have to get information on employees only from these two departments. The following code demonstrates how I created a SQL query to filter through the employees table for employee machines from the employees in the Finance or Sales departments:

![image](https://github.com/user-attachments/assets/e27fbc75-2643-4e23-b5ae-c272384b8fcb)

The first three lines of the screenshot is my query, and the rest is a portion of the output. This query returns all employees in the Finance and Sales departments. First, I started by selecting all data from the employees table. Then, I used a WHERE clause together with OR to filter for employees who are in the Finance and Sales departments. I used the OR operator instead of AND because I want to show all employees who are in either department. The first condition is department = 'Finance', which filters for employees from the Finance department. The second condition is department = 'Sales', which filters for employees from the Sales department. 

### Retrieve all employees not in IT

My team needs to make one more security update on employees who are not in the Information Technology department. To make the update, I first have to get information on these employees. The following demonstrates how I created a SQL query to filter through the employees table for employee machines from employees not in the Information Technology department:

![image](https://github.com/user-attachments/assets/e41cde8e-8d3e-4224-a0e1-0fc179b9faad)

The first part of the screenshot is my query, and the second part is a portion of the output. The query returns all employees not in the Information Technology department. First, I started by selecting all data from the employees table by using the SELECT clause with an asterisk(*). Then, I used a WHERE clause with the != operator to filter for employees not in this department. 

## Summary

In this lab, I enhanced the organization's system security by applying SQL commands to filter and retrieve targeted data from the log_in_attempts and employees tables. Using the WHERE clause in conjunction with AND, OR, BETWEEN, NOT, LIKE, and != operators, I efficiently pinpointed failed login attempts after hours, investigated suspicious activities on specific dates, and filtered login attempts outside of Mexico. Additionally, I isolated employees in the Marketing, Finance, and Sales departments, as well as those not in IT, to ensure their workstations received necessary security updates. These precise SQL queries allowed me to extract critical information, supporting focused security measures across the organization.





















