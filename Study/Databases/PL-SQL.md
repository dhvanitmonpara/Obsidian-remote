---
sticker: lucide//chevron-up
---
## Introduction to PL/SQL
- PL/SQL stands for Procedural Language/Structured Query Language.
- It is an extension of SQL used in Oracle databases for writing procedural code.
- PL/SQL allows you to create stored procedures, functions, triggers, packages, and more.

## PL/SQL Blocks
- A PL/SQL block is a group of one or more PL/SQL statements.
- It starts with the `DECLARE` keyword, followed by optional declarations of variables and constants.
- The `BEGIN` keyword marks the beginning of executable statements.
- The `EXCEPTION` block handles exceptions that occur during the execution of the block.
- The `END;` keyword marks the end of the block.

```plsql
DECLARE
    -- Declarations
BEGIN
    -- Executable Statements
EXCEPTION
    -- Exception Handling
END;
```

In which `EXCEPTION` section is optional.

## Variables and Constants
- Variables are used to store data temporarily within a PL/SQL block.
- Constants are like variables but their values cannot be changed.
- Declared using the `DECLARE` section.

```plsql
DECLARE
    v_variable1 VARCHAR2(50);
    v_variable2 NUMBER := 10;
    c_constant CONSTANT NUMBER := 100;
BEGIN
    -- Statements using variables and constants
END;
```

## Control Structures
- PL/SQL supports various control structures such as `IF-THEN-ELSE`, `CASE`, `LOOP`, `WHILE`, etc.

```plsql
IF condition THEN
    -- Statements
ELSIF condition THEN
    -- Statements
ELSE
    -- Statements
END IF;
```

```plsql
CASE expression
    WHEN value1 THEN
        -- Statements
    WHEN value2 THEN
        -- Statements
    ELSE
        -- Statements
END CASE;
```

```plsql
LOOP
    -- Statements
    EXIT WHEN condition;
END LOOP;
```

```plsql
WHILE condition LOOP
    -- Statements
END LOOP;
```

## Cursors
- Cursors are used for traversing through the records returned by a SELECT query.
- They can be either explicit or implicit.

```plsql
DECLARE
    CURSOR cur_name IS
        SELECT column1, column2
        FROM table_name;
    v_variable1 table_name.column1%TYPE;
    v_variable2 table_name.column2%TYPE;
BEGIN
    OPEN cur_name;
    LOOP
        FETCH cur_name INTO v_variable1, v_variable2;
        EXIT WHEN cur_name%NOTFOUND;
        -- Process fetched data
    END LOOP;
    CLOSE cur_name;
END;
```

## Exception Handling
- PL/SQL provides robust exception handling mechanisms to deal with errors.
- Exceptions can be predefined or user-defined.

```plsql
BEGIN
    -- Statements
EXCEPTION
    WHEN exception1 THEN
        -- Handle exception1
    WHEN exception2 THEN
        -- Handle exception2
    WHEN OTHERS THEN
        -- Handle all other exceptions
END;
```

## Procedures and Functions
- Procedures and functions are named PL/SQL blocks that can be called multiple times.
- Procedures do not return values, whereas functions return a single value.

```plsql
CREATE [OR REPLACE] PROCEDURE procedure_name
    (parameter1 IN datatype1, parameter2 OUT datatype2)
AS
BEGIN
    -- Procedure body
END;
```

```plsql
CREATE [OR REPLACE] FUNCTION function_name
    (parameter1 IN datatype1, parameter2 IN datatype2)
RETURN return_datatype
AS
BEGIN
    -- Function body
    RETURN value;
END;
```

## Triggers
- Triggers are PL/SQL blocks associated with a table.
- They are executed automatically when certain events occur on the table (e.g., INSERT, UPDATE, DELETE).

```plsql
CREATE [OR REPLACE] TRIGGER trigger_name
BEFORE INSERT OR UPDATE OR DELETE ON table_name
FOR EACH ROW
BEGIN
    -- Trigger body
END;
```
