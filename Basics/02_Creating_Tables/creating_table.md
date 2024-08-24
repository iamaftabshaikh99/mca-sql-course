# Creating Tables in SQL

## What is a Table?
A table is a collection of related data entries that consists of rows and columns. Each row represents a record, and each column represents an attribute of the data.

## Creating a Table
To create a table, use the `CREATE TABLE` statement. Here is the basic syntax:

```sql
CREATE TABLE table_name (
    column1 datatype constraints,
    column2 datatype constraints,
    ...
);
```

# Example: Creating a Students Table
Let's create a simple students table:

```sql
CREATE TABLE students (
    student_id INT PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    enrollment_date DATE
);
```

- student_id: This column stores the unique ID for each student. It is of type INT and is the primary key.
- first_name: Stores the first name of the student as a VARCHAR of up to 50 characters.
- last_name: Stores the last name of the student.
- enrollment_date: Stores the date when the student enrolled.

