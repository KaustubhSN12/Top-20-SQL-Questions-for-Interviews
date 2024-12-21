
# 🎓 **Top 20 SQL Interview Questions and Answers**

Welcome to the **Top 20 SQL Interview Questions** repository! This resource is designed to help you ace SQL interviews by covering essential concepts with detailed explanations and answers.

---

## 🌟 **Table of Contents**
1. [Basic SQL Questions](#basic-sql-questions)
2. [Intermediate SQL Questions](#intermediate-sql-questions)
3. [How to Use This Repository](#how-to-use-this-repository)
4. [Contributing](#contributing)
5. [License](#license)

---

## 🟢 **Basic SQL Questions**

### 1️⃣ Retrieve all records from a table  
**Query:**  
```sql
SELECT * FROM employees;
```  
**Explanation:**  
Fetches all rows and columns from the `employees` table. Use cautiously as it retrieves a large dataset.

---

### 2️⃣ Fetch unique departments from the employees table  
**Query:**  
```sql
SELECT DISTINCT department_id FROM employees;
```  
**Explanation:**  
The `DISTINCT` keyword eliminates duplicate rows, returning only unique department IDs.

---

### 3️⃣ Sort employees by their salary in descending order  
**Query:**  
```sql
SELECT * FROM employees ORDER BY salary DESC;
```  
**Explanation:**  
Sorts employees by their `salary` in descending order using the `ORDER BY` clause.

---

### 4️⃣ Count the total number of employees in the company  
**Query:**  
```sql
SELECT COUNT(*) AS total_employees FROM employees;
```  
**Explanation:**  
Counts all rows in the `employees` table and displays the total as `total_employees`.

---

### 5️⃣ Retrieve employees who joined after a specific date  
**Query:**  
```sql
SELECT * FROM employees WHERE hire_date > '2022-01-01';
```  
**Explanation:**  
Filters rows where the `hire_date` is greater than the given date.

---

### 6️⃣ Find employees whose name starts with 'A'  
**Query:**  
```sql
SELECT * FROM employees WHERE name LIKE 'A%';
```  
**Explanation:**  
The `LIKE` operator matches patterns. `%` represents any sequence of characters.

---

### 7️⃣ Fetch employees who belong to specific departments (HR and Finance)  
**Query:**  
```sql
SELECT * FROM employees WHERE department_id IN (101, 102);
```  
**Explanation:**  
The `IN` clause filters rows matching the specified department IDs.

---

### 8️⃣ Retrieve employees with salaries between 50,000 and 100,000  
**Query:**  
```sql
SELECT * FROM employees WHERE salary BETWEEN 50000 AND 100000;
```  
**Explanation:**  
The `BETWEEN` operator filters rows within a range of values.

---

### 9️⃣ Find the total salary paid to all employees  
**Query:**  
```sql
SELECT SUM(salary) AS total_salary FROM employees;
```  
**Explanation:**  
Calculates the sum of salaries for all employees.

---

### 🔟 Fetch employees who do not have a manager assigned  
**Query:**  
```sql
SELECT * FROM employees WHERE manager_id IS NULL;
```  
**Explanation:**  
Finds employees where the `manager_id` is `NULL`.

---

## 🔵 **Intermediate SQL Questions**

### 1️⃣1️⃣ Find the department-wise average salary of employees  
**Query:**  
```sql
SELECT department_id, AVG(salary) AS avg_salary 
FROM employees 
GROUP BY department_id;
```  
**Explanation:**  
Groups rows by `department_id` and calculates the average salary for each department.

---

### 1️⃣2️⃣ Fetch the top 3 highest salaries  
**Query:**  
```sql
SELECT * FROM employees ORDER BY salary DESC LIMIT 3;
```  
**Explanation:**  
Sorts salaries in descending order and retrieves the top 3 records using `LIMIT`.

---

### 1️⃣3️⃣ Identify duplicate records based on employee name and department  
**Query:**  
```sql
SELECT name, department_id, COUNT(*) 
FROM employees 
GROUP BY name, department_id 
HAVING COUNT(*) > 1;
```  
**Explanation:**  
Identifies duplicates by grouping records and using `HAVING COUNT(*) > 1`.

---

### 1️⃣4️⃣ Retrieve employees with no matching records in another table  
**Query:**  
```sql
SELECT e.* 
FROM employees e 
LEFT JOIN projects p ON e.employee_id = p.employee_id 
WHERE p.employee_id IS NULL;
```  
**Explanation:**  
Uses `LEFT JOIN` to find employees without corresponding project records.

---

### 1️⃣5️⃣ Write a query to find the employee with the maximum salary  
**Query:**  
```sql
SELECT * FROM employees WHERE salary = (SELECT MAX(salary) FROM employees);
```  
**Explanation:**  
Finds the highest salary using a subquery.

---

### 1️⃣6️⃣ Calculate the difference between the highest and lowest salaries  
**Query:**  
```sql
SELECT MAX(salary) - MIN(salary) AS salary_difference FROM employees;
```  
**Explanation:**  
Computes the difference using `MAX` and `MIN` functions.

---

### 1️⃣7️⃣ Retrieve employees who share the same manager  
**Query:**  
```sql
SELECT manager_id, GROUP_CONCAT(name) AS employees 
FROM employees 
GROUP BY manager_id 
HAVING COUNT(*) > 1;
```  
**Explanation:**  
Groups employees by `manager_id` and lists employees under each manager.

---

### 1️⃣8️⃣ Fetch employees along with their department names  
**Query:**  
```sql
SELECT e.name, d.department_name 
FROM employees e 
JOIN departments d ON e.department_id = d.department_id;
```  
**Explanation:**  
Uses `JOIN` to combine `employees` and `departments` tables.

---

### 1️⃣9️⃣ Rank employees based on their salary  
**Query:**  
```sql
SELECT name, salary, RANK() OVER (ORDER BY salary DESC) AS rank 
FROM employees;
```  
**Explanation:**  
Ranks employees using the `RANK()` window function.

---

### 2️⃣0️⃣ Identify employees who earn above the department’s average salary  
**Query:**  
```sql
SELECT e.* 
FROM employees e 
JOIN (SELECT department_id, AVG(salary) AS avg_salary 
      FROM employees 
      GROUP BY department_id) dept_avg 
ON e.department_id = dept_avg.department_id 
WHERE e.salary > dept_avg.avg_salary;
```  
**Explanation:**  
Compares employee salaries with their department’s average using a subquery.

---

## 📘 **How to Use This Repository**
1. Clone the repository:  
   ```bash
   git clone https://github.com/[your-username]/sql-interview-questions.git
   ```
2. Open and practice the SQL queries in your database environment.
3. Refer to explanations for a better understanding of the queries.

---

## 🤝 **Contributing**
Contributions are welcome!  
- Fork the repository.  
- Make your changes.  
- Submit a pull request.

---

## 📜 **License**
This repository is licensed under the MIT License. For details, see the [LICENSE](LICENSE) file.

---

**🌟 Master SQL and ace your interviews! 🌟**
