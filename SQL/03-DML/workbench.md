```sql

SHOW DATABASES;

USE techforallwithpriya;

SHOW TABLES;

DESC employee;

-- Inserting a single record into the table "employee"
INSERT INTO employee (FirstName, LastName, Age, Salary, Location) VALUES ("Priya","Bhatia",27,200000,"Bengalure");

-- Inserting a multiple records into the table "employee
INSERT INTO employee (FirstName, LastName, Age, Salary, Location) VALUES
("Akhil","George",26,100000,"Gurugram"),
("Kaneeshka","Brownlee",27,300000,"London"),
("Megha","Meka",24,50000,"America"),
("Naga","Sai",30,150000,"Bengalure"),
("Prabuthva","Kakkar",35,70000,"Noida"),
("Yesheswi","Ghandak",29,90000,"Delhi");

SELECT * FROM employee;

-- Always prefer to filter data using the Primary Key

-- Records Salary > 100000
SELECT FirstName, LastName FROM employee WHERE Salary > 100000;

-- Records age > 25
SELECT FirstName, LastName FROM employee WHERE Age > 25;

-- Update the LastName for the  records whose eid = 1
UPDATE employee SET LastName = "Bhatt" , Location = "Hyderabad" WHERE EID=2;

-- Delete the records whose eid = 4
DELETE FROM employee WHERE EID = 4;

-- *******************************************************************************************************
DESC courses;

-- Insert records into courses table
INSERT INTO courses (courseName,courseInstructor,courseDurationInMonths,courseFee) VALUES
("Excel Mastery", "Priya Bhatia", 3,1499),
("DSA for Interview Prep", "Priya Bhatia", 2,4999),
("SQL Bootcamp", "Priya Bhatia", 1,2999);

SELECT * FROM courses;

-- ************************************************************************************************************

DESC learners;

INSERT INTO learners
(learnerFirstName,learnerLastName, learnerEmail, learnerPhoneNum, location, sourceOfJoining, YearsOfExperience, learnerCompany, learnerEnrollmentDate, EnrolledCourses, BatchStartDate)
VALUES
("Akhil","George", "akhil.George.8743@gmail.com", 9124567865, "Hyderabad", "LinkedIn", 2, "Infosys", '2024-01-10', 2, '2024-01-16'),
("Rishikesh","Joshi", "carjkop@gmail.com", 9167865001, "Mumbai", "Community", 1, "Plivo", '2024-01-10', 1, '2024-02-29'),
("Madhuram","Ravichandran", "ravichandran.maduram@gmail.com", 8124537895, "Noida", "LinkedIn", 2, "ofbusiness", '2024-01-15', 2, '2024-01-16'),
("Jeevan","Hedge", "jeevenhedgek@yahoo.com", 6129067864, "Hyderabad", "Youtube", 0, "TCS", '2024-01-21', 1, '2024-02-29'),
("Nagasai","Sreedhar", "saisreedhar2001@gmail.com", 8789764569, "Jaipur", "Community", 1, "HCL", '2024-03-19', 3, '2024-03-25');

SELECT * FROM  learners;

INSERT INTO learners
(learnerFirstName,learnerLastName, learnerEmail, learnerPhoneNum, location, sourceOfJoining, YearsOfExperience, learnerCompany, learnerEnrollmentDate, EnrolledCourses, BatchStartDate)
VALUES
("Manoj","Tiwary", "Tiwary.Manoj.743@gmail.com", 9127767865, "Lucknow", "Youtube", 3, "Nvidia", '2024-02-12', 3, '2024-03-25'),
("Mike","Tyson", "Tyson438@gmail.com", 6527767865, "Lucknow", "community", 3, "Paytm", '2024-02-22', 1, '2024-02-29');

-- ****************************************************************************************************************************

-- # Data Analysis

-- sorting the records - ORDERBY
SELECT * FROM employee ORDER BY Salary ;
SELECT * FROM employee ORDER BY Salary DESC LIMIT 3;

-- record getting highest salary and age is greater than 25
-- Execution flow : From - where - select - order by - limit
SELECT * FROM employee WHERE age > 30 ORDER BY Salary DESC LIMIT 1;

-- COUNT -> An Aggregate function that counts all not null entries

-- display the number of enrollments in the website of techforallwithpriya
SELECT COUNT(*) AS numberOfEnrollments FROM learners;

-- display the number of enrollments in the courseId = 3
SELECT COUNT(*) AS EnrollmentsInSQlCourse FROM learners WHERE  EnrolledCourses = 1;

-- LIKE is a wildcard expression.
-- Count the no.of enrollments in the month of jan
SELECT COUNT(*) AS enrollmentsInJan FROM learners WHERE learnerEnrollmentDate LIKE '%-01-21';

--  count the no.of comapnies learners belong to "Paytm"
SELECT COUNT(DISTINCT learnerCompany) FROM learners WHERE learnerCompany = 'Paytm';

-- Update the Jeeven record with yearsOfExperience = 1 and learnerCompany = AMAZON
UPDATE learners SET YearsOfExperience = 1, learnerCompany = "Infosys" WHERE learnerId = 4;

```
