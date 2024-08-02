```sql
-- # show available databases
SHOW DATABASES;

--  # select a specific database
USE techforallwithpriya;

-- # show all the available tables in the database
SHOW TABLES;

-- # creata a new table "courses" in the database "techforallwithpriya"
CREATE TABLE IF NOT EXISTS courses(
courseId INT AUTO_INCREMENT,
courseName VARCHAR(50) NOT NULL,
courseInstructor VARCHAR(50) NOT NULL,
courseDurationInMonths INT NOT NULL,
courseFee INT NOT NULL,
PRIMARY KEY (courseId)
);

-- # Describe the table schema
DESC courses;

-- # Insert data into courses table

-- Insert a single dataItem into courses table
INSERT INTO courses (courseName,courseInstructor,courseDurationInMonths,courseFee) VALUES ("Excel Mastery", "Priya Bhatia", 3,1499);

-- Insert a multiple dataItem into courses table at once
INSERT INTO courses (courseName,courseInstructor,courseDurationInMonths,courseFee) VALUES
("DSA for Interview Prep", "Priya Bhatia", 2,4999),
("SQL Bootcamp", "Priya Bhatia", 1,2999);

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

INSERT INTO learners
(learnerFirstName,learnerLastName, learnerEmail, learnerPhoneNum, location, sourceOfJoining, YearsOfExperience, learnerCompany, learnerEnrollmentDate, EnrolledCourses, BatchStartDate)
VALUES
("Akhil","George", "akhil.George.8743@gmail.com", 9124567865, "Hyderabad", "LinkedIn", 2, "Infosys", '2024-01-10', 2, '2024-01-16'),
("Rishikesh","Joshi", "carjkop@gmail.com", 9167865001, "Mumbai", "Community", 1, "Plivo", '2024-01-10', 1, '2024-02-29'),
("Madhuram","Ravichandran", "ravichandran.maduram@gmail.com", 8124537895, "Noida", "LinkedIn", 2, "ofbusiness", '2024-01-15', 2, '2024-01-16'),
("Jeevan","Hedge", "jeevenhedgek@yahoo.com", 6129067864, "Hyderabad", "Youtube", 0, "TCS", '2024-01-21', 1, '2024-02-29'),
("Nagasai","Sreedhar", "saisreedhar2001@gmail.com", 8789764569, "Jaipur", "Community", 1, "HCL", '2024-03-19', 3, '2024-03-25');


INSERT INTO learners
(learnerFirstName,learnerLastName, learnerEmail, learnerPhoneNum, location, sourceOfJoining, YearsOfExperience, learnerCompany, learnerEnrollmentDate, EnrolledCourses, BatchStartDate)
VALUES
("Manoj","Tiwary", "Tiwary.Manoj.743@gmail.com", 9127767865, "Lucknow", "Youtube", 3, "Nvidia", '2024-02-12', 3, '2024-03-25'),
("Mike","Tyson", "Tyson438@gmail.com", 6527767865, "Lucknow", "community", 3, "Paytm", '2024-02-22', 1, '2024-02-29');
```
