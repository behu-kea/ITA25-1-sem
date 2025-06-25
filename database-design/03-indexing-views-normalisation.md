### Questions:

- What is the cardinality between **Author** and **Book**? Can a book have multiple authors? Can an author write more than one book?
- What is the cardinality between **Book** and **Publisher**? Can a book be published by more than one publisher? Can a publisher publish multiple books?
- What is the cardinality between **Book** and **Review**? Can a book have multiple reviews? Can a user review multiple books?
- What is the cardinality between **User** and **Review**? Can a user leave multiple reviews? Can a review belong to more than one user?



### Indexing Exercises

**A) Employees and departments dataset**

The employees from employees and departments receive very few new employees every year. But external API calls uses the database many times daily to view retrieve data of each departments location. What is the current status of the database and how could it be improved with indexing?

Implement the solution.

**B) Spotify dataset**

Data scientists of spotify have identified that 99% of users always searches for a song according to its title and popularity. Implement a solution that could speed up their requests.

Implement the solution.

### Normalisation

Ensure the following schemes are in 3NF - present changes (if any) and clarify why

**A)**

*store(store_id, manager_id, longitude, lattitude, continent, country, revenue, goal_revenue, staff_size)*

**B)**

*employee(employee_id, employee_name, department, supervisor_name, supervisor_department*

**C)**

*invoice(invoice_number, customer_name, customer_address, employee_name, employee_department)*

**D)**

**In MySQL workbench EED**

Create a normalised relational model (up to 3NF) about medical appointments with the following information in mind:

- Each doctor can have individual appointments with many patients.
- Each patient can book individual appointments with many doctors.
- Attributes to include:
  - DoctorID
  - DoctorName
  - DoctorAddress
  - PatientID
  - PatientName
  - PatientPhoneNo
  - AppointmentDate



**E) Consider the pokemon dataset**

Arguably the dataset is in 3rd normal form - but is still susceptible to update anomalies due to data duplication. How can decomposition be utilized to reduce data redundancy?

### Views

Employees and departments

**A)**

Create a view that displays full name and department location of employees

**B)**

Create a view that displays the average salary of all employees except the ones working in sales

**C)**

Create a view with columns: department name & average salary pr. department

**D) Advanced (optional)**

Create a view that displays the name of all employees with a salary higher than the average salary.

- 

  Employees with a commission should not be included