    Project Overview
This project involves an in-depth analysis of a synthetic HR dataset using SQL. 
The primary goal is to extract actionable insights related to employee demographics, performance, tenure, and termination trends. 
By querying the data, we aim to answer critical business questions that can help in strategic workforce planning and improving employee retention.

Dataset
The analysis is based on a single CSV file (employee_data.csv) containing over 3,000 employee records. The key columns in the dataset include:

EmpID

FirstName, LastName

DepartmentType

EmployeeStatus

Performance Score

Current Employee Rating

StartDate, ExitDate

TerminationType, TerminationDescription, etc.


TOOT USED :- MYSQL



CREATE DATABASE employee_hr;
USE employee_hr;

#1.Count Employees by Their Status
#Goal: To see a quick summary of how many employees are active, on leave, or have been terminated.
SELECT
    EmployeeStatus,
    COUNT(EmpID) AS NumberOfEmployees
FROM
    employee_data
GROUP BY
    EmployeeStatus;
SELECT * FROM employee_data LIMIT 10;

#2.Performance Score Breakdown
#Goal: To understand the overall performance distribution in the company
SELECT
    "Performance Score",
    COUNT(ï»¿EmpID) AS Total
FROM
    employee_data
GROUP BY
    "Performance Score"
ORDER BY
    Total DESC;

#3.Top 5 Most Common Job Titles
#Goal: To find out the most common roles within the organization.



SELECT
    Title,
    COUNT(ï»¿EmpID) AS NumberOfEmployees
FROM
    employee_data
GROUP BY
    Title
ORDER BY
    NumberOfEmployees DESC
LIMIT 5;

#4.Employee Count by State
#Goal: To see the geographic distribution of your employees across different states.

SELECT
    State,
    COUNT(ï»¿EmpID) AS NumberOfEmployees
FROM
    employee_data
GROUP BY
    State
ORDER BY
    NumberOfEmployees DESC;
    

#5.Find the 10 Longest-Serving Active Employees
#Goal: To identify the employees who have been with the company the longest and are still active. This is useful for recognizing loyalty.


SELECT
    FirstName,
    LastName,
    StartDate
FROM
    employee_data
WHERE
    EmployeeStatus = 'Active'
ORDER BY  
    StartDate ASC
LIMIT 10;

...............................................#>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
