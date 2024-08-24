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