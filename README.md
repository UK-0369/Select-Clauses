# Select-Clauses
assignmnet
CREATE TABLE Manager (
    Manager_Id INT IDENTITY(1,1) PRIMARY KEY,
    First_Name NVARCHAR(50) NOT NULL,
    Last_Name NVARCHAR(50) NOT NULL,
    DOB DATE NOT NULL,
    Age INT CHECK (Age >= 18 AND Age <= 65),
    Last_Update DATETIME DEFAULT GETDATE(),
    Gender NVARCHAR(10) CHECK (Gender IN ('Male', 'Female', 'Other')),
    Department NVARCHAR(50) NOT NULL,
    Salary DECIMAL(10, 2) NOT NULL
);



select * from Manager

INSERT INTO Manager (First_Name, Last_Name, DOB, Age, Gender, Department, Salary)
VALUES 
('Alice', 'Johnson', '1985-04-12', 39, 'Female', 'HR', 75000.00),
('Bob', 'Smith', '1990-09-20', 34, 'Male', 'Finance', 82000.00),
('Clara', 'Williams', '1988-02-15', 36, 'Female', 'IT', 95000.00),
('David', 'Brown', '1983-06-25', 41, 'Male', 'Marketing', 72000.00),
('Aaliya', 'Jones', '1992-12-10', 32, 'Female', 'Sales', 68000.00),
('Frank', 'Taylor', '1980-07-07', 44, 'Male', 'Finance', 87000.00),
('Grace', 'Moore', '1987-03-30', 37, 'Female', 'HR', 77000.00),
('Harry', 'Anderson', '1995-01-05', 29, 'Male', 'IT', 80000.00),
('Ivy', 'Thomas', '1993-08-18', 31, 'Female', 'Operations', 67000.00),
('Jack', 'White', '1989-11-22', 35, 'Male', 'Marketing', 73000.00);



SELECT First_Name, Last_Name, DOB 
FROM Manager 
WHERE Manager_Id = 1;


SELECT Manager_Id, First_Name, Last_Name, (Salary * 12) AS Annual_Income 
FROM Manager;

SELECT (Salary * 12) AS Annual_Income 
FROM Manager;

SELECT * 
FROM Manager 
WHERE First_Name = 'Aaliya';

SELECT * 
FROM Manager
WHERE First_Name != 'Aaliya';

SELECT * 
FROM Manager
WHERE Department = 'IT' AND Salary > 25000;
