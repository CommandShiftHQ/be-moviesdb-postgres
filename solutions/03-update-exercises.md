# Solutions: Update exercises

**💡Remember**:
If you make a mistake you can always remove the container and start a new one.

1. Write a statement to change the name of `terror` keyword to `horror`.

```sql
UPDATE keyword
SET keyword_name = 'horror'
WHERE keyword_name = 'terror';
```

2. Write a statement to change the all the keywords `horror` to `secret keyword`. 

```sql
UPDATE keyword
SET keyword_name = 'secret keyword'
WHERE keyword_name = 'horror';
```

3. Write a statement to change `name` of the person `RZA` to `Robert Fitzgerald Diggs`.

```sql
UPDATE person
SET person_name = 'Robert Fitzgerald Diggs'
WHERE person_name = 'RZA';
```

4. Write a statement to change the `homepage` of all the movies with a revenue higher than 1m to the Wikipedia page for Avatar - The Way of Water. 

```sql
UPDATE movie
SET homepage = 'https://en.wikipedia.org/wiki/Avatar:_The_Way_of_Water'
WHERE revenue > 1000000;
```

Now that we've wrecked these tables, let's look at the `production_company` and `movie` tables:

1. The production company behind `Forrest Gump` movie recently changed their name. They have requested that we update the company name to `Paramount+`.

```sql
```

2. They also requested that you change all homepages for the movies that they produced to the Paramount+ streaming service. 

```sql
```
