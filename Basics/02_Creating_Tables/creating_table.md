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

# Data Types and Constraints
- INT: A numeric data type for integers.
- VARCHAR(size): A variable-length character string.
- DATE: A date format (YYYY-MM-DD).
- PRIMARY KEY: Uniquely identifies each row in a table.

# Creating Multiple Tables
In addition to the students table, let's create courses and enrollments tables to manage student enrollments in courses.

```sql
CREATE TABLE courses (
    course_id INT PRIMARY KEY,
    course_name VARCHAR(100)
);

CREATE TABLE enrollments (
    enrollment_id INT PRIMARY KEY,
    student_id INT,
    course_id INT,
    enrollment_date DATE,
    FOREIGN KEY (student_id) REFERENCES students(student_id),
    FOREIGN KEY (course_id) REFERENCES courses(course_id)
);
```

# courses: Manages course details with course_id as the primary key.
enrollments: Tracks which students are enrolled in which courses, with student_id and course_id as foreign keys.

# Practice
Refer to the `examples/` directory for SQL scripts to create these tables and populate them with data.

Continue to the next lesson: **[Inserting Data into Tables](../03_Inserting_Data/inserting_data.md)**
