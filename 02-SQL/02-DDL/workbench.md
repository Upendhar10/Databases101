```sql

-- Single line comment

/*
multi
line
comment
*/

-- # show available databases
SHOW DATABASES;

-- # Create a new database
CREATE DATABASE IF NOT EXISTS techforallwithpriya;

--  # select a specific database
USE techforallwithpriya;

-- # show all the available tables in the database
SHOW TABLES;

-- # creata a new table "employee" in the database "techforallwithpriya"
CREATE TABLE IF NOT EXISTS employee (
EID INT AUTO_INCREMENT ,
FirstName VARCHAR(50) NOT NULL,
LastName VARCHAR(50) NOT NULL,
Age INT NOT NULL,
Salary INT NOT NULL,
Location VARCHAR(50) NOT NULL,
PRIMARY KEY(EID)
);

-- # Describe the table schema
DESC employee;

-- # Alter table
ALTER TABLE employee ADD COLUMN JobRole varchar(50);
ALTER TABLE employee MODIFY COLUMN  LastName varchar(40);
ALTER TABLE employee DROP COLUMN JobRole;

-- # Rename table name "employee" to "staff"
ALTER TABLE employees
RENAME TO staff;

-- # Drop the table
DROP TABLE staff;

-- # creata a new table "courses" in the database "techforallwithpriya"
CREATE TABLE IF NOT EXISTS courses(
courseId INT AUTO_INCREMENT,
courseName VARCHAR(50) NOT NULL,
courseInstructor VARCHAR(50) NOT NULL,
courseDurationInMonths INT NOT NULL,
courseFee INT NOT NULL,
PRIMARY KEY (courseId)
);

DESC courses;

-- # creata a new table "learners" in the database "techforallwithpriya"
CREATE TABLE IF NOT EXISTS learners(
learnerId INT AUTO_INCREMENT,
learnerFirstName VARCHAR(50) NOT NULL,
learnerLastName VARCHAR(50) NOT NULL,
learnerEmail VARCHAR(50),
learnerPhoneNum VARCHAR(10) NOT NULL,
location VARCHAR(50) NOT NULL,
sourceOfJoining VARCHAR(50) NOT NULL,
YearsOfExperience INT NOT NULL,
learnerCompany VARCHAR(50),
learnerEnrollmentDate TIMESTAMP NOT NULL,
EnrolledCourses INT NOT NULL,
BatchStartDate TIMESTAMP NOT NULL,

PRIMARY KEY (learnerId),
UNIQUE KEY(learnerEmail),
FOREIGN KEY (EnrolledCourses) REFERENCES courses(courseId)
);

DESC learners;

```
