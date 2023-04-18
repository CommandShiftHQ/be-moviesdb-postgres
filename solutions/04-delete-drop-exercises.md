# DELETE, DROP & Truncate Exercises

1. Write a statement to delete the keyword with `id` = `839` from the eyword table. This is trickier than it seems. Remember that foreign key constraints prevent us from deleting records that are referenced in other tables. To get around foreign key constraints, you can: manually delete related records from other tables, alter the table to enable [cascading deletes](https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-foreign-key/) or remove foreign key constraints (temporarily or permanently). Think about the advantages and disadvantages of each of these options. 
2. Delete any movies that are produced by the `"Cowboy Films"` production company.
3. Delete any movies that have a revenue of 0.
4. Pick a person or actor from the `person` table, delete them and all the movies they are associated with or have played in. Consider foreign key constraints again!
5. Delete the entire `movie_languages` table. You might want to check the [TRUNCATE](https://www.postgresql.org/docs/current/sql-truncate.html) command.
