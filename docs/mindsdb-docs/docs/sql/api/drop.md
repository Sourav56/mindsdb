# `#!sql DROP PREDICTOR` Statement

## Description

The `#!sql DROP PREDICTOR` statement is used to delete the model table:

## Syntax

```sql
DROP PREDICTOR [predictor_name];
```

On execution, we get:

```sql
Query OK, 0 rows affected (0.058 sec)
```

Where:

| Name               | Description                     |
| ------------------ | ------------------------------- |
| `[predictor_name]` | Name of the model to be deleted |

## Validation

```sql
SELECT name
FROM mindsdb.predictors
WHERE name = '[predictor_name]';
```

On execution, we get:

```sql
Empty set (0.026 sec)
```

## Example

The following SQL statement drops the model table called `home_rentals_model`. Given the following query to list all predictors by name

```sql
SELECT name
FROM mindsdb.predictors;
```

On execution, we get:

```sql
+---------------------+
| name                |
+---------------------+
| other_model         |
+---------------------+
| home_rentals_model  |
+---------------------+
```

Execute the `#!sql DROP PREDICTOR` statement as:

```sql
DROP PREDICTOR home_rentals_model;
```

On execution, we get:

```sql
Query OK, 0 rows affected (0.058 sec)
```

Validate that the model has been deleted by listing again all predictors by name:

```sql
SELECT name
FROM mindsdb.predictors;
```

On execution, we get:

```sql
+---------------------+
| name                |
+---------------------+
| other_model         |
+---------------------+
```