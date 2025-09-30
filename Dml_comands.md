# DML (Data Manipulation Language) Commands

Data Manipulation Language (DML) commands are used to manipulate data stored in a database. The most common DML commands are:

* **INSERT**: Add new records into a table.
* **UPDATE**: Modify existing records in a table.
* **DELETE**: Remove records from a table.
* **SELECT**: Retrieve data from a table.

---

## 1. INSERT Command

The `INSERT` statement is used to add data into a table.

### Example Table: `students`

```sql
CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT,
    course VARCHAR(50)
);
```

### Ways to Insert Data

#### a) Insert without mentioning columns (all values must be provided in order)

```sql
INSERT INTO students VALUES (1, 'Alice', 20, 'Mathematics');
```

#### b) Insert by mentioning column names (recommended, flexible)

```sql
INSERT INTO students (id, name, age, course)
VALUES (2, 'Bob', 22, 'Computer Science');
```

#### c) Insert into specific columns (other columns will be NULL if not provided)

```sql
INSERT INTO students (id, name)
VALUES (3, 'Charlie');
```

#### d) Insert multiple rows at once

```sql
INSERT INTO students (id, name, age, course) VALUES
(4, 'David', 23, 'Physics'),
(5, 'Eve', 21, 'Chemistry');
```

---

## 2. UPDATE Command

The `UPDATE` statement is used to modify existing records.

### Syntax

```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

### Examples

#### a) Update a single column

```sql
UPDATE students
SET age = 24
WHERE id = 2;
```

#### b) Update multiple columns

```sql
UPDATE students
SET age = 25, course = 'Statistics'
WHERE name = 'Alice';
```

#### ⚠️ Important:

If you **omit the `WHERE` clause**, all rows will be updated.

```sql
UPDATE students
SET course = 'General';
```

---

## 3. DELETE Command

The `DELETE` statement is used to remove records.

### Syntax

```sql
DELETE FROM table_name WHERE condition;
```

### Examples

#### a) Delete a specific row

```sql
DELETE FROM students
WHERE id = 3;
```

#### b) Delete multiple rows based on a condition

```sql
DELETE FROM students
WHERE age > 22;
```

#### c) Delete all rows (table remains)

```sql
DELETE FROM students;
```

⚠️ If you want to remove all rows **faster**, use `TRUNCATE`, but note that it is a **DDL command**, not DML.

---

## 4. SELECT Command

The `SELECT` statement is used to retrieve data.

### Syntax

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

### Examples

#### a) Select all columns

```sql
SELECT * FROM students;
```

#### b) Select specific columns

```sql
SELECT name, course FROM students;
```

#### c) Apply conditions

```sql
SELECT * FROM students
WHERE age < 23;
```

#### d) Use ORDER BY

```sql
SELECT * FROM students
ORDER BY age DESC;
```

#### e) Use DISTINCT

```sql
SELECT DISTINCT course FROM students;
```

---

## Conclusion

* **INSERT** → Add data into tables (multiple ways).
* **UPDATE** → Modify existing records.
* **DELETE** → Remove records (with or without conditions).
* **SELECT** → Retrieve and filter data.

👉 Always use `WHERE` carefully in `UPDATE` and `DELETE` to avoid unintentional changes.

---
