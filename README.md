# MYSQL-09
# Experiment 9
# Aim:
To implement ROLLUP function.

# Program:
```
CREATE TABLE EMPLOYEE (  
 emp_id int identity,  
 fullname varchar(65),  
 occupation varchar(45),  
 gender varchar(30),  
 salary int,  
 country varchar(55)  
);  
INSERT INTO EMPLOYEE(fullname, occupation, gender, salary, country)  
VALUES ('John Doe', 'Writer', 'Male', 62000, 'USA'),  
('Mary Greenspan', 'Freelancer', 'Female', 55000, 'India'),  
('Grace Smith', 'Scientist', 'Male', 85000, 'USA'),  
('Mike Johnson', 'Manager', 'Male', 250000, 'India'),  
('Todd Astel', 'Business Analyst', 'Male', 42000, 'India');
SELECT country, SUM(salary) AS "Total Salary"  
FROM EMPLOYEE  
GROUP BY country;  
SELECT country, SUM(salary) AS "Total Salary"  
FROM EMPLOYEE  
GROUP BY ROLLUP (country);  
SELECT country, SUM(salary) AS "Total Salary"  
FROM EMPLOYEE  
GROUP BY country WITH ROLLUP;  
SELECT COALESCE(country, 'GRAND TOTAL' ) AS country, SUM(salary) AS "Total Salary"  
FROM EMPLOYEE  
GROUP BY ROLLUP (country);  
```
# Output:
![image](https://github.com/SOMEASVAR/MYSQL-09/assets/93434149/35625149-e70d-42d9-ab3b-dc566dd34c82)

# Result:
Therefore we have successfully implemented ROLLUP function.
