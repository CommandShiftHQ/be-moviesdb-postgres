## Solutions: Create and Insert Exercises

1. Write a statement to create a simple table called `rating`. It should include the columns `rating_id`, `rating_value`, `title` and `content`.

```sql
CREATE TABLE rating (
	rating_id INTEGER,
	rating_value INTEGER,
	title VARCHAR,
	content VARCHAR
);
```

1. Write a statement to insert a record into your `rating` table. Confirm that the record exists with `SELECT * FROM rating`.

```sql
INSERT INTO rating (
    rating_id
	rating_value, 
	title, 
	content
) 
 VALUES (1, 10, 'Good movie 10/101', 'Interesting premise, surprising ending');
```

1. Remove the `rating` table with `DROP TABLE rating`. Now write a statement to create the same table again, none of the fields should be able to be null. Confirm that this is the case by attempting to insert a record with null values.

```sql
CREATE TABLE rating (
	rating_id INTEGER NOT NULL,
	rating_value VARCHAR(40) NOT NULL,
	title VARCHAR NOT NULL,
	content VARCHAR NOT NULL
);
```

1. Remove the `rating` table and create it again. This time make sure that only values from `0` to `10` can be inserted for the `rating_value` field.

```sql
CREATE TABLE rating (
	rating_id INTEGER,
	rating_value INTEGER CHECK (rating_value BETWEEN 0 AND 10),
	title VARCHAR,
	content VARCHAR
);
```

1. Delete and recreate this table. This time, in addition to previous valid `rating_value` requirement, make sure that no duplicate data against column `rating_id` will be allowed at the time of insertion.

```sql
CREATE TABLE rating (
	rating_id INTEGER UNIQUE,
	rating_value INTEGER CHECK (rating_value BETWEEN 0 AND 10),
	title VARCHAR,
	content VARCHAR
);
```

1. Now recreate the table, but this time make the `title` a `unique` field. This can be used to prevent duplicate data.

```sql
CREATE TABLE rating (
	rating_id INTEGER,
	rating_value INTEGER,
	title VARCHAR UNIQUE,
	content VARCHAR
);
```

1. Finally, recreate the table with the `rating_id` as a `primary key` with auto increment. Insert a few records into the table to confirm that it is auto-incrementing this column.

```sql
CREATE TABLE rating (
	rating_id SERIAL PRIMARY KEY,
	rating_value VARCHAR(40),
	title VARCHAR,
	content VARCHAR
);
```

1. Write a statement to create a table named `reviewer`. It should have the columns `reviewer_id`, `reviewer_name`, `registered_date`, `points`. You should make sure that `points` that a reviewer can have is a value between 0 and can't exceed 10000.

```sql
CREATE TABLE reviewer (
	reviewer_id SERIAL PRIMARY KEY,
	reviewer_name VARCHAR,
	registered_date DATE, 
	points INTEGER CHECK (points BETWEEN 0 AND 10000)
);
```

1. Write a SQL statement to **change** (or ALTER) the rating table and add a new Foreign Key Column called `reviewer_id` to the `ratings` table. Set the default to `NULL`. 

```sql
ALTER TABLE rating
ADD COLUMN reviewer_id INTEGER CONSTRAINT rating_reviewer_id_fk REFERENCES reviewer(reviewer_id);
```

1. Drop the `rating` table altogether and this time ensure the `reviewer_id` foreign key is part of the initial create statement. 

```sql
CREATE TABLE rating (
	rating_id SERIAL PRIMARY KEY,
	rating_value INTEGER,
	title VARCHAR,
	content VARCHAR NOT NULL,
	reviewer_id INTEGER CONSTRAINT rating_reviewer_id_fk REFERENCES reviewer(reviewer_id)
);=
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

```sql
CREATE TABLE rating (
	rating_id SERIAL PRIMARY KEY NOT NULL,
	rating_value INTEGER NOT NULL CHECK (rating_value BETWEEN 0 AND 10),
	title VARCHAR(100) UNIQUE NOT NULL,
	content VARCHAR NOT NULL CONSTRAINT min_content_length CHECK (char_length(contens) > 10)
);
```
    

1. Write a SQL statement to insert a record with your own values into the `ratings` table against each column.

```sql
INSERT INTO rating (
	rating_value,
	title, 
	content
) 
VALUES (10, 'Best movie Ive seen', 'Interesting premise, surprising ending');
```

2. Write a SQL statement to insert 3 rows by using a single INSERT statement.

```sql
INSERT INTO rating (
	rating_value,
	title, 
	content
) 
VALUES 
(10, 'Best movie Ive seen this year', 'Interesting premise, surprising ending'),
(1, 'Not worthwhile', 'Wish I didnt watch this movie'),
(8, 'Go if you are a genre fan', 'Best for the fans of this genre');
```

