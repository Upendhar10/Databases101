```sql
SHOW DATABASES;

USE techforallwithpriya;

SHOW TABLES;

SELECT * FROM learners;

-- count the number of learners who joined the courses via linkedIn, Youtube, Community
SELECT COUNT(*) FROM learners WHERE sourceOfJoining = "LinkedIn";

-- The columns speciified after the SELECT should be same as that of the columns specified after GROUP BY clause.
SELECT sourceOfJoining, COUNT(*) as no_of_students FROM learners GROUP BY sourceOfJoining;

-- Find In each of the available no.of learners had enrolled
SELECT EnrolledCourses, COUNT(*) AS no_of_students FROM learners GROUP BY EnrolledCourses;

-- Corresponding to individual sourceOfJoining, Give the maximum YearsOfExperience any person holds
SELECT sourceOfJoining, YearsOfExperience FROM learners GROUP BY sourceOfJoining, YearsOfExperience;
SELECT sourceOfJoining, MAX(YearsOfExperience) FROM learners GROUP BY sourceOfJoining;

-- Corresponding to individual sourceOfJoining, Give the minimum YearsOfExperience any person holds
SELECT sourceOfJoining, MIN(YearsOfExperience) AS min_YOE FROM learners GROUP BY sourceOfJoining;

-- Corresponding to individual sourceOfJoining, Give the minimum YearsOfExperience any person holds
SELECT sourceOfJoining, AVG(YearsOfExperience) AS AVG_YOE FROM learners GROUP BY sourceOfJoining;

-- HAVING Clause : filters the data that obtained after GROUP BY or Aggregation
-- WHERE Clause : filters the data before any aggregation functions
-- Never use HAVING clause before GROUP BY for filteration

-- Display the records of those learners who have joined the course via muitiple sourceOfJoinings

-- Display the count of students who joined via community
SELECT sourceOfJoining, COUNT(*) AS num_of_students
FROM learners
GROUP BY sourceOfJoining
HAVING sourceOfJoining = "community";

-- Display the courses which doesnot include "EXCEL"
SELECT * FROM courses WHERE courseName NOT LIKE "%EXCEL%";

-- Display the records of those students who has 1+ YOE and also joined the course via LinkedIn
SELECT * FROM learners WHERE YearsOfExperience > 1 AND  sourceOfJoining = "LinkedIn";

-- Display the records of those students who has 1+ YOE or joined the course via Youtube
SELECT * FROM learners WHERE YearsOfExperience > 1 OR  sourceOfJoining = "youtube";

-- Display the records of those students who has YOE between 1 to 3 ; 3 inclusive
SELECT * FROM learners WHERE YearsOfExperience BETWEEN 1 AND 3;

DESC employee;

-- # DECIMAL datatype in SQl
-- create a new table "courses_Update"
CREATE TABLE IF NOT EXISTS courses_Update(
courseId INT AUTO_INCREMENT,
courseName VARCHAR(50) NOT NULL,
courseInstructor VARCHAR(50) NOT NULL,
courseDurationInMonths DECIMAL(3,1) NOT NULL,
courseFee INT NOT NULL,
changedAt TIMESTAMP DEFAULT NOW() ON UPDATE NOW(),
PRIMARY KEY (courseId)
);

DESC courses_Update;

INSERT INTO courses_update (courseName,courseInstructor,courseDurationInMonths,courseFee) VALUES
("DSA Mastery", "Priya Bhatia", 2.5,4999),
("SQL Bootcamp", "Priya Bhatia", 1.5,2999),
("RESTAPI Mastery", "Priya Bhatia", 1.5,2999);

INSERT INTO courses_update (courseName,courseInstructor,courseDurationInMonths,courseFee) VALUES
("ML Bootcamp", "Priya Bhatia", 3.5,4599);

SELECT * FROM courses_update;
```
