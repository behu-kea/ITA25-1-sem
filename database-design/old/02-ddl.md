# Data Definition Language

- CREATE
- AUTO_INCREMENT
- NOT NULL
- DEFAULT
- PRIMARY_KEY

**Preparation**

[Create](https://www.mysqltutorial.org/mysql-create-table/)

[Drop](https://www.mysqltutorial.org/mysql-drop-column/)

[Add](https://www.mysqltutorial.org/mysql-add-column/)

[Auto Increment](https://www.mysqltutorial.org/mysql-sequence/)

[How to create a database in workbench](https://youtu.be/OnXB3ZRrOW0)



# Examples

**Creating a database (Remember to refresh)**

```sql
CREATE DATABASE pokedex;
```



**An example table:**

```SQL
CREATE TABLE IF NOT EXISTS checklists (
    todo_id INT AUTO_INCREMENT,
    task_id INT,
    todo VARCHAR(255) NOT NULL,
    is_completed BOOLEAN NOT NULL DEFAULT FALSE,
    PRIMARY KEY (todo_id , task_id),
);
```



**Inserting with AUTO_INCREMENT**

```sql
-- customer has the following scheme
-- customer(customer_id, firstname, lastname, gender, phone_number)
-- customer_id is AUTO_INCREMENT
INSERT INTO customer (firstname, lastname, gender, phone_number)
VALUES ("Nicklas", "Frederiksen", "M", 20436262);
```



# Exercise 1 (Study groups)

- List at least 10 requirements from the case e.g:

- - A movie has a unique ID
  - *A movie can be …*
  - *The cast of a movie is …*

- Formalise the requirements in a document (SAVE THE DOCUMENT)



# Exercise 2 (Study groups)

- Implement new IMDB data model
- - Using Create 

  - Primary Key, NOT NULL, DEFAULT

  - (Foreign Key)

- Reverse Engineer as EER diagram (Ask for help if needed)
- Hand-in: get **AS FAR AS POSSIBLE WHILE STILL HANDING IN (AFAP)**
- - Identified requirements
  - EER Diagram



**Handin here:**

Deadline 28th September

https://kea-fronter.itslearning.com/LearningToolElement/ViewLearningToolElement.aspx?LearningToolElementId=1052653
