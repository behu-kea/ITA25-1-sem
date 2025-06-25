# Constraints & Foreign Keys

**Preparation**

- https://www.youtube.com/watch?v=hjgJZtLgB4w

- The following constraints from: https://www.mysqltutorial.org/

  (Scroll down – right side of page)

  ![img](assets/2a6e3e6e-105d-47af-a9ac-b3d63d4b1d0e.png)

# Constraints

A table with only a Primary Key constraint 

```sql
CREATE TABLE departments (	
	department_number INTEGER, 
	department_name VARCHAR(30), 
	location VARCHAR(30), 
	PRIMARY KEY (department_number)
);
```

```SQL
CREATE TABLE employees(	
	id INTEGER, 
	employee_name VARCHAR(30), 
	job VARCHAR(30), 
	manager INTEGER, 
	hiredate DATE, 
	salary INTEGER, 
	commission INTEGER, 
	department_number INTEGER, 
	PRIMARY KEY (id),
	FOREIGN KEY (department_number) REFERENCES departments(department_number)
);
```



# Exercise 1: Individual

Implement the following constraints in departments and employees

- A department number has to be higher than 0 and lower than 1000
- A department name and location cannot be null
- An employee must be hired after 1980
- An employee cannot have a negative salary, but they can receive 0 (In the case of an intern)
- The default value for an employees manager is 7839



# Exercise 2: Individual

Implement the following constraints in departments and employees

- If a department number is changed, all employees will update their values
- If a department is deleted, all employees are also deleted from the database
- **Test** your implementation - ensure that it works



# Exercise 3: Study Groups

| Gruppe 1                                | Gruppe 2                    |
| --------------------------------------- | --------------------------- |
| Christoffer Brandt, Jeppe Jæger         | Ammar, Deniz, Lasse, Nadine |
| Mads, Oskar                             | Amalie, Hans                |
| Abdul, David, Rajana, William           | Gustav x3 Klara             |
| Arne, Frederik, Frederik, Lenah, Maheen | Alisa, Frederik, Nicklas    |

**Hand-over your design to your partner group**

- Diagram & Requirements



**Answer the following questions**

- Do the group live up to all their 10 identified requirements? 
- Why / Why not? 
- What do they need to change / update to reach their goal



**Give feedback / Receive feedback**



**A group is randomly selected to present their findings**