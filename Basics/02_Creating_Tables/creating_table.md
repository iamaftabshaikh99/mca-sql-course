
# Creating and Managing Databases

## Creating a Database
Before creating tables, you need to have a database where these tables will reside. A database is a collection of related data organized for easy access, management, and updating.

To create a new database, use the following `CREATE DATABASE` statement:

```sql
CREATE DATABASE database_name;
```

### Example: Creating a New Database

```sql
CREATE DATABASE school;
```

**Explanation**: This command creates a new database named `school`.

---

## Listing Existing Databases
To see a list of all existing databases on your server, you can use the `SHOW DATABASES` statement:

```sql
SHOW DATABASES;
```

**Explanation**: This command lists all databases currently available on your server.

---

## Selecting a Database
Before creating tables, you need to select the database where the tables will be created. You can select a database using the `USE` command:

```sql
USE school;
```

**Explanation**: This command selects the `school` database, making it the active database for all subsequent operations.

---

### Displaying the Selected Database
To confirm that you are working in the correct database, you can use the `SELECT DATABASE();` command:

```sql
SELECT DATABASE();
```

**Explanation**: This command returns the name of the currently selected database.

---

# Creating Tables in SQL

## What is a Table?
A table is a collection of related data entries consisting of rows and columns. Each row represents a record, and each column represents an attribute of the data.

## Creating a Table
To create a table within a selected database, use the `CREATE TABLE` statement. Here is the basic syntax:

```sql
CREATE TABLE table_name (
    column1 datatype constraints,
    column2 datatype constraints,
    ...
);
```

---

### Example: Creating a Students Table
Let's create a simple `students` table within the `school` database:

```sql
CREATE TABLE students (
    student_id INT PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    enrollment_date DATE
);
```

**Explanation**: The `students` table contains information about students. The `student_id` uniquely identifies each student, `first_name` and `last_name` store the student's names, and `enrollment_date` records the date they enrolled.

#### **Expected Output**
After running `DESCRIBE students;` or `SHOW COLUMNS FROM students;`, you should see:

| Field           | Type        | Null | Key | Default | Extra          |
|-----------------|-------------|------|-----|---------|----------------|
| **student_id**  | INT         | NO   | PRI | NULL    | auto_increment |
| **first_name**  | VARCHAR(50) | YES  |     | NULL    |                |
| **last_name**   | VARCHAR(50) | YES  |     | NULL    |                |
| **enrollment_date** | DATE    | YES  |     | NULL    |                |

---

### Example: Creating a Courses Table
Next, let's create a `courses` table:

```sql
CREATE TABLE courses (
    course_id INT PRIMARY KEY,
    course_name VARCHAR(100)
);
```

**Explanation**: The `courses` table contains details about different courses. The `course_id` uniquely identifies each course, and `course_name` stores the name of the course.

#### **Expected Output**
After running `DESCRIBE courses;` or `SHOW COLUMNS FROM courses;`, you should see:

| Field       | Type         | Null | Key | Default | Extra          |
|-------------|--------------|------|-----|---------|----------------|
| **course_id** | INT        | NO   | PRI | NULL    | auto_increment |
| **course_name** | VARCHAR(100) | YES |  | NULL    |                |

---

### Example: Creating an Enrollments Table
Finally, let's create an `enrollments` table:

```sql
CREATE TABLE enrollments (
    enrollment_id INT PRIMARY KEY,
    student_id INT,
    course_id INT,
    enrollment_date DATE,
    FOREIGN KEY (student_id) REFERENCES students(student_id),
    FOREIGN KEY (course_id) REFERENCES courses(course_id)
);
```

**Explanation**: The `enrollments` table tracks which students are enrolled in which courses. It includes `student_id` and `course_id` as foreign keys that reference the `students` and `courses` tables, respectively, establishing a relationship between the tables.

#### **Expected Output**
After running `DESCRIBE enrollments;` or `SHOW COLUMNS FROM enrollments;`, you should see:

| Field           | Type | Null | Key | Default | Extra          |
|-----------------|------|------|-----|---------|----------------|
| **enrollment_id** | INT | NO   | PRI | NULL    | auto_increment |
| **student_id**  | INT  | YES  | MUL | NULL    |                |
| **course_id**   | INT  | YES  | MUL | NULL    |                |
| **enrollment_date** | DATE | YES | | NULL    |                |

---

## Practice
Refer to the `examples/` directory for SQL scripts to create these tables and populate them with data.

---

### Examples Directory

- **create_students_table.sql**:

```sql
CREATE TABLE students (
    student_id INT PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    enrollment_date DATE
);
```

- **create_courses_table.sql**:

```sql
CREATE TABLE courses (
    course_id INT PRIMARY KEY,
    course_name VARCHAR(100)
);
```

- **create_enrollments_table.sql**:

```sql
CREATE TABLE enrollments (
    enrollment_id INT PRIMARY KEY,
    student_id INT,
    course_id INT,
    enrollment_date DATE,
    FOREIGN KEY (student_id) REFERENCES students(student_id),
    FOREIGN KEY (course_id) REFERENCES courses(course_id)
);
```

---

Continue to the next lesson: **[Inserting Data into Tables](../03_Inserting_Data/inserting_data.md)**.



