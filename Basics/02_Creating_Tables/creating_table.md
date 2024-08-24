### **02_Creating_Tables/creating_tables.md**

```markdown
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

### Example: Creating a Students Table
Let's create a simple `students` table:

```sql
CREATE TABLE students (
    student_id INT PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    enrollment_date DATE
);
```

**Explanation**: The `students` table contains information about students, where `student_id` uniquely identifies each student, `first_name` and `last_name` store the student's names, and `enrollment_date` records the date they enrolled.

### Example: Creating a Courses Table
Next, let's create a `courses` table:

```sql
CREATE TABLE courses (
    course_id INT PRIMARY KEY,
    course_name VARCHAR(100)
);
```

**Explanation**: The `courses` table contains details about different courses. The `course_id` uniquely identifies each course, and `course_name` stores the name of the course.

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