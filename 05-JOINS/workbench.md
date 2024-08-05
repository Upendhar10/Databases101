```sql
SHOW DATABASES;

USE techforallwithpriya;

SHOW TABLES;

SELECT * FROM employee;

-- for each location, what is the count of employee and their avg salary in that location
SELECT location , COUNT(*) AS EmployeeCount, AVG(Salary) FROM employee GROUP BY location;

-- for each location, what is the count of employee and their avg salary in that location
-- Also , display the firstname and the lastname corresponding to each record
SELECT firstName, lastName, employee.location, EmployeeCount, Avg_Salary  FROM employee
JOIN
(SELECT location, COUNT(*) AS EmployeeCount , AVG(Salary) AS Avg_Salary FROM employee GROUP BY location) AS temp
ON employee.location = temp.location;

-- Inserting values into employees table
INSERT INTO employee (FirstName, LastName, Age, Salary, Location) VALUES
("Jeevan","Hedge",27,100000,"Noida"),
("Priya","Bhatia",26, 150000,"Delhi");

SELECT * FROM learners;

SELECT * FROM courses;

-- solution-1 : using JOINS
SELECT courseId, courseName, COUNT(learnerId) AS EnrollmentCount
FROM learners
JOIN courses
ON learners.EnrolledCourses = courses.courseId
GROUP BY courses.courseId;

-- solution-2 : without using joins
SELECT EnrolledCourses, COUNT(*) AS EnrollmentCount
FROM learners
GROUP BY EnrolledCourses
ORDER BY EnrollmentCount DESC;
```
