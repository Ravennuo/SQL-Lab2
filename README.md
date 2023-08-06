# SQL-Lab2

# We will use the Employees and Awards table below:

 <img src="Lab2.png" width="500" height="500">

### Q1: Choose all employees who have received an award (Nested Query)?
Query:
'''SQL
SELECT id, name
FROM employee
WHERE id in (SELECT employee_id 
             FROM awards);
'''

Output:
<img src="img/01.png" alt="Q1" style="width:400px;"/>

### Q2: Choose all employees who have never received an award (Nested Query)?
Query:

'''SQL
SELECT id, name
FROM employee
WHERE id NOT IN (SELECT employee_id 
             FROM awards);
'''

Output:
<img src="img/02.png" alt="Q2" style="width:400px;"/>
 
### Q3: Choose all Developers who make more than all Managers combined (Nested Query)?
Query:
'''SQL
SELECT *
FROM employee
WHERE role = "Developer"
and salary > (SELECT MAX(salary)
              FROM employee
              WHERE role = "Manager");
'''

Output:
<img src="img/03.png" alt="Q4" style="width:400px;"/>

### Q4: Choose all Developers who make more money than any Manager (Nested Query)?
Query:
'''SQL
SELECT id, name
FROM employee
WHERE role = "Developer" 
and salary > (SELECT MIN(salary)
                  FROM employee
                  WHERE role = "Manager");
'''
Output:
<img src="img/04.png" alt="Q4" style="width:400px;"/>
 
### Q5: Choose all employees whose salaries are higher than the average for their position. (Nested Query)?
Query:
'''SQL
SELECT *
FROM employee
WHERE salary > (SELECT AVG(salary)
                    FROM employee
                    GROUP by role);
'''

Output:
<img src="img/05.png" alt="Q5" style="width:400px;"/>
