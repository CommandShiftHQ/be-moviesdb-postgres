## Solutions: Create and Insert Exercises

1. Write a statement to create a simple table called `rating`. It should include the columns `rating_id`, `rating_value`, `title` and `content`.

```sql
```

1. Write a statement to insert a record into your `rating` table. Confirm that the record exists with `SELECT * FROM rating`.

```sql
```

1. Remove the `rating` table with `DROP TABLE rating`. Now write a statement to create the same table again, none of the fields should be able to be null. Confirm that this is the case by attempting to insert a record with null values.

```sql
```

1. Remove the `rating` table and create it again. This time make sure that only values from `0` to `10` can be inserted for the `rating_value` field.

```sql
```

1. Delete and recreate this table. This time, in addition to previous valid `rating_value` requirement, make sure that no duplicate data against column `rating_id` will be allowed at the time of insertion.

```sql
```

1. Now recreate the table, but this time make the `title` a `unique` field. This can be used to prevent duplicate data.

```sql
```

1. Finally, recreate the table with the `rating_id` as a `primary key` with auto increment. Insert a few records into the table to confirm that it is auto-incrementing this column.

```sql
```

1. Write a statement to create a table named `reviewer`. It should have the columns `reviewer_id`, `reviewer_name`, `registered_date`, `points`. You should make sure that `points` that a reviewer can have is a value between 0 and can't exceed 10000.

```sql
```

1. Write a SQL statement to **change** (or ALTER) the rating table and add a new Foreign Key Column called `reviewer_id` to the `ratings` table. Set the default to `NULL`. 

```sql
```

1. Drop the `rating` table altogether and this time ensure the `reviewer_id` foreign key is part of the initial create statement. 

```sql
```

# Insert Exercises

Create the following table in your database:

```
    +--------------+---------------+------+--------------+---------------------------------+
    | Field        | Type          | Null | Key          | Extra Constraints               |
    +--------------+---------------+------+--------------+---------------------------------+
    | RATING_ID    | serial        | NO   | PRIMARY KEY  |                                 |
    | RATING_VALUE | integer       | NO   |              | RATING_VALUE between 0 and 10   |
    | TITLE        | varchar(100)  | NO   |              | UNIQUE                          |
    | CONTENT      | varchar(255)  | NO   |              | Minimum CONTENT length 10 chars |
    +--------------+---------------+------+--------------+---------------------------------+
```
    

1. Write a SQL statement to insert a record with your own values into the `ratings` table against each column.

```sql
```

2. Write a SQL statement to insert 3 rows by using a single INSERT statement.

```sql
```

