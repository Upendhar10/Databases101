# Mastering Data Retrieval with SELECT Statements

## Datatypes

1. TIMESTAMP : represents a Date along with Time => YY-MM-DD HH:MM:SS

## Constraints

1. Primary Key : Unique and Not Null
2. Unique Key : Unique but Not Null

## Clauses

1. WHERE : Used to perform filtering
2. ORDER BY : By default, Sorts the data in Ascending order
3. ORDER BY DESC : Sorts the data in Descending order
4. LIMIT : Limit the number of records to be displayed

## Flow of Execution

1. Statement containing SELECT, FROM, ORDER BY, WHERE and LIMIT

   > SELECT \* FROM employee ORDER BY employee Salary LIMIT 2;

   - FROM => SELECT => ORDER BY => LIMIT

2. Statement containing SELECT, AGGREGATE and FROM

   > SELECT COUNT(\*) AS totalEntrollments FROM learners;

   - FROM => SELECT => AGGREGATE

# Data Analysis

-- sorting the records - ORDERBY
SELECT _ FROM employee ORDER BY Salary ;
SELECT _ FROM employee ORDER BY Salary DESC LIMIT 3;

-- record getting highest salary and age is greater than 25 | From - where - select - order by - limit
SELECT \* FROM employee WHERE age > 30 ORDER BY Salary DESC LIMIT 1;

-- display the number of enrollments in the website of techforallwithpriya
SELECT COUNT(\*) AS numberOfEnrollments FROM learners;

-- display the number of enrollments in the courseId = 3
SELECT COUNT(\*) AS EnrollmentsInSQlCourse FROM learners WHERE EnrolledCourses = 1;

-- Count the no.of enrollments in the month of jan
SELECT COUNT(\*) AS enrollmentsInJan FROM learners WHERE learnerEnrollmentDate LIKE '%-01-21';

-- Update the Jeeven record with yearsOfExperience = 1 and learnerCompany = AMAZON
UPDATE learners SET YearsOfExperience = 1, learnerCompany = "Infosys" WHERE learnerId = 4;

-- count the no.of comapnies learners belong to
-- COUNT -> counts all not null entries
SELECT COUNT(DISTINCT learnerCompany) FROM learners;
