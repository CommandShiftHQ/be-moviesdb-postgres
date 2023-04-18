# Solutions: Read Exercises

1. Write a query to get movie `title`, `budget` and `release_date`.

```sql
SELECT title, budget, release_date
FROM movie;
```

3. Write a query to get a list of movies that have a website or homepage (`title` and `homepage`).

```sql
SELECT title, homepage
FROM movie
WHERE homepage <> '';
```

5. Write a query to get a list of movies that are longer than 2 hours (`title` and `runtime`).

```sql
SELECT title, runtime
FROM movie
WHERE runtime > 120;
```

7. Write a query to get the `title` and `vote_average` of the movie with most revenue.

```sql
SELECT title, vote_average
FROM movie
ORDER BY revenue DESC
LIMIT 1;
```

9. Write a query to get the `title` and `vote_average` of the movie with the least revenue.

```sql
SELECT title, vote_average
FROM movie
ORDER BY revenue ASC
LIMIT 1;
```

11. Write a query to get the movies with a vote average higher than 8.

```sql
SELECT title, vote_average
FROM movie
WHERE vote_average > 8;
```

12. Write a query to get the movies released between 1 August 2015 and 1 January 2016.

```sql
SELECT *
FROM movie
WHERE release_date BETWEEN '2015-06-01' AND '2016-01-01';
```

14. Write a query to get the count of all movies released after 1 January 2016.

```sql
SELECT COUNT(*)
FROM movie
WHERE release_date > '2016-01-01';
```

15. Write a query to get a list of the top 10 most popular movies.

```sql
SELECT *
FROM movie
ORDER BY vote_average DESC
LIMIT 10;
```

17. Write a query to get the count of all movies that have a vote average higher than 9 and were released before 2020. 

```sql
SELECT COUNT(*)
FROM movie
WHERE vote_average > 9 AND release_date < '2020-01-01';
```

